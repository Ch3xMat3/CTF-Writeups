# Bandit Level 4 -> 5

## Description
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the "reset" command.

### Commands you may need to solve this level
ls, cd, cat, file, du, find

## Solution
```
$ ssh bandit4@bandit.labs.overthewire.org -p 2220
'''
bandit4@bandit.labs.overthewire.org's password: <bandit4 password>
'''

bandit4@bandit:~$ file inhere/*
inhere/-file00: OpenPGP Public Key
inhere/-file01: data
inhere/-file02: data
inhere/-file03: data
inhere/-file04: data
inhere/-file05: data
inhere/-file06: data
inhere/-file07: ASCII text
inhere/-file08: data
inhere/-file09: data
bandit4@bandit:~$ cat inhere/-file07 
<bandit5 password>
```
