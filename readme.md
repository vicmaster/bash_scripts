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

* Used to store data by name
* To create: just assign a value
  - x=10
  - If x already existed, it is assigned the new value
  - filenames="notes.txt picture.jpg movie.mov"
  - Values containing spaces: use quotes
  - Don't use white space around =
* To get the value
  - Prefix with $
  - echo $x
* Bash variables have no type
  - Basically just store a string
* Names:
  - Only letters, numbers, and underscore are allowed
  - First character should be a letter or an underscore
  - Variable names are case-sensitive

* Upercase variables:
 - Bash has many pre-defined variables
 - PATH, HOME, SECONDS, IFS, etc.
 - You don't want to override them by mistake

* Good Habit:
 - Use lowercase names for your variables

* Good habit: surround your variables with quotes
 - Use "$x" instead of $x
 - Prevent surprises when it contains spaces
 - User double quotes: keep meaning of dollar sign intact

* Braces
 - Where does your variable name end?
 - echo "${foo}bar"
 - prints value of var "foo" followed by string "bar"
 echo "$foobar" prints value of "foobar"
 - Using braces a lot is a Good Habit

* Another good habit
 - use $HOME instead of ~

* read
 - Reads a line of input into variable
 - read var
 - Is a shell builtin
 - "help read"
 - "man builtins"
 - read -p "Type your name:" name

 * Debugging

  - user -x
  - set -x : set options to bash
  - set + x

* Summary
 - Variables
   - Assign value
   - Get value ($)
   - No whitespace around=
* Variables
  - Quotes
  - Braces
* Reading input
  - read
* Debugging
  - Use -x option in hashbang line
  - Or use "set-x" to enable and "set +x" to disable


