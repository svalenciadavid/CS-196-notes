# APIs, Libraries, Frameworks
[**Slides **](https://docs.google.com/presentation/d/1dz0HmHO0maUW4qAp42FDtBHeWXw-ROF-cAxLGmkXAHA/edit#slide=id.g80fd5b557d_0_231) 

[**Youtube Video **](https://www.youtube.com/watch?v=31UYJXGzfdQ&feature=youtu.be)

As programmers we use libraries and APIs to make our work easier. If someone has already done it, why not use what they made?
## Libraries
Libraries provide a set of helper functions/objects/modules for your code to call

**_Notes:_** If you want good libraries, google for them, check git stars, check documentation(example code), README, check support (look at the issues tab, are people getting the help they need?). 

### Language:
* **Module:** A file with a .py extension
* **Package:** a directory containing an \_\_init\_\_.py file
* **Build in module:** A module natively installed with Python
* **Object:** anything inside a module/package that can be referenced like a class or function or variable

To import an entire module/package you use:
```python
import <module/package>
# Example:
import math
```
If you only need to use a small portion of it use:
```python
from <module/package> import <stuff you're-using>, <stuff>, <stuff>
# Example:
from math import gcd, factorial
```
You can also change the names of the functions/rename what's being imported:
```python
from <module/package> import <stuff you're-using> as <rename-here>
# Example:
from math import factorial as <fact>
print(fact(10))
# Output prints out 10!
```
**What about third party ones?**
we need a package manager for that because people use libraries to build their libraries, we create then dependency graphs.
Python's package manager is **Pip**
(Rust-> Cargo, JS-> NMP, Java-> Maven)

In bash we type:
```bash
$ pip install <package-name>
```
If we need a lot of packages we create a requirements.txt
```
Mako==1.1.1
MarkupSafe==1.1.1
six==1.14.8
```
```bash
$ pip install -r requirements.txt
```


## Frameworks
 Frameworks are more like skeletons to build on, either open or unimplemented functions that the user implements for their custom app.
 **ex:** Web frameworks like Django


## APIs
Application programming interface

We don't reinvent the wheel, we use what other services have already been created, such as google maps for maps..etc

We communicate from client to server through HTTP(Hyper Transfer Protocol) 
The data gets represented in:
#### JSON- Javascript Object Notation
#### XML- Extensible Markup Language (older)

**Some** of these requests we can make are:

### GET
Gets request data from a specified source 
Gets should never be used to deal with sensitive data, they are only used to request data, not modify.
```python
GET <url><query_string>
```
### POST
POST are used to send data to a server to create or update records
Data sent to a server via POST is stored in the body of the HTTPS request
POST is a little safer than GET
```python
GET <url><query_string>
```

To make these calls we will use a HTTP client (psf)