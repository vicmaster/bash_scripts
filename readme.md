```
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts
$ ./tn test
Hello, World!
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts
$ ls
tn
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts
$ ./tn test
Hello, World!
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts
$ ls
notes.txt tn
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts
$ cat notes.txt
Tue Jan 16 01:28:22 CST 2018 : test
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts
$ ./tn working
Hello, World!
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts
$ cat notes.txt
Tue Jan 16 01:28:22 CST 2018 : test
Tue Jan 16 01:28:36 CST 2018 : working
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts
$ ls
notes.txt tn
```

Let's put a confirmation for user:

```
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ ./tn hello
Hello, World!
Note saved: hello
```

How to check if your bash script name is not reserved by bash:

```

# Use type

$ type test
test is a shell builtin
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ type cp
cp is /bin/cp
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ type foo
-bash: type: foo: not found
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ type bar
-bash: type: bar: not found
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
```

Recap:

```
Shell Script

- A file containing commands
- Executed by your shell

Naming your scripts

Don’t forget to set permissions

- chmod u+w

Shebang
 
- First line
- #!/bin/bash

Use comments

- Comments start with #

Add script to your PATH

- ./tn
- /home/zazvick/tn
- Tip: make a bin folder in your home
- PATH=“$PATH:~/bin”

Or call it with a full pathname

```

### Variables

* Variables
  - Create
  - Assign value
  - Use value

* Variable Names

* Good habits when using variables

```
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ greeting="hello"
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ $greeting
-bash: hello: command not found
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ echo $greeting
hello
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ filename="somefile.txt"
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ touch $filename
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ ls
notes.txt    readme.md    somefile.txt tn
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ files="file1 file2"
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ touch $files
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ ls -l files
ls: files: No such file or directory
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ ls -l $files
-rw-r--r--  1 zazvick  staff  0 Jan 16 23:49 file1
-rw-r--r--  1 zazvick  staff  0 Jan 16 23:49 file2
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ echo $greeting, $USER
hello, zazvick
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ echo $greeting, $user
hello,
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ usergreeting="$greeting, $USER"
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ echo $usergreeting
hello, zazvick
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ x = 5
-bash: x: command not found
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ x=5
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ $x
-bash: 5: command not found
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
$ echo $x
5
Victors-MacBook-Pro-2@zazvick: ~/Projects/personal/training/bash-scripts (master)
```
