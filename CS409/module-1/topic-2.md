---
layout: default
course: CS409
module: 1
topic: 2
---

## Ciphers and Encryption

### Plaintext
Plaintext is viewed as a sequence of elements.
 It is the plain, unencrypted message that needs to be encrypted.

### Classical Ciphers

>A classical cipher is a type of cipher that was used historically but for the most part, has fallen into disuse...[Read More on Wikipedia](https://en.wikipedia.org/wiki/Classical_cipher)

Mainly 3 Types:
1. Substitution Ciphers
2. Transposition (Permutation) Ciphers
3. Product Ciphers

#### Substitution cipher
Works by replacing each element of the plaintext with another element.

Common Substituition ciphers are,
- Caeser Cipher
- Monoalphabetic Substitution Cipher
- Playfair Cipher
- Vignere Cipher (Polyalphabetic)
- Hill cipher

##### Caeser Cipher (Additive Cipher)

Each letter is replaced by the letter which is of some position (secret key) further down the alphabet. 

Each letter is offsetted by a certain value.

|A|B|C|D|E|....|
|-|-|-|-|-|-   |
|d|e|f|g|h|....|

Here the offset is 3 (secret key = 3)

**Encryption**
$$c = E_k (p) =  (p+k)mod 26 $$

**Decryption**
$$p = D_k (p) =  (c-k)mod 26 $$

> **Mod:** the modulo (mod) operation returns the remainder or signed remainder of a division. [Read more](https://en.wikipedia.org/wiki/Modulo_operation)

where 
- p is plain text
- c is cipher text
- k is the offset/ secret key
- E is encryption function
- D is decryption function

**Disadvantages**
- Vulnerable to brute-force attacks.

[Caeser Cipher - Simulator](https://www.dcode.fr/caesar-cipher)

##### Monoalphabetic Substitution Cipher

Shuffle letters and map each plaintext letter to different random ciphertext letter.

Letters of the alphabet is randomly mapped to a different letter and stored as the key.

> **Mono** meaning One and **alpha** meaning alphabet, shows that One alphabet is substituted to another alphabet.

**Advantages**
- Safe from normal bruteforce attacks

**Disadvantages**
- Vulnerable to cryptanalysis.
- Humans are predictable, 
    - Human languages are not random.
    - Letters are not equally frequently used.

[Monoalphabetic Substitution Cipher - Online](https://www.dcode.fr/monoalphabetic-substitution)

##### Playfair cipher

Works with a 5X5 matrix of letters based on a keyword.
Steps:

- Split the Plaintext to pair of 2 letters.
-  If a pair is a repeated letter, insert a filler X
    When BALLOON is the plaintext,

    |BA|LL|OO|N|
    |-|-|-|-|
    |BA|LX|LO|ON|

- Follow the Encryption rules below.
- Write the Key in a 5x5 matrix and fill-in the rest of the letters.

> When filling the 5x5 Matrix, Note. the position of "i" is usually shared with "j". If "i" is already used in the key, you may share the position of "j" with the next letter i.e "k".

**Encryption:**

1. If both letters fall in the **same row**,
    - replace each with letter to right (wrap around), 
    - e.g., "AR" encrypts as "RM"

2. If both letters fall in the **same column** 
    - replace each with the letter below it (wrap around),
    - e.g. "MU" encrypts to "CM".

3. Otherwise each letter is replaced by the one in its row in the column of the other letter of the pair, 
    - e.g., "HS" encrypts to "BP", and "EA" to "IM" or "JM“.

**Decryption:**

- Decrypting the Playfair cipher is as simple as doing the same process in reverse.


##### Polyalphabetic Ciphers

Use a key to select which alphabet is used for each letter of the message. 

> **Poly** meaning Many alphabets, shows that for each pair of letters (row and column), there are many alphabets mapped to it.

Most common cipher is the Vignere Cipher.

![Vignere Cipher](https://upload.wikimedia.org/wikipedia/commons/9/9a/Vigen%C3%A8re_square_shading.svg)

**Encryption**

Given the plaintext : GIVE MONEY

|Plaintext:|G|I|V|E|M|O|N|E|Y|
|-|-|-|-|-|-|-|-|-|-|
|**Key:**|L|O|C|K|L|O|C|K|L|

Using the Vignere Table we get the cipher text as

**Cipher Text:** RWXOXCPOJ

##### Hill Cipher

Another form of polysubstituion cipher.
It uses matrices to transform blocks of plaintext letters into blocks of ciphertext.

**Advantages**
- can be used on any size block of characters.
- more secure.

**Encryption:**
- Assign each letter an index
- $$ C=K P \  mod \  26 $$ where k is the secret key and P is the plaintext
- Matrix K is the key.

**Decryption**
- $$P = Inverse(K) \ mod \ 26 $$ where k is the secret key and P is the plaintext

#### Transposition (or permutation) cipher
Achieved by performing **some sort of permutation** on the plaintext letters.
This technique **rearranges** the letter order without altering the actual letters.

Mainly 2 ciphers,
- Railfence Ciphers
- Columnar Ciphers

##### Railfence Cipher

Uses depth parameter to create rows which are later filled with the plain text.

**Encryption**

Example: P= "meet me after the toga party"

|m||e||m||a||t||r|..|
|-|-|-|-|-|-|-|-|-|-|-|-|
||e||t||e||f||e||..|

and the **Cipher Text:** is: MEMATRHTGPRYETEFETEOAAT

**Decryption**

Using the depth parameter as key, we redraw the table, this time we fill the letters row wise.

|m||e||m||a||t||r|..|
|-|-|-|-|-|-|-|-|-|-|-|-|
||

##### Columnar Cipher

Involves writing the plaintext out in rows, and then reading the ciphertext off in columns one by one.

Example: P = "attack today"

- Secret Key = "XYLE" 
    - length("XYLE") = 4
    - order of alphabets in "XYLE" is "3421"



**Encryption**

We then write the plaintext **row-wise** (length 4) and continue downwards.

For Ciphertext, we read the columns according to the key-order from top to bottom.

|Key|3|4|2|1|
|-|-|-|-|-|
|P =|a|t|t|a|
||c|k|t|o|
||d|a|y|x|

Therefore, the **Cipher Text:** is "AOXTTYTKAACD"

**Decryption** 

For Plaintext, 
- Take the key provided
- Make columns matching the length of the Key
- write the ciphertext **column-wise**

|Key|3|4|2|1|
|-|-|-|-|-|
|P =|a|t|t|a|
||c|k|t|o|
||d|a|y|x|

Therefore, the **Cipher Text:** is "ATTACKTODAY"

---

> **SideNote:** The Letter X is often added when the necessary size of the plaintext isn't matched. This allows the ciphertext to be more uniform and resistant to some cryptanalytic approaches.