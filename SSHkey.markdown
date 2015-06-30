# Generate Secure Shell (SSH) key on Linux or MacOS

## Check if SSH key already exists
```sh
ls -l  ~/.ssh/
total 72
-rw-------+ 1 maartenk  staff    287 Mar 10 09:13 config
-rw-------+ 1 maartenk  staff   1679 Nov 25  2014 id_rsa
-rw-r--r--+ 1 maartenk  staff    409 Nov 25  2014 id_rsa.pub
-rw-r--r--+ 1 maartenk  staff  17351 Jun 30 12:13 known_hosts
````

## Generate SSH key
```sh
ssh-keygen -t rsa -b 4096 -f /home/user/.ssh/id_rsa
Generating public/private rsa key pair.
/home/user/.ssh/id_rsa_test already exists.
Overwrite (y/n)? y
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/user/.ssh/id_rsa
Your public key has been saved in /home/user/.ssh/id_rsa.pub
The key fingerprint is:
40:1f:33:78:32:51:b5:c4:51:56:99:b6:6a:3d:18:8b user@computer.surfsara.nl
The key's randomart image is:
+--[ RSA 4096]----+
|      o=B+++.o   |
|     .+oo*. +    |
|      .++. = .   |
|       .E o o    |
|        V  o .   |
|          o .    |
|         .       |
|                 |
|                 |
+-----------------+
```
## Copy your SSH key
```sh
cat ~/.ssh/id_rsa
```
# Generate Secure Shell (SSH) key on Windows

A way to generate a SSH key under Windows is with help of PutTTY-gen. PuTTYgen can be downloaded at http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html or directly downloaded from http://the.earth.li/~sgtatham/putty/latest/x86/puttygen.exe .

* Start PuTTYgen
* In the field "Type of key to generate", please select "SSH-2 RSA".

![puttygen_default](https://doc.hpccloud.surfsara.nl/oortdoc/docs/raw/master/images/puttygen_default.png)

* Click on  "Generate".

![puttygen_random](https://doc.hpccloud.surfsara.nl/oortdoc/docs/raw/master/images/puttygen_random.png)

* Move your pointer under the bar and move the mouse in this field until the bar is completely green.

![puttygen_done](https://doc.hpccloud.surfsara.nl/oortdoc/docs/raw/master/images/puttygen_done.png)

* Fill in a passphrase in the "Key passphrase" field. A passphrase is the same as a password, but in general it contains more characters. Repeat the same passphrase in the  "Confirm passphrase" field. It is possible to not use a passphrase, but this is not considered as good practice in terms of security.
* Save your private key at a secure spot with the "Save Private Key".
* Save your public key at with the "Save Pubilic Key".
* Select all text from the "Public key for pasting into OpenSSH authorized_keys file" and copy paste this in OpenNebula [link link]