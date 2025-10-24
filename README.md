# application_cleaner
We all hate unused applications piling up and eating up storage on our machines. So, here's a solution. Go through ReadMe and find out how you can use these to clean up your PC. I might create one for Android and iOS later. Currently you can use these for Linux, Windows and MacOS. Enjoy !!

🧹 Unused Application Cleanup ScriptsThis repository contains two scripts designed to help free up disk space by identifying and optionally deleting applications or directories that haven't been accessed in a specified number of days.⚠️ 
Crucial Warnings: READ BEFORE EXECUTION ⚠️Both scripts use the file system's Last Access Time as a proxy for determining when an application was last used.
Last Access Time Reliability: On many modern operating systems (Windows and Linux/macOS with SSDs), access time tracking (atime) is often disabled or minimized for performance reasons. 
This means the time stamps might be old, unreliable, or simply reflect the time of installation, not the last launch time.PREVIEW FIRST: By default, both scripts operate in a Preview Mode and will only list the files they would delete. 
No files will be removed unless you explicitly modify the script file to enable deletion.Irreversible Action: Once deletion is enabled and run, the action is irreversible. 
Review the preview list carefully.
🍏 Linux / macOS Script (application_cleaner.sh)This script uses the find command and the -atime flag to locate inactive directories.
Configuration : 
  You MUST edit these variables directly inside the application_cleaner.sh file:VariableDescriptionAction Required INACTIVITY_DAYS The minimum number of days since the last access. Default is 20.
  APP_DIR The directory to search (e.g., /Applications or ~/Applications).MUST BE CHANGED to your target path.Execution Make executable: chmod +x application_cleaner.shRun Preview Mode (Recommended): bash application_cleaner.sh
  Enable Deletion: To permanently delete the listed files, you must uncomment the find ... -exec rm -rf {} \; section in STEP 3 of the script and run it again.🪟 
  Windows Script (application_cleaner.ps1)This script uses PowerShell's Get-ChildItem and Where-Object commands to filter items based on the LastAccessTime property.ConfigurationYou MUST edit these variables directly inside the application_cleaner.ps1 file:VariableDescriptionAction Required$INACTIVITY_DAYSThe minimum number of days since the last access.Default is 20.
  $APP_DIRThe directory to search (e.g., C:\Program Files or a user-specific folder).
  MUST BE CHANGED to your target path.
  $DELETE_ENABLEDSafety flag ($false for preview, $true for deletion).Default is $false. Change to $true to delete.
  ExecutionOpen PowerShell (You may need to run as Administrator for system folders).Run Preview Mode (Recommended): .\application_cleaner.ps1
  Enable Deletion: To permanently delete the listed files, you must change the $DELETE_ENABLED flag from $false to $true inside the script file and run it again.
