# "D" is for Decryption

## Description
Now that you know the correct RSA decryption value `d` from "D" is for Dumb Mistakes, can you use it to properly decrypt one of DEADFACE's private messages? The ciphertext that De Monne's security team intercepted was:

`992478-1726930-1622358-1635603-1385290`

Assuming each - character separates each letter of the ciphertext and every letter in the alphabet is represented by its position (i.e., a = 1, b = 2, etc.), what is the plaintext version of this message? Submit the flag as `flag{plaintext}`.

## Solution
This solution will feed off of the solution for `"D" is for Dumb Mistakes`.

To solve this we will again use a python script taking as input the value of `d` and `n`. The value of `n` being equal to `p*q` from the `"D" is for Dumb Mistakes` challenge.

The formula to decrypt a message in `RSA` is message = encryption<sup>d</sup> (mod n)

To solve this we will decrypte each letter one at a time from the message and then convert the integer value to an alphabetic character. To do this we will use the following script taking the `d` and `n` value as command line arguments.

The calculations on each encrypted character can take some time so allow a minute for the script to finish executing.

```Python3
#!/usr/bin/python3
# rsa.py

import sys

if len(sys.argv) != 3:
	print("Usage: <script.py> dValue nValue")
	quit()
	
d = sys.argv[1]
n = sys.argv[2]

alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']

decrypted_ascii = [(x**d) % n for x in [992478,1726930,1622358,1635603,1385290]]

decrypted_text = ''.join(alphabet[x-1] for x in decrypted_ascii)

print(decrypted_text)
```

Looking at the output of the program we get the value `ghost`

`flag{ghost}`
