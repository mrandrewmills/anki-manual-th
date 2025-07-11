# Managing Files and Your Collection

<!-- toc -->

## Checking Your Collection

It is a good idea to occasionally check your collection file for
problems. You can do this via the Tools&gt;Check Database menu item.
Checking the database ensures the file has not been corrupted, rebuilds some
internal structures, and optimizes the file.

When you check the database, your tag list is also rebuilt. When you
delete individual decks or cards, Anki does not update the list of used
tags, as it's inefficient to do so. If you want to clear old tags out
from the list that are no longer in use, checking your database is the
way to do it.

Please note that Anki will automatically optimize your collection once
every 2 weeks. This optimization ensures the collection performs well,
but it does not check for errors or rebuild the tag list when
automatically optimizing.

<a id="file-locations"></a>

## User Data

On **Windows**, the latest Anki versions store your collection files in your
appdata folder. You can access it by opening the file manager, and
typing `%APPDATA%\Anki2` in the location field. Older versions of Anki
stored your Anki files in a folder called `Anki` in your `Documents`
folder.

On **Mac** computers, recent Anki versions store all user data in the
`~/Library/Application Support/Anki2` folder. The Library folder is
hidden by default, but can be revealed in Finder by holding down the
option key while clicking on the Go menu. If you're on an older Anki
version, your Anki files will be in your `Documents/Anki` folder.

On **Linux**, recent Anki versions store your user data in
`~/.local/share/Anki2`, or `$XDG_DATA_HOME/Anki2` if you have set a
custom data path. If you are using a third-party **Flatpak** build,
your files will be in `~/.var/app/net.ankiweb.Anki/data/Anki2/`.
Older versions of Anki stored your files in
`~/Documents/Anki` or `~/Anki`.

Within the Anki folder, the program-level and profile-level preferences
are stored in a file called `prefs.db`.

There is also a separate folder for each profile. The folder contains:

- Your notes, decks, cards and so on in a file called `collection.anki2`

- Your audio and images in a `collection.media` folder

- A backups folder

- Some system files

You should never copy or move your collection while Anki is open. Doing
so could cause your collection to become corrupt. Please do not move or
modify the other files in the folder either.

## Program Files

Anki's launcher is installed in the following locations by default:

- Windows: `%LOCALAPPDATA%\Programs\Anki`
- macOS: `/Applications/Anki.app`
- Linux: `/usr/local/share/anki`

When you install/update Anki with the launcher, it downloads support
files and places them in the following locations:

- Windows: `%LOCALAPPDATA%\AnkiProgramFiles`
- macOS: `~/Library/Application Support/AnkiProgramFiles`
- Linux: `~/.local/share/AnkiProgramFiles`

Removing that folder will cause the launcher to behave like a fresh install.

The `AnkiProgramFiles` contains all the files needed to run Anki aside from
the launcher. You can copy it to a different folder or system, and start
Anki from the new location by opening `AnkiProgramFiles/.venv/bin/anki` (or
`AnkiProgramFiles\.venv\scripts\anki` on Windows). If placed in the standard location on a new computer, the launcher will also be able to re-use the existing files, provided the files were copied with modification times preserved.

See the flash drive section below for more.

## Startup Options

If you have made a destructive change on one computer and have an
undamaged copy on another computer, you may wish to start Anki without
syncing in order to use the full sync option without first downloading
the changes. Similarly, if you are experiencing problems with Anki, you
might need to (or might be instructed to) disable add-ons temporarily to
see if one might be causing the problem. To do both of these things at the same time, you can
open Anki in safe mode by holding down the <kbd>Shift</kbd> key while starting Anki. Keep holding <kbd>Shift</kbd> down until the on-screen message informs you that Anki has started in safe mode.

It is possible to specify a custom folder location during startup. This
is an advanced feature that is primarily intended to be used with
portable installations, and we recommend you use the default location in
most circumstances.

The syntax to specify an alternate folder is as follows:

    anki -b /path/to/anki/folder

- If you have multiple profiles, you can pass -p &lt;name&gt; to load
  a specific profile.
- If you pass -p some-fake-name, Anki will show the profile screen on startup.
  If no profile is provided, the last-used profile is loaded.

- To change the interface language, use -l &lt;iso 639-1 language
  code&gt;, such as "-l ja" for Japanese.

If you always want to use a custom folder location, you can modify your
shortcut to Anki. On Windows, right-click on the shortcut, choose
Properties, select the Shortcut tab, and add "-b
\\path\\to\\data\\folder" after the path to the program, which should
leave you with something like

    "C:\Program Files\Anki\anki.exe" -b "C:\AnkiDataFolder"

You can also use this technique with the -l option to easily use Anki in
different languages.

On Windows, you should use a backslash (\\) not a forward slash (/).

On a Mac there is no easy way to alter the behaviour when clicking on
the Anki icon, but it is possible to start Anki with a custom base
folder from a terminal:

    open /Applications/Anki.app --args -b ~/myankifolder

Alternatively, you can define the environment variable "ANKI_BASE".
On Windows, you can define the environment variable with:

    set "ANKI_BASE=C:/path/to/AnkiDataFolder"

On Linux and macOS, you can use:

    export ANKI_BASE="/path/to/AnkiDataFolder"

## DropBox and File Syncing

We do not recommend you sync your Anki folder directly with a
third-party synchronization service, as it can lead to database
corruption when files are synced while in use.

If you just want to synchronize your media, you can link external
folders into services like DropBox. Please see [DropboxWiki: Sync
Folders Outside Dropbox (archive.org)][dropboxwiki-sync-other]
for more info.

[dropboxwiki-sync-other]: http://web.archive.org/web/20180919153730/http://www.dropboxwiki.com/tips-and-tricks/sync-other-folders

If you wish to keep your collection in sync as well, it is strongly
recommended that you create a script that copies your files from your
synced folder to a local folder, launches Anki, and then copies the
files back when Anki is closed. This will ensure that the files are
never synchronized while they are open.

## Network Filesystems

We strongly recommend you have Anki store your files on a local hard
disk, as network filesystems can lead to database corruption. If a
network filesystem is your only option, regular use of Tools&gt;Check
Database to detect corruption is recommended.

## Running from a Flash Drive

On Windows, Anki can be installed on a USB / flash drive and run as a
portable application. The following example assumes your USB drive is
drive G. Please ensure you've read the Program Files section above first.

- Copy the `AnkiProgramFiles` folder to the flash drive, so you
  have a folder like `G:\Anki`.

- Create a text file called `G:\anki.bat` with the following text:

  `g:\anki\.venv\scripts\pythonw -c 'import aqt; aqt.run()' -b g:\ankidata`

- Double-clicking on `anki.bat` should start Anki with the user data
  stored in `G:\\ankidata`.

Media syncing with AnkiWeb may not work if your flash drive is formatted
as FAT32. Please format the drive as NTFS to ensure media syncs
correctly.

## Backups

Please see [this section](./backups.md).

## Inaccessible Harddisk

If Anki can't write to files in the [Anki folder](#user-data), a message
will be displayed on startup saying that Anki can't write to the
harddisk, and Anki will close. If you're unsure how to fix the
permissions, please contact someone near you who is knowledgeable about
computers and can help you out.

## Permissions of Temp Folder

Anki uses the system's temporary folder to store temporary data. If the
permissions of this folder have been changed from the default settings
by a rogue app or buggy antivirus app, Anki will not function properly.

If you're on a Windows 7 machine, the general steps to fix the problem
are listed below. As this is somewhat complicated, please ask someone
knowledgeable about Windows if you are not sure.

1. Click on the start bar, and type in %temp% (including the percents),
   then hit <kbd>Enter</kbd>.

2. Go up one folder, and locate the temp folder. Right click on it, and
   choose Properties.

3. In the security tab, click on Advanced.

4. Click on the Owner tab. If you're not listed as the owner, click the
   button to take ownership.

5. On the permissions tab, ensure that you have full control. On a
   default W7 install the control will actually be inherited from
   c:\\users\\your-username.

## Corrupt Collections

Anki uses a file format that is robust against program and computer
crashes, but it's still possible for your collection to become corrupt
if the files are modified while Anki is open, stored on a network drive,
or corrupted by a bug.

When you run Tools&gt;Check Database, you will receive a message if Anki
detects the file has been corrupted. **The best way to recover from this
is to restore from the most recent [automatic backup](#backups)**, but
if your backup is too old, then you can attempt to repair the corruption
instead.

On Linux, make sure sqlite3 is installed. On a Mac, it should be
installed already. On Windows, download
<http://www.sqlite.org/sqlite-3_6_23.zip>.

Next, create a backup of your collection.anki2 file, in case something
goes wrong with the steps below.

### Linux/macOS

Open a terminal, change to the folder your collection is located in, and
type:

    sqlite3 collection.anki2 .dump > dump.txt

Open the resulting dump.txt file in a text editor, and look at the final
line. If it reads "rollback;", change it to "commit;"

Then run the following in a terminal:

    cat dump.txt | sqlite3 temp.file

Make sure you use temp.file - do not put collection.anki2 on the right,
or you will blank out the file. When you're done, proceed to the final
step.

### Windows

Copy the `sqlite3.exe` program and your deck to your desktop. Then go to
**Start&gt;Run** and type in `cmd.exe`.

If you're on a recent Windows, the command prompt may not start on your
desktop. If you don't see desktop displayed in the command prompt, type
something like the following, replacing "administrator" with your login
name.

    cd C:\Users\Administrator\Desktop

Then type:

    sqlite3 collection.anki2 .dump > dump.txt

Open the resulting dump.txt file in a text editor, and look at the final
line. If it reads "rollback;", change it to "commit;"

Then run the following in a terminal:

    type dump.txt | sqlite3 temp.file

Make sure you use temp.file - do not put collection.anki2 on the right,
or you will blank out the file. When you're done, proceed to the final
step.

### Final Step

Check that you didn't get an error message, and that temp.file is not
empty. The procedure optimizes the collection in the process, so it's
normal for the new file to be somewhat smaller than the old one.

When you've confirmed the file is not empty:

- rename the original collection.anki2 file to something else

- rename temp.file to collection.anki2

- move collection.anki2 back into your collection folder, overwriting
  the old version

- start Anki and go to Tools&gt;Check Database to make sure the
  collection has been successfully restored.
