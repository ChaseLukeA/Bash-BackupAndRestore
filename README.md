#Terminal Backup And Restore

##Why I made this:

I use a Mac at work and a different Mac at home. I wanted certain preferences (from ~/Library/Preferences/ or ~/Library/Application Support/) to be in a list of files to backup so I could just type `./backup` or something simple every day to sync these files into my Dropbox directory, or to restore them from the Dropbox directory. From my folder, I can type `./backup` at work to backup the current prefs states, then Dropbox syncs itself, then when I get home I can type `./restore` from my backup folder and it restores my work Mac's prefs to my home Mac. I couldn't get a symbolic or hard link of any file in either of those directories to work, nor could any good answers be found elsewhere. This works for me.

##Usage:

In terminal, navigate to the folder the t_<command> and install files are in. Run `./install` to copy the 5 executables to your usr/local/bin directory. You may now type any of the following commands from any directory.

From any directory you want to use as a backup directory:

Make your backup files `.files` list:
  Type `t_makelist <file1> <file2> <etc>` at a terminal to create a list of files for regular backup or archiving; you can also type `t_makelist ` and just drag/drop files to the terminal as well

Backing up files in your `.files` list:

  Type `t_backup` to copy the list of files in `.files` to the current directory

Restoring files in your `.files` list:

  Type `t_restore` to copy the list of files in the current directory back to their original copy directory

Archiving the backed up files in your backup folder:

  Type `t_archive` to make a zip file of the files in `.files` with the same name as the current folder

Unarchiving the archived files in your backup folder:

  Type `t_unarchive` to unzip the zipped file of the current folder's name to the current folder
