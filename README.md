# Decimal-To-Binary-Conversion-C-Program

Decimal to Binary Conversion in C
Here, on this page, we will discuss Decimal to Binary conversion in C. The C program to convert a decimal number into a binary number is done by counting the number of 1s. Let’s have a look on different ways for Decimal to Binary in C.

Decimal to Binary in C Program
Different Methods Covered in this post
Method 1: Using an additional array to store Binary bits
Method 2: Using mathematical operations to generate binary equivalent.
Method 1
C Program to Convert Decimal to Binary
Method 1 Code
Run
// Decimal to binary conversion using an Array in C
#include<stdio.h>
 
void convert(int num)
{
    // creating an array to store binary equivalent
    int binaryArray[32];
 
    // using i to store binary bit at given array position
    int i = 0;
    while (num > 0) {
 
        // resultant remainder is stored at given array position
        binaryArray[i] = num % 2;
        num = num / 2;
        i++;
    }
 
    // printing binary array in reverse order
    for (int j = i - 1; j >= 0; j--)
        printf("%d",binaryArray[j]);
}
 
int main()
{
    int n = 11;
    convert(n);
    return 0;
}
Output
1011
Related Pages
Octal to Decimal conversion

Hexadecimal to Decimal conversion

Decimal to Binary conversion

Decimal to Octal Conversion

Decimal to Hexadecimal Conversion

Binary to Octal conversion

Method 2
In this method rather than using an array, we will try to form the number using mathematical operations.

C Program to Convert Decimal to Binary method 2
Method 2 Code
Run
#include<stdio.h>

void convert(int num)
{
    // long long used to store large binary values
    long long binary = 0;
    int rem, i = 1;
    
    while(num!=0)
    {
        rem = num % 2;
        num /= 2;
        binary += rem * i;
        
        // moving to next position ex: units -> tens
        i *= 10;
    }
    printf("%d",binary);
}
 
int main()
{
    int decimal_num = 14;
    convert(decimal_num);
    return 0;
}
Output
1110
