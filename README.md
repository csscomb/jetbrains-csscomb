## Install

There is no special plugin for JetBrains' IDEs.    
Instead, you can use CSScomb as an external tool:

1. Install CSScomb: `npm install csscomb`
1. Go to  `Preferences > External Tools` (or press `⌘,` on Mac)
1. Click on `Add` icon (or press `⌘N` on Mac)
1. Fill the form with following info:    
   – Name: `CSScomb`    
   – Program: `path_to_installed_csscomb/bin/csscomb` (see NB for Windows users below)    
   – Parameters: `$FilePath$ -t`    
   – Working directory: `$FileDir$`

All checkboxes in the form are optional, you can check whichever you want.    
CSScomb will be available then in all menus you select.

NB. On Windows you may need to use `npm config get prefix` to get a directory with `csscomb.cmd`. So in "Program" field you will need to put something like `C:\Users\User\AppData\Roaming\npm\csscomb.cmd`.

## Configure

You can place `.csscomb.json` file in the project's directory, or your `HOME`
directory, or anywhere else.    
[See
docs](https://github.com/csscomb/csscomb.js/blob/master/doc/configuration.md#where-to-put-config) for info.

## Version Compatibility Notes

If you've updated csscomb, you may notice it no longer work correctly as an external tool within JetBrains editors (eg. Intellij IDEA, WebStorm, PhpStorm). It does not finish the process anymore. However, it works correctly when run from the command line.

To get it working again:
1. Check if your installed version is higher than 3.1.5:

   ```npm -g list --depth=0```

2. If so, open your editor's Preferences > Tools > External Tools > CSScomb.

3. Edit the Parameters field to include `-t`, for example:  `-t $FilePath$`. From CSScomb's documentation:
    
    > -t, --ttyy-mode     execution in TTY mode (useful, when running tool using external app, e.g. IDE)
   
3. Confirm csscomb runs and exits correctly in your JetBrains editor.
