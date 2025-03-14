# EX-4 Vigenere Cipher
Vigenere Cipher using with different key values

# AIM:

To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:

### Step 1:

Design of Vigenere Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

Testing algorithm with different key values. 
ALGORITHM DESCRIPTION:
The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a repeating keyword.



## PROGRAM:
```
Developed by: Karan A
Register number: 212223230099
```
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void encrypt(char *text, char *key) {
    int textLen = strlen(text), keyLen = strlen(key);
    for (int i = 0, j = 0; i < textLen; i++) {
        if (isalpha(text[i])) {
            char base = isupper(text[i]) ? 'A' : 'a';
            text[i] = (text[i] - base + (tolower(key[j % keyLen]) - 'a')) % 26 + base;
            j++;
        }
    }
}

void decrypt(char *text, char *key) {
    int textLen = strlen(text), keyLen = strlen(key);
    for (int i = 0, j = 0; i < textLen; i++) {
        if (isalpha(text[i])) {
            char base = isupper(text[i]) ? 'A' : 'a';
            text[i] = (text[i] - base - (tolower(key[j % keyLen]) - 'a') + 26) % 26 + base;
            j++;
        }
    }
}

int main() {
    char text[100], key[100];
    printf("Simulation of Vigenere Cipher\n");
    printf("Enter text: ");
    fgets(text, sizeof(text), stdin);
    text[strcspn(text, "\n")] = 0;
    printf("Enter key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = 0;
    
    encrypt(text, key);
    printf("Encrypted text: %s\n", text);
    
    decrypt(text, key);
    printf("Decrypted text: %s\n", text);
    
    return 0;
}
```
## OUTPUT:

![image](https://github.com/user-attachments/assets/1efde9ba-4edd-419c-93df-3811b947e055)

## RESULT:
The program is executed successfully
