# RansomeWAR 1 - Let's HASH This Out, Fellas

## Description
RansomWAR 1 Challenge 1 - Obtain the SHA512 hash of the DarkAngel Encryptor program (Windows version). Enter the flag as the first eight hex digits, a colon (":"), and the last eight digits of the SHA512 hash, in lower case, as follows:

`flag{aabbccdd:eeff0011}`

## Solution
For this challenge all you have to do is download the `DarkAngel Encrypter 03` file and obtain the `SHA512` hash.

Let us do this with the use of the `sha512sum` function within linux.

Once the file is downloaded execute the following command in a linux terminal `sha512sum <filename>`. This gets us the following output.

`d5241cbd99afdd521fe9122b3ca77c8e2750a1fef050ecb88e6a5b91b74cf155fdae5b600e22ccceb97ad45a14fddf26394d066456969ed9e5514c8d681ebf44  <filename>`

Let us grab the first 8 and last 8 characters for our flag.

`flag{d5241cbd:681ebf44}`
