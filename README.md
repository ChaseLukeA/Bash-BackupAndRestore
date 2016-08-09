#BackupAndRestore

##Why I made this:

I use a Mac at work and a different Mac at home. I wanted certain preferences (from ~/Library/Preferences/ or ~/Library/Application Support/) to be in a list of files to backup so I could just type `./backup` or something simple every day to sync these files into my Dropbox directory, or to restore them from the Dropbox directory. From my folder, I can type `./backup` at work to backup the current prefs states, then Dropbox syncs itself, then when I get home I can type `./restore` from my backup folder and it restores my work Mac's prefs to my home Mac. Or something like that. It works for me.

##Usage:

You'll need the file files `makelist backup restore archive unarchive` in the directory you want to use as your backup directory

`makelist` - type `./makelist <file1> <file2> <etc>` at a terminal to create a list of files for regular backup or archiving; you can also type `./makelist ` and just drag/drop files to the terminal as well

`backup` - type `./backup` to copy the list of files in `.files` to the current directory

`restore` - type `./restore` to copy the list of files in the current directory back to their original copy directory

`archive` - type `./archive` to make a zip file of the files in `.files` with the same name as the current folder

`unarchive` - type `./unarchive` to unzip the zipped file of the current folder's name to the current folder
