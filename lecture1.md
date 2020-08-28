# CS 199
## bash (Bourne Again SHell) 
[**Slides (contains setup instructions)**](https://docs.google.com/presentation/d/1iuELVwGU6MBl9vpwHtxOs0x__NFibD2vYLL9QNNc1vw/edit#slide=id.g7cf61f9430_0_48) 
### Keywords:
**Commands:** Commands are unique statements that indicate specific tasks
**Arguments:** Variables/inputs needed to complete commands (some commands need more than one argument)
**Flags:** Come at the end of a command, found in 'man' pages. Pretty much do extra behavior.
**Directory:** The same thing as a folder in your computer

## Commands:
/cats1/ directory has /cats2/cats3/ and cats4/ directories inside it. What you type is after the "$"

- **ls :**  Lists all the files in the current directory

By itself it will just print all files in current directory
```bash
~/Desktop/cats1 $ ls
cats2/ cats/4
```
With the option -a you can see hidden files (they start with " . " ) 
_Note:_ ./ and  . ./ refers to the outside directories (aka the desktop in this case, where cats1 folder is located
```bash
~/Desktop/cats1 $ ls -a
./ ../ .secretCats.txt cats2/ cats/4
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
_Note:_ Will print out metadata for images
```bash
$ cat <fileName>
```
```bash
~/Desktop/cats1 $ cat .secretCats.txt
Secret, shhh!
```
- **touch:** Creates file in current directory
_Note:_ You can create files without extension
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
notes mainly for me: leave vim press-> escape ":" and !q or something like that
