![image-20230911102440405](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20230911102440405.png)

How do Alice and Bob communicate without Eve listening to the conversation?

| Encrypt     | Decrypt     |
| ----------- | ----------- |
| C = A(P_0k) | P = A'(C,k) |

If Eve knows the key, she will be able to decrypt the text



How can we do it? 

1. An app sends a key to Alice and Bob
2. Public-private key (asymmetric crypto)
3. In-person: It takes too much effort to exchange to exchange the key.
4. Trusted Authority: For example, an HTTP (SSL certificate). Instead of asking Bob for they key, I am asking Authority for the key.



![image-20230911111403786](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20230911111403786.png)





![image-20230911111434977](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20230911111434977.png)



Each one is an independent event. One key for each of them.

The probability is (1/26)^5

![image-20230911111648411](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20230911111648411.png)

The vigeniere makes it harder to guess.





**In order to maintain perfect secrecy:**

l(c) = l(k)

For 1000 characters I need a key of 1000 characters







**Asymmetric Cryptography**

![image-20231002102026416](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20231002102026416.png)



Signatures: How do we know the message was really sent by Nicole?

![image-20231002102511788](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20231002102511788.png)

Nicole can encrypt the message with her private key

![image-20231002102756460](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20231002102756460.png)

If Joel sends m1, sebastian will decrypt with the private key. (Inverse Process).

![image-20231002102938529](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20231002102938529.png)

Sebastian check that to Nicole, but it does not match with m1. That signal was not originates of that message.

[Man in the Middle Attack]



**How to use it for authetication ?**

I can use the private key. 

![image-20231002103330436](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20231002103330436.png)

Send encrypted private keys. After the session is destroyed.



![image-20231002104130031](C:\Users\joeld\AppData\Roaming\Typora\typora-user-images\image-20231002104130031.png)

Keep sending cypher texts after you confirm that the other person is authenticated.



Pay for a private service for storing passwords and share with my wife.



Each session is encrypted with a unique session key. 