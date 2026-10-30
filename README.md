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

int main()
{
    char text[100], encrypted[100], decrypted[100];
    int key, i;

    printf("Enter your name: ");
    scanf("%s", text);

    printf("Enter key: ");
    scanf("%d", &key);

    key = key % 26;

    // Encryption
    for(i = 0; text[i] != '\0'; i++)
    {
        if(isupper(text[i]))
            encrypted[i] = (text[i] - 'A' + key) % 26 + 'A';
        else if(islower(text[i]))
            encrypted[i] = (text[i] - 'a' + key) % 26 + 'a';
        else
            encrypted[i] = text[i];
    }
    encrypted[i] = '\0';

    // Decryption
    for(i = 0; encrypted[i] != '\0'; i++)
    {
        if(isupper(encrypted[i]))
            decrypted[i] = (encrypted[i] - 'A' - key + 26) % 26 + 'A';
        else if(islower(encrypted[i]))
            decrypted[i] = (encrypted[i] - 'a' - key + 26) % 26 + 'a';
        else
            decrypted[i] = encrypted[i];
    }
    decrypted[i] = '\0';

    printf("\nOriginal Text: %s", text);
    printf("\nEncrypted Text: %s", encrypted);
    printf("\nDecrypted Text: %s\n", decrypted);

    return 0;
}

```
## OUTPUT:
<img width="922" height="362" alt="image" src="https://github.com/user-attachments/assets/892bf264-f2dd-4678-bcc9-dedb9e72677e" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
