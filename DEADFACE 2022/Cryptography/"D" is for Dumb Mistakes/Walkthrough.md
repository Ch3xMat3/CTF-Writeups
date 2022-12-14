# "D" is for Dumb Mistakes

## Description
To show off their 1337 programming skills, DEADFACE attempted to create their own encryption process to help them communicate privately. Although the encryption process is working, the decryption process is flawed. The De Monne security team was able to find DEADFACE's code and can see that they are trying to use the RSA algorith with these variables:

* Prime numbers of `1049` and `2063`
* Exponent of `777887`

Recompute the decryption key (`d`) and submit the flag as `flag{d=value}`

## Solution
The challenge here is to figure out the decryption key of RSA with the provided knowledge. A little research into RSA we can find the formula for d to be 
`ed mod φ(n) = 1`

`φ(n)` (also known as phi) is calculated by using p and q with the following formula `φ(n) = (p-1)(q-1)`

In older versions of python you had to create your own functions for finding gcd values and looking for the correct value for d such that the forumla equaled 1. A new python function was released in Python version 3.8 that performs this for you as long as you know the value of `e` and `φ(n)`.

The python function `pow()` performs the mod inverse functionality to calculate `d` taking the paramters `e`, `-1`, and `φ(n)` as such `pow(e, -1, φ(n))`

This can easily be done in a python terminal by executing python3 from a linux terminal. For use in future challenges we will create a script that takes in the paramters `p`, `q`, and `e` and return the value of d.

```Python3
#!/usr/bin/python3
# rsa-d.py

import sys

if len(sys.argv) != 4:
  print("Usage: <script.py> pValue qValue eValue")
  quit()

p = int(sys.argv[1])
q = int(sys.argv[2])
e = int(sys.argv[3])
phi = (p-1)*(q-1)

print("d=" + str(pow(e, -1, phi)))
```

Calling our new script as follows produces the value of `d`

`python3 rsa-d.py 1049 2063 777887`

`d=1457215`

Flag = `flag{d=1457215}`
