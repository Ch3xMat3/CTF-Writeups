# Bandit Level 5 -> 6

## Description
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not exeutable
  
### Commands you may need to solve this level
ls, cd, cat, file, du, find

## Solution
```
ssh bandit5@bandit.labs.overthewire.org -p 2220
'''
bandit5@bandit.labs.overthewire.org's password: <bandit5 password>
'''

bandit5@bandit:~$ find inhere/ -type f -size 1033c ! -executable
inhere/maybehere07/.file2
bandit5@bandit:~$ cat inhere/maybehere07/.file2
<bandit6 password>
```
