# CS 199
## bash (Bourne Again SHell) 
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

- **ls :**  Lists all the files in the current directory

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

- **pwd:**  Print Working Directory, prints out the path of the current directory
```bash
~/Desktop/cats1 $ pwd
/c/Users/me/Desktop/cats1
 ```

- **clear:** clears commands from screen

This is moments after using the clear command

```
~/Desktop/cats1 $
``` 

- **cd:** Change directory, basically your way of travelling the maze that are your files.


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

- **cat:**  Concatenate, display contents of a file
_Note: Will print out meta-data for images_
```bash
$ cat <fileName>
```
```bash
~/Desktop/cats1 $ cat .secretCats.txt
Secret, shhh!
```
- **touch:** Creates file in current directory
_Note: You can create files without extension_
```bash
$ touch <fileNane>.<fileExtension>
```
```bash
~/Desktop/cats1 $ touch catDestroyer.md
~/Desktop/cats1 $ ls
catDestroyer.md cats2/ cats4/
```

- **rm:** Remove, deletes files **_does NOT put them in the trash, SCaaAARy!!_**
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
- **mkdir:** Make empty directory

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

- **rmdir :** Remove Directory
_Note: will only delete an **empty** directory. Refer to rm for deleting directories and it's contents_

```bash
$ rmdir <directory_to_remove>
```
- **mv :** Move. Serves two purposes:
	When _**renaming**_ the original file will get deleted once it gets moved to the new file.
_Note: Renaming to an already used name will overwrite the file with that name (aka, it get's deleted!! Make sure your name is unique!_
```bash
$ mv <directory_to_rename> <new_file_name>
```
When _**moving a file to a new location**_ specify the files (can be more than one) and the location (directory)
```bash
$ mv <file1> <file2> <file...> <directory_to_move>
```
- **cp :** Copy a file into a new location, does not delete original.
```bash
$ mv <file1> <directory_to_copy_to>
```
- **man :** Manual. When google isn't an option. Opens up the manual for a specific command (ex: ls, mv, man man??!!).
```bash
$ man <some_command>
```
## Piping to files (WIP):




_notes mainly for me: leave vim press-> escape ":" and !q or something like that
For vim, there are two modes: Insert and commands (not sure if those are the actual names, but that's what I call them)
To exit vim, you must be in command mode. To do so, press escape.
To enter any commands in command mode, press ":" and then the command.
Quit is "q". If there are unsaved changes, you can quit without changes using "!" after "q"
To save changes is "w".
You can also combine commands, such as ":wq" to save and exit._
