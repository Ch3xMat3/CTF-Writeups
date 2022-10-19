# Bandit Level 3 -> 4

## Description
The password for the next level is stored in a hidden fie in the inhere directory

### Commands you may need to solve this level
ls, cd, cat, file, du, find

## Solution
```
$ ssh bandit3@bandit.labs.overthewire.org -p 2220
'''
bandit3@bandit.labs.overthewire.org's password: <bandit3 password>
'''

bandit3@bandit:~$ ls -al inhere/
total 12
drwxr-xr-x 2 root     root    4096 Sep  1 06:30 .
drwxr-xr-x 3 root     root    4096 Sep  1 06:30 ..
-rw-r----- 1 bandit4  bandit3   33 Sep  1 06:30 .hidden
bandit3@bandit:~$ cat inhere/.hidden
<bandit4 password>
```
