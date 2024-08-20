#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>

// Function to convert decimal to binary
void decimalToBinary(int decimal) {
    if (decimal == 0) {
        printf("0");
        return;
    }

    int binary[32];
    int index = 0;

    while (decimal > 0) {
        binary[index++] = decimal % 2;
        decimal /= 2;
    }

    // Print binary in reverse order
    for (int i = index - 1; i >= 0; i--) {
        printf("%d", binary[i]);
    }
}

// Function to convert binary to decimal
int binaryToDecimal(const char *binary) {
    int decimal = 0;
    int length = strlen(binary);

    for (int i = 0; i < length; i++) {
        if (binary[length - i - 1] == '1') {
            decimal += (int)pow(2, i);
        }
    }

    return decimal;
}

// Function to convert decimal to hexadecimal
void decimalToHexadecimal(int decimal) {
    if (decimal == 0) {
        printf("0");
        return;
    }

    char hex[100];
    int index = 0;

    while (decimal > 0) {
        int remainder = decimal % 16;
        if (remainder < 10) {
            hex[index++] = remainder + '0';
        } else {
            hex[index++] = remainder - 10 + 'A';
        }
        decimal /= 16;
    }

    // Print hexadecimal in reverse order
    for (int i = index - 1; i >= 0; i--) {
        printf("%c", hex[i]);
    }
}

// Function to convert hexadecimal to decimal
int hexadecimalToDecimal(const char *hex) {
    int decimal = 0;
    int length = strlen(hex);

    for (int i = 0; i < length; i++) {
        char c = hex[length - i - 1];
        int value;

        if (c >= '0' && c <= '9') {
            value = c - '0';
        } else if (c >= 'A' && c <= 'F') {
            value = c - 'A' + 10;
        } else {
            // Invalid hexadecimal character
            return -1;
        }

        decimal += value * (int)pow(16, i);
    }

    return decimal;
}

int main() {
    int decimal;
    char binary[33];
    char hex[100];

    // Example: Decimal to Binary
    decimal = 29;
    printf("Decimal to Binary: %d = ", decimal);
    decimalToBinary(decimal);
    printf("\n");

    // Example: Binary to Decimal
    strcpy(binary, "11101");
    printf("Binary to Decimal: %s = %d\n", binary, binaryToDecimal(binary));

    // Example: Decimal to Hexadecimal
    decimal = 255;
    printf("Decimal to Hexadecimal: %d = ", decimal);
    decimalToHexadecimal(decimal);
    printf("\n");

    // Example: Hexadecimal to Decimal
    strcpy(hex, "FF");
    printf("Hexadecimal to Decimal: %s = %d\n", hex, hexadecimalToDecimal(hex));

    return 0;
}
