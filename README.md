# ascii2binary

### COMP 122: Converting ASCII digits to a binary number.


# Purpose
Now that you have one programming assignment within C, coupled with the use of Make and git, you are to write another program to reinforce your knowledge.  This program will also validate and exercise your knowledge of the ASCII encoding for digits ('0' - '9'), binary uncoding of unsigned integers, and the algorthm to convert ASCII digits to an unsigned value.

# Assignment
Your tasks is to develop a C program that
  * reads a string of ASCII binary digits, and 
  * outputs the equivalent decimal number 

For each input string your program must
  1. exercises the read() system call to read a single byte at a time from stdin
  1. validate that the read byte is appropriate for conversion, e.g., it must be either an ASCII '0' or '1'
  1. converts each byte into an integer value via a mathematical expression
  1. uses the resulting integer as part of the calcuation to determine the final number
  1. identifies the end of a input string by either end of file or by a new line.
      1.  End of file is detected when read() returns the value '0'
      2.  A new line is identified in the ASCII table as either: newline, nl, LF, or \n'
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

### Starter Code:
Pull the starter code from you last C program.

### Final Validate and Submission
To obtain credit for this assignment, you must ensure your program works correctly on ssh.sandbox.csun.edu.  This server is shared resource in which you can finalize you work and the professor can validate this work.  The final steps for validation are as follows:

* Clone your github repo onto ssh.sandbox.csun.edu
```
$ ssh ssh.sandbox.csun.edu
$ mkdir -p comp122 ; cd comp122              # Optional: create a subdirectory for comp122
$ git clone $URL                             # Clone your repo
$ cd ascii2binary                            # Change to the correct working directory
$ make                                       # Use the make command to build all necessary software components 
```

* Test your program:
```
$ script ascii2bin.typescript 
$ ascii2bin
0101
^d
5
$ cat 65.txt  | ascii2bin
54356
$ cat 138.txt | ascii2bin
138
$ cat 2863311530.txt | ascibin
2863311530
$ cat 4294967295.txt | asciibin
4294967295
$ exit
```

* Submit your assignent to Canvas with the following information:
1. The URL to your github repo
1. The checksum.typescript file

