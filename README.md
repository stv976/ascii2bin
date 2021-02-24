# ascii2bin

### COMP 122: Converting ASCII digits to a number.


# Purpose
Now that you have one programming assignment within C, coupled with the use of make and git, you are to write another program to reinforce your knowledge.  This program will also validate and exercise your knowledge of the ASCII encoding for digits ('0' - '9'), binary uncoding of unsigned integers, and the algorthm to convert ASCII digits to an unsigned value.

# Assignment
Your task is to develop a C program, called ascii2bin, that
  * reads a string of ASCII binary digits, and 
  * outputs the equivalent decimal number 

For each input string your program must
  1. exercises the read() system call to read a single byte at a time from stdin
  1. validate that the read byte is appropriate for conversion, e.g., it must be either an ASCII '0' or '1'
  1. converts each byte into an integer value via a mathematical expression
  1. uses the resulting integer as part of the calcuation to determine the final number
  1. identifies the end of a input string by either end of file or by a new line.
      *  End of file is detected when read() returns the value '0'
      *  A new line is identified in the ASCII table as either: newline, nl, LF, or \n'
  3. prints this final number on stdout
  4. returns a value of 0 upon success and 1 otherwise


### The Algorithm
```
    offset = ?;
    number = 0;
    
    retval = read(0, &ascii_value, 1);
    while (retval == 1)
        digit = ascii_value - offset;
        number = number << 1 + digit;  // same thing as: number = number * 2 + digit; 
        retval = read(0, &ascii_value, 1);
        
    printf("%d\n", number);
    return 0;
```

### Validation Checks:
1. Each ASCII input character is one of the following characters: '0', '1', or '\n'
1. The calculated number does not exceed 2^32

### Developement Process
Some of you have some expertise in devoping your code on your home computer---great.  You can continue to develop your code in this way, using your favorite editory.  During this develop process, you need to continue to integrate git into your process.  


#### Getting Started
  * Fork this github reposity to create your own repository for your project.  Do this via the github GUI.
  * Clone the repo onto your development computer:  $ git clone $URL
  * Change your working directory to where you code is located:  $ cd ascii2bin
  * Create your first version of you ascii2bin.c file: $ touch ascii2bin.c
  * Run the make command to build anything the Professor is providing you: $ make
  * Introduce ascii2bin.c to your local repo: $ git add ascii2bin.c
  * Commit ascii2bin.c to your local repo:  $ git commit -m 'Initial version' ascii2bin.c

To recap:
```
git clone https://github.com/COMP122/ascii2bin.git    # for example
cd ascii2bin
touch ascii2bin
make
git add ascii2bin.c
git commit -m 'Initial version' ascii2bin.c
```

  * Now create a copy on the ssh.sandbox.csun.edu server
```
$ ssh ssh.sandbox.csun.edu
$ mkdir -p comp122 ; cd comp122              # Optional: create a subdirectory for comp122
$ git clone $URL                             # Clone your repo
$ cd ascii2bin                               # Change to the correct working directory
$ ls                                         # Review that you have all the files from the repo
$ exit
```

#### Continuing to develop your code on your laptop or on ssh.sandbox.csun.edu

* REPEAT
    * REPEAT
      1. update your ascii2bin.c program
      1. recompile the code to validate it compiles correctly, etc.
      1. perform some test case
    * UNTIL you are satisfied 
    * commit your changes to your local git repo
    ```
       $ git status
       $ git add ascii2bin.c
       $ git commit -m 'Revised Message'
    ```
    * if your code is good enough to share, push it to your remote repo
    ```
      $ git push
    ```
    * take a break
* UNTIL complete


### Final Validate and Submission
To obtain credit for this assignment, you must ensure your program works correctly on ssh.sandbox.csun.edu.  This server is shared resource in which you can finalize you work and the professor can validate this work.  The final steps for validation are as follows:

* Update repo on ssh.sandbox.csun.edu
```
$ ssh ssh.sandbox.csun.edu
$ cd comp122/ascii2bin
$ git pull
$ make    
```

* Test your program:
```
$ script ascii2bin.typescript 
$ ascii2bin
0101
^d
5
$ cat 54356.txt  | ascii2bin
54356
$ cat 138.txt | ascii2bin
138
$ cat 2863311530.txt | asciibin
2863311530
$ cat 4294967295.txt | asciibin
4294967295
$ exit
```
* Copy the typescript file from the server
```
$ scp  ssh.sandbox.csun.edu:comp122/ascii2bin/ascii2bin.typescript .
```

### Submission
* Submit your assignent to Canvas with the following information:
  * The URL to your github repo
  * The checksum.typescript file

