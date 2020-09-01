# CS 199
## bash pt.2 
[**Youtube Video**](https://www.youtube.com/watch?v=KQWygP2JSsM)

## Tips in Bash (again):
- **tab :** tries to auto-complete what you are typing
- **Ctrl-C :** ends the current program; keep a note of this one.
- **!! :** Runs/brings up previous command entered, hope it's not _rm_ :(

## Commands:
/cats1/ directory has /cats2/cats3/12coolfile.txt and cats4/ directories inside it. What you type is after the "$"

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
- **:**
```bash
$  <>
```

- **:**
```bash
$  <>
```