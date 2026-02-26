## h5 Uryyb, Greb!

### Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition

Messaging:
	A message is written by a sender and is sent to another individual, the receiver.
	The sender wants the message to only be readable for the receiver. What the sender 	can do is encrypt, or encipher their plain text into ciphertext. The receiver is now responsible for decrypting, or deciphering the cipher text to read its contents.


The practice of ciphering messages is called cryptography, and it is highly needed in today's digital world where sensitive data is an abundance. Breaking these ciphertexts is called cryptanalysis, and an area of mathematics which is used to cipher and decipher messages is called cryptology.

https://www.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec006

### PGP - Send Encrypted and Signed Message - gpg

This article explains how to send encrypted messages through untrusted internet. By encrypting, you are preventing anyone from reading its contents, and by signing it you are preventing any changes to the message.
The article explains how using PGP encryption with the gpg tool, how to simulate two users, share public keys, and send over a message from one to another.

Gpg is a common encryption and signing tool and is used in Linux.
For two people to send messages they must have they own keypair which can be generated with "gpg --gen-key" in the command line once they have installed gpg onto their computer.

To share access to the other user's public key, the article explains to export the key with "gpg --export --armor --output tero.pub". Once a new "user" is created as a file, a keypair is created for it. Now there are two different users each with their own public keys. Next would be to import and verify the public key from the other user. Now the other user exports their public key for the other user to import it, same process as before. Once this is complete, both users have verified each other as the correct users.

One user creates a file, writes a message, then encrypts it with " gpg --homedir . --encrypt --recipient tero@example.com.invalid --sign --output encrypted.pgp --armor message.txt". "--encrypt" encrypts the message, "--recipient" specifies who will be receiving the message, and "--sign" signs the message with the writing user's key. Only those with the recipient's public key can decrypt the text, therefore, the message can now be sent through the untrusted internet. The recipient user receives an "encrypted.pgp" an can decrypt it with "gpg --decrypt encrypted.pgp"
https://terokarvinen.com/2023/pgp-encrypt-sign-verify/


### Install OpenSSH server, connect to it using 'ssh' client

OpenSSH was already installed so all I needed to do was log in using my "username@virtualmachine-name"

<img width="607" height="45" alt="image" src="https://github.com/user-attachments/assets/b8240a65-ea26-431a-a3ba-d9d2b4df6dfa" />
After entering the system passeord I successfully log in. This is what is shown <img width="919" height="169" alt="image" src="https://github.com/user-attachments/assets/e3d05209-ae40-469a-95d6-0ae435d24c6c" />

 ### Automate SSH connection using public keys.

 I had somne issues for this task. I followed the step-by-step from tht PGP task. I was able to create a public key for my self using gpg, and I also simulated another user as a file called "alice".
 When I created a key for alice, both keys happened to exist in the same file for some reason. Because of this, I was not able to simulate two users.
 <img width="904" height="485" alt="image" src="https://github.com/user-attachments/assets/2d0d049e-245e-4ffa-bb36-7f3862121968" />
 As you can read "can't connec to the gpg.agent: No such file or directory". Maybe I created the file in the wrong directory, thinking it was in the home direectory.

### Password manager
 The password manager I will use is Proton Pass.
 Proton pass uses zero-knowledge end-to-end encryption.
 We start by choosing what we want to save
 <img width="1154" height="699" alt="Screenshot 2026-02-26 141050" src="https://github.com/user-attachments/assets/907216f0-c57b-4cd2-ab81-cb0c9f1a04a3" />
 We choose a title, enter the credentials, and optionally add a 2FA key for more security.
<img width="879" height="768" alt="image" src="https://github.com/user-attachments/assets/ce6b72df-7ff5-4f90-bbc6-8435dd18c1d7" />
Password managers are important for many reasons. We keep all our credentials in one secure space. Why is it secure? The sercice provider themselves do not store any user data, rather they create a local space for users to keep their data, and then encrypts the data with banking-level encryption. Even if attackers breach into the password managers system, they wont have any access to data.
https://proton.me/pass

###  "ETAOIN": ETAOIN. Crack this ciphertext:


HDMH'B TH. KWU'YI AWR WSSTOTMJJK M OWQINYIMLIY! MB KWU BII, BTGPJI BUNBHTHUHTWA OTPDIYB OMA NI NYWLIA RTHD SYIEUIAOK MAMJKBTB. BII KWU MH DHHP://HIYWLMYCTAIA.OWG
That's it. you're now officially a codebreaker! As you see, simple substitution ciphers can be broken with frequency analysis. see you at Http:/terokarvinen

Cracking this was pretty simple. I saw that the link was encrypted, but the links always start with http/ https. 
I also was pretty lucky to guess that the link was terokarvinen from the beginning. I made a substitute alphabet and went to work.
