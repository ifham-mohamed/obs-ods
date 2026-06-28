
2024-08-10 21:28

Status:

Tags: #UOM #L2S2-S4 #CA-CO 


# CO&CA - Number System

## Binary, Decimal Number System, and Conversions


*The world of numbers is vast and diverse, with different systems and ways of representing quantities. Two commonly used number systems are binary and decimal. In this text, we will explore the binary and decimal number systems and discuss how to convert between them.*

### Binary Number System

The binary number system is a numerical system that uses only two digits: 0 and 1. These two digits are called bits. Each bit represents an "on" or "off" state, which is the foundation of digital computing. Binary numbers are used extensively in computer science and information technology. 

In the binary system, each digit has a place value. The rightmost digit represents the value 1, the next digit to the left represents the value 2, then 4, 8, 16, and so on. To express a number, we sum the values of the digits with a 1 in them. For example, the binary number 1011 represents the decimal value: 

``` math
(1 x 2^3) + (0 x 2^2) + (1 x 2^1) + (1 x 2^0) = 8 + 0 + 2 + 1 = 11
```

### Decimal Number System


The decimal number system, also known as the base-10 system, is the most commonly used number system in our daily lives. It uses ten digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9. Each digit represents a value according to its position in a number. 

Decimal numbers also have place values. The rightmost digit represents the unit place, the next digit to the left represents the tens place, then hundreds, thousands, and so on. To express a number, we sum the values of the digits multiplied by the corresponding power of 10. For example, the decimal number 365 represents the value: 

```math
(3 x 10^2) + (6 x 10^1) + (5 x 10^0) = 300 + 60 + 5 = 365
```


### Converting Binary to Decimal


Converting a binary number to a decimal number is a straightforward process. We can use the place value system to determine the decimal equivalent of each digit. 

Let's take the binary number 10101 as an example. To convert it to a decimal number, we multiply each digit by the corresponding power of 2 and then sum the results: 

```math
(1 x 2^4) + (0 x 2^3) + (1 x 2^2) + (0 x 2^1) + (1 x 2^0) = 16 + 0 + 4 + 0 + 1 = 21 
```

Therefore, the binary number 10101 is equivalent to the decimal number 21.


### Converting Decimal to Binary


Converting a decimal number to a binary number can be a bit more challenging but follows a systematic approach. We repeatedly divide the decimal number by 2 and record the remainder until the quotient becomes 0. 

For instance, let's convert the decimal number 37 to binary. We divide 37 by 2 to get a quotient of 18 and a remainder of 1. We continue dividing 18 by 2 to get a quotient of 9 and a remainder of 0. We repeat this process: 

```math
9 divided by 2 equals 4 with a remainder of 1. 
4 divided by 2 equals 2 with a remainder of 0. 
2 divided by 2 equals 1 with a remainder of 0. 
1 divided by 2 equals 0 with a remainder of 1. 
```

The remainders, read in reverse order, give us the binary representation: 100101. Therefore, the decimal number 37 is equivalent to the binary number 100101.


# Reference