# Cybersecurity

### CMP-5006

### Alejandro Proano, PhD

# Introduction to Symmetric Cryptography

## What is Symmetric Cryptography?

Symmetric cryptography, also known as secret-key cryptography, is a method of encryption where the same key is used for both the encryption and decryption processes. It is one of the oldest and most widely used forms of cryptography.

In symmetric cryptography, the sender and the receiver share a secret key that is used to encrypt and decrypt the message. This key must be kept confidential to ensure the security of the communication.

## How Does Symmetric Cryptography Work?

1. **Encryption**: The sender uses the shared secret key to encrypt the plaintext message into ciphertext. This process involves applying a mathematical algorithm to transform the original message into an unreadable form.

2. **Transmission**: The encrypted ciphertext is transmitted over an insecure channel, such as the internet or a wireless network.

3. **Decryption**: The receiver uses the same shared secret key to decrypt the ciphertext back into the original plaintext message. This process involves applying the inverse of the encryption algorithm to reverse the transformation.

## Advantages of Symmetric Cryptography

- **Efficiency**: Symmetric cryptography is computationally efficient, making it suitable for encrypting large amounts of data quickly.

- **Simplicity**: The algorithms used in symmetric cryptography are relatively simple and easy to implement.

- **Security**: When properly implemented and managed, symmetric cryptography provides a high level of security.

## Examples of Symmetric Cryptographic Algorithms

1. **Data Encryption Standard (DES)**: DES is a symmetric encryption algorithm that uses a 56-bit key. It was widely used in the past but is now considered insecure due to its small key size.

2. **Advanced Encryption Standard (AES)**: AES is a symmetric encryption algorithm that replaced DES. It supports key sizes of 128, 192, and 256 bits, making it more secure than DES.

3. **Triple Data Encryption Standard (3DES)**: 3DES is a symmetric encryption algorithm that applies DES three times with different keys. It provides a higher level of security than DES but is slower due to the multiple encryption rounds.


## Perfect Secrecy

Perfect secrecy refers to a cryptographic system where the ciphertext provides no information about the plaintext, even if the attacker has unlimited computational power and resources. In other words, the encrypted message is completely secure and cannot be decrypted without the correct key.

## Requirements for Perfect Secrecy
To achieve perfect secrecy, the following requirements must be met:

1. Key Length: The key used for encryption must be at least as long as the plaintext message. This ensures that each possible plaintext has a unique corresponding ciphertext, making it impossible for an attacker to determine the original message.

2. Key Distribution: The key must be securely distributed between the sender and the receiver. If the key falls into the wrong hands, perfect secrecy is compromised.

3. Key Usage: The key should only be used once and then discarded. Reusing the same key for multiple messages increases the risk of decryption.

## Limitations and Practicality
While perfect secrecy provides the highest level of security, it has certain limitations and practicality concerns:

1. Key Length: Generating and managing long keys can be challenging and resource-intensive, especially for large-scale communication systems.

2. Key Distribution: Securely distributing keys to all intended recipients can be a complex task, especially in scenarios where multiple parties are involved.

3. Key Usage: Using a key only once for encryption and then discarding it can be impractical for real-world applications that require frequent communication.

## Block Ciphers



## Substitution-Permutation Networks

Block ciphers are symmetric encryption algorithms that operate on fixed-size blocks of data. They divide the input data into blocks of a fixed length and apply a series of transformations to each block. One common approach to designing block ciphers is using Substitution-Permutation Networks (SPN).



### Substitution

The substitution step in an SPN involves replacing each element of the input block with another element from a predefined substitution table. This table, known as an S-box, maps each possible input value to a corresponding output value. The S-box is typically designed to be highly nonlinear, providing confusion and making it difficult for an attacker to deduce the original input.



### Permutation

After the substitution step, the permutation step rearranges the elements of the block according to a predefined permutation table. This step provides diffusion, spreading the influence of each input bit across the entire block. The permutation table ensures that each bit in the output block depends on multiple bits from the input block, increasing the complexity of the encryption process.



### Key Expansion

To enhance the security of block ciphers, a key expansion algorithm is used to generate a set of round keys from the original encryption key. Each round key is used in the encryption process to modify the input block. The key expansion algorithm ensures that each round key is unique and independent of the original key, making it harder for an attacker to recover the key.



### Rounds

The encryption process in block ciphers is typically performed in multiple rounds. Each round consists of a combination of substitution, permutation, and key mixing operations. The number of rounds depends on the specific block cipher algorithm and the desired level of security. More rounds generally provide stronger encryption but also increase the computational overhead.
