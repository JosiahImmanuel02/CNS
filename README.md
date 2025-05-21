## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


## PROGRAM :-
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char plain[100], cipher[100];
    int key, i, length;

    printf("Enter the plain text: ");
    scanf("%s", plain);

    printf("Enter the key value: ");
    scanf("%d", &key);

    printf("\nPLAIN TEXT: %s", plain);
    printf("\nENCRYPTED TEXT: ");

    length = strlen(plain);
    for (i = 0; i < length; i++) {
        cipher[i] = plain[i] + key;
        if (isupper(plain[i]) && cipher[i] > 'Z') {
            cipher[i] -= 26;
        }
        if (islower(plain[i]) && cipher[i] > 'z') {
            cipher[i] -= 26;
        }
        printf("%c", cipher[i]);
    }

    cipher[length] = '\0';

    printf("\nDECRYPTED TEXT: ");
    for (i = 0; i < length; i++) {
        plain[i] = cipher[i] - key;
        if (isupper(cipher[i]) && plain[i] < 'A') {
            plain[i] += 26;
        }
        if (islower(cipher[i]) && plain[i] < 'a') {
            plain[i] += 26;
        }
        printf("%c", plain[i]);
    }

    plain[length] = '\0';

    return 0;
}
```



## OUTPUT :-

![Screenshot 2025-03-19 090622](https://github.com/user-attachments/assets/b9c00bb8-c6eb-4d78-966c-83e3db1ecb4d)

## Result

The program is executed successfully
