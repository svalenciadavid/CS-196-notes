# Regex
A **regular expression** is a sequence of characters that define a search pattern.

Tl:dr; they allow you to define a **pattern** to **match** in text.

You can use [regexpal.com](www.regexpal.com) to practice using regex. 

## Cheat Sheet
1. abcdef... are letters
2. 0123456... are numbers
3. \d is any digit
4. \D any non digit (any uppercase metacharacter is always the inverse of the lowercase counterpart)
5. . matches anything
6. \ is used to escape
7. \[a-z] \[0-9] defines a set or range of acceptable characters
8. \[^] anything except for these characters
9. {m} repeat the previous character
10. {m,n} m to n repetitions
11. \+ , one or more
12. \* , zero or more
13. ? optionality, one or none.
14. (...) capture group
15. (..(...)) capture subgroup
16. (x|y) logical OR

## Examples
Demo Text:
``` Hello, CS196 @ Illinois
This is the honors add-on to CS125: Introduction to Computer Science!

We Hope you enjoy our class and wish you the best of luck in future classes such as CS173, CS225, CS233, CS241, CS374 and beyond. 
```
1. Parse all the CS courses:  
```
'CS\d\d\d'
```
C followed by S followed by any digit, any digit, any digit.
2. Parse all things that come before a comma:
```
.....,
```
3. Regex for a phone number   
either 123-456-7890   
or 123.4556.7890
```
\d\d\d[-.]\d\d\d[-.]\d\d\d
```
4. Anything but CS courses!
```
[^CS]
```
5. Only 200, 300 or 400 lvl classes
```
CS[2-4]\d\d
```
6. Back to digits. 
Use brackets for repeating patterns.
```
\d{3}[-.]\d\{3}[-.]\d\{4}
```
7. Repeating Letters
Example text:
```
hy! hey! heeeeey! heeeeeeeeeeeeey!!!
```
Match one with 5 heys ``h+e{5}+y!``   

8. Phone numbers improved   
what if it is formatted like this? (123)-456-7890 or (123).456.7890
```
\(?\d{3}\)?[-.]\d\{3}[-.]\d\{4}
```
9. Repeating stuff
Sample Text
```
123 abc123 abcabc123 abcabcabc123
```
Use parenthesis! `` (abc)+123``
