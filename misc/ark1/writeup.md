### A.R.K. 1

Level: Easy

One sheep, two sheep, three sheep. (Note: to speed up the process, only include entries containing "sheep" in your attempts) 

Flag is in the format TUCTF{<password>} (don't include the brackets)

### Solution

We have file that name "sheep" and recognizing the type of data contained in a computer file.

```
$ file sheep
sheep: OpenSSH private key
```

Okey, see the contents:

```
$ cat sheep

-----BEGIN OPENSSH PRIVATE KEY-----
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
luog==
-----END OPENSSH PRIVATE KEY-----
```

Then need hash file using the ssh2john Python tool, locate the ssh2john.py script that is on Kali Linux by default or download the script.

```
$ locate ssh2john.py

# OR

$ curl https://raw.githubusercontent.com/openwall/john/bleeding-jumbo/run/ssh2john.py -O
```

Convert the private key into a hash. That hash can be cracked by the password cracking tool John the Ripper using ssh2john.py.

```
$ python ssh2john.py sheep > sheep.hash

```

We have a hint "Note: to speed up the process, only include entries containing "sheep" in your attempts". 

```
$ grep -r -i sheep rockyou.txt > sheep.txt
```

Crack the hash of the private key (sheep.hash) to determine its passphrase using John the Ripper.

```
$ john sheep.hash -wordlist=./sheep.txt

Using default input encoding: UTF-8
Loaded 1 password hash (SSH, SSH private key [RSA/DSA/EC/OPENSSH 32/64])
Cost 1 (KDF/cipher [0=MD5/AES 1=MD5/3DES 2=Bcrypt/AES]) is 2 for all loaded hashes
Cost 2 (iteration count) is 16 for all loaded hashes
Will run 20 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
baabaablacksheep (sheep)     
1g 0:00:00:00 DONE (2023-12-07 21:25) 1.136g/s 181.8p/s 181.8c/s 181.8C/s blacksheep..funnysheep28
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

```

Get flag **TUCTF{baabaablacksheep}**

