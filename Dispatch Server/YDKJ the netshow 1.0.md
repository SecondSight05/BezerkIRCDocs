# Dispatch Server - YDKJ the netshow 1.0
## `/cgi/register0.cgi`
The first file that the netshow 1.0 engine tries to access if running the game for the first time.
<br>Used for registering a new user - The details given here would of originally been placed into a database.

Needed values:
<br>`BuildOKToRun` - If the version of netshow that is being played is up to date. Only use "Y" or "N" here.
<br>`EmailValid` - If the player's email is valid or not. Only use "1" or "0" here.

Example response:
<br>`BuildOKToRun=Y&EmailValid=1`

## `/cgi/dispatch2.cgi`
The first file that the netshow 1.5 engine tries to access.
<br>Fills in information about the current episode, interstitial ads, and more.

Note: Any spaces are replaced by a "+". For example, `Hello there!` would be changed to `Hello+there!`

Needed values:
<br>`BuildOKToRun` - If the version of netshow that is being played is up to date. Only use "Y" or "N" here.
<br>`EmailValid` - If the player's email is valid or not. Only use "1" or "0" here.
<br>`Episode` - The current episode number.

- The episode number is important for downloading its files properly, so be careful.

`ContentServer` - A location of a server where SRF files are downloaded from. You can have multiple of these.
<br>`ContentServerCount` - The amount of content servers that are avaliable. The limit for this is unknown.
<br>`Ad` - The redirection name, SRF file name, and positioning of an interstitial ad.

- Example ad use: `Ad=ACR182,acr182.srf,11`
  - Once the game is over, the ad that the player requested more information on would be processed on the Bezerk website. That's what the "redirection name" is for.
  - The positioning number is used to tell the game when the ad should be played, and which ad break it should be played on. The first one (or two) numbers in the position is for which question the ad will be played on, and the third number is for the order in which the ad should be played.
  - For example, if the positioning number was 141, that ad would be the first one played after the 14th question.

`AdCount` - The amount of interstitial ads that will be played. Must be the same as the amount of "Ad" values.

Example response:<br>`BuildOKToRun=Y&EmailValid=1&Episode=82&ContentServer=127.0.0.1&ContentServer=127.0.0.1&ContentServerCount=2&Ad=ACR182,acr182.srf,11&Ad=BUD143,bud143.srf,41&Ad=HUG173,hug173.srf,71&Ad=NAB184,nab184.srf,91&Ad=USR135,usr135.srf,121&Ad=VIS171,vis171.srf,141&AdCount=6`

## `/cgi/endofgame1.cgi`
This file is accessed during various points during the game, as well as the end of it.
<br>Despite the file's name, it's not just for the end of the game.

I'm not sure what response is supposed to be given here.
<br>However, I just use the same one as register0.cgi's example response, and it works fine.
