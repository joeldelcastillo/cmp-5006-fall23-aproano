# Cybersecurity

### CMP-5006

### Alejandro Proano, PhD

## Cryptography

Cryptography is the practice of securing communication by converting plain text into an unreadable format, known as ciphertext, using various mathematical algorithms. It ensures the confidentiality, integrity, and authenticity of data by making it difficult for unauthorized individuals to access or modify the information.



## Applications of Cryptography

1. **Secure Communication**: Cryptography is widely used in secure communication protocols such as Secure Sockets Layer (SSL) and Transport Layer Security (TLS). These protocols encrypt data transmitted over the internet, ensuring that sensitive information like passwords, credit card details, and personal data remain confidential and protected from eavesdropping.

2. **Password Storage**: When storing passwords in databases, it is crucial to protect them from unauthorized access. Cryptographic hash functions like bcrypt or SHA-256 are used to convert passwords into irreversible hash values. This way, even if the database is compromised, the original passwords cannot be easily retrieved.

3. **Digital Signatures**: Cryptography is used to create digital signatures, which provide proof of authenticity and integrity for digital documents or messages. By using asymmetric encryption algorithms, a sender can encrypt a document with their private key, and the recipient can verify the signature using the sender's public key. This ensures that the document has not been tampered with and originated from the claimed sender.


4. **Virtual Private Networks (VPNs)**: VPNs use cryptography to create secure tunnels for transmitting data over public networks. By encrypting the data packets, VPNs ensure that the information remains confidential and protected from unauthorized access. This is particularly important when accessing sensitive corporate networks remotely or when using public Wi-Fi networks.

5. **Blockchain Technology**: Cryptography plays a vital role in securing blockchain networks. It is used to create digital signatures, hash functions, and consensus algorithms that ensure the integrity and immutability of the blockchain. Cryptography enables secure transactions, prevents double-spending, and maintains the overall security of the decentralized network.

## Elements of Cryptography

1. **Plaintext:** Plaintext refers to the original message or data that is in a readable and understandable format. It is the information that needs to be protected from unauthorized access.

2. **Ciphertext:** Ciphertext is the encrypted form of the plaintext. It is the result of applying cryptographic algorithms and techniques to the plaintext, making it unintelligible to anyone without the proper decryption key.

3. **Key:** A key is a piece of information used in the encryption and decryption processes. It is a parameter that determines the specific transformation of the plaintext into ciphertext and vice versa. The key is essential for both encrypting and decrypting the message.

4. **Encryption Algorithm:** An encryption algorithm is a set of mathematical rules and procedures used to convert plaintext into ciphertext. It defines the specific steps and operations required to transform the data securely.

5. **Decryption Algorithm:** A decryption algorithm is the reverse of the encryption algorithm. It is used to convert the ciphertext back into plaintext using the same key that was used for encryption. The decryption algorithm follows a specific set of rules to reverse the encryption process.

## Types of Cryptography

1. **Symmetric Cryptography**
   - Uses a single key for both encryption and decryption
   - Examples: Data Encryption Standard (DES), Advanced Encryption Standard (AES)

2. **Asymmetric Cryptography**
   - Uses a pair of keys: public key for encryption and private key for decryption
   - Examples: RSA, Elliptic Curve Cryptography (ECC)

3. **Hash Functions**
   - Converts data of any size into a fixed-size hash value
   - Examples: MD5, SHA-256

## History of Cryptography

Cryptography, the practice of secure communication, has a long and fascinating history. Throughout the ages, individuals and organizations have used various techniques to protect their sensitive information from unauthorized access.

## 1. Ancient Egypt: 
The Egyptians used hieroglyphics to encode their messages. They would often substitute symbols or use complex patterns to hide the true meaning of their texts.

![](./images/tomb-substitution.webp) 

## 2. Julius Caesar:
 The Roman emperor, Julius Caesar, used a simple substitution cipher known as the Caesar cipher. He would shift each letter in the alphabet by a fixed number of positions to encrypt his messages.

## 3. Mary, Queen of Scots: 

During her imprisonment, Mary, Queen of Scots, used a cipher called the Babington Plot cipher to communicate secretly with her supporters. This cipher involved using a grid to substitute letters with numbers.

## 4. World War II: 

The Enigma machine, developed by the Germans, was a complex encryption device used to secure their military communications. It involved a series of rotors and plugboard connections to encrypt and decrypt messages.

![](./images/enigmamachinelabeled.jpg) 

## 5. Modern Cryptography: 

With the advent of computers, cryptography has evolved significantly. Today, we use advanced algorithms and mathematical principles to ensure secure communication over the internet.

## Classic Cryptography

Classic cryptography refers to the traditional methods of encrypting and decrypting messages that were used before the advent of modern computer-based encryption algorithms. These techniques have been employed for centuries to ensure the confidentiality and integrity of sensitive information. Classic cryptography primarily involves the use of substitution and transposition techniques to transform plaintext into ciphertext.

    - Shift cipher
    - Substitution cipher
    - Affine cipher
    - Vigenere cipher
    - Hill cipher
    - Permutation cipher
    - Stream ciphers

## Caesar Cipher Implementation

The Caesar cipher is a simple substitution cipher that is used to encrypt and decrypt messages. It works by shifting the letters of the plaintext by a certain number of positions in the alphabet. This number is known as the key or the shift.

## Example

Let's consider an example where the plaintext message is "HELLO" and the key is 3.

### Encryption

1. Convert the plaintext to uppercase: "HELLO".
2. Iterate through each letter:
   - "H" -> position 7 -> 7 + 3 = 10 -> 10 % 26 = 10 -> "J"
   - "E" -> position 4 -> 4 + 3 = 7 -> 7 % 26 = 7 -> "H"
   - "L" -> position 11 -> 11 + 3 = 14 -> 14 % 26 = 14 -> "O"
   - "L" -> position 11 -> 11 + 3 = 14 -> 14 % 26 = 14 -> "O"
   - "O" -> position 14 -> 14 + 3 = 17 -> 17 % 26 = 17 -> "R"
3. The ciphertext is "JHOOO".

### Decryption

1. Convert the ciphertext to uppercase: "JHOOO".
2. Iterate through each letter:
   - "J" -> position 10 -> 10 - 3 = 7 -> 7 % 26 = 7 -> "H"
   - "H" -> position 7 -> 7 - 3 = 4 -> 4 % 26 = 4 -> "E"
   - "O" -> position 14 -> 14 - 3 = 11 -> 11 % 26 = 11 -> "L"
   - "O" -> position 14 -> 14 - 3 = 11 -> 11 % 26 = 11 -> "L"
   - "O" -> position 14 -> 14 - 3 = 11 -> 11 % 26 = 11 -> "L"
3. The plaintext is "HELLO".

### Encryption Process

To encrypt a message using the Caesar cipher, the following steps are performed:

1. Convert the plaintext message to uppercase (optional).
2. Iterate through each letter in the plaintext message.
3. Determine the position of the letter in the alphabet.
4. Add the key (shift) to the position.
5. Take the modulus of the result with 26 (the number of letters in the alphabet) to ensure the result stays within the range of the alphabet.
6. Convert the new position back to a letter.
7. Append the encrypted letter to the ciphertext.

## Decryption Process

To decrypt a message encrypted with the Caesar cipher, the following steps are performed:

1. Convert the ciphertext message to uppercase (optional).
2. Iterate through each letter in the ciphertext message.
3. Determine the position of the letter in the alphabet.
4. Subtract the key (shift) from the position.
5. Take the modulus of the result with 26 (the number of letters in the alphabet) to ensure the result stays within the range of the alphabet.
6. Convert the new position back to a letter.
7. Append the decrypted letter to the plaintext.

## Vigenere Cipher Implementation

The Vigenere cipher is a polyalphabetic substitution cipher that was invented by Giovan Battista Bellaso in the 16th century. It is a simple and effective way to encrypt and decrypt messages. The cipher uses a series of Caesar ciphers based on the letters of a keyword.

## Example

Let's encrypt the plaintext message "HELLO" using the keyword "KEY" using the Vigenere cipher:

Plaintext: H E L L O
Keyword: K E Y K E
Key numbers: 10 4 24 10 4
Plaintext numbers: 7 4 11 11 14

Encryption:
- H + K = 7 + 10 = 17 (R)
- E + E = 4 + 4 = 8 (I)
- L + Y = 11 + 24 = 9 (J)
- L + K = 11 + 10 = 21 (V)
- O + E = 14 + 4 = 18 (S)

Ciphertext: R I J V S

To decrypt the ciphertext, the same keyword "KEY" is used, and the process is reversed to obtain the original plaintext message "HELLO".

Note: The Vigenere cipher is a relatively weak encryption method and can be easily broken with modern cryptographic techniques. It is mainly used for educational purposes or as a component in more complex encryption algorithms.

## Encryption Process

To encrypt a plaintext message using the Vigenere cipher, the following steps are performed:

1. Choose a keyword: Select a keyword that will be used to encrypt the message. The keyword should be a word or phrase that is easy to remember and not too short.

2. Convert the keyword to a key: Convert the keyword into a key by repeating it until it matches the length of the plaintext message. For example, if the keyword is "KEY" and the plaintext message is "HELLO", the key would be "KEYKE".

3. Convert the plaintext to numbers: Assign a number to each letter in the plaintext message using a standard numbering system, such as A=0, B=1, C=2, and so on.

4. Convert the key to numbers: Assign a number to each letter in the key using the same numbering system.

5. Encrypt the message: Add the corresponding numbers of the plaintext and key together, modulo 26. This means that if the sum is greater than 26, subtract 26 from the sum. Convert the resulting numbers back to letters using the same numbering system.

6. Repeat the process: Repeat steps 3-5 for each letter in the plaintext message, using the next letter of the key each time.

7. Generate the ciphertext: The resulting letters from step 6 form the ciphertext, which is the encrypted message.

## Decryption Process

To decrypt a ciphertext message encrypted with the Vigenere cipher, the following steps are performed:

1. Choose the same keyword: Use the same keyword that was used to encrypt the message.

2. Convert the keyword to a key: Convert the keyword into a key by repeating it until it matches the length of the ciphertext message.

3. Convert the ciphertext to numbers: Assign a number to each letter in the ciphertext message using the same numbering system.

4. Convert the key to numbers: Assign a number to each letter in the key using the same numbering system.

5. Decrypt the message: Subtract the corresponding numbers of the ciphertext and key, modulo 26. This means that if the difference is negative, add 26 to the difference. Convert the resulting numbers back to letters using the same numbering system.

6. Repeat the process: Repeat steps 3-5 for each letter in the ciphertext message, using the next letter of the key each time.

7. Generate the plaintext: The resulting letters from step 6 form the plaintext, which is the decrypted message.
