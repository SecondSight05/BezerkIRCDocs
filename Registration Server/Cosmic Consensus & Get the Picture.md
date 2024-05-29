# Registration Server - Cosmic & GTP
## `/big/validate.cgi` & `/gtp/validate.cgi` (Validation)
Used for logging in.
### Example Request:
`player_name=user&password=pass&origin_code=M1&version=1.0.0.26&platform_code=W`
- `player_name`: The account's username.
- `password`: The account's password. (WARNING: It's plaintext!)
- `origin_code`: The "Installer Origin ID".
  - Known Origin ID's: `b1` for Cosmic Consensus, and `M1` for Get the Picture.
  - If the origin is `err` or `NA+`, then the client couldn't find it in the registry.
- `version`: The version of the game client.
- `platform_code`: What the game is being played on. (`W` means Windows)
### Example Response:
`player_name=SecondSight&version=1.0.0.26&platform_code=W&player_id=746&playersession_id=6712950&adult=1&result=1`
- `player_name`: The username of the account.
- `version`: The latest version of the game.
- `platform_code`: What the game is being played on. (`W` means Windows)
- `player_id`: The ID of the account.
- `playersession_id`: The ID of the current play session.
- `adult`: If the account is over 18.
  - This allows or denies access to Adult Language rooms.
- `result`: The result code.

Anything other than a success only returns the result code.
<br>List of result codes:
- `0.999` or `1`: Validation was successful.
- `2`: Database "CGI error" or No content length.
- `5`: Username isn't registered.
- `6`: Username or password incorrect.
- `8`: Bad username, enter a new one.
- `10`: Account has been banned.
- `11`: Email invalid, enter a new one.
- `12`: Username expired due to inactivity.
- `13`: Database "DB error".
<br>

## `/cgi/bezreg0.cgi` (Registration)
Used for registering new accounts. Not all of the details below are required, thankfully.
<br>A lot of these details were used to send out prizes won through competitions.
### Example Request:
`Email=fake@mail.com&Name=user&Password=pass&Country=US&Zip=11111&Gender=M&Agerange=7&Notices=1&RealName=real+name&Address=1+road&City=city&State=state&Cpu=4&Ram=5&Monitor=3&ConnectSpeed=4&Income=1&Job=8&Education=1&SurfPlace=1`
- `Email`: The email address of the new account.
- `Name`: The username for the new account.
- `Password`: The password for the new account. (WARNING: It's plaintext!)
- `Country`: The country that the player is from.
- `Zip`: The ZIP code of the player.
- `Gender`: The gender of the player.
- `Agerange`: The age range of the player.
  - `0` is under 18, anything else is over 18.
- `Notices`: If the Bezerk newsletter should be sent to the player's email.
- `RealName`: The player's real name.
- `Address`: The address of the player.
- `City`: The city that the player lives in.
- `State`: The state that the player lives in.
- `Cpu`: The CPU speed of the player's computer.
- `Ram`: The amount of RAM installed in the player's computer.
- `Monitor`: The monitor size of the player's computer.
- `ConnectSpeed`: The speed of the player's internet connection.
- `Income`: The player's income range.
- `Job`: The type of job that the player works in.
- `Education`: The level of education that the player is at.
- `SurfPlace`: Where the player uses the internet at the most.
## Example Response:
`Result=0`
<br>List of result codes:
- `0.999`: Registration was successful.
- `2`: Database "CGI error".
- `4`: Username already in use.
- `6`: Username in use by you, but with a different password.
- `8`: Bad username, enter a new one.
- `9`: Database "DB error".
- `10`: Account has been banned.
- `12`: Username expired, and was given to someone else.
- `13`: Database "DB error", missing field.
- `14`: Database cannot process a detail.
- `15`: Database "DB Open error".
- `16`: Database "DB Bind error".
- `17`: Database "DB Exec error".
<br>

## `/cgi/bezchange0.cgi` (Detail Changing)
Used for changing bad usernames and invalid email addresses.
### Example Requests
When changing email: `NameOriginal=username&PasswordOriginal=password&Email=fake@mail.com&`
<br>When changing username: `NameOriginal=username&PasswordOriginal=password&Name=newname`
- `NameOriginal`: The username entered during the initial validation attempt.
- `PasswordOriginal`: The password entered during the initial validation attempt. (WARNING: It's plaintext!)
- `Email`: The email to change to. (If changing email)
- `Name`: The username to change to. (If changing username)
## Example Response:
`Result=0`
<br>List of result codes:
- `0.999`: Detail changing was successful.
- `2`: Database "CGI error".
- `4`: Username already in use. (If changing username)
- `5`: Database cannot process change. (Username not registered)
- `6`: Database cannot process change. (Incorrect password)
- `8`: Bad username, enter a new one. (If changing username)
- `9`: Database "DB error".
- `10`: Database cannot process change. (Account banned)
- `12`: Username expired due to inactivity, enter a new one.
- `13`: Database "DB error", missing field.
- `14`: Database cannot process a detail.
- `15`: Database "DB Open error".
- `16`: Database "DB Bind error".
- `17`: Database "DB Exec error".
