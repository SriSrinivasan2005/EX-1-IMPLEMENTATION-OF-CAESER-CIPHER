## Exp : 1 IMPLEMENTATION OF CAESER CIPHER 
## NAME : SRI SRINIVASAN K
## REGISTER NUMBER : 212224220104
## AIM: 
To encrypt and decrypt the given message by using Caeser Cipher encryption algorithm. 
  
 ## ALGORITHM: 
1. Calculate the length of the plaintext. 
2. For each character in the plaintext:  
 a. Add the key to the character to get the cipher character.  
 b. If the result exceeds 'Z' for uppercase or 'z' for lowercase, subtract 26 to wrap within the  alphabet.  
3. Display the encrypted text.  
4. For decryption, subtract the key from each character of the ciphertext.  
 a. If the result is less than 'A' for uppercase or 'a' for lowercase, add 26 to wrap within the  alphabet.  
5. Display the decrypted text.  

## PROGRAM: 
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char plain[100], cipher[100];
    int key, i, length;

    printf("Enter the plain text: ");
    fgets(plain, sizeof(plain), stdin); 

    plain[strcspn(plain, "\n")] = '\0';

    printf("Enter the key value: ");
    scanf("%d", &key);

    printf("\nPLAIN TEXT: %s", plain);
    printf("\nENCRYPTED TEXT: ");

    length = strlen(plain);
    for (i = 0; i < length; i++)
    {
        if (isalpha(plain[i]))
        {
            cipher[i] = plain[i] + key;

            if (isupper(plain[i]) && cipher[i] > 'Z')
                cipher[i] -= 26;

            if (islower(plain[i]) && cipher[i] > 'z')
                cipher[i] -= 26;
        }
        else
        {
            cipher[i] = plain[i];  
        }
        printf("%c", cipher[i]);
    }

    cipher[length] = '\0';

    printf("\nDECRYPTED TEXT: ");
    for (i = 0; i < length; i++)
    {
        if (isalpha(cipher[i]))
        {
            plain[i] = cipher[i] - key;

            if (isupper(cipher[i]) && plain[i] < 'A')
                plain[i] += 26;

            if (islower(cipher[i]) && plain[i] < 'a')
                plain[i] += 26;
        }
        else
        {
            plain[i] = cipher[i];  
        }

        printf("%c", plain[i]);
    }

    plain[length] = '\0';
    return 0;
}

```
## OUTPUT: 
<img width="816" height="337" alt="image" src="https://github.com/user-attachments/assets/de8fe665-fed5-45d9-8f7e-a7290450315b" />

## RESULT: 
The program implementing the Caesar cipher for encryption and decryption has been successfully  executed, and the results have been verified.
