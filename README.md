## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-
```
#include <stdio.h>
#include <ctype.h>
void caesar_encrypt(char *text, int key) {
for (int i = 0; text[i] != '\0'; i++) {
if (isalpha(text[i])) {
char base = isupper(text[i]) ? 'A' : 'a';
text[i] = ((text[i] - base + key) % 26 + 26) % 26 + base;
}
}
}
void caesar_decrypt(char *text, int key) {
caesar_encrypt(text, -key); // Decryption is just encryption with negative key
}
int main() {
char message[1000];
int key;
printf("Enter the message to encrypt: ");
fgets(message, sizeof(message), stdin);
printf("Enter the Caesar Cipher key (an integer): ");
scanf("%d", &key);
caesar_encrypt(message, key);
printf("Encrypted Message: %s", message);
caesar_decrypt(message, key);
printf("Decrypted Message: %s", message);
return 0;
}
```



OUTPUT :-
![image](https://github.com/user-attachments/assets/5577af7a-9a01-4ce1-ae47-728ea4c25ff8)

