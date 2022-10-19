# Bandit Level 2 -> 3

## Description
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

### Commands you may need to solve this level
ls, cd, cat, file, du, find

### Helpful Reading Material
Google Search for "spaces in filname"

## Solution
```
$ ssh bandit2@bandit.labs.overthewire.org -p 2220
'''
bandit2@bandit.labs.overthewire.org's password: <bandit2 password>
'''

bandit2@bandit:~$ cat "spaces in this filename"
<bandit3 password>
```
