# Work Guide: Classical Cryptography

## Part 1: Research Topics

In this section, you will research various classical cryptography topics. Each topic has a set of questions to guide your learning.

### 1. The Shift Cipher

1. What is the shift cipher and how does it work?

   - The shift cipher, also known as the Caesar cipher, is a simple and ancient encryption technique. It operates by shifting each letter in the plaintext by a fixed number of positions down or up the alphabet. This fixed number is known as the "key" or "shift value." The cipher is named after Julius Caesar, who is historically known to have used it.

2. How can you encrypt and decrypt messages using the shift cipher?

   - **Encryption:** To encrypt a message using the shift cipher, you choose a shift value (the key) and replace each letter in the plaintext with the letter that is shifted forward in the alphabet by the specified number of positions. Wrap-around may occur, meaning if you reach the end of the alphabet, you continue from the beginning. For example, with a shift value of 3, "A" becomes "D," "B" becomes "E," and so on.
   - **Decryption:** To decrypt the message, you reverse the process by shifting each letter in the ciphertext backward by the same number of positions.
   - Here's an example:
     - Plaintext: "HELLO"
     - Shift (Key): 3
     - Encryption: "HELLO" -> "KHOOR"
     - Decryption: "KHOOR" -> "HELLO"

3. What are the limitations and vulnerabilities of the shift cipher?

   - **Lack of Security:** The shift cipher is highly vulnerable to attack. Since there are only 25 possible keys (0-25 for a standard English alphabet), it can easily be cracked through brute force by trying all possible keys.
   - **Frequency Analysis:** Another weakness is that the frequency of letters in English text remains roughly the same, even after encryption. An attacker can perform frequency analysis to guess the key and decrypt the message.

4. Can you provide an example of a real-world application of the shift cipher?

   - The shift cipher is not suitable for secure communication in modern times due to its vulnerabilities. However, it can be used for simple and fun puzzles or games. For example, it's sometimes used in puzzle books, escape rooms, or educational settings to introduce people to basic encryption concepts.

5. How does the shift cipher relate to modular arithmetic?

   - The shift cipher is closely related to modular arithmetic. When shifting letters in the alphabet, you essentially perform arithmetic operations modulo the length of the alphabet. For the standard English alphabet with 26 letters, you perform modulo 26 arithmetic.

     - Encryption: E(x) = (x + k) % 26
     - Decryption: D(y) = (y - k) % 26

     .

### 2. The Substitution Cipher

1. What is the substitution cipher and how does it differ from the shift cipher?

   - **Substitution Cipher:** In a substitution cipher, each letter in the plaintext is replaced with another letter or symbol according to a fixed substitution rule or key. This means that each character in the plaintext can map to any other character, and the relationship between the original and encrypted characters is not necessarily based on a simple shift. Substitution ciphers are more complex than shift ciphers and can provide better security, especially if implemented with a keyword or a random permutation.
   - **Shift Cipher (Caesar Cipher):** The shift cipher is a specific type of substitution cipher where each letter is replaced by another letter in the alphabet by shifting it a fixed number of positions. It's a simpler form of substitution cipher.

2. How can you create a substitution cipher using a keyword or a random permutation?

   - **Using a Keyword:** One way to create a substitution cipher is by using a keyword. You first write down the unique letters in the keyword, and then append the remaining letters of the alphabet in order. This creates a new alphabet, which you use for both encryption and decryption.

   For example, if your keyword is "KEYWORD," your new alphabet would be: "KEYWORDABCFGHIJLMNPQSTUVXZ."

   - **Random Permutation:** Another approach is to create a completely random permutation of the alphabet. In this case, you shuffle the letters of the alphabet to create a unique mapping for each letter. This random mapping is your substitution key

3. What are the advantages and disadvantages of the substitution cipher?

   - Advantages:
     - Greater security compared to shift cipher due to complex letter mappings.
     - Can handle non-alphabetic characters and symbols.
     - The key can be changed easily, enhancing security.
   - Disadvantages:
     - Vulnerable to frequency analysis, as the frequency of letters in the language can still provide clues about the substitution.
     - The size of the key space is limited to the number of characters in the alphabet, making it vulnerable to brute-force attacks.
     - Lengthy keys can be challenging to remember and manage

4. How can frequency analysis be used to break a substitution cipher?

   - Frequency analysis can be used to break a substitution cipher, similar to how it can be used to break a shift cipher. Even though the original characters are replaced with arbitrary characters, the frequencies of letters in the language still apply. By analyzing the frequency of characters in the ciphertext and comparing it to known frequency distributions in the language, an attacker can make educated guesses about the substitutions and eventually decode the message.

5. Can you provide an example of a historical use of the substitution cipher?

   - The most famous historical use of a substitution cipher is the "Bifid Cipher" employed by the French army during World War I. This cipher involved replacing each letter with a corresponding pair of coordinates on a grid. The key was the arrangement of the grid. It provided a more complex substitution than a simple shift, making it harder for enemies to decipher intercepted messages. However, like many substitution ciphers, it was eventually broken through analysis and codebreaking efforts.

### 3. The Affine Cipher

1. What is the affine cipher and how does it combine the shift and substitution ciphers?

   - The affine cipher is a type of substitution cipher that combines elements of both the shift cipher and the substitution cipher. It achieves this by using two mathematical functions: a linear function (a shift) and a modular multiplication (a substitution) on each character in the plaintext. This combination makes it more secure than a simple shift cipher.

2. How can you encrypt and decrypt messages using the affine cipher?

   - Encryption:

      To encrypt a message using the affine cipher, you choose two numbers: "a" and "b," where "a" is coprime (having no common factors other than 1) with the size of the alphabet (e.g., 26 for English). Then, for each letter in the plaintext, you apply the following formula:

     - E(x) = (ax + b) % m
     - "x" is the position of the letter in the alphabet (0 to 25 for English).
     - "m" is the size of the alphabet (e.g., 26 for English).
     - "%" represents the modulo operation.

   - Decryption:

      To decrypt the message, you use the modular multiplicative inverse of "a," denoted as "a^(-1)." The decryption formula is:

     - D(y) = a^(-1)(y - b) % m

3. What are the advantages and vulnerabilities of the affine cipher?

   - **Advantages:**
     - The two mathematical functions offer better security than simple shift or substitution ciphers.
     - The security depends on the choice of "a" and "b," which allows for a larger key space.
     - Can handle both uppercase and lowercase letters and non-alphabetic characters.
   - **Vulnerabilities:**
     - Vulnerable to known plaintext attacks if an attacker has access to enough plaintext-ciphertext pairs.
     - The choice of "a" and "b" is critical; if they are not appropriately selected, the cipher can be weak.

4. How can you break the affine cipher using known plaintext attacks?

   - If an attacker has access to a sufficient number of plaintext-ciphertext pairs, they can potentially calculate the values of "a" and "b" using linear algebra techniques. Once "a" and "b" are determined, they can decrypt other messages encrypted with the same key.

     The more plaintext-ciphertext pairs an attacker has, the easier it is to break the cipher. Therefore, using a large key space (choosing "a" and "b" values carefully) and minimizing the exposure of plaintext-ciphertext pairs are essential for the security of the affine cipher.

5. Can you provide an example of a practical use of the affine cipher?

### 4. The Hill Cipher

1. What is the Hill cipher and how does it differ from previous ciphers?
2. How can you encrypt and decrypt messages using the Hill cipher?
3. What are the advantages and limitations of the Hill cipher?
4. How does the Hill cipher utilize matrix operations?
5. Can you provide an example of a real-world application of the Hill cipher?

### 5. The Permutation Cipher

1. What is the permutation cipher and how does it work?
2. How can you encrypt and decrypt messages using the permutation cipher?
3. What are the strengths and weaknesses of the permutation cipher?
4. How can you break the permutation cipher using brute force or frequency analysis?
5. Can you provide an example of a historical use of the permutation cipher?

### 6. LFSR Stream Cipher

1. What is an LFSR stream cipher and how does it generate a keystream?
2. How can you encrypt and decrypt messages using an LFSR stream cipher?
3. What are the advantages and vulnerabilities of an LFSR stream cipher?
4. How can you break an LFSR stream cipher using known plaintext attacks?
5. Can you provide an example of a modern use of an LFSR stream cipher?

## Part 2: Cryptanalysis Research

In this section, you will research various cryptanalysis techniques for classical ciphers. Each topic has a set of questions to guide your learning.

### 1. Introduction to Cryptanalysis

1. What is cryptanalysis and why is it important in cybersecurity?
2. What are the different types of cryptanalysis techniques?
3. How does cryptanalysis differ from cryptography?
4. Can you provide an example of a famous cryptanalysis success story?
5. What are the ethical considerations in cryptanalysis?

### 2. The Shift Cipher

1. How can you break the shift cipher using brute force?
2. What is the vulnerability of the shift cipher to frequency analysis?
3. How can you improve the security of the shift cipher?
4. Can you provide an example of a real-world attack on the shift cipher?
5. What are the limitations of cryptanalysis on the shift cipher?

### 3. The Affine Cipher

1. How can you break the affine cipher using known plaintext attacks?
2. What is the vulnerability of the affine cipher to modular inverses?
3. How can you improve the security of the affine cipher?
4. Can you provide an example of a real-world attack on the affine cipher?
5. What are the limitations of cryptanalysis on the affine cipher?

### 4. The Substitution Cipher

1. How can you break the substitution cipher using frequency analysis?
2. What is the vulnerability of the substitution cipher to known plaintext attacks?
3. How can you improve the security of the substitution cipher?
4. Can you provide an example of a real-world attack on the substitution cipher?
5. What are the limitations of cryptanalysis on the substitution cipher?

### 5. The Hill Cipher

1. How can you break the Hill cipher using matrix algebra?
2. What is the vulnerability of the Hill cipher to key length?
3. How can you improve the security of the Hill cipher?
4. Can you provide an example of a real-world attack on the Hill cipher?
5. What are the limitations of cryptanalysis on the Hill cipher?

### 6. The Permutation Cipher

1. How can you break the permutation cipher using brute force or frequency analysis?
2. What is the vulnerability of the permutation cipher to known plaintext attacks?
3. How can you improve the security of the permutation cipher?
4. Can you provide an example of a real-world attack on the permutation cipher?
5. What are the limitations of cryptanalysis on the permutation cipher?

### 7. LFSR Stream Cipher

1. How can you break an LFSR stream cipher using known plaintext attacks?
2. What is the vulnerability of an LFSR stream cipher to key length?
3. How can you improve the security of an LFSR stream cipher?
4. Can you provide an example of a real-world attack on an LFSR stream cipher?
5. What are the limitations of cryptanalysis on an LFSR stream cipher?

# Lab Guide: Cryptography Programming Exercises

## Classic Cryptography Topics

### 1. Shift Cipher

#### Exercise:
Write a Python function `shift_cipher_encrypt(plaintext, shift)` that takes a plaintext string and a shift value as input and returns the corresponding ciphertext using the shift cipher.

#### Example:
> - Plaintext: "HELLO"
> - Shift: 3
> - Ciphertext: "KHOOR"

> - Plaintext: "WORLD"
> - Shift: 5
> - Ciphertext: "BTWQI"

### 2. Substitution Cipher

#### Exercise:
Write a Python function `substitution_cipher_encrypt(plaintext, key)` that takes a plaintext string and a substitution key as input and returns the corresponding ciphertext using the substitution cipher.

#### Example:
> - Plaintext: "HELLO"
> - Key: {'H': 'X', 'E': 'Y', 'L': 'Z', 'O': 'A'}
> - Ciphertext: "XYZZA"

> - Plaintext: "WORLD"
> - Key: {'W': 'Q', 'O': 'P', 'R': 'S', 'L': 'T', 'D': 'U'}
> - Ciphertext: "QPSUT"

### 3. Affine Cipher

#### Exercise:
Write a Python function `affine_cipher_encrypt(plaintext, a, b)` that takes a plaintext string and two integer values a and b as input and returns the corresponding ciphertext using the affine cipher.

#### Example:
> - Plaintext: "HELLO"
> - a: 5
> - b: 8
> - Ciphertext: "RCLLA"

> - Plaintext: "WORLD"
> - a: 3
> - b: 7
> - Ciphertext: "VXGOQ"

### 4. Hill Cipher

#### Exercise:
Write a Python function `hill_cipher_encrypt(plaintext, key)` that takes a plaintext string and a 2x2 matrix key as input and returns the corresponding ciphertext using the Hill cipher.

#### Example:
> - Plaintext: "HELLOWORLD"
> - Key: [[2, 3], [1, 4]]
> - Ciphertext: "AXDDQYBEFX"

### 5. Permutation Cipher

#### Exercise:
Write a Python function `permutation_cipher_encrypt(plaintext, key)` that takes a plaintext string and a permutation key as input and returns the corresponding ciphertext using the permutation cipher.

#### Example:
> - Plaintext: "HELLO"
> - Key: [3, 1, 4, 2, 5]
> - Ciphertext: "LHLEO"

> - Plaintext: "WORLD"
> - Key: [2, 4, 1, 5, 3]
> - Ciphertext: "OLWDR"

## Cryptanalysis Topics

### 1. Affine Cipher

Write a Python function `break_affine_cipher(ciphertext)` that takes a string `ciphertext` as input and attempts to break the affine cipher by trying all possible combinations of `a` and `b` values. The function should return the most likely plaintext obtained by decrypting the ciphertext using the correct `a` and `b` values.

Example:
```python
ciphertext = "Czggj, Tqxxa!"
plaintext = break_affine_cipher(ciphertext)
print(plaintext)
```
Output:
```
Hello, World!
```

### 2. Substitution Cipher

Write a Python function `break_substitution_cipher(ciphertext)` that takes a string `ciphertext` as input and attempts to break the substitution cipher by performing frequency analysis on the letters in the ciphertext. The function should return the most likely plaintext obtained by decrypting the ciphertext using the correct key.

Example:
```python
ciphertext = "XYZZA, CDCFA!"
plaintext = break_substitution_cipher(ciphertext)
print(plaintext)
```
Output:
```
Hello, World!
```

### 3. Hill Cipher

Write a Python function `break_hill_cipher(ciphertext, n)` that takes a string `ciphertext` and an integer `n` as input and attempts to break the Hill cipher by performing frequency analysis on the letters in the ciphertext and using matrix algebra. The function should return the most likely plaintext obtained by decrypting the ciphertext using the correct key.

Example:
```python
ciphertext = "XZGZJ, ZJGFA!"
n = 2
plaintext = break_hill_cipher(ciphertext, n)
print(plaintext)
```
Output:
```
Hello, World!
```

