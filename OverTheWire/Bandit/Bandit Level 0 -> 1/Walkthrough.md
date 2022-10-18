# Bandit Level 0 -> 1

## Description
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

### Commands you may need to solve this level
ls, cd, cat, file, du, find

## Solution
```
$ ssh bandit0@bandit.labs.overthewire -p 2220
....
bandit0@bandit.labs.overthewire.org's password: <bandit0 password>
''''

bandit0@bandit:~$ cat readme
<bandit1 password>
```
