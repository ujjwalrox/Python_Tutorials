# Part 2: Python OS Module (import os)

Part 1: [Python OS Module: Part 1](os_module_1.md) 

## os.walk()
 OS.walk() generate the file names in a directory tree by walking the tree either top-down or bottom-up.
 For each directory in the tree rooted at directory top (including top itself),
 it yields a 3-tuple (dirpath, dirnames, filenames).

* root : Prints out directories only from what you specified.
* dirs : Prints out sub-directories from root.
* files : Prints out all files from root and directories.

```
for dirpath, dirnames, filenames in os.walk('dir1'):
    print("Current Path: ", dirpath)
    print("directories: ", dirnames)
    print("files: ", filenames)
    print()
```


## Environment Variable:

 Environment variables are global system variables accessible by all the processes running under the Operating System (OS).
 Environment variables are useful to store system-wide values such as the directories to search for the executable programs ( PATH ) and the OS version.
```
print(os.environ.get('HOME')) # Get value of environment variable 'HOME'
```

## os.path:
 This module contains some useful functions on pathnames.
 The path parameters are either strings or bytes.
 These functions here are used for different purposes such as merging, normalizing and retrieving path names in python.
 All of these functions accept either only bytes or only string objects as their parameters (Path objects also from python 3.6).
 The result is an object of the same type, if a path or file name is returned.
 As there are different versions of operating system so there are several versions of this module.
 
 os.path.join() is used to join two path without caring about which operating system is executing it.

```
home_path = os.environ.get('HOME')
file_path = os.path.join(home_path, 'test_file.txt')
print(file_path)
```
## Some other os.path functions:

```

print(os.path.basename('/tmp/test.txt'))  # output: 'test.txt'
print(os.path.dirname('/tmp/test.txt'))  # output: 'tmp'
print(os.path.split('/tmp/test.txt'))  # output: ('/tmp', 'test.txt')


print(os.path.exists('/tmp/test.txt'))  # Checks if a path exists or not.
print(os.path.isdir('/tmp'))  # checks if given path is a directory
print(os.path.isfile('test.txt'))  # checks if given path is a file

print(os.path.splitext('/tmp/test.txt'))  # output: ('/tmp/test', '.txt')
```

### Further Study: [pathlib module: Object-oriented filesystem paths](https://docs.python.org/3/library/pathlib.html)
