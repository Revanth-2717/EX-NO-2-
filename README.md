## EX. NO:2 IMPLEMENTATION OF PLAYFAIR CIPHER

 

## AIM:
 
To write a C program to implement the Playfair Substitution technique.

## DESCRIPTION:

The Playfair cipher starts with creating a key table. The key table is a 5×5 grid of letters that will act as the key for encrypting your plaintext. Each of the 25 letters must be unique and one letter of the alphabet is omitted from the table (as there are 25 spots and 26 letters in the alphabet).

To encrypt a message, one would break the message into digrams (groups of 2 letters) such that, for example, "HelloWorld" becomes "HE LL OW OR LD", and map them out on the key table. The two letters of the diagram are considered as the opposite corners of a rectangle in the key table. Note the relative position of the corners of this rectangle. Then apply the following 4 rules, in order, to each pair of letters in the plaintext:
1.	If both letters are the same (or only one letter is left), add an "X" after the first letter
2.	If the letters appear on the same row of your table, replace them with the letters to their immediate right respectively
3.	If the letters appear on the same column of your table, replace them with the letters immediately below respectively
4.	If the letters are not on the same row or column, replace them with the letters on the same row respectively but at the other pair of corners of the rectangle defined by the original pair.
5.  lies on the same row as the first letter of the plaintext pair.
6.  .To decrypt, use the INVERSE (opposite) of the last 3 rules, and the 1st as-is (dropping any extra "X"s, or "Q"s that do not make sense in the final message when finished).defined by the original pair. The order is important – the first letter of the encrypted pair is the one that lies on the same row as the first letter of the plaintext pair. To decrypt, use the INVERSE (opposite) of the last 3 rules, and the 1st as-is (dropping any extra "X"s, or "Q"s that do not make sense in the final message when finished). 
 
## ALGORITHM:

STEP-1: Read the plain text from the user.
STEP-2: Read the keyword from the user.
STEP-3: Arrange the keyword without duplicates in a 5*5 matrix in the row order and fill the remaining cells with missed out letters in alphabetical order. Note that ‘i’ and ‘j’ takes the same cell.
STEP-4: Group the plain text in pairs and match the corresponding corner letters by forming a rectangular grid.
STEP-5: Display the obtained cipher text.




Program:
```
#include <stdio.h>  
#include <string.h>  
int main()  
{     int key;     char 
s[1000];  
printf("Enter a plaintext to encrypt:\n");     
fgets(s, sizeof(s), stdin);     
key:\n");     
printf("Enter 
scanf("%d", &key);  
int n = strlen(s);  
for (int i = 0; i < n; i++)   
    {         char c = s[i];         if (c 
>= 'a' && c <= 'z')   
        {             s[i] = 'a' + (c - 'a' + key) % 
26;         }  
        else if (c >= 'A' && c <= 'Z')  
        {             s[i] = 'A' + (c - 'A' + key) % 
26;  
        }  
    }  
    printf("Encrypted message: %s\n", s);  
  
    for (int i = 0; i < n; i++)  
    {         char c = s[i];         if (c 
>= 'a' && c <= 'z')   
        {             s[i] = 'a' + (c - 'a' - key + 26) % 
26;   
        }  
        else if (c >= 'A' && c <= 'Z')  
        {             s[i] = 'A' + (c - 'A' - key + 26) % 
26;   
        }  
    }  
    printf("Decrypted message: %s\n", s);  
  
return 0;  
}
```




Output:

![image](https://github.com/user-attachments/assets/f35d336b-dce3-4282-9346-45b2ee37e85f)

Result:
Thus the program for playfair cipher is executed successfully.
