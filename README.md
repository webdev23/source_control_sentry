## [SCS] Source Control Sentry<br>
Backup/Restore files. Watch for recursive content,ownerships and rights changes.<br>
Create hard copies and display file diffs.<br>
Optionally execute one -or more- commands, reload a browser tab, at a file change.<br>
Restore files on demand.<br>

<img src="https://raw.githubusercontent.com/webdev23/source_control_sentry/master/scs.png">SCS</img>

Automatize your dev flow. Example, run a test script, or compile at a file change.<br>
Backup all files versions, while keeping an eye on the flow. No more code lost with CTRL+Z<br>
Exclude hidden git files. Works well on top of git. Exclude nohup.out as well.<br>
Can inject some javascript into a browser console tab, at a file change.<br>

By default, without parameters, the program starts to watch the current directory.
And display file diffs at a change.


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
Those are all changes made in the current DIR, by date, while the current program was running.

    scs -b --browse

#### Examples:

### Reload focused tabs of many browsers
    scs -r firefox -r chromium

### Run commands
    scs -r firefox -e "ls -ltrapR"

### Inject alert("xss") in the currently focused Firefox tab
    scs -x script.js
