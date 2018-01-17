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
