# Game List Server - Acrophobia
IMPORTANT: All string details must have quotes around them! For example, Acrophobia would be sent as "Acrophobia".
## `logon_now`
After the client enters the game list IRC channel (usually `#Acro_List` for Acrophobia), it waits until this gets sent to it.
<br>NOTE: Only send this in private messages to clients that haven't logged on yet!
### Example use:
`logon_now 0 "message"`
<br>Details:
- 1: Authenticate value. Unknown use, not required.
- 2: Logon message. Unknown use, not required.

No request command used, this is sent independently.
<br>

## `logon_accepted`
If the details given in the `logon` request command are correct, then send this privately.
### Example use:
`logon_accepted 0 "message"`
<br>Details:
- 1: Server version. Unknown use, not required.
- 2: Logon message. Unknown use, not required.
### Request command: `logon`
Example use: `logon "user" "pass" 29407 1 2 0 130 746 6712950`
<br>Request Details:
- 1: The account's username.
- 2: The account's password. (WARNING: It's plaintext!)
- 3: Encrypted value. Unknown use.
- 4 - 7: The version of the game client.
  - For example, the details `1 2 0 130` would mean that the game version is 1.2.0.130
  - If "Path" is not set correctly in the registry, then the details will be `0 0 4915348 4915348`.
- 8: The ID of the account.
- 9: The ID of the current play session.
<br>

## `bot` (List)
Once the login has been accepted, the room list is sent.
<br>This is a list, so it works in three steps:
<br>One - Start the list with `start_list bot`.
<br>Two - Send each room with a `list_item bot`, then the details.
<br>Three - Once all the rooms have been sent, end the list with `end_list bot`.
### Example use (for list_item bot):
`list_item bot 0 "room name" 0 "127.0.0.1" 6667 0 "irc_channel" 0 "Acrobot" 1 "mode" 0 0 0 0`
<br>Details:
- 1: Unknown use.
- 2: The room's name.
- 3: Unknown use.
- 4: The IP of the Game Room Server.
- 5: The port of the Game Room Server.
- 6: Unknown use.
- 7: The IRC channel to join on the Game Room Server.
  - You can do this with or without the # at the beginning.
- 8: Unknown use.
- 9: The IRC bot name to look for on the Game Room Server.
- 10: If the room has the language filter on or not.
  - 1 for a Keep It Clean room, 0 for an Adult Language room.
- 11: The room's game mode.
  - The two known modes are "Practice" and "Play".
  - If a room has no players, keep this blank. (Don't forget the quotes!)
- 12: The number of players currently in the room.
- 13: The current high score of the room.
- 14: Unknown use.
- 15: If the room is Special Interest or not.
  - Special Interest rooms only appear green in versions of Acrophobia after 1.0.24.84

No request command used, this is sent independently.
<br>

## `player_not_found`
If the requested player is offline when using the Find My Friends feature.
### Example use:
`player_not_found "user"`
<br>Details:
- 1: The username of the requested player.
### Request command: `command find_player`
Example use: `command find_player "user"`
<br>Request Details:
- 1: The requested player.
<br>

## `player_found`
If the requested player is online when using the Find My Friends feature.
### Example use:
`player_found "user" "room name" 0 "127.0.0.1" 6667 0 "irc_channel" 0 "Acrobot" 1 "mode" 1 0 0`
<br>Details:
- 1: The username of the requested player.
- 2: The room's name.
- 3: Unknown use.
- 4: The IP of the Game Room Server.
- 5: The port of the Game Room Server.
- 6: Unknown use.
- 7: The IRC channel to join on the Game Room Server.
  - You can do this with or without the # at the beginning.
- 8: Unknown use.
- 9: The IRC bot name to look for on the Game Room Server.
- 10: If the room has the language filter on or not.
  - 1 for a Keep It Clean room, 0 for an Adult Language room.
- 11: The room's game mode.
  - The two known modes are "Practice" and "Play".
- 12: The number of players currently in the room.
- 13: The current high score of the room.
- 14: If the requested player is online, but not in a room.
  - If this is the case, you don't need to fill out legit information for everything else.
### Request command: `command find_player`
Example use: `command find_player "user"`
<br>Request Details:
- 1: The requested player.
