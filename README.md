# C-Program-for-Octal-To-Decimal-Conversion

Octal to Decimal Conversion in C
Here, in this section, we will discuss the C program for Octal to Decimal conversion in C. Octal to Decimal in C happens with the principle that a decimal number can be attained by multiplying every digit of octal number with a power of 2 and adding each multiplication outcome. The power of the integer starts from 0 and counts to n-1 where n is assumed as the overall digits of integers in octal numbers.

(653)8 = 6 * 82 + 5 * 81 + 3 * 80
384 + 40 + 3 = (427)10
Octal to Decimal in C
Algorithm:-
Initialize i = 0, decimal = 0, base = 8
Extract the last digit (digit = num% 10)
Calculate decimal equivalent of this digit
Add it to decimal variable
decimal += digit * pow(8 ,i);
Reduce the number (num /= 10
increment i value
Octal to Decimal Conversion in C Program New
C program for Octal to Decimal Conversion
Code in C
<
Run
// C Program to convert octal to decimal
#include<stdio.h>
#include<math.h>

// function to convert octal to decimal
int convert(long long num)
{
    int i = 0, decimal = 0;
    
    // will only work for bases 2 - 10
    int base = 8;
    
    //converting octal to decimal
    while (num!=0)
    {
        int digit = num % 10;
        decimal += digit * pow(base, i);

        num /= 10;
        i++;
    }
    return decimal;
}

//main program
int main()
{
    // long used rather than int to store large values
    long long octal;
    
    printf("Enter Octal Number: ");
    scanf("%lld", &octal);
    
    printf("Decimal: %lld", convert(octal));
    
    return 0;
}
Output
Enter octal number: 653
427
