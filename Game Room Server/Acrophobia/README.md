# Game Room Server - Acrophobia
IMPORTANT: All string details must have quotes around them! For example, Acrophobia would be sent as "Acrophobia".
## `logon_now`
After the client enters the game room IRC channel, it waits until this gets sent to it.
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

## `sponsor_ad`
Once the login has been accepted, the interstitial ad for the current sponsor is downloaded.
<br>After the ad is downloaded, the player is allowed to skip the game instructions.
### Example use:
`sponsor_ad "acr182.srf"`
<br>Details:
- 1: The SRF file to download.

No request command used, this is sent independently.
<br>

## `current_state`
After the client wants to start the game, this is sent.
<br>Tells the client what round the current game is at.
### Example use:
`current_state start_game`
<br>Details:
- 1: The current round of the currently running game.
  - This can be any command that begins with `start_` and starts a round.
### Request command: `start_play`
Example use: `start_play`
<br>No request details are used besides the command.

<br>After this, the server is (mostly) on its own.
<br>See the other files in this folder for the other commands.
