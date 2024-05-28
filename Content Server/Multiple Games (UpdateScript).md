# Content Server - The UpdateScript
The UpdateScript is responsible for updating the game's files, as well as some variables.
<br>It can usually be found at `/`>Game Name Here<`/content/UpdateScript.ini`.
<br>It's too long to show an example of here, so [click here](/%3COriginal%20File%20Examples%3E/UpdateScript.ini) to view the original.
<br>(NOTE: The UpdateScript does not effect either of the netshow games.)
## `[Update Script]`
The first part of the script sets the version of the script, and the Show ID/Name.

## `[Server Version Folders]`
The second part (not linked to by anything else) sets the folder where SRF file updates will be downloaded from.
<br>You can set different folders for each client version.

## The rest of the script
This is where things get a bit complicated.
<br>The UpdateScript system is designed in a way where tasks link to and from each other. For example:
<br>If the script called to Goto "Update This Thing", it of course could just update the thing and move on. However, if you want to be more efficient in your updating, you can then link to another task,
which does a completely seperate thing. You can even have multiple Goto's for each task, with "1 Goto", "2 Goto", etc, and basically set up a network of tasks.
<br>I would highly recommend looking at one of the original UpdateScripts (linked above) to get a better understanding on how this whole system works.

## The commands of the script
When you arrive at a command, and want to do something, there's several things that are allowed.
<br>You can:
- Create folders (e.g. `IF CLIENT_FOLDER DOESNOTEXIST THEN CREATE_FOLDER`)
- Download files (e.g. `IF CLIENT_PATH NOTEQUALTO VERSION THEN UPDATE`)
- Goto somewhere else (e.g. `IF THIS LESSTHANOREQUALTO VERSION THEN GOTO`)

Again, I would recommend looking at one of the original scripts...
