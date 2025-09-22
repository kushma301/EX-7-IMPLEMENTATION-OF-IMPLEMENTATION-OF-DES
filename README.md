## NAME: S.KUSHMA
## REG NO: 212224040168

## EX 7 : IMPLEMENTATION OF IMPLEMENTATION OF DES
## AIM:
To implement the working of the Data Encryption Standard (DES) using a simplified XOR-based encryption and decryption method in C programming.

## ALGORITHM:
To Perform Encryption:
1.	Start the program.
2.	Accept the plaintext message and encryption key from the user.
3.	Calculate the length of the message.
4.	For each character in the message:
•	XOR the character with the corresponding character in the key.
•	If the key is shorter than the message, repeat the key using key[i % keyLength].
•	Store the result in the encrypted message array.
5.	Null-terminate the encrypted message string.
6.	Display the encrypted message in hexadecimal format.
To Perform Decryption:
7.	For each character in the encrypted message:
•	XOR it with the same corresponding character from the key.
•	This reverses the XOR operation, retrieving the original character.
8.	Null-terminate the decrypted message string.
9.	Display the decrypted message.
10.	End the program.

## PROGRAM:
```
#include <stdio.h>
  #include <string.h>
  void encrypt(char *message, char *key, char *encryptedMessage, int messageLength)  
  { 
      int keyLength = strlen(key); 
      for (int i = 0; i < messageLength; i++)  
      { 

          encryptedMessage[i] = message[i] ^ key[i % keyLength]; 
      } 
      encryptedMessage[messageLength] = '\0';  
  } 
  void decrypt(char *encryptedMessage, char *key, char *decryptedMessage, int messageLength)  
  { 
      int keyLength = strlen(key); 
      for (int i = 0; i < messageLength; i++)  
      { 
          decryptedMessage[i] = encryptedMessage[i] ^ key[i % keyLength]; 
      } 
      decryptedMessage[messageLength] = '\0'; 
  } 
  
  int main()  
  { 
      char message[100]; 
      char key[100]; 
      char encryptedMessage[100]; 
      char decryptedMessage[100]; 
      printf("Enter the message to encrypt: "); 
      fgets(message, sizeof(message), stdin); 
      message[strcspn(message, "\n")] = '\0';  
      printf("Enter the encryption key: "); 
      fgets(key, sizeof(key), stdin); 
      key[strcspn(key, "\n")] = '\0';
      int messageLength = strlen(message);
      encrypt(message, key, encryptedMessage, messageLength); 
      printf("\nOriginal Message: %s\n", message); 
      printf("Encrypted Message (in Hex): "); 
      for (int i = 0; i < messageLength; i++)  
      { 
          printf("%02X ", (unsigned char)encryptedMessage[i]); 
      } 
      printf("\n");
      decrypt(encryptedMessage, key, decryptedMessage, messageLength); 
      printf("Decrypted Message: %s\n", decryptedMessage); 
  
      return 0; 
  }
```
## OUTPUT:
<img width="803" height="307" alt="image" src="https://github.com/user-attachments/assets/de61eb5a-0276-4b12-8d07-134a07f3872e" />

## Result:
The program implementing the Data Encryption Standard (DES) for encryption and decryption	has	been	successfully	executed,	and	the	results	have	been	verified.
