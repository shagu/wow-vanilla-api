# World of Warcraft 1.12 Addon Tutorial (English)

> *Note: I wrote this tutorial in 2015 for the forum of a german private server. It was planned to write a series of addon tutorials, which I had stopped due to lack of demand.*

Through this small tutorial I try to explain small addons using the source code and bring everyone closer to the world of Lua and the WoW API.

This first guide is about **ShaguCombat**. This is a small addon that shows the infight status by a pulsating red glowing screen border.

The addon has only 50 lines and is therefore ideal for beginners.

The following topics will be covered:
1. TOC files
2. Color codes
3. Frames
4. Backdrop graphics
5. Events
6. Timer & OnUpdate

## 1. TOC files

If you want to write an addon, you first have to create a .toc file, which has the same filename as the folder. In this case: ShaguCombat

```toc
## Interface: 11200
## Title: |cff33ffccShagu|cffffffffCombat
## Author: Shagu
## Notes: Notifies about your infight state via glowing screen edges
## Version: 0.1

ShaguCombat.lua
```

The interface line refers to the Wow version for which we are writing the addon. For vanilla Wow version 1.12 use: 11200.

As title you can set what the Wow client displays when you select an addon. For color codes we use "|c". (see chapter: 2. color codes)

Author and version should be self-explanatory. "Notes" appears in the addon selection as description of the addon.

Now you have to specify the .lua file which the game should load for the addon. In this example it is `ShaguCombat.lua`.


## 2. Color codes

To set inline color codes in the game, `|c` is usually used. The first two hexadecimal digits after the |c are for transparency, the next ones are for red, then green, then blue. `00` is the lowest value, `FF` is the highest value. Counting is done in hexadecimal system from 0-9 then from A-F (`0123456789ABCDEF`).

**|cFF**$\color{red}{\textsf{00}}\color{green}{\textsf{FF}}\color{blue}{\textsf{00}}$ would be for example:
- Transparency: 100% visible (FF)
- Red: 0% visible (00)
- Green: 100% visible (FF)
- Blue: 0% visible (00)

To reset the color later `|r` is used:

**|c**$\textsf{FF0000FF}\color{blue}{\textsf{Blue Text}}$**|r**Normal Text

## 3. Frames

Let's start with the Lua code. First you start to create a frame:

```lua
-- build the frame
local ShaguCombat = CreateFrame("Frame")

ShaguCombat:SetFrameStrata("BACKGROUND")
ShaguCombat:SetWidth(GetScreenWidth() * UIParent:GetEffectiveScale())
ShaguCombat:SetHeight(GetScreenHeight() * UIParent:GetEffectiveScale())

ShaguCombat:SetPoint("CENTER",0,0)
ShaguCombat:Hide()
```

In the first line a frame with the name "ShaguCombat" is created here. By means of "SetFrameStrata" you can set on which layer it should be drawn.

Here are the following options:
- "PARENT"
- "BACKGROUND"
- "LOW"
- "MEDIUM"
- "HIGH"
- "DIALOG"
- "FULLSCREEN"
- "FULLSCREEN_DIALOG"
- "TOOLTIP"

To understand the order: `"BACKGROUND"` is covered by `"LOW"`, `"LOW"` is covered by `"MEDIUM"`, `"MEDIUM"` is covered by `"HIGH"` and so on....
Exception here is `"PARENT"`, because there it is not the lowest level, but the same STRATA is used as for the frame from which it originated.

In the following lines we set the width and the height (`SetWidth()` & `SetHeight()`) to the screen size (`GetScreenWidth()` & `GetScreenHeight()`).
In addition, the UIScale is taken into account using: `UIParent:GetEffectiveScale()`.

Now we align the frame to the center of the screen by setting `SetPoint()` to `"CENTER"` with an x-offset of 0 and a y-offset of 0.
Last but not least we hide the frame with `Hide()`.


## 4. Backdrop graphics

Since we now have an invisible frame that has no graphics even when visible, we need to add a texture to it. This can be done very easily by using a backdrop.
A backdrop is usually a background image + graphics for the edges. In the Lua code we now add the following:

```diff
+ -- define the border as "backdrop"
+ local backdrop = {
+   edgeFile = "Interface\\AddOns\\ShaguCombat\\border", edgeSize = 16,
+   insets = {left = 16, right = 16, top = 16, bottom = 16},
+ }

 -- build the frame
 local ShaguCombat = CreateFrame("Frame")

 ShaguCombat:SetFrameStrata("BACKGROUND")
 ShaguCombat:SetWidth(GetScreenWidth() * UIParent:GetEffectiveScale())
 ShaguCombat:SetHeight(GetScreenHeight() * UIParent:GetEffectiveScale())

+ ShaguCombat:SetBackdrop(backdrop)

 ShaguCombat:SetPoint("CENTER",0,0)
 ShaguCombat:Hide()
```

We define the variable (or table) called "backdrop". Here it would be possible to also set "bg" for a background, but we don't want the complete screen to be painted over as soon as we have aggro. Therefore we only use "edgeFile" which takes care of the backdrop of the frame.

A backdrop consists of 8 images next to each other. How big the images are is defined by "edgeSize". In this case each backdrop graphic is 16x16 pixels. By "insets" is described, which distance the backdrop should have from the frame.

So you have an image with the dimensions: 8*16 on 16 => 128x16 pixels. The first image (from the left) is the left border, followed by the right border. Then Top, Bottom, Left Top (corner), Right Top (corner), Left Bottom (corner) and last but not least Right Bottom (corner). The important thing to know here is that the top and bottom borders are rotated 90°.

A graphic in Wow must always be a multiple of 8 pixels. ie:
128x16 = divisible by 8 -> Fits.
129x17 = Not divisible by 8 -> Will not be loaded.

Mostly a .tga graphic is used for this. If you create it with [GIMP](https://www.gimp.org/), you should disable the RLE compression.

Here is an example how the backdrop image can look like in the end:

![border.jpg](border.jpg)[[TGA]](border.tga)

In-game testing could now be done as follows:
```
/script ShaguCombat:Show()
```

to make the frame visible.
```
/script ShaguCombat:Hide()
```
to hide the frame again.

## 5. Events

Since it is relatively boring to show and hide a frame by hand, we want to do this through EVENTS. Roughly speaking, EVENTS take place in the game for various things, on which we can sit down and perform actions. For this addon we use `"PLAYER_REGEN_ENABLED"` and `"PLAYER_REGEN_DISABLED"`. The first one is triggered when the mana and HP regeneration starts (outfight) and the second one is triggered when the regeneration stops (infight).

```diff
 -- define the border as "backdrop"
 local backdrop = {
   edgeFile = "Interface\\AddOns\\ShaguCombat\\border", edgeSize = 16,
   insets = {left = 16, right = 16, top = 16, bottom = 16},
 }

 -- build the frame
 local ShaguCombat = CreateFrame("Frame")

 ShaguCombat:SetFrameStrata("BACKGROUND")
 ShaguCombat:SetWidth(GetScreenWidth() * UIParent:GetEffectiveScale())
 ShaguCombat:SetHeight(GetScreenHeight() * UIParent:GetEffectiveScale())

 ShaguCombat:SetBackdrop(backdrop)
 ShaguCombat:SetPoint("CENTER",0,0)
 ShaguCombat:Hide()

+-- register for events
+ShaguCombat:RegisterEvent("PLAYER_REGEN_ENABLED")
+ShaguCombat:RegisterEvent("PLAYER_REGEN_DISABLED")
+
+-- show/hide on combat
+ShaguCombat:SetScript("OnEvent", function()
+    if event == "PLAYER_REGEN_DISABLED" then
+        ShaguCombat:Show()
+        -- UIErrorsFrame:AddMessage("ShaguCombat |cffffffaa INFIGHT")
+    end
+    if event == "PLAYER_REGEN_ENABLED" then
+        ShaguCombat:Hide()
+        -- UIErrorsFrame:AddMessage("ShaguCombat |cffffffaa OUTFIGHT")
+    end
+end)
```

We now set our frame to the two events by "RegisterEvent()". Now the "OnEvent" function is called in our frame every time one of the two events occurs. The content of this function can now be filled with `SetScript("OnEvent", function() ... end)`.

We first check which of the two events has taken place. The current event is in the variable "event".

The commented out lines (lines beginning with `--`) show, if you want to use them, on the center of the screen "ShaguCombat INFIGHT" or "ShaguCombat OUTFIGHT". This can be useful for debugging.

## 6. Timer & OnUpdate

Now the addon shows whether you are Infight or Outfight with a white frame around the screen. Of course, this doesn't look very pretty, so we will now add the "glow" effect.

```diff
 -- define the border as "backdrop"
 local backdrop = {
   edgeFile = "Interface\\AddOns\\ShaguCombat\\border", edgeSize = 16,
   insets = {left = 16, right = 16, top = 16, bottom = 16},
 }

 -- build the frame
 local ShaguCombat = CreateFrame("Frame")

 ShaguCombat:SetFrameStrata("BACKGROUND")
 ShaguCombat:SetWidth(GetScreenWidth() * UIParent:GetEffectiveScale())
 ShaguCombat:SetHeight(GetScreenHeight() * UIParent:GetEffectiveScale())

 ShaguCombat:SetBackdrop(backdrop)
 ShaguCombat:SetPoint("CENTER",0,0)
 ShaguCombat:Hide()

 -- register for events
 ShaguCombat:RegisterEvent("PLAYER_REGEN_ENABLED")
 ShaguCombat:RegisterEvent("PLAYER_REGEN_DISABLED")

+-- let it fade..
+ShaguCombat:SetScript("OnUpdate",function(s,e)
+    if not ShaguCombat.clock then    ShaguCombat.clock = GetTime() -0.1 end
+    if GetTime() >= ShaguCombat.clock + 0.1 then
+        ShaguCombat.clock = GetTime()
+
+        if not ShaguCombat.fadeValue then    ShaguCombat.fadeValue = 1 end
+        if ShaguCombat.fadeValue >= 0.3 then
+            ShaguCombat.fadeModifier = -0.1
+        end
+        if ShaguCombat.fadeValue <= 0 then
+            ShaguCombat.fadeModifier = 0.1
+        end
+        ShaguCombat.fadeValue = ShaguCombat.fadeValue + ShaguCombat.fadeModifier
+        ShaguCombat:SetBackdropBorderColor(1,0.2+ShaguCombat.fadeValue, ShaguCombat.fadeValue, 1-ShaguCombat.fadeValue);
+    end
+end)

 -- show/hide on combat
 ShaguCombat:SetScript("OnEvent", function()
     if event == "PLAYER_REGEN_DISABLED" then
         ShaguCombat:Show()
         -- UIErrorsFrame:AddMessage("ShaguCombat |cffffffaa INFIGHT")
     end
     if event == "PLAYER_REGEN_ENABLED" then
         ShaguCombat:Hide()
         -- UIErrorsFrame:AddMessage("ShaguCombat |cffffffaa OUTFIGHT")
     end
 end)
```

For this we use the `OnUpdate` function of our frame. This is called with every drawing. I.e. at 30 FPS it is called 30x per second.
Bringing in the "Glow" effect directly here would mean that it blinks slower at 8 FPS than at 116 FPS. To prevent this we use the system time.

If the variable ShaguCombat.clock is not set, we fill it with the content of the current time - 0.1 seconds.
(`if not ShaguCombat.clock then ShaguCombat.clock = GetTime() - 0.1 end`)

Now we check at every frame if the current time is already the variable content + 0.1 second. If this is the case, our "clock" variable is set to the current time and the content of our "timer" block is executed. (`if GetTime() >= ShaguCombat.clock + 0.1 then [...]`) Finished is the 0.1 second timer.

I won't go into detail here, because setting variables, calculating with variables etc. should be understandable even for someone who doesn't program, if he tries a little bit.

What happens now is that temporary fade-variables are set, which are counted up or down. And by "SetBackdropBorderColor()" our backdrop border gets the appropriate coloring every 0.1 seconds. This function needs the following parameters: SetBackdropBorderColor(<span style="color:#f00">Red</span>, <span style="color:#0f0">Green</span>, <span style="color:#00f">Blue</span>, Transparency)


## 7. End

The complete code should now look like this:
```lua
-- define the border as "backdrop"
local backdrop = {
  edgeFile = "Interface\\AddOns\\ShaguCombat\\border", edgeSize = 16,
  insets = {left = 16, right = 16, top = 16, bottom = 16},
}

-- build the frame
local ShaguCombat = CreateFrame("Frame")

ShaguCombat:SetFrameStrata("BACKGROUND")
ShaguCombat:SetWidth(GetScreenWidth() * UIParent:GetEffectiveScale())
ShaguCombat:SetHeight(GetScreenHeight() * UIParent:GetEffectiveScale())

ShaguCombat:SetBackdrop(backdrop)
ShaguCombat:SetPoint("CENTER",0,0)
ShaguCombat:Hide()

-- register for events
ShaguCombat:RegisterEvent("PLAYER_ENTERING_WORLD")
ShaguCombat:RegisterEvent("PLAYER_REGEN_ENABLED")
ShaguCombat:RegisterEvent("PLAYER_REGEN_DISABLED")

-- let it fade..
ShaguCombat:SetScript("OnUpdate",function(s,e)
  if not ShaguCombat.clock then  ShaguCombat.clock = GetTime() -0.1 end
  if GetTime() >= ShaguCombat.clock + 0.1 then
    ShaguCombat.clock = GetTime()

    if not ShaguCombat.fadeValue then  ShaguCombat.fadeValue = 1 end
    if ShaguCombat.fadeValue >= 0.3 then
      ShaguCombat.fadeModifier = -0.1
    end
    if ShaguCombat.fadeValue <= 0 then
      ShaguCombat.fadeModifier = 0.1
    end
    ShaguCombat.fadeValue = ShaguCombat.fadeValue + ShaguCombat.fadeModifier
    ShaguCombat:SetBackdropBorderColor(1,0.2+ShaguCombat.fadeValue, ShaguCombat.fadeValue, 1-ShaguCombat.fadeValue);
  end
end);

-- show/hide on combat
ShaguCombat:SetScript("OnEvent", function()
  if event == "PLAYER_REGEN_DISABLED" then
    ShaguCombat:Show()
    -- UIErrorsFrame:AddMessage("ShaguCombat |cffffffaa INFIGHT")
  end
  if event == "PLAYER_REGEN_ENABLED" or event == "PLAYER_ENTERING_WORLD" then
    ShaguCombat:Hide()
    -- UIErrorsFrame:AddMessage("ShaguCombat |cffffffaa OUTFIGHT")
  end
end)
```

That's it already. Here is the complete addon for download:
[Download: ShaguCombat](https://github.com/shagu/ShaguCombat/archive/master.zip)

Have fun in the code and don't forget to leave a ⭐.
