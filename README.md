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
   – Working directory: `$FileDir$`

All checkboxes in the form are optional, you can check whichever you want.    
CSScomb will be available then in all menus you select.

## Configure

You can place `.csscomb.json` file in the project's directory, or your `HOME`
directory, or anywhere else.    
[See
docs](https://github.com/csscomb/csscomb.js/blob/master/doc/configuration.md#where-to-put-config) for info.

## Version Compatibility Notes

If you've recently updated csscomb, you may notice it no longer work correctly as an external tool within JetBrains editors (eg. Intellij IDEA, WebStorm, PhpStorm). It does not finish the process anymore. However, it works correctly when run from the command line.

To get it working again:
1. Check if your installed version is higher than 3.1.5:

   ```npm -g list --depth=0```

2. If so, remove it:

   ```npm remove -g csscomb```

3. Install version 3.1.5:

   ```npm install -g csscomb@3.1.5```

4. Verify version 3.1.5 is installed:

   ```npm -g list --depth=0```
   
5. Confirm csscomb runs and exits correctly in your JetBrains editor.
