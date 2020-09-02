## bash pt.2 
[**Youtube Video**](https://www.youtube.com/watch?v=KQWygP2JSsM)

## Tips in Bash (again):
- **tab :** tries to auto-complete what you are typing
- **Ctrl-C :** ends the current program; keep a note of this one.
- **!! :** Runs/brings up previous command entered, hope it's not _rm_ :(

## Commands:
/cats1/ directory has /cats2/cats3/12coolfile.txt /cats2/cats3/dogscool.txt and cats4/ directories inside it. What you type is after the "$"

- **sudo :**  Gives user root privileges (admin rights), typed before command. Makes command be run as what's called a "super user"

After typing it, you will be prompted to type password (don't be alarmed if you don't see your password being typed out, it's normal, just type it and press enter once you're done.
```bash
$ sudo <some_command>
```
- **echo:** Allows you to print into bash. This is useful when chaining longer commands to debug what went wrong.

This command will print out whatever "some_string" is.
```bash
$ echo <some_string>
```

- **find:** A tool for locating files (is Amazing). This command will print out everything in the path specified, that is, files and everything inside directories in that path.

By just typing a " . ", bash will print out everything in the current directory.
```bash
$ find <path_to_directory>
$ find .
```
Using the flag **"-name"** will lead the terminal to only print out paths for files with that specific name.
```bash
$ find <path_to_directory> -name <file_name>
```
```bash
~/Desktop/cats1 $ find /cats2 -name 12coolfile.txt
cats2/cats3/12coolfile.txt
```
Additionally you can use the **" * " _wildcard_** to find files with a specific beginning, or files that are all the same type:
```bash
~/Desktop/cats1 $ find /cats2 -name 12*file*.txt
cats2/cats3/12coolfile.txt
```
Using the **-iname** flag instead of -name will cause the search to be case-_insensitive_ (aka, doesn't care about caps):
```bash
~/Desktop/cats1 $ find /cats2 -iname *FiLe*.txt
cats2/cats3/12coolfile.txt
```
Using the **-delete** flag will lead to all files found to be deleted. In this example I combine two flags.
```bash
~/Desktop/cats1 $ find /cats2 -name 12*file*.txt -delete
~/Desktop/cats1 $ find .
.
./.secretCats.txt
./cats2
./cats2/cats3
./cats4
```
- **grep:**Global Regular Expression Print, used to find all text instances in a specified file (will return lines where text was found)
```bash
$  grep <text_to_look_for> <file_path>
```
```bash
$  grep david cats2/cats3/12coolfile.txt
david was here
david was also down here
cats are evil! david
```
Using the **"-w"** flag will return only those lines with exact matches, that is something like "davidAndFriends" won't return if you're looking for "david"
Additionally, the **"-i"** flag will cause the search to be case-insensitive.
**_Note:_** Flags can stack on top of each other, that is, "wi" will do the case, and the exact match search.
```bash
$  grep <search_text> <file_to_search> -w
$  grep <search_text> <file_to_search> -wi
```
- **diff:** Will compare two files line by line, and then identify the lines where they differ
```bash
$  diff <file1> <file2>
```
## Logical Operators
Extra features, can chain them!

- **&&:** Let's you do several commands sequentially all in one line as long as all preceding commands complete successfully 
```bash
$  <command1> && <command2> && <command...>
```

- **||:** will try the first command and if the first command fails, will do the command after the operator 
```bash
$  <command1> || <command2>
```

# Text Editors in bash
We use these to edit files in bash, some examples are:
	- **Vim**
	- **Emacs**
	- **Nano (not as popular)**
## Vim: 
If file exists, vim will open the file, if not, if you save when closing, vim will create the file. 
```bash
$  vim <file_name>
```
vim opens in **command mode** This can be identified by a lack of description at the bottom of the window.

_**Keys:**_
_**Essential:**_
- **" i "** = Enters _**insert mode**_
- **Esc key (in insert mode)** = Press esc to go back to command mode
- **" :q "** = To quit
- **" :q! "** = To quit without saving
- **" :wq  "** = Write and quit

_**Travel:**_
-  **" h ", " j ", " k ", " l ",** = left, down, up, right (arrow keys also work)
- **" $ "** = Moves cursor to the end of the line
- **" _ "** = Moves cursor to the beginning of line
- **" w " and " b "** = Moves cursor forward and backward, one word at a time
- **" /<some_word> "** = will move the cursor to the next occurrence of <some_word>
- **" <line_number>gg "** = Will move cursor to line
- **" dd "** = deletes the line the cursor is on
- **" u "** = Undo
## Emacs
Creates file if doesn't exist if you save (same as Vim)
Does not use 'modes' like vim, has GAMES

**Note:**_Commands here are prefixed by the control key or meta (alt/option) key

When you start emacs, you can start typing right away!
```bash
$  emacs <file_name>
```
_**Keys:**_
_**Ctrl + :**_
- **" h "** = Bring up help page
- **" x + s "** = Save a file
- **" x + c "** = Exit emacs
- **" _ "** = Undo changes
- **" e "** = Moves cursor to the end of the line
- **" a "** = Moves cursor to the beginning of line

- **" :q "** = To quit
- **" :q! "** = To quit without saving
- **" :wq  "** = Write and quit

_**meta_key (option/alt) + :**_
-  **" f ", " b "** = forwards, backwards by one word
- **" a ", " e "** = Move to the start, end of the sentence

_**esc + :**_
-  **" > ", " < "** = Move to end, start of file

## Nano
```bash
$  nano <file_name>
```
Commands for Nano are at the bottom, those are all!, just press crtl and the key

# Aliasing
Aliasing is a powerful tool to create shortcuts for bash

This creates an alias so that when we type "shortcut_name" in bash, <full_command> will run
```bash
$  alias <shortcut_name>=<full_command>
```
To remove an alias we use:
```bash
$  unalias <shortcut_name>
```

# Intro to Bash Scripting
You can write scripts to run commands. These can take input!

To run the scripts you type:
```bash
$  bash <script_name.sh>
```
