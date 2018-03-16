# Mac OS
Tested on version: 10.13.3 (17D102)

## Documents
### Expand Default Printing Preferences
The default printing settings are acceptable if you do not need to customize your printing options frequently and therefore have the advanced options collapsed. To force the printing dialog to always show the expanded form with the advanced options, use the following command:
```bash
# Expand by default: 
defaults write -g PMPrintingExpandedStateForPrint -bool TRUE

# Revert back to collapse by default:
defaults write -g PMPrintingExpandedStateForPrint -bool FALSE
```
