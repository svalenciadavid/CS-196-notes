# bash (Bourne Again SHell) 
[**Slides (contains setup instructions)**](https://docs.google.com/presentation/d/1iuELVwGU6MBl9vpwHtxOs0x__NFibD2vYLL9QNNc1vw/edit#slide=id.g7cf61f9430_0_48) 

[**Youtube Video**](https://www.youtube.com/watch?v=J1fCBAW9V5g)

## Keywords:
- **Commands:** Commands are unique statements that indicate specific tasks

- **Arguments:** Variables/inputs needed to complete commands (some commands need more than one argument)

- **Flags:** Come at the end of a command, found in 'man' pages. Pretty much do extra behavior.

- **Directory:** The same thing as a folder in your computer
## Tips in Bash:
- **tab :** tries to auto-complete what you are typing
- **Ctrl-C :** ends the current program; keep a note of this one.
- **!! :** Runs/brings up previous command entered, hope it's not _rm_ :(

## Commands:
/cats1/ directory has /cats2/cats3/ and cats4/ directories inside it. What you type is after the "$"

### ls  
 Lists all the files in the current directory

By itself it will just print all files in current directory
```bash
~/Desktop/cats1 $ ls
cats2/ cats4/
```
With the option -a you can see hidden files (they start with " . " ) 
_Note:_ ./ and  . ./ refers to the outside directories (aka the desktop in this case, where cats1 folder is located
```bash
~/Desktop/cats1 $ ls -a
./ ../ .secretCats.txt cats2/ cats4/
```
You can even see files in directories you aren't even at with:
```bash
$ ls <file-path>
```
```bash
~/Desktop/cats1 $ ls cats2/
cats3/

```

### pwd 
Print Working Directory, prints out the path of the current directory
```bash
~/Desktop/cats1 $ pwd
/c/Users/me/Desktop/cats1
 ```

### clear
 clears commands from screen

This is moments after using the clear command

```
~/Desktop/cats1 $
``` 

### cd 
Change directory, basically your way of travelling the maze that are your files.


```bash
~/Desktop/cats1 $ cd <file-path>
```
Pay attention to what's before the "$" (current location)
```bash
~/Desktop/cats1 $ cd ..

~/Desktop $ cd cats1/cats2/

~/Desktop/cats1/cats2 $ cd ..

~/Desktop/cats1 $


```

### cat  
Concatenate, display contents of a file
_Note: Will print out meta-data for images_
```bash
$ cat <fileName>
```
```bash
~/Desktop/cats1 $ cat .secretCats.txt
Secret, shhh!
```
### touch 
Creates file in current directory
_Note: You can create files without extension_
```bash
$ touch <fileNane>.<fileExtension>
```
```bash
~/Desktop/cats1 $ touch catDestroyer.md
~/Desktop/cats1 $ ls
catDestroyer.md cats2/ cats4/
```

### rm 
Remove, deletes files **_does NOT put them in the trash, SCaaAARy!!_**
```bash
$ rm <file-you-want-to-delete>
```
```bash
~/Desktop/cats1 $ ls
catDestroyer.md cats2/ cats4/

~/Desktop/cats1 $ rm catDestroyer.md
~/Desktop/cats1 $ ls 
cats2/ cats4/
```
Using the "-rf" flag allows us to delete directories, as well as everything inside of them. Ultimate purge, try to avoid.
```bash
~/Desktop/cats1 $ ls
cats2/ cats4/

~/Desktop/cats1 $ rm -rf cats2/
~/Desktop/cats1 $ ls 
cats4/
```
### mkdir 
Make empty directory

```bash
$ mkdir <directoryName>
```
```bash
~/Desktop/cats1 $ ls
cats4/

~/Desktop/cats1 $ mkdir cats2/
~/Desktop/cats1 $ mkdir cats2/cats3
~/Desktop/cats1 $ ls
cats/2 cats4/

~/Desktop/cats1 $ ls cats/2
cats3/
```

### rmdir
Remove Directory
_Note: will only delete an **empty** directory. Refer to rm for deleting directories and it's contents_

```bash
$ rmdir <directory_to_remove>
```
### mv
Move. Serves two purposes:
	When _**renaming**_ the original file will get deleted once it gets moved to the new file.
_Note: Renaming to an already used name will overwrite the file with that name (aka, it get's deleted!! Make sure your name is unique!_
```bash
$ mv <directory_to_rename> <new_file_name>
```
When _**moving a file to a new location**_ specify the files (can be more than one) and the location (directory)
```bash
$ mv <file1> <file2> <file...> <directory_to_move>
```
### cp  
Copy a file into a new location, does not delete original.
```bash
$ mv <file1> <directory_to_copy_to>
```
### man
 Manual. When google isn't an option. Opens up the manual for a specific command (ex: ls, mv, man man??!!).
```bash
$ man <some_command>
```
## Piping to files (WIP):
Piping redirects output from command line, to a file you specify. With both characters typed after the command, ">" creates a new file and ">>" appends to an already existing file (creates a new one if none exist) 
```bash
$ ls >> <file_name>
```
# bash pt.2 
[**Slides**](https://docs.google.com/presentation/d/1g-CW-oYopvPaRq-3YrcGIRgdjd9GFtEfQ-9nNzMyH-8/edit) 

[**Youtube Video**](https://www.youtube.com/watch?v=KQWygP2JSsM)

## Commands:
/cats1/ directory has /cats2/cats3/12coolfile.txt /cats2/cats3/dogscool.txt and cats4/ directories inside it. What you type is after the "$"

### sudo 
 Gives user root privileges (admin rights), typed before command. Makes command be run as what's called a "super user"

After typing it, you will be prompted to type password (don't be alarmed if you don't see your password being typed out, it's normal, just type it and press enter once you're done.
```bash
$ sudo <some_command>
```
### echo
 Allows you to print into bash. This is useful when chaining longer commands to debug what went wrong.

This command will print out whatever "some_string" is.
```bash
$ echo <some_string>
```

### find
A tool for locating files (is Amazing). This command will print out everything in the path specified, that is, files and everything inside directories in that path.

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
### grep
Global Regular Expression Print, used to find all text instances in a specified file (will return lines where text was found)
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
### diff
Will compare two files line by line, and then identify the lines where they differ
```bash
$  diff <file1> <file2>
```
## Logical Operators
Extra features, can chain them!

### &&
Let's you do several commands sequentially all in one line as long as all preceding commands complete successfully 
```bash
$  <command1> && <command2> && <command...>
```

### | |
 will try the first command and if the first command fails, will do the command after the operator 
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

### Keys:
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
### Keys:
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
You can write scripts to run commands. These can take input! (note that bash files have extension " .sh "

To run the scripts you type:
```bash
$  bash <script_name.sh>
```
## Bash script programming
[cheat sheet](https://devhints.io/bash)

**_Note:_** From this point on, I will explain the programming language basics for bash scripting, that is, everything coming up is what you would write in the .sh file

### Variables
You don't need to declare type for variables, to use a variable use " $ " before you type your variable name

This example should declare secret_var and then run the echo command with the value of that variable. All of these accomplish the same thing.
```bash
secret_var="example1"
echo $secret_var
echo "$secret_var"
echo "${secret_var}"
```
### Conditionals
if, else, elif statements.

**_Note:_** You need spaces between the condition and the bracket.
```bash
if [[ <condition> ]]; then
	<do something>
elif [[ <condition> ]]; then
	<do something>
else 
	<do something>
fi
```

Because if statements are so closely related, we will talk about **Operators:**

* **" -eq " :** is an equals operator for _numerical_ comparisons

* **" -ne " :** is a not equals operator for _numerical_ comparisons
 
* **" == " :**  is an equals operator for _string_ comparisons

* **" != " :** is a not equals operator for _string_ comparisons

### Loops
for loop will iterate from i = 1 to i = 10
```bash
for i in {1..10}; do
	echo $i
done
```
This one has steps, sort of like range in Python
```bash
for i in {5..50..5}; do
    echo "Welcome $i"
done
```
Here are C-like for loops
```bash
for ((i = 0 ; i < 100 ; i++)); do
  echo $i
done
```
### Functions

```bash
<function-name>() {
    <stuff it does>
}
<function-name> <value-to-pass> <value-to-pass...>
```
This is an alternative syntax, is an example with a function declaration, and function call
```bash
function myfunc() {
    echo "hello"
}
myfunc
```
Now, when you pass values into a function, they get saved as " $1 ",  " $2 " and so on, so:
```bash
myfunc() {
    echo "Hi $1, it's $2 outside eh?"
}
myfunc "Jenny" "cold"
```
Will print out "Hi Jenny, it's cold outside eh?"

Note how there was no need to specify how many variables our function asked for when we declared it
Make sure you call the function after declaring it, otherwise it won't run!
