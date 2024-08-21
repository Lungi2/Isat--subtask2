{
    int decimal;
    char binary[33];
    char hex[100];

    // Example: Decimal to Binary
    decimal = 67; // Changed from 29 to 67
    printf("Decimal to Binary: %d = ", decimal);
    decimalToBinary(decimal);
    printf("\n");

    // Example: Binary to Decimal
    strcpy(binary, "1000011"); // Changed from "11101" to "1000011"
    int decimalFromBinary = binaryToDecimal(binary);
    if (decimalFromBinary != -1) {
        printf("Binary to Decimal: %s = %d\n", binary, decimalFromBinary);
    }

    // Example: Decimal to Hexadecimal
    decimal = 439; // Changed from 255 to 439
    printf("Decimal to Hexadecimal: %d = ", decimal);
    decimalToHexadecimal(decimal);
    printf("\n");

    // Example: Hexadecimal to Decimal
    strcpy(hex, "1B7"); // Changed from "FF" to "1B7"
    int decimalFromHex = hexadecimalToDecimal(hex);
    if (decimalFromHex != -1) {
        printf("Hexadecimal to Decimal: %s = %d\n", hex, decimalFromHex);
    }

    return 0;
}  
