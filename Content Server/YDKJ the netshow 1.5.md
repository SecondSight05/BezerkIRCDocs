# Content Server - YDKJ the netshow 1.5
All content that the netshow 1.5 engine or the Bezerk Updater asks for must be inside the `jol` folder.
## `/jol/patches/`
The two bootup SRF files, `boot.srf` and `patch.srf`, are stored here. They're downloaded every time by the Bezerk Updater.
<br>You must make a folder in here for the engine's version. (e.g. `/jol/patches/v123/`)
<br>The known engine versions of 1.5 are `v116` and `v123`.
<br>On older versions (v116), only `boot.srf` is downloaded.

## `/jol/download/`
Contains updates to the game in the form of ZIP's for each file.
<br>For example, `adclick.srf` would be added to a ZIP file called `adclick.zip`.
<br>Like patches, you must make a folder for the engine's version. (e.g. `/jol/download/v123/`)
<br>NOTE: `Jack Netshow.exe` must be added to `jacknetshow.zip`. However, I haven't been able to get the EXE to work properly when extracted through the Bezerk Updater.

## `/jol/adfold/`
The SRF files for the interstitial ads are found here.

## `/jol/qfold/`
All the questions for the episodes are here, as well as the file that contains the episode's introduction audio.
<br>They are seperated into folders with their episode numbers. (e.g. `/jol/qfold/e217/`)

## `/jol/teaser/`
This only contains one SRF file, used for the "teaser" section at the end of the game. (After the YDKJ shout)

## `/jol/additional/`
The additional audio SRF files are stored here.
<br>This also uses a version folder, but it is completely different from the engine version.
<br>v116 uses `v7`, and v123 uses `v10`.
