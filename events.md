# World of Warcraft Event-Listing (1.12.1 Vanilla)

## ACTIONBAR_PAGE_CHANGED
Fired when the actionbar page changes, typically when you press the pageup or pagedown button.

- **arg1**: the mouse button used to click the button. Known values: "LeftButton", "RightButton"

## ACTIONBAR_SHOWGRID
Fired when the actionbar numbers appear, typically when you drag a spell to the actionbar.

- **arg1**: the mouse button used to drag the spell. Known values: "LeftButton", "RightButton"

## ACTIONBAR_HIDEGRID

## ACTIONBAR_SLOT_CHANGED
Fired when any actionbar slot's contents change.

- **arg1**: the number of the slot that changed

## ACTIONBAR_UPDATE_COOLDOWN
Fired when the cooldown for an actionbar or inventory slot starts or stops. Also fires when you log into a new area.

- **arg1**: if the cooldown is starting, the mouse button used to click the button. Known values: "leftButton"
    * if the cooldown is stopping or you are logging into a new zone, this is nil

## ACTIONBAR_UPDATE_STATE
Fired when the state of anything on the actionbar changes. This includes cooldown and disabling.

- **arg1**: the mouse button used to click the button. Known values: "LeftButton", "RightButton"
    * can also be nil

## ACTIONBAR_UPDATE_USABLE
Fired when something in the actionbar or your inventory becomes usable again (after eating or drinking a potion, for example).

## AREA_SPIRIT_HEALER_IN_RANGE

## AREA_SPIRIT_HEALER_OUT_OF_RANGE

## ADDON_LOADED
This event fires whenever an AddOn is loaded (fires once for each AddOn loaded if multiple AddOns are being loaded), whether that is during the inital Loading Phase or when an AddOn is loaded using the LoadAddOn("addonname") or UIParentLoadAddon("addonname") function.  This event always fires after that Saved Variables of the AddOn that just finished loading have been loaded from the disk.

- **arg1**: name of the AddOn that was just loaded

## ADDON_ACTION_FORBIDDEN

## AUCTION_BIDDER_LIST_UPDATE

## AUCTION_HOUSE_CLOSED

## AUCTION_HOUSE_SHOW

## AUCTION_ITEM_LIST_UPDATE

## AUCTION_OWNED_LIST_UPDATE

## AUTOEQUIP_BIND_CONFIRM
Fired when the game attempts to autobind bind-on-equip items.

## AUTOFOLLOW_BEGIN
Fired when you begin automatically following an ally.

- **arg1**: The unit you are following.  Not necessarily your target (in case of right-clicking a group member's portrait or using the "/follow" command).

## AUTOFOLLOW_END
Fired when the player ceases following an ally

## BAG_CLOSED
Fired when a bag is closed

- **arg1**: container ID

## BAG_OPEN
Fired when a bag (NOTE: This is NOT fired for player containers, it's for those bag-like objects that you can remove items from but not put items into) is opened.

- **arg1**: container ID

## BAG_UPDATE
Fired when a bags inventory changes

- **arg1**: container ID

## BAG_UPDATE_COOLDOWN
Fired when a cooldown update call is sent to a bag

- **arg1**: container ID

## BANKFRAME_CLOSED
Fired when the bank window is closed

## BANKFRAME_OPENED
Fired when the bank frame is opened

## BATTLEFIELDS_CLOSED

## BATTLEFIELDS_SHOW

## BILLING_NAG_DIALOG

## BIND_ENCHANT
Fired when Enchanting an unbound item.

## CANCEL_LOOT_ROLL

## CHARACTER_LIST_UPDATE

## CHARACTER_POINTS_CHANGED
Fired when the player's character points are changed.

## CHAT_MSG
Fired when the client recieves a chat message.

- **arg1**: TODO
- **arg2**: TODO
- **arg3**: TODO
- **arg4**: channel length

## CHAT_MSG_ADDON

## CHAT_MSG_AFK
Fired when the client receives an AFK auto-response

- **arg1**: AFK response message
- **arg2**: author

## CHAT_MSG_BATTLEGROUND

## CHAT_MSG_BATTLEGROUND_LEADER

## CHAT_MSG_BG_SYSTEM_ALLIANCE
Fired for alliance specific events in the battleground such as assaulting a graveyard.

- **arg1**: Battleground Message  (eg. "The Alliance has taken the Blacksmith!")

## CHAT_MSG_BG_SYSTEM_HORDE
Fired for horde specific events in the battleground such as assaulting a graveyard.

- **arg1**: Battleground Message  (eg. "The Horde has taken the Blacksmith!")

## CHAT_MSG_BG_SYSTEM_NEUTRAL
Fired for non faction specific events in the battlegrounds such as the battle start announcement.

## CHAT_MSG_CHANNEL
Fired when the client recieves a channel message.

- **arg1**: chat message
- **arg2**: author
- **arg3**: language
- **arg4**: channel name with number ex: "5. General - Stormwind City"
    * zone is always current zone even if not the same as the channel name
- **arg5**: target
    * second player name when two users are passed for a CHANNEL_NOTICE_USER (E.G. x kicked y)
- **arg6**: AFK/DND/GM "CHAT_FLAG_"..arg6 flags
- **arg7**: zone ID used for genaric system channels (General, Trade, LookingForGroup and LocalDefense)
    * not used for custom channels or if you joined an Out-Of-Zone channel ex: "General - Stormwind City"
- **arg8**: channel number
- **arg9**: channel name without number
    * zone is always current zone even if not the same as the channel name

## CHAT_MSG_CHANNEL_JOIN
Fired when someone joins a chat channel you are in

- **arg1**: seems to be empty
- **arg2**: Name of the player that joined
- **arg3**: seems to be empty again
- **arg4**: Number and name of the channel (e.g. "5. MyOwnChannel")
- **arg8**: Channel number
- **arg9**: Channel name without number

## CHAT_MSG_CHANNEL_LEAVE

## CHAT_MSG_CHANNEL_LIST

## CHAT_MSG_CHANNEL_NOTICE

## CHAT_MSG_CHANNEL_NOTICE_USER

## CHAT_MSG_COMBAT_CREATURE_VS_CREATURE_HITS
Fired when a creature hits another creature

- **arg1**: chat message

## CHAT_MSG_COMBAT_CREATURE_VS_CREATURE_MISSES
Fired when a creature misses another creature

- **arg1**: chat message

## CHAT_MSG_COMBAT_CREATURE_VS_PARTY_HITS
Fired when a creature hits a party member

- **arg1**: chat message

## CHAT_MSG_COMBAT_CREATURE_VS_PARTY_MISSES
Fired when a creature misses a party memeber

- **arg1**: chat message

## CHAT_MSG_COMBAT_CREATURE_VS_SELF_HITS
Fired when a creature hits you

- **arg1**: chat message

## CHAT_MSG_COMBAT_CREATURE_VS_SELF_MISSES
Fired when a creature misses you

- **arg1**: chat message

## CHAT_MSG_COMBAT_ERROR

## CHAT_MSG_COMBAT_FACTION_CHANGE

## CHAT_MSG_COMBAT_FRIENDLYPLAYER_HITS

## CHAT_MSG_COMBAT_FRIENDLYPLAYER_MISSES

## CHAT_MSG_COMBAT_FRIENDLY_DEATH

## CHAT_MSG_COMBAT_HONOR_GAIN
Fired when you successfully kill a worthy pvp opponent

- **arg1**: chat message (format: "%s dies, honorable kill Rank: %s (Estimated Honor Points: %d)")

## CHAT_MSG_COMBAT_HOSTILEPLAYER_HITS

## CHAT_MSG_COMBAT_HOSTILEPLAYER_MISSES

## CHAT_MSG_COMBAT_HOSTILE_DEATH
Fired when any hostile (NPC or player) dies near you.

- **arg1**: complete text from combat-log (e.g. "Snowshoe Rabbit dies.")

## CHAT_MSG_COMBAT_LOG

## CHAT_MSG_COMBAT_MISC_INFO
Fired when you gain reputation from killing a creature or finishing a quest.

## CHAT_MSG_COMBAT_PARTY_HITS

## CHAT_MSG_COMBAT_PARTY_MISSES

## CHAT_MSG_COMBAT_PET_HITS

## CHAT_MSG_COMBAT_PET_MISSES

## CHAT_MSG_COMBAT_SELF_HITS
Fired when a you hit a creature. Also called when you hurt yourself by falling, drowning or burning on a campfire.

- **arg1**: *localized* chat message

## CHAT_MSG_COMBAT_SELF_MISSES
Fired when a you miss a creature

- **arg1**: chat message

## CHAT_MSG_COMBAT_XP_GAIN
Fired when you gain xp from killing a creature or finishing a quest. Does not fire if you gain no xp from killing a creature.

- **arg1**: chat message

## CHAT_MSG_DND
Fired when the client receives a Do-Not-Disturb auto-response

- **arg1**: DND response message
- **arg2**: author

## CHAT_MSG_EMOTE
Fired on sending or revicing a custom emote (one used by /e, /emote or a send chat message command with the emote flag)

- **arg1**: Message that was sent/received.
- **arg2**: Name of the player who sent the message.

## CHAT_MSG_FILTERED

## CHAT_MSG_GUILD
Fired when a message is sent or received in the Guild channel.

- **arg1**: Message that was sent/received.
- **arg2**: Name of the player who sent the message.
- **arg3**: Language the message was spoken in. (See [CHAT_MSG_SAY](http://www.wowwiki.com/Events_C_%28Cancel%2C_Character%2C_Chat%2C_Cinematic%2C_Clear%2C_Close%2C_Confirm%2C_Corpse%2C_Craft%2C_Current%2C_Cursor%2C_CVar%29#CHAT_MSG_SAY) for example code)

## CHAT_MSG_IGNORED

## CHAT_MSG_LOOT
Fired when a unit loots an item.

- **arg1**: Message that was sent/received.

## CHAT_MSG_MONEY

## CHAT_MSG_MONSTER_EMOTE

## CHAT_MSG_MONSTER_SAY

## CHAT_MSG_MONSTER_WHISPER

## CHAT_MSG_MONSTER_YELL

- **arg1**: Text of message.

## CHAT_MSG_OFFICER
Fired when a message is sent or received in the Guild Officer channel.

- **arg1**: Message that was sent/received.
- **arg2**: Name of the player who sent the message.
- **arg3**: Language the message was spoken in.(See [CHAT_MSG_SAY](http://www.wowwiki.com/Events_C_%28Cancel%2C_Character%2C_Chat%2C_Cinematic%2C_Clear%2C_Close%2C_Confirm%2C_Corpse%2C_Craft%2C_Current%2C_Cursor%2C_CVar%29#CHAT_MSG_SAY) for example code)

## CHAT_MSG_PARTY
Fired when a message is sent or received in the Party channel.

- **arg1**: Message that was sent/received.
- **arg2**: Name of the player who sent the message.
- **arg3**: Language the message was spoken in.(See [CHAT_MSG_SAY](http://www.wowwiki.com/Events_C_%28Cancel%2C_Character%2C_Chat%2C_Cinematic%2C_Clear%2C_Close%2C_Confirm%2C_Corpse%2C_Craft%2C_Current%2C_Cursor%2C_CVar%29#CHAT_MSG_SAY) for example code)

## CHAT_MSG_RAID
Fires when a player speaks in /raid chat.

## CHAT_MSG_RAID_BOSS_EMOTE

## CHAT_MSG_RAID_LEADER

## CHAT_MSG_RAID_WARNING
Fired when a warning message is sent or received from the raid leader.

## CHAT_MSG_SAY
Fired when a message is sent or received in the Say channel.

- **arg1**: chat message
- **arg2**: author
- **arg3**: language
- **arg4**: channel name with number
- **arg5**: unknown (empty string)
- **arg6**: unknown (empty string)
- **arg7**: unknown (appears to be channel number)
- **arg8**: channel number ("0")
- **arg9**: channel name without number

_Example:_Place `this:RegisterEvent("CHAT_MSG_SAY");` in the `<OnLoad>`/`<OnLoad>` section of your MyMod.xml file. Then, have an `if (event == "CHAT_MSG_SAY") then MyMod_Say(event, arg1, arg2, arg3); end` line, or something like it, in the `<OnEvent>`/`</OnEvent>` section of your MyMod.xml file. Then, have a function like the following in your MyMod.lua file:
```
function MyMod_Say(event, arg1, arg2, arg3)
  PrevMsg = arg1;
  PrevPlyr = arg2;
  PrevLang = arg3;
end
```
This would store the previous message, player who said it, and language it was said in into some variables.

## CHAT_MSG_SKILL
Fired when some chat messages about skills are displayed.


- **arg1**: The content of the chat message. **arg1** formats are found in Blizzard's `GlobalStrings.lua`.  Some possibilities:
    * `ERR_SKILL_GAINED_S` (eg. "You have gained the Blacksmithing skill.")
    * `ERR_SKILL_UP_SI` (eg. "Your skill in Cooking has increased to 221.")

## CHAT_MSG_SPELL_AURA_GONE_PARTY

## CHAT_MSG_SPELL_AURA_GONE_OTHER
Fired whenever a buff or debuff wears off of a mob, npc, or another player.
Examples: Thorns, Trueshot Aura, Recently Bandaged. arg1 is the full chat text, i.e. "Thorns fades from Someguy."

## CHAT_MSG_SPELL_AURA_GONE_SELF
Fired whenever a buff or debuff wears off - examples, Prowl, Mark of the Wild, Cat Form, or Disarm.  arg1 is the full chat text, i.e. "Prowl fades from you."

## CHAT_MSG_SPELL_BREAK_AURA

## CHAT_MSG_SPELL_CREATURE_VS_CREATURE_BUFF
Fired when a mob begins casting a beneficial spell and again when the casting is completed. arg1 is the full combat chat text.
Examples: Mob begins to cast Heal. Mob's Heal heals Mob for 20.

## CHAT_MSG_SPELL_CREATURE_VS_CREATURE_DAMAGE
Fired when a creature casts a damage spell on a raid member who is not in your group. Also triggered when a pet is damaged by a creature's spell. Ex: Ragnaros' Wrath of Ragnaros hits PlayerName for 1000.

## CHAT_MSG_SPELL_CREATURE_VS_PARTY_BUFF

## CHAT_MSG_SPELL_CREATURE_VS_PARTY_DAMAGE

## CHAT_MSG_SPELL_CREATURE_VS_SELF_BUFF

## CHAT_MSG_SPELL_CREATURE_VS_SELF_DAMAGE
Fired when a mob completes casting a harmful spell on you. (The message for the mob beginning to cast is given by CHAT_MSG_SPELL_CREATURE_VS_CREATURE_DAMAGE.) arg1 is the full combat chat text and includes results of the cast or skill use (e.g. hit, resist, dodge). Examples: Mob's Poison hits you for 10. Mob's  Melee Special was dodged. Mob's Nuke was resisted.

## CHAT_MSG_SPELL_DAMAGESHIELDS_ON_OTHERS

## CHAT_MSG_SPELL_DAMAGESHIELDS_ON_SELF
Fired when a buff (or possibly item) damages an opponent in response to an action... IE Thorns.

## CHAT_MSG_SPELL_FAILED_LOCALPLAYER
Fired when you fail to successfully cast a spell, for one of several reasons. arg1 is the full combat chat text and includes the reason. Examples: You fail to cast Heal: Interrupted. You fail to perform Bear Form: Not enough mana.

## CHAT_MSG_SPELL_FRIENDLYPLAYER_BUFF
Fired when a non-hostile player begins casting a spell or using a skill. arg1 is the full combat chat text. Some examples: Someguy casts Reinforced Armor +40 on Someguys's Pants. Someguy begins to cast Elixir of Whatever. Someguy begins to cast Conjure Food. Someguy begins to cast Summon Felsteed.

## CHAT_MSG_SPELL_FRIENDLYPLAYER_DAMAGE

## CHAT_MSG_SPELL_HOSTILEPLAYER_BUFF

## CHAT_MSG_SPELL_HOSTILEPLAYER_DAMAGE

## CHAT_MSG_SPELL_ITEM_ENCHANTMENTS

## CHAT_MSG_SPELL_PARTY_BUFF

## CHAT_MSG_SPELL_PARTY_DAMAGE

## CHAT_MSG_SPELL_PERIODIC_CREATURE_BUFFS
Fired when a mob gains an "insta-cast" beneficial effect. arg1 is the full combat chat text. Examples: Mob gains Defensive Stance. Mob gains Rushing Charge. Mob gains Demon Skin.

## CHAT_MSG_SPELL_PERIODIC_CREATURE_DAMAGE
example: "Highland Strider suffers 8 Fire damage from your Fireball."

## CHAT_MSG_SPELL_PERIODIC_FRIENDLYPLAYER_BUFFS
Fired when a non-hostile player gains a "buff" effect. arg1 is the full combat chat text. Some examples: Someguy gains Arcane Intellect. Someguy gains Aspect of the Pack. Someguy gains Felsteed.

## CHAT_MSG_SPELL_PERIODIC_FRIENDLYPLAYER_DAMAGE

## CHAT_MSG_SPELL_PERIODIC_HOSTILEPLAYER_BUFFS
For some weird reason, this event is fired when someone heals yourself or another player, eg *"Priest's Flash Heal critically heals you for 2342"*
Haven't tested any other conditions as of yet.

## CHAT_MSG_SPELL_PERIODIC_HOSTILEPLAYER_DAMAGE

## CHAT_MSG_SPELL_PERIODIC_PARTY_BUFFS

## CHAT_MSG_SPELL_PERIODIC_PARTY_DAMAGE

## CHAT_MSG_SPELL_PERIODIC_SELF_BUFFS
Fired when a buff is cast on self. (Unknown if external buff triggers this).
Arg 1 is "You gain $foo" Where $foo is the name of the buff.
*Also called for each "tick" of recurring effects, such as "heal-over-time" spells. Example: You gain 10 health from Rejuvenation. --Syllani*

## CHAT_MSG_SPELL_PERIODIC_SELF_DAMAGE
Fired (possibly among other times) when you are debuffed - so Disarm, Silenced, etc.  I know the name doesn't match, but if you want to verify, enable printing this in your chat log.  Get into combat and get debuffed.  After combat, scroll back up, and while the debuff message is onscreen, change the chat color of this message, and you will see it change...  Very strange.  I assume this is named after poisons or diseases, but I haven't actually tested if those trigger this.  See CHAT_MSG_SPELL_AURA_GONE_SELF if you want to know when it wears off (both buffs and debuffs).  This is accurate as of US Release 1.2.4 (4222), tested by hacking Scrolling Combat Text.  arg1 is the full text of the debuff message, e.g. "You are Disarmed."
This is also fired during the Gnomish Death Ray's channel.
*This is indeed triggered by poison / disease. arg1 messages in the form of: "You suffer 3 damage from Scorpid's Poison" or "You are afflicted by Something" come from this event. --Syllani*

## CHAT_MSG_SPELL_PET_BUFF

## CHAT_MSG_SPELL_PET_DAMAGE

## CHAT_MSG_SPELL_SELF_BUFF
Fired when you cast a beneficial spell. arg1 is the full combat chat text. Examples: Your Heal heals you for 50. Your Regrowth critically heals Someguy for 100.

## CHAT_MSG_SPELL_SELF_DAMAGE
Fired whenever you cast a damage-dealing spell. arg1 holds the exact same string that is posted to the Battle Log (Something like "SpellXY hits EnemyPQ with 42 damage")

## CHAT_MSG_SPELL_TRADESKILLS

## CHAT_MSG_SYSTEM
Fired when a system chat message (they are displayed in yellow) is received.

- **arg1**: The content of the chat message. **arg1** formats are found in Blizzard's `GlobalStrings.lua`.  Some possibilities:
    * `ERR_LEARN_RECIPE_S` (eg. "You have learned how to create a new item: Bristle Whisker Catfish.")
    * `MARKED_AFK_MESSAGE` (eg. "You are now AFK: Away from Keyboard")

## CHAT_MSG_TEXT_EMOTE
Fired for emotes with an emote token. /dance, /healme, etc

- **arg1**: Emote Message
- **arg2**: Name of person who emoted

## CHAT_MSG_WHISPER
Fired when a whisper is received from another player.arg1 = text sent.arg2 = player who sent whisper.arg6 = status of player (AFK or DND)Note: the rest of the arguments seem to be nil, although arg7 and arg8 are 0. I have yet to discover their meaning.

## CHAT_MSG_WHISPER_INFORM
Fired when a whisper is sent to another player.Arg1 = text sent.Arg2 = player whisper sent to.Arg3 = Language message was sent in (even though the other player, if of the same faction, can read the message regardless, and doesn't even see what language you sent it in).

## CHAT_MSG_YELL
Fired when a message is sent or received in the Yell channel.

- **arg1**: Message that was sent/received.
- **arg2**: Name of the player who sent the message.
- **arg3**: Language the message was spoken in. (See [CHAT_MSG_SAY](http://www.wowwiki.com/Events_C_%28Cancel%2C_Character%2C_Chat%2C_Cinematic%2C_Clear%2C_Close%2C_Confirm%2C_Corpse%2C_Craft%2C_Current%2C_Cursor%2C_CVar%29#CHAT_MSG_SAY) for example code)

## CINEMATIC_START

## CINEMATIC_STOP

## CLEAR_TOOLTIP
Fired when the tooltip needs to be wiped

## CLOSE_INBOX_ITEM

## CLOSE_TABARD_FRAME
Fired when the guild dress frame is closed

## CLOSE_WORLD_MAP
Fired when the world map is hidden.

## COMBAT_TEXT_UPDATE

## CONFIRM_BINDER

## CONFIRM_LOOT_ROLL

## CONFIRM_PET_UNLEARN

## CONFIRM_SUMMON

## CONFIRM_TALENT_WIPE

## CONFIRM_XP_LOSS
loss in exchange for his body back.

## CORPSE_IN_INSTANCE

## CORPSE_IN_RANGE
Fired when the player is in range of his body.

## CORPSE_OUT_OF_RANGE
Fired when the player is out of range of his body.

## CRAFT_CLOSE
Fired when a crafting skill window closes. Crafting skills are Enchanting, <craftSkill2>,...

- **arg1**: The mouse button used to close the window.

## CRAFT_SHOW
Fired when a crafting skill window opens. Crafting skills are Enchanting, <craftSkill2>,...

- **arg1**: The mouse button used to open the window.

## CRAFT_UPDATE
Fired when a crafting event is updating.

## CURRENT_SPELL_CAST_CHANGED
Fired when the spell being cast is changed.

## CURSOR_UPDATE
Fired when the player single-clicks terrain. This excludes doodads, NPCs and other PCs.

## CVAR_UPDATE
Fired when a CVar is changed

- **arg1**: cvarname
- **arg2**: value

## DELETE_ITEM_CONFIRM
Fired when the player attempts to destroy an item.

- **arg1**: item name

## DISPLAY_SIZE_CHANGED

## DUEL_FINISHED
Fired when a duel is finished.

## DUEL_INBOUNDS
Fired when the player is still in the bounds of the duel.

## DUEL_OUTOFBOUNDS
Fired when the player leaves the bounds of the duel

## DUEL_REQUESTED
Fired when the player is challenged to a duel

- **arg1**: opponent name

## EQUIP_BIND_CONFIRM
Fired when the player attempts to equip bind on equip loot.

## EXECUTE_CHAT_LINE
Fired when the chat line needs to be processed.

- **arg1**: Chat line

## FRIENDLIST_UPDATE
Fired when...
1. You log in
2. Open the friends window (twice)
3. Switch from the ignore list to the friend's list
4. Switch from the guild, raid, or who tab back to the friends tab (twice)
5. Add a friend
6. Remove a friend
7. Friend comes online
8. Friend goes offline

## GOSSIP_CLOSED
Fired when you close the talk window for an npc (Seems to be called twice)

- **arg1**: The mouse button used to close the window (nil if closed when you go out of range)

## GOSSIP_ENTER_CODE

## GOSSIP_SHOW
Fired when you talk to an npc (Quest dialogue boxes and Vending boxes do not call this event)

## GUILD_INVITE_CANCEL
Fired when the guild invitation is declined.

## GUILD_INVITE_REQUEST
Fired when you are invited to join a guild.

- **arg1**: guild inviter
- **arg2**: guild name

## GUILD_MOTD

## GUILD_REGISTRAR_CLOSED

## GUILD_REGISTRAR_SHOW

## GUILD_ROSTER_SHOW

## GUILD_ROSTER_UPDATE
Fired when the client's guild info cache has been updated after a call to [GuildRoster()](http://wowwiki.wikia.com/wiki/API_GuildRoster).

## GM_PLAYER_INFO

## GMSURVEY_DISPLAY

## IGNORELIST_UPDATE
Fired when a player is added or removed from the ignore list.  Event is called twice.  Not certain why it is called twice.

## IGR_BILLING_NAG_DIALOG

## INSPECT_HONOR_UPDATE

## INSTANCE_BOOT_START
Fired when the countdown to boot a player from an instance starts.

## INSTANCE_BOOT_STOP
Fired when the countdown to boot a player from an instance stops.

## ITEM_LOCK_CHANGED

## ITEM_PUSH
Fired when an item is pushed onto the "inventory-stack". For instance when you manufacture something with your trade skills or picks something up.
arg1 - the stack size (i.e. how many copies of this item fit in a single inventory slot)
arg2 - the path to the item's icon

## ITEM_TEXT_BEGIN
Fired when an items text begins displaying

## ITEM_TEXT_CLOSED
Fired when the items text has completed its viewing and is done.

## ITEM_TEXT_READY
Fired when the item's text can continue and is ready to be scrolled.

## ITEM_TEXT_TRANSLATION
Fired when an item is in the process of being translated.

## LANGUAGE_LIST_CHANGED

## LEARNED_SPELL_IN_TAB
Fired when a new spell/ability is added to the spellbook. e.g. When training a new or a higher level spell/ability.
arg1 - Number of the tab which the spell/ability is added to

## LOCALPLAYER_PET_RENAMED

## LOGOUT_CANCEL

## LOOT_BIND_CONFIRM
Fired when the player attempts to take 'bind-on-pickup' loot

## LOOT_CLOSED
Fired when a player ceases looting a corpse.

## LOOT_OPENED
Fired when a corpse is looted

## LOOT_SLOT_CLEARED
Fired when loot is removed from a corpse.
arg1 - Slot number

## LOTTERY_ITEM_UPDATE

## LOTTERY_SHOW

## MACRO_ACTION_FORBIDDEN

## MAIL_CLOSED

## MAIL_FAILED

## MAIL_INBOX_UPDATE
Fired when the opened inbox changes in any way. For example when the inbox list is loaded after the frame has been opened, or when a mail item changes from new to read.

## MAIL_SEND_INFO_UPDATE
Fired when an item is dragged to or from the Send Item box in an outgoing mail message.

## MAIL_SEND_SUCCESS
Fired when a mail has been successfully sent to the mailbox of the recipient, it is also called when the mailbox is opened for some reason ... bug?

## MAIL_SHOW
Fired when the mailbox is opened.

## MEETINGSTONE_CHANGED
?

## MEMORY_EXHAUSTED
Fired when all memory allocated to the UI is exhausted.

- **arg1**: Current memory limit (in MB).

## MEMORY_RECOVERED
Fired when WoW recovers from an out of memory error.

## MERCHANT_CLOSED
Fired when a merchant frame closes.

## MERCHANT_SHOW
Fired when the merchant frame is shown.

## MERCHANT_UPDATE
Fired when a merchant updates

## MINIGAME_UPDATE

## MINIMAP_PING
Fired when the minimap is pinged.

- **arg1**: UnitId of the one that created the ping (ie "player" or any of the group members)
- **arg2**: x
- **arg3**: y

## MINIMAP_UPDATE_ZOOM
Fired when the minimap scaling factor is changed.  This happens, generally, whenever the player moves indoors from outside, or vice versa.  There are no arguments to this event.  To test the player's location, compare the `minimapZoom` and `minimapInsideZoom` CVars with the current minimap zoom level (see [GetZoom](http://wowwiki.wikia.com/wiki/API_Minimap_GetZoom)).
This event does not relate to the **+** and **-** minimap zoom buttons.

## MINIMAP_ZONE_CHANGED

## MIRROR_TIMER_PAUSE
Fired when the mirror timer is paused.

- **arg1**: pause duration

## MIRROR_TIMER_START
Fired when some sort of timer starts.

- **arg1**: timer
- **arg2**: value
- **arg3**: maxvalue
- **arg4**: scale
- **arg5**: paused
- **arg6**: label

## MIRROR_TIMER_STOP
Fired when a mirror timer is stopped.

## NEW_AUCTION_UPDATE

## OPEN_MASTER_LOOT_LIST

## OPEN_TABARD_FRAME
Fired when the guild dress frame is opened.

## PARTY_INVITE_CANCEL
Fired when you decline a party invite.

## PARTY_INVITE_REQUEST
Fired when a player invite you to party.

- **arg1**: team leader name

## PARTY_LEADER_CHANGED
Fired when the player's leadership changed.
Referred to as *buggy*.

## PARTY_LOOT_METHOD_CHANGED
Fired when the party's loot method changes

## PARTY_MEMBERS_CHANGED
Fired when the player's party changes. As of 1.8.3 this event also fires when players are moved around in a Raid and when a player leaves the raid. This holds true even if the changes do not affect your party within the raid. This event is called twice when the event `PARTY_LOOT_METHOD_CHANGED` is called. This event is generated whenever someone rejects an invite and your in a group, also generated obviously when someone joins or leaves the group.  Also, if for instance you have 3 people in your group and you invite a 4th, it will generate 4 events.  If you call `GetNumPartyMembers()` it will return 0, 1, 2, and 3. First event returing zero, 2nd event returning 1, etc etc.

## PARTY_MEMBER_DISABLE
Fired when a specific party member is offline or dead

- **arg1**: Player Name

## PARTY_MEMBER_ENABLE
Fired when a specific party member is still connected

- **arg1**: Player Name

## PETITION_CLOSED

## PETITION_SHOW

## PET_ATTACK_START
Fired when the player's pet begins attacking.

## PET_ATTACK_STOP
Fired when the player's pet ceases attack

## PET_BAR_HIDEGRID
Fired when the pet bar should be hidden. (dismiss/die)

## PET_BAR_SHOWGRID
Fired when the Pet bar is supposed to be displayed

## PET_BAR_UPDATE
Fired when the pet bar is updates.

## PET_BAR_UPDATE_COOLDOWN
Fired when a pet spell cooldown starts. It is not called when cooldown ends.

## PET_DISMISS_START

## PET_STABLE_CLOSED

## PET_STABLE_SHOW

## PET_STABLE_UPDATE

## PET_STABLE_UPDATE_PAPERDOLL

## PET_UI_CLOSE

## PET_UI_UPDATE

## PLAYERBANKBAGSLOTS_CHANGED
Fired when the One of the six bag slots bank changes.
Does **not** fire when an item is added to or removed from a bank bag, only when
a bag is added or removed from the bag slots.

## PLAYERBANKSLOTS_CHANGED
Fired when the One of the slots in the pleyer's 24 bank slots has changed.
Does **not** fire when an item is added to or removed from a bank bag.

## PLAYER_ALIVE
Fired when the player:
1. Releases from death to a graveyard.
2. Feigns Death with the hunter skill.
3. Lands from a jump or fall.
4. Accepts a resurrect before releasing their spirit.

This is *not* called when the player is alive after being a ghost. `PLAYER_UNGHOST` is triggered in that case.

## PLAYER_AURAS_CHANGED
Called when a buff or debuff is either applied to a unit or is removed from the player.  (Further details to follow, study needed).
- **Druid**: This event is also called when a Druid changes Form (or changes Prowl state when in Cat Form).  **arg1** - **arg9** are all nil in these cases. These args are probably nil for other classes as well. Also, this event can be called multiple times per Form change.

## PLAYER_CAMPING
Fired when the player is camping

## PLAYER_COMBO_POINTS
arg1 is always 'player' not the number of combo points you have.
Use the function GetComboPoints(); to get the exact number of combo points you have.

## PLAYER_CONTROL_GAINED
Fires after the PLAYER_CONTROL_LOST event, when control has been restored to the player.

## PLAYER_CONTROL_LOST
Fires whenever the player is unable to control the character.  Examples are when afflicted by fear or when using a taxi.

## PLAYER_DAMAGE_DONE_MODS

## PLAYER_DEAD
Fired when the player has died.

## PLAYER_ENTERING_WORLD
Fired when the player enters the world, enters/leaves an instance, or respawns at a graveyard.  Also fires any other time the player sees a loading screen. To check if the player is entering an instance, check [GetPlayerMapPosition](http://wowwiki.wikia.com/wiki/API_GetPlayerMapPosition) to see if both X and Y are zero.

## PLAYER_FARSIGHT_FOCUS_CHANGED

## PLAYER_ENTER_COMBAT
Fired when a player engages auto-attack. Note that firing a gun or a spell, or getting aggro, does NOT trigger this event.

From a post by Dhrago on the WoW forums:
`PLAYER_ENTER_COMBAT` and `PLAYER_LEAVE_COMBAT` are for *MELEE* combat only. They fire when you initiate autoattack and when you turn it off. However, any spell or ability that does not turn on autoattack does not trigger it. Nor does it trigger when you get aggro.
You probably want [PLAYER_REGEN_ENABLED](http://wowwiki.wikia.com/wiki/Events_A-Z_(full_list)?direction=prev&amp;oldid=161492#PLAYER_REGEN_ENABLED) (happens when you lose aggro).

## PLAYER_FLAGS_CHANGED
This event fires when a Unit's flags change (eg: due to /afk, /dnd, etc.)

- **arg1**: The [UnitId](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) affected, eg: "player"
- **NOTE**: WoW appears to condense simultaneous flag changes into a single event. If you are currently AFK and not(DND) but you type /dnd you'll see two Chat Log messages ("You are no longer AFK" and "You are now DND: Do Not Disturb") but you'll only see a single PLAYER_FLAGS_CHANGED event.

## PLAYER_GUILD_UPDATE

## PLAYER_LEAVE_COMBAT
Fired when the players opponents die or he dies

## PLAYER_LEAVING_WORLD
Fired when a player logs out and possibly at other situations as well

## PLAYER_LEVEL_UP
Fired when a player levels up.

- **arg1**: New player level. *Note that [UnitLevel("player")](http://wowwiki.wikia.com/wiki/API_UnitLevel) will most likely return an incorrect value when called in this event handler or shortly after, so use this value.*
- **arg2**: Hit points gained from leveling.
- **arg3**: Mana points gained from leveling.
- **arg4**: Talent points gained from leveling. Should always be 1 unless the player is between levels 1 to 9.
- **arg5 - arg9**: Attribute score increases from leveling. Strength (5) / Agility (6) / Stamina (7) / Intellect (8) / Spirit (9).

## PLAYER_LOGIN
Triggered immediately before PLAYER_ENTERING_WORLD on login and UI Reload, but NOT when entering/leaving instances.

## PLAYER_LOGOUT
Sent when the player logs out or the UI is reloaded, after PLAYER_LEAVING_WORLD, but before variables are saved.

## PLAYER_MONEY
Fired whenever the player gains or looses money.

## PLAYER_PET_CHANGED
Fired when a player's pet changes.

## PLAYER_PVP_KILLS_CHANGED
Fired when you slay another player

## PLAYER_PVP_RANK_CHANGED

## PLAYER_PVPLEVEL_CHANGED

## PLAYER_QUITING
Fired when the player hits the quit button.

## PLAYER_REGEN_DISABLED
Fired whenever you get aggro, as normal regen rates are disabled during combat.

## PLAYER_REGEN_ENABLED
Fired a few seconds after ending combat, as regen rates return to normal.

## PLAYER_SKINNED

## PLAYER_TARGET_CHANGED

- **arg1**: holds the same value as GetTime() yields.

## PLAYER_TRADE_MONEY
Fired when the player trades money

## PLAYER_UNGHOST
Fired when the player is alive after being a ghost.  Called after one of:
- Performing a successful corpse run and the player accepts the 'Resurrect Now' box.
- Accepting a resurrect from another player after releasing from a death.
- Zoning into an instance where the player is dead.
- When the player accept a resurrect from a Spirit Healer.

The player is alive when this event happens.  This is *not* called when the player is resurrected before releasing. PLAYER_ALIVE is triggered in that case.

## PLAYER_UPDATE_RESTING
Fired when the player starts or stops resting, ei when entering/leaving inns/major towns.

## PLAYER_XP_UPDATE
Fired when the player's XP is updated (due quest completion or killing)

## PLAYTIME_CHANGED
Fired when the playtime state changes.

## QUEST_ACCEPT_CONFIRM (TODO)
Fired when the player needs to confirm he wishes to accept a quest.

- **arg1**: npc name?
- **arg2**: quest name?

## QUEST_COMPLETE
Fired when the player hits the "Continue" button in the quest-information page, before the "Complete Quest" button.
As far as i can tell this is only ever called when you complete a quest, but just before you actually complete the quest(as stated above)

## QUEST_DETAIL
Fired when the player is given a more detailed view of his quest.

## QUEST_FINISHED
Fired whenever the quest frame changes (Detail to Progress to Reward, etc.) or is closed.

## QUEST_GREETING
Fired when a quest is offered

## QUEST_ITEM_UPDATE
Fired when the quest items are updated

## QUEST_LOG_UPDATE
This event is fired very often.  This includes, but is not limited to: viewing a quest for the first time in a session in the Quest Log; (once for each quest?) every time the player changes zones across an instance boundry;  every time the player picks up a non-grey item;  every time the player performs a quest activity, such as killing a mob for a quest.

## QUEST_PROGRESS
Fired when a player is viewing the status of their quest.

## QUEST_WATCH_UPDATE

## RAID_ROSTER_UPDATE
Fired whenever a raid is formed or disbanded, players are leaving or joining a raid (unsure if rejected join requests also fire the event), or when looting rules are changed (regardless of being in raid or party!)

## RAID_TARGET_UPDATE

## READY_CHECK

## REPLACE_ENCHANT
Fired when the player must confirm an enchantment replacement.

- **arg1**: enchantmentname
- **arg2**: item name

## RESURRECT_REQUEST
Fired when another player resurrects you

- **arg1**: player name

## SCREENSHOT_FAILED
Fired when a screenshot fails.

## SCREENSHOT_SUCCEEDED
Fired when a screenshot is successfully taken.

## SELECT_FIRST_CHARACTER

## SELECT_LAST_CHARACTER

## SEND_MAIL_COD_CHANGED

## SEND_MAIL_MONEY_CHANGED

## SHOW_COMPARE_TOOLTIP

## SKILL_LINES_CHANGED

## SPELLCAST_CHANNEL_START
Fired when a spellcaster begins channelling

- **arg1**: Duration (in milliseconds)
- **arg2**: Spell Name
On version 1.2.1, this event doesnt seem to work.

## SPELLCAST_CHANNEL_STOP

## SPELLCAST_CHANNEL_UPDATE
Fired when a channelling spell is updated.

- **arg1**: remaining Duration (in milliseconds)

## SPELLCAST_DELAYED
Fired when a spellcast duration is increased

- **arg1**: Disruption time

## SPELLCAST_FAILED
Fired when a spell fails.

## SPELLCAST_INTERRUPTED
Fired when a spellcast is interrupted

## SPELLCAST_START
Fired when a spellcast is begun. This event seems to work if the spell has a casting time. For instant, there is no SPELLCAST_START but SPELLCAST_STOP.

- **arg1**: Spell Name
- **arg2**: Duration (arg2 seems to be in milliseconds ex. 1.5 second cast time shows as 1500

## SPELLCAST_STOP
Fired when a spell cast stops. Called twice when the spell is channelled. Once at start, once at completion.

## SPELLS_CHANGED
Fired when:
1. Learning new stuff that goes in the spellbook.
2. Opening the spellbook.
3. Changing/Equiping weapons. (Changes the Attack icon)

- **arg1**: nil when the char learns stuff. Also when changing weapons and shapeshifting. In addition it seems to be called on regular intervals for no apparent reason.

- **arg1**: # when the user opens the spellbook.

- **arg1**: 'LeftButton' when using the mouse to open the spellbook or to browse through the pages and tabs of the open spellbook.

## SPELL_UPDATE_COOLDOWN
Fired when spell cooldown starts.

- **arg1**: if the spell is triggered by keypress, returns the [GetTime()](http://wowwiki.wikia.com/wiki/API_GetTime) output in string format.  Otherwise, it will return "LeftButton" or "RightButton"

## SPELL_UPDATE_USABLE
Fires when you enter combat or die.

## START_AUTOREPEAT_SPELL

## START_LOOT_ROLL
Fired when a group loot item is being rolled on.

- **arg1**: The rollID of the item being rolled on.
- **arg2**: The roll time.

## START_MINIGAME

## STOP_AUTOREPEAT_SPELL

## SUGGEST_REALM

## SYSMSG
Fired when a system message occurs.

- **arg1**: message
- **arg2**: red
- **arg3**: green
- **arg4**: blue

## TABARD_CANSAVE_CHANGED
Fired when it is possible to save a tabard.

## TABARD_SAVE_PENDING

## TAXIMAP_CLOSED
Fired when the taxi frame is closed.

## TAXIMAP_OPENED
Fired when the taxi viewer is opened

## TIME_PLAYED_MSG
Fired when the client recieved a time played message.

- **arg1**: Total time
- **arg2**: Current time at this level

## TOOLTIP_ADD_MONEY
*Event was removed in version 1700. See [OnTooltipAddMoney](http://wowwiki.wikia.com/wiki/API_GameTooltip_OnTooltipAddMoney)*
Fired when a tooltip has money added to it.

- **arg1**: tooltip name
- **arg2**: money amount

## TOOLTIP_ANCHOR_DEFAULT
Fired when the tooltip anchor should be reset

## TRADE_ACCEPT_UPDATE
Fired when the status of the player and target accept buttons has changed

- **arg1**: Player has agreed to the trade (1) or not (0)
- **arg2**: Target has agreed to the trade (1) or not (0)

## TRADE_CLOSED

## TRADE_MONEY_CHANGED
Fired when the trade window's money value is changed.

## TRADE_PLAYER_ITEM_CHANGED
Fired when the specified player itme will be changed by the trade.

- **arg1**: item

## TRADE_REPLACE_ENCHANT
Fired when the the player must confirm an enchantment replacement in the trade window.

- **arg1**: enchantment
- **arg2**: item name

## TRADE_REQUEST
Fired when another player wishes to trade with you.

- **arg1**: player name

## TRADE_REQUEST_CANCEL
Fired when a trade attempt is cancelled.

## TRADE_SHOW
Fired when the Trade window appears after a trade request has been accepted or auto-accepted

## TRADE_SKILL_CLOSE
Fired when a trade skill window is closed.

## TRADE_SKILL_SHOW
Fired when a trade skill window is opened.

## TRADE_SKILL_UPDATE
Fired immediately after TRADE_SKILL_SHOW, after something is created via tradeskill, or anytime the tradeskill window is updated (filtered, tree folded/unfolded, etc.)

## TRADE_TARGET_ITEM_CHANGED
Fired when a specific item will be altered during the trade.

- **arg1**: item

## TRADE_UPDATE
Fired when the trade window is changed.

## TRAINER_CLOSED
Fired when the trainer is closed.

## TRAINER_SHOW

## TRAINER_UPDATE
Fired when the trainer window needs to update.

## TUTORIAL_TRIGGER

## UI_ERROR_MESSAGE
Fired when the interface creates an error message. These are the red messages that show in the top middle of the screen. "Your inventory is full." is one example.

- **arg1**: message

## UI_INFO_MESSAGE
Fired when the interface generates a message. These are the yellow messages in the top middle of the window. "No fish are hooked." is one example.

- **arg1**: message

## UNIT_ATTACK
Fired when a units attack is affected.

## UNIT_ATTACK_POWER
Fired when a unit's attack power changes.

## UNIT_ATTACK_SPEED
Fired when your attack speed is being listed or affected

## UNIT_AURA
Fired when an buff, debuff, status, or item bonus was gained by or faded from a player, NPC, or mob.

- **arg1**: the [UnitID](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) of the entity
NOTE: This event is fired not only when a unit's buffs change, but when you change targets as well! -Myrrion

## UNIT_AURASTATE
Seems like the same as UNIT_AURA above (including arguments) but only for short buffs. As a Paladin, it was triggered each time I gained a 30 second buff (Paladin Seals), lost/canceled it, or switched targets from another player to myself. Needs more testing with other classes etc.

## UNIT_CLASSIFICATION_CHANGED

## UNIT_COMBAT
Fired when an npc or player participates in combat

- **arg1**: the [UnitID](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) of the entity
- **arg2**: Action,Damage,etc (e.g. DODGE, WOUND, MISS, PARRY...)
- **arg3**: Critical indicator (e.g. CRITICAL)
- **arg4**: The numeric damage
- **arg5**: Damage type in numeric value (0 - physical; 1 - holy; 2 - fire; 5 - shadow; 6 - arcane)

## UNIT_COMBO_POINTS

## UNIT_DAMAGE
Fired when the units melee damage changes.
Be warned that this often gets fired multiple times, for example when you change weapons.

## UNIT_DEFENSE
Fired when a units defense is affected

## UNIT_DISPLAYPOWER
Fired when the unit's mana stype is changed.

- **arg1**: unit name

## UNIT_DYNAMIC_FLAGS
Fired when the unit's flags are changed.

## UNIT_ENERGY
Fired whenever a units energy is affected.

- **arg1**: the name of the unit whose energy is affected
Seen unit names:
    * player

## UNIT_FACTION
Fired when a target's faction is announced.

## UNIT_FLAGS

## UNIT_FOCUS
Same as UNIT_MANA, except for certain classes. Hunter used to use focus, but now they use mana. But it is still used when a pets energy changes.

## UNIT_HAPPINESS
*Not studied*

## UNIT_HEALTH
Fired whenever a units health is affected.
It is so important that it gets called twice when it's about the player (might do the same for other things too)

- **arg1**: the name of the unit whose health is affected
Seen unit names:
    * player, pet, target, mouseover, party1..4, partypet1..4

## UNIT_INVENTORY_CHANGED
Fired when the player equips or unequips an item. This is also be called if your target, [mouseover](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) or party member changes equipment (untested for hostile targets).
This event is also raised when a new item is placed in the player's inventory, taking up a new slot. If the new item(s) are placed onto an existing stack or when two stacks already in the inventory are merged, the event is not raised. When an item is moved inside the inventory or to the bank, the event is not raised. The event *is* raised when an existing stack is split inside the player's inventory.

- **arg1**: the [UnitID](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) of the entity

## UNIT_LEVEL
Fired whenever the level of a unit is submitted (e.g. when clicking a unit or someone joins the party)

- **arg1**: the [UnitID](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) of the entity whose level is submitted

## UNIT_LOYALTY

## UNIT_MANA
Fired whenever a unit's mana change either by usage or by regeneration.
The event is also called when a unit is click on.
Only gets called once, unlike its more important brother, UNIT_HEALTH.

- **arg1**: the [UnitID](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) of the entity

## UNIT_MAXENERGY
Fired when a unit's maximum energy changes.

## UNIT_MAXFOCUS
Fired when a unit's maximum focus changes.

## UNIT_MAXHAPPINESS
*Not studied*

## UNIT_MAXHEALTH
Fired when a unit's maximum health changes.

## UNIT_MAXMANA
Fired when a unit's maximum mana changes.

## UNIT_MAXRAGE
Fired when a unit's maximum rage changes.

## UNIT_MODEL_CHANGED
Fired when the unit's 3d model changes.

## UNIT_NAME_UPDATE
Fired when a unit's name changes.

- **arg1**: the [UnitID](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) of the entity whose name changed

## UNIT_PET
Fired when a unit's pet changes.

- **arg1**: The [UnitID](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) of the entity whose pet changed

## UNIT_PET_EXPERIENCE

## UNIT_PET_TRAINING_POINTS

## UNIT_PORTRAIT_UPDATE
Fired when a units portrait changes.

- **arg1**: Unit name

## UNIT_PVP_UPDATE
Fired when the UI is loaded, and when player PVP status is changed or updated.

- **arg1**: the unit whose pvp status has changed (ie. "player")

## UNIT_QUEST_LOG_CHANGED

## UNIT_RAGE
Fired whenever a units rage is affected.

- **arg1**: the name of the unit whose rage is affected
Seen unit names:
    * player

## UNIT_RANGEDDAMAGE
Fired when a unit's ranged damage changes.

## UNIT_RANGED_ATTACK_POWER
Fired when a unit's ranged attack power changes.

## UNIT_RESISTANCES
Fired when the units resistance changes

## UNIT_SPELLMISS
Fired when a spell misses

- **arg1**: Unit Name. arg1 can be 'target' 'mouseover' 'player' or 'partyX' possibly also 'raidX' in party and raid the 'X' represents the number
- **arg2**: action. **arg2** can be 'RESISTED' 'DODGED' 'PARRIED' or 'BLOCKED'

## UNIT_STATS
Fired when a units stats are being passed to the player/thing

## UPDATE_BATTLEFIELD_SCORE
Fired in Warsong Gulch whenever the flag status changes (picked up, dropped, etc).

## UPDATE_BATTLEFIELD_STATUS
Fired whenever you join the queue, change the instance, enter the instance, or leave the instance. Which is nice.

## UPDATE_BINDINGS
Fired when the keybindings are changed.  Fired after completion of [SaveBindings()](http://wowwiki.wikia.com/wiki/API_SaveBindings" title="API SaveBindings).

## UPDATE_BONUS_ACTIONBAR

## UPDATE_CHAT_COLOR
Fired when the chat colour needs to be updated.

- **arg1**: Chat type
- **arg2**: red
- **arg3**: green
- **arg4**: blue

## UPDATE_CHAT_WINDOWS
Fired when there's a reason to update the chat windows.

## UPDATE_EXHAUSTION

## UPDATE_FACTION

## UPDATE_GM_STATUS

## UPDATE_INVENTORY_ALERTS

## UPDATE_INSTANCE_INFO

## UPDATE_LFG

## UPDATE_LFG_LIST

## UPDATE_LFG_TYPES

## UPDATE_MACROS

## UPDATE_MASTER_LOOT_LIST

## UPDATE_MOUSEOVER_UNIT
Fired when the mouseover object needs to be updated.
Fired when the target of the [UnitID](http://wowwiki.wikia.com/wiki/API_TYPE_UnitId" title="API TYPE UnitId) 'mouseover' has changed.
No Arguments.

## UPDATE_PENDING_MAIL
Fired when the player enters the world and enters/leaves an instance, if there is mail in the player's mailbox.
Fired when new mail is received.
Fired when mailbox window is closed if the number of mail items in the inbox changed (I.E. you deleted mail)
Does not appear to trigger when auction outbid mail is received... may not in other cases as well

## UPDATE_SELECTED_CHARACTER

## UPDATE_SHAPESHIFT_FORMS
Fired when the player changes his shape

## UPDATE_TICKET

## UPDATE_TRADESKILL_RECAST

## UPDATE_WORLD_STATES
Fired within Battlefields when certain things occur such as a flag being captured.

## USE_BIND_CONFIRM

## VARIABLES_LOADED
Fired during the loading phase of the UI to indicate that the Saved Variables of all AddOns that will be loaded during the initial load (or reload) of the UI have have been read into memory from their files.

## WHO_LIST_UPDATE
Fired when the client receives the result of a SendWho() request from the server. use [API SetWhoToUI](http://wowwiki.wikia.com/wiki/API_SetWhoToUI) to manipulate this functionality.

## WORLD_MAP_NAME_UPDATE

## WORLD_MAP_UPDATE
Fired when the world map should be updated.

## ZONE_CHANGED
Fired when the player enters a new zone.  Zones are the smallest named subdivions of the game world and are contained within areas (also called regions). Whenever the text over the minimap changes, this event is fired.

## ZONE_CHANGED_INDOORS
Fired when a player enters a new zone within a city.

## ZONE_CHANGED_NEW_AREA
Fired when the user enters a new zone and a new area.  e.g. moving from Duskwood to Stranglethorn Vale.  In interface terms, this is anytime you get a new set of channels.  The ZONE_CHANGED events are mutually exclusive!

## ZONE_UNDER_ATTACK
This doesn't seem to be sent for WorldDefense - it comes in on CHAT_MSG_CHANNEL and totally skips the ZONE_UNDER_ATTACK code in the client.  Is the same true for LocalDefense?

