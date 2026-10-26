# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```

#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char text[100];
    int shift, i;

    printf("Enter the message: ");
    fgets(text, sizeof(text), stdin);

    printf("Enter the shift value: ");
    scanf("%d", &shift);

    shift = ((shift % 26) + 26) % 26;

    for (i = 0; text[i] != '\0'; i++) {
        if (text[i] >= 'A' && text[i] <= 'Z') {
            text[i] = (text[i] - 'A' + shift) % 26 + 'A';
        } else if (text[i] >= 'a' && text[i] <= 'z') {
            text[i] = (text[i] - 'a' + shift) % 26 + 'a';
        }
    }

    printf("Encrypted message: %s", text);

    for (i = 0; text[i] != '\0'; i++) {
        if (text[i] >= 'A' && text[i] <= 'Z') {
            text[i] = (text[i] - 'A' - shift + 26) % 26 + 'A';
        } else if (text[i] >= 'a' && text[i] <= 'z') {
            text[i] = (text[i] - 'a' - shift + 26) % 26 + 'a';
        }
    }

    printf("Decrypted message: %s", text);

    return 0;
}

```
## OUTPUT:
<img width="1917" height="780" alt="image" src="https://github.com/user-attachments/assets/458edec2-9186-42bd-8c66-1160899426e0" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
