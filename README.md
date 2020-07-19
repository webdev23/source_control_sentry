## [SCS] Source Control Sentry<br>
Backup/Restore files.<br>
Run actions on any change in a directory.<br>
Create hard copies and display file diffs.<br>
Verify content, ownserships and rights.<br>
Can execute one -or more- commands, or reload a browser tab, at a file change.<br>
Restore files on demand.<br>
Automatize dev flow. Example, run a test script, or compile at a file change.<br>
Recursive to the whole directory tree.<br>
Backup all files versions, keeping the flow by timestamp.<br>
Exclude git hidden files. Works well on top of git. Exclude nohup.out as well.<br>
Can inject some javascript into a browser console tab, at a file change.<br>

By default, without parameters, starts to watch the current directory.
Display diffs at a file change.

### PARAMS:
<pre>
 -e  --exec    command
               Execute command (Use quotes if necessary)
 -r  --reload  program_name
               Reload program_name (must have F5 capabilities)
 -x  --inject  <js file>
               javascript injection in browser console
     --purge 
               Delete cache
 -b  --browse  
               Explore diffs changes and restore files
 </pre>

### Browse historic and restore files

Browse current DIR historic and restore files.
Those are all changes made in the current DIR, by date, while the current program was running
-b --browse

### Examples:

### Reload focused tabs of many browsers
-r firefox -r chromium

### Run commands
 ./dev -r firefox -e "ls -ltrapR"

### Inject alert("xss") in the currently focused Firefox tab
 -x script.js

 Can be used on top of any text editor CTR+Z + Fat fingers = lost code

