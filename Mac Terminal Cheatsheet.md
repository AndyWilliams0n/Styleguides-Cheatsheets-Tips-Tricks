# Mac Terminal Cheatsheet

## TERMINAL COMMANDS

| Command | Description |
| ------- | ----------- |
| Sudo [Command] | Run command with super-user privileges |
|  |  |
| Cd /path/to/directory | Change directory |
| Cd ~ | Home directory, ex .: 'cd ~ / folder /' |
| Cd / | Root directory |
| Cd .. | Parent directory |
| Cd ../../ | Move above two levels |
| Cd. | Current Folder |
|  |  |
| Ls | List files in folder |
| Ls -l | List files in a folder, list format |
| Ls -a | List files in a folder, including hidden files |
| Ls -lh | Lists a folder of files with details |
| Ls -R | List files in a folder, recursively |
|  |  |
| Rm /path/to/file.txt | Delete files |
| Rm -i /path/to/file.txt | Delete with confirmation |
| Rm -R /path/to/directory | Deletes a directory and files recursively |
| Rm -f /path/to/file.txt | Forces deletion without confirmation |
|  |  |
| Ditto /path/to/file.txt /path/to/file.txt | Copy file, while keeping permissions |
| Ditto /path/to/directory /path/to/directory | Copy directory |
| Ditto -V /path/to/file.txt /path/to/file.txt | Copy file, list files copied |
|  |  |
| Cp /path/to/file.txt /path/to/file.txt | Copy file |
| Cp /path/to/file.txt /path/to/directory | Copy a file to another directory |
|  |  |
| Mv /path/to/file.txt /path/to/new.txt | Move or Rename a file |
|  |  |
| mkfile 1g /path/to/directory | Create a file of 1Gb |
|  |  |
| Mkdir /path/to/directory | Create a new folder |
| Mkdir -p /path/to/directory / directory | Creates a folder with a subfolder |
|  |  |
| Rmdir /path/to/directory | Remove folder, only if empty |
|  |  |
| Touch /path/to/file.txt | Creates a new file |
| Pwd | Full path to the working directory |
|  |  |
| Open /path/to/file.txt | Opens a file |
| Nano /path/to/file.txt | Open the Terminal editor |
| Peak /path/to/file.txt | Open the Terminal editor |
| Uptime | Display the current time and how long our Mac has been running |
| Exit | Terminal Out |
| Clear | Clear screen |



## HISTORY

| Command | Description |
| ------- | ----------- |
| History n | Shows the typed commands - How many historical are displayed from the last command |
| Ctrl-r | Lets you search through previously used commands |
| ! [Value] | Run the last command entered that begins with 'value' |
| !! | Run the last command entered |



## TO FILE

| Command | Description |
| ------- | ----------- |
| > /path/to/file.txt | Generates a new file, noting that it can be overridden |
| >> /path/to/file.txt | Adds the output to the file |



## HELP

| Command | Description |
| ------- | ----------- |
| [Command] -h | Displays help for the command |
| [Command] --help | help Displays the command |
| [Command] help | Displays help for the command |
| Reset | Resets your current screen terminal |
| Man [Command] | Displays help for your 'command' |
| Whatis [Command] | Give a description of a line of command '|



## TERMINAL TIPS

| Command | Description |
| ------- | ----------- |
| python -m SimpleHTTPServer 8000 | Start a simple HTTP Server in any folder |
|  |  |
| defaults write com.apple.screencapture type [Extention] | Change the default Screenshot File Format * |
| defaults write com.apple.screencapture location [/path/to/directory,~/Desktop] | Change the default Screenshot File Location *** |
| defaults write com.apple.dock pinning -string end | Move dock to any corner you want ** |
| defaults write com.apple.dashboard devmode [YES,NO] | Add widgets to you desktop [YES,NO] ** |
| defaults write com.apple.finder AppleShowAllFiles [TRUE,FALSE] | Show hidden files [TRUE,FALSE] * |
| defaults write com.apple.NetworkBrowser BrowseAllInterfaces -bool [TRUE,FALSE] | Enable AirDrop on older macs [TRUE,FALSE] * |
| defaults write com.google.Chrome.plist AppleEnableSwipeNavigateWithScrolls -bool [TRUE,FALSE] | Disable Google Chrome’s two-finger swipe navigation [TRUE,FALSE] |
| defaults write com.apple.Dock showhidden -bool [TRUE,FALSE] | Make the icon of any hidden app in the Dock translucent [TRUE,FALSE] ** |
|  |  |
| caffeinate -t [3600] | Prevent your mac from sleeping [Seconds] |
| say [Hello, how are you] | Get you mac to talk to you [Words] |
| /System/Library/Frameworks/CoreServices.framework + /Frameworks/LaunchServices.framework/Support/lsregister -kill -r -domain local -domain system -domain user | Remove duplicate “Open With…” entries |
| open -a /Applications/AppName.app /path/to/file.txt | Open documents directly from the Terminal in your chosen app |
| curl -O http://www.urltofile.com/path/to/file.txt | Download a file without a browser |
| sudo shutdown -h now | Shutdown your Mac immediately |
| sudo shutdown -r now | Restart your Mac immediately |
| sudo shutdown -h +60 | Shutdown your Mac in 60s |
| tail -f /path/to/file.txt | Continually monitor the output of a file |
| ipconfig getifaddr en0 | Get your network IP address |
| curl ipecho.net/plain; echo | Get your external IP address |
| ping -c 10 www.google.co.uk | Test network connectivity |
| sudo nvram SystemAudioVolume=%50 | Set the startup chime volume |
| sudo asr -restore -noverify -source /path/to/diskimage/dmg -target /Volumes/VolumeToRestoreTo | Restore a disk image to an external drive |
| defaults write com.apple.dashboard mcx-disabled -boolean [TRUE,FALSE] | Turn off dashboard [TRUE,FALSE] ** |
|  |  |
| telnet towel.blinkenlights.nl | Play StarWars in ASCII format |
|  |  |
| killall Finder | * Relaunch finder, use after some of these commands |
| killall Dock  | ** Relaunch dock, use after some of these commands |
| killall SystemUIServer  | *** Relaunch UI, use after some of these commands |


## KEY SHORTCUTS

| Keys | Description |
| ---- | ----------- |
| Tab | Auto-Complete commands and filenames. |
| Ctrl + A | Go to top of the line you are typing |
| Ctrl + E | Go to the end of the line you are typing |
| Ctrl + L | Clear screen |
| Ctrl + U | Clears the line before the cursor position. If at the end of the line, clears the entire line |
| Ctrl + H | Same as backspace |
| Ctrl + R | Lets you search through previously used commands |
| Ctrl + C | Exit what you're running |
| Ctrl + D | Exit current shell |
| Ctrl + Z | Place which is running in a background process |
| Ctrl + W | To delete the word before the cursor |
| Ctrl + K | Delete the line after the cursor |
| Ctrl + T | Swap the last two characters before the cursor |
| Esc + T | Swap the last two words before the cursor |
| Alt + F | Move the cursor forward one word on the current line |
| Alt + B | Move cursor backward one word on the current line |
