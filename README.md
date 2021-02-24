# ascii2binary

### COMP 122:  Converting ASCII digits to a binary number.


# Purpose

# Learning Objective

# Assignment

### The Algorithm
```
    1. offset = 0x30;
    1. number = 0;
    retval = read(0, &ascii_value, 1);
    while (retval == 1)
    digit = ascii_value - offset;
    number = number << 1 + digit;  // same thing as: number = number * 2 + digit; 
    retval = read(0, &ascii_value, 1);
    printf("%d\n", number);
    return 0;
```

### Minimum Validation Checks:

### Starter Code:
### Testing:

```
$ scp checksum.java ssh.sandbox.csun.edu:    # Secure copy your program to the ssh.sandbox.csun.edu server.
$ scp 156.txt ssh.sandbox.csun.edu:          # Secure copy the 156 test case to the ssh.sandbox.csun.edu server.
$ ssh ssh.sandbox.csun.edu                   # Log into the ssh.sandbox.csun.edu server
$ javac checksum.java                        # Compile your checksum program
```


### Submission:
1. The checksum.java source code
1. The checksum.typescript file
