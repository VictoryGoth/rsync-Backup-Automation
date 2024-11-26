# Steps to automate rsync to external drive
This should automatically run an rsync backup whenever you mount an external drive. The code provided will create a notification letting you know the backup has started and when it's completed. You can disable notifications by removing all osascript lines.

### Creating the backup script:
1. In Terminal, bash:
   - nano ~/backup-to-archive.sh
3. Copy and paste code from **Archive Script** and edit.
   - If you have any issues running the script because it has issues finding any of your Finder paths, copy and paste code from **Archive Script File Path Fix** 
5. Save edits and Exit: Ctrl+0, Enter, Ctrl+X

### Make the script executable:
1. chmod +x ~/backup-to-archive.sh
2. Run the script: ~/backup-to-archive.sh

If it executes without any issues, move on to "Automate with LaunchAgent" 

### Automate with LaunchAgent
The code for the LaunchAgent will open a new Terminal window so you can see exactly what it's doing. You can disable by removing all osascript lines.

1. bash: diskutil info /Volumes/YourArchiveDrive | grep 'Volume UUID'
   - If that doesn't show the Volume UIDD either copy the code from **DiskUtil Info** or open the Disk Utility app and click "Info" on your volume.
2. Copy the Volume UIDD number and paste it somewhere where you can grab it again later (or leave Dis Utility window open).
3. Open Terminal and bash:
   - nano ~/Library/LaunchAgents/com.user.backuptoarchive.plist
5. Copy and paste code from **LaunchAgent Script** and edit.

### You're (hopefully) done! 
Test by unplugging your external drive then plug it back in.
