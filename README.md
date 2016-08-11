#Terminal Backup And Restore

##Why I made this:

I use a Mac at work and a different Mac at home. I wanted certain preferences (from ~/Library/Preferences/ or ~/Library/Application Support/) to be in a list of files to backup so I could just type something simple every day to sync these files into my Dropbox directory, or to restore them from the Dropbox directory. From a backup folder, I can type `tbar -b` at work to backup the current prefs states, then Dropbox syncs itself, then when I get home I can type `tbar -r` from my backup folder and it restores my work Mac's prefs to my home Mac. I couldn't get a symbolic or hard link of any file in either of those directories to work, nor could any good answers be found elsewhere. This works for me.

##Installation:

In terminal, navigate to the folder containing `install`. Run `./install` OR `sh install` to copy the executables to your usr/local/bin directory. You may now type any of the following commands from any directory.

#####Troubleshooting install:

If you cannot execute `./install` in terminal, give yourself execute permissions by typing `chmod 755 install` and then trying again.

Make sure you have permissions to `/usr/local/bin` (you should) if you have any copy or permission change errors.

##Usage:

####You can use either `tbar -'flag'` or direct `t_'command'` commands from any directory you wish to use as a backup directory:

#####Make your backup files `.files` list:

  * Type `tbar -m file1 file2 etc` OR `tbar makelist file1 file 2 etc` OR `t_makelist file1 file2 etc` at a terminal to create a list of files for regular backup or archiving; you can also type `t_makelist ` OR `tbar makelilst ` OR  `tbar -m ` and just drag/drop files to the terminal as well

#####Backing up files in your `.files` list:

  * Type `tbar -b` OR `tbar backup` OR `t_backup` to copy the list of files in `.files` to the current directory

#####(Quick) Backing up files in your `.files` list:

  * Type `tbar -q` OR `tbar backupquick` OR `t_backupquick` to copy the list of files in `.files` to the current directory
  * This mode is nearly silent and does not clear screen, great for use in multiple-backup script so you can see easy line-by-line successes or failures


#####Restoring files in your `.files` list:

  * Type `tbar -r` OR `tbar restore` OR `t_restore` to copy the list of files in the current directory back to their original copy directory

#####Archiving the backed up files in your backup folder:

  * Type `tbar -a` OR `tbar archive` OR `t_archive` to make a zip file of the files in `.files` with the same name as the current folder

#####Unarchiving the archived files in your backup folder:

  * Type `tbar -u` OR `tbar unarchive` OR `t_unarchive` to unzip the zipped file of the current folder's name to the current folder

##Examples:

I like having a copy of my WindowTidy preferences for when they change, etc. Here's how that worked:

On the first Mac, I navigate to my WindowTidy preferences backup folder:

  `cd ~/Dropbox/Preferences/WindowTidy`

Then the first time I run `tbar` I create the `.files` backup list:

  `tbar -m ~/Libarary/Preferences/com.lightpillar.Window-Tidy.plist ~/Library/Application\ Support/WindowTidy/Layouts.data`

This adds those two files to a new `.files` list. Next I type:

  `tbar -b`

This copies those two files to the directory I'm in with the `.files` file. Finally I type:

  `tbar -a`

This creates a zip file of both preference files named the same as my directory name (just in case I screw something up, I have a backup of the current files now).

On another Mac with Dropbox installed, I navigate to my WindowTidy preferences save folder:

  `cd ~/Dropbox/Preferences/WindowTidy`

Here I can restore those settings to the preferences folder on the second Mac:

  `tbar -r`

A few minutes later, I made a mistake in my WindowTidy layout. I'd like to go back to the recent archive of it:

  `tbar -u`

And now restore those files:

  `tbar -r`

That's it!
