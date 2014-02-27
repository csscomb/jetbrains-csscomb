## Install

There is no special plugin for JetBrains' IDEs.    
Instead, you can use CSScomb as an external tool:

1. Install CSScomb: `npm install csscomb`
1. Go to  `Preferences > External Tools` (or press `⌘,` on Mac)
1. Click on `Add` icon (or press `⌘N` on Mac)
1. Fill the form with following info:    
   – Name: `CSScomb`    
   – Program: `path_to_installed_csscomb/bin/csscomb`    
   – Parameters: `$FilePath$`

All checkboxes in the form are optional, you can check whichever you want.    
CSScomb will be available then in all menus you select.

## Configure

You can place `.csscomb.json` file in the project's directory, or your `HOME`
directory, or anywhere else.    
[See
docs](https://github.com/csscomb/csscomb.js/blob/master/doc/configuration.md#where-to-put-config) for info.
