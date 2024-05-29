# Registration Server - Acrophobia (Older Versions)
## `/cgi/acrval0.cgi` (Validation)
Used for logging in.
### Example Request:
`Username=user&Password=pass&ShowID=ACR&Origin=V1.0&Version=1.0.24&Platform=W`
- `Username`: The account's username.
- `Password`: The account's password. (WARNING: It's plaintext!)
- `ShowID`: The "Show ID" of the game. (Always ACR for Acrophobia)
- `Origin`: The "Installer Origin ID".
  - Known Origin ID's: `BETA3` for 1.0.4.72/1.0.18.79, and `V1.0` for 1.0.24.84
  - If the origin is `error`, then the client couldn't find it in the registry.
- `Version`: The version of the game client.
  - If "Path" is not set correctly in the registry, then the version will be `0.0.0.4915348`.
- `Platform`: What the game is being played on. (`W` means Windows)
### Example Response:
`UserName=user&UserID=746&SessionID=6712950&RetCode=0&Message=Success`
- `UserName`: The username of the account.
- `UserID`: The ID of the account.
- `SessionId`: The ID of the current play session.
- `RetCode`: The return code.
- `Message`: The message to be displayed on an error.

Anything other than a success only returns the return code and the message.
<br>List of return codes:
- `0`: Validation was successful.
- `2`: Database error? (Internally just says "Failed")
- `5`: Username isn't registered.
- `6`: Username or password incorrect.
- `7`: Database error? (Internally called "FailBadData")
- `8`: Bad username, enter a new one.
- `9`: Database error.
- `10`: Account has been banned.
- `11`: Database error? (Internally called "FailUnknownScript")
<br>

## `/cgi/bezreg0.cgi` (Registration)
Used for registering new accounts. Not all of the details below are required, thankfully.
<br>A lot of these details were used to send out prizes won through competitions.
### Example Request:
`Email=fake@mail.com&Username=user&Password=pass&Country=US&Zip=11111&Gender=M&Agerange=7&Notices=1&ShowID=ACR&Realname=real+name&Address1=1+road&City=city&State=state&CPU=4&Ram=5&Monitor=3&ISP=ispname&ConnectSpd=4&Income=1&Job=8&Education=1&SurfPlace=1&Origin=error`
- `Email`: The email address of the new account.
- `Username`: The username for the new account.
- `Password`: The password for the new account. (WARNING: It's plaintext!)
- `Country`: The country that the player is from.
- `Zip`: The ZIP code of the player.
- `Gender`: The gender of the player.
- `Agerange`: The age range of the player.
  - `0` is under 18, anything else is over 18.
- `Notices`: If the Bezerk newsletter should be sent to the player's email.
- `ShowID`: The "Show ID" of the game. (Always ACR for Acrophobia)
- `Realname`: The player's real name.
- `Address1`: The address of the player.
- `City`: The city that the player lives in.
- `State`: The state that the player lives in.
- `CPU`: The CPU speed of the player's computer.
- `Ram`: The amount of RAM installed in the player's computer.
- `Monitor`: The monitor size of the player's computer.
- `ISP`: The name of the ISP that the player is using.
- `ConnectSpd`: The speed of the player's internet connection.
- `Income`: The player's income range.
- `Job`: The type of job that the player works in.
- `Education`: The level of education that the player is at.
- `SurfPlace`: Where the player uses the internet at the most.
- `Origin`: The "Installer Origin ID".
  - Known Origin ID's: `BETA3` for 1.0.4.72/1.0.18.79, and `V1.0` for 1.0.24.84
  - If the origin is `error`, then the client couldn't find it in the registry.
## Example Response:
`RetCode=0&Message=Thank+you+for+registering+for+beZerk.+Have+fun!`
- `RetCode`: The return code.
- `Message`: The message to be displayed.

List of return codes:
- `0`: Registration was successful.
- `2`: Database error? (Internally just says "Failed")
- `7`: Database error? (Internally called "FailBadData")
- `9`: Database error.
- `10`: Account has been banned.
- `11`: Database error? (Internally called "FailUnknownScript")
