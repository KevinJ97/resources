# Mac OS
Tested on version: 10.13.3 (17D102)

### Expand Default Printing Preferences
The default printing settings are acceptable if you do not need to customize your printing options frequently and therefore have the advanced options collapsed. To force the printing dialog to always show the expanded form with the advanced options, use the following command:
```bash
# Expand by default: 
defaults write -g PMPrintingExpandedStateForPrint -bool TRUE

# Revert back to collapse by default:
defaults write -g PMPrintingExpandedStateForPrint -bool FALSE
```

### Disable Dashboard
I have not seen anyone use the built in Mac OS Dashboard application unless on accident by pressing the keyboard shortcut. Leaving the dashboard running idle will still take up CPU. To disable the dashboard entirely:
```bash
# Disable:
defaults write com.apple.dashboard mcx-disabled -boolean TRUE; killall Dock

# Enable: 
defaults write com.apple.dashboard mcx-disabled -boolean FALSE; killall Dock
```

### Speed Up Hiding Dock
Using all of the screen is important for multitasking and hiding the dock comes with the issue of having to hold the mouse to show the dock. This delay is annoying for users who use the dock frequently. To disable the delay entirely:
```bash
# Disable delay:
defaults write com.apple.dock autohide-delay -float 0; killall Dock

# Enable delay:
defaults write com.apple.dock autohide-delay -float 1; killall Dock

# Disable dock animation for faster dock:
defaults write com.apple.dock autohide-time-modifier -float 0; killall Dock

# Enable dock animation:
defaults delete com.apple.dock autohide-time-modifier; killall Dock
```

### Window Screenshots
Apple's Grab application allows users to take screenshots very easily. `Shift-Command-3` will take a screenshot of the entire display and save it to the desktop. For users with multiple displays, the screenshots will be saved separately for each display. `Shift-Command-4` will take a selection screenshot of whatever the user selects. Hitting the `Space bar` after the command will enable window screenshot mode, however by default Apple will add a gradient background to the window screenshot. To remove this:
```bash
# Disable gradient shadow: 
defaults write com.apple.screencapture disable-shadow -bool TRUE; killall SystemUIServer

# Enable gradient shadow:
defaults write com.apple.screencapture disable-shadow -bool FALSE; killall SystemUIServer
```