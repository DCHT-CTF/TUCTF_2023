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
b3BlbnNzaC1rZXktdjEAAAAACmFlczI1Ni1jdHIAAAAGYmNyeXB0AAAAGAAAABD4MNgGrk
< .. >
kx0QJFJ+cATXGtje+ngQUS77jh9pQMMGREqJ6pyuoXVtSho2UsdCEdZ7ZpCg+l3xhiGwh7
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
python ssh2john.py sheep > sheep.hash

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

