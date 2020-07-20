## [SCS] Source Control Sentry<br>
Backup/Restore files. Watch for recursive content,ownerships and rights changes.<br>
Create hard copies and display file diffs.<br>
Optionally execute *commands*, reload a browser tab, at a file change.<br>
Restore files on demand.<br>

<img src="https://raw.githubusercontent.com/webdev23/source_control_sentry/master/scs.png">

Automatize your dev flow. Example, run a test script!<br>
Backup all files versions, while keeping an eye on the flow.<br>
Exclude hidden git files. Works well on top of git. Exclude nohup.out as well.<br>
Can inject some javascript into a browser console tab, at a file change.<br>

By default, without parameters, the program starts to watch the current directory.
And display file diffs at a change.


### PARAMS:
<pre>
 -e  --exec    command
               Execute command (Use quotes if necessary)
 -r  --reload  program_name
               Refresh program_name (must have F5 capabilities)
 -x  --inject  js_file
               javascript injection in browser console
     --purge 
               Delete cache
 -b  --browse  
               Explore diffs changes and restore files
 </pre>

### Browse historic and restore files

Browse current DIR historic and restore files.
Those are all changes made in the current DIR, by date, while the current program was running.

    cd /mydir && scs -b

### Examples:

#### Reload focused tabs of many browsers, when a file changed.
    scs -r firefox -r chromium

#### Run commands, when a file changed.
    scs -e "./mytest.sh"

#### Inject the content of script.js in the currently focused Firefox tab, when a file changed.
    scs -x script.js

---

### Simple run:

This is a monolithic script written in php. It will take care to create a hidden backup directory `.scs` in the home folder.
The following tools are necessary on the system. (Notice `scs` might verify and update them at the first launch)

    php curl xdotool diffutils colordiff wdiff

The simplest usage is to put `scs` in the target directory and run it:

    ./scs

---

### Or global Installation:

To install globally in one command, with all the dependencies and shortcuts, you can use my <a href="https://github.com/webdev23/phi">dedicated tool φ phi</a>:
If φ phi is not currently installed, do:

    php <(curl https://webdev23.github.io/phi/phi) install https://webdev23.github.io/source_control_sentry/scs
    
If φ phi is already there, simply:

    phi install https://webdev23.github.io/source_control_sentry/scs

Then, from any directory, start the program:

    scs
    
 ---
 
###💡Usage cases
 
#### 🌐 Web development
 
Simply reload your browser tab automaticaly. Visualize your css without leaving your editor.
 
#### 🔧 Automatization and testing

A file change event will trigger the javascript code you wrote, in the browser console. 

#### 🔍 Trace a program

Observe how a program works by viewing the change made in his files in real time.

#### ✅ Run automagic tests

Write your test scripts, and pass them in the `-e` param.<br>
Their output are going to be displayed on the `scs` screen.

#### 🚗 Compile and run on the fly

For the tasks requiring compilation, simply get the result by just saving your editor.

#### 🔥 A simple text editor become all what we need

No risks to loose code, rapid debugging. No more code lost with too much CTRL+Z.

#### 😜 Assist development

Keep an eye and quickly remember the changes made across files and line numbers.
