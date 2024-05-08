# Dispatch Server - All Other Games
NOTE: When I say "All Other Games", I mean Acrophobia, Cosmic Consenus/What's the Big Idea, and Get the Picture.
## `/`>Game Name Here<`/dispatch/client/Dispatch.ini`<br>& `/acrophobia/Dispatch.ini`
(`/acrophobia/Dispatch.ini` is only used by older versions of Acrophobia.)
<br>This file is too long to show an example of here, so [click here](/%3COriginal%20File%20Examples%3E/Dispatch.ini) to view the original.

Dispatch.ini is the first file that the other games try to access.
<br>The file is split into sections, so I will explain each of them separately.

### `[Dispatch File]`
This first section is used to set up the Show ID/Name, the path to the Update Script, the names for the other sections, and the names for the CGI files in the Registration Server.
<br>Also, any sections after this one with XYZ in their name below can be used multiple times. The other versions of that section will be used as alternatives if one of the servers isn't working.

### `[Content Server XYZ]`
Sets up the name and the port (yes, port 80 is required) of the Content Server, which is a web server.

### `[Game List Server XYZ]`
Sets up the name and port of the Game List Server, which is an IRC server.

### `[Registration Server XYZ]`
Sets up the name and port (port 80 is required again) of the Registration Server, which is a web server.

### `[Web Server]`
Sets up the name, and the web pages that will open when the game closes of the Web Server. Setting the port isn't needed.
<br>This is the only one of these "server sections" that doesn't allow multiple uses.

## `/acrophobia/shell/configfiles/files.lst`
This is only used in the WON version of Acrophobia.
<br>It lists the files that should be updated before letting you login.
<br>Below is the original lines from the file:
<br>`wonauth.dll 196608 01-17-2000 02:07p`
<br>`Acro.swf 65793 08-30-1999 01:41p`
<br>`Acrophobia.dll 729088 03-13-2000 02:20p`
<br>`AdLet.dll 618572 10-11-1999 09:31a`
<br>`Bezerk.swf 177880 08-18-1999 01:47p`
<br>`eula.abc 11046 09-15-1999 11:07a`
<br>`ShellUpdate.exe 61440 10-09-1999 04:50p`
<br>`splashlist.txt 22 11-04-1999 04:58p`

## `/acrowonver/shell/configfiles/shell.cfg`
This is only used in the WON version of Acrophobia.
<br>It sets up various information used in the WON Shell program, including the size of the window, the servers to connect to, and the web page that opens when the game closes.
<br>You won't be able to just copy the text without problems, so you can view the original file by [clicking here](/%3COriginal%20File%20Examples%3E/shell.cfg).
