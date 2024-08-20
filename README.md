# Isat--subtask2
#include <iostream>
using namespace std;

void decToBinary(int n) {
    int binaryNum[32];
    int i = 0;
    while (n > 0) {
        binaryNum[i] = n % 2;
        n = n / 2;
        i++;
    }
    for (int j = i - 1; j >= 0; j--)
        cout << binaryNum[j];
}

int main() {
    int n;
    cout << "Enter a decimal number: ";
    cin >> n;
    cout << n << " in decimal = ";
    decToBinary(n);
    cout << " in binary" << endl;
    return 0;
}

#include <iostream>
#include <cmath>
using namespace std;

int binToDecimal(long long n) {
    int decimalNum = 0, i = 0, rem;
    while (n != 0) {
        rem = n % 10;
        n /= 10;
        decimalNum += rem * pow(2, i);
        ++i;
    }
    return decimalNum;
}

int main() {
    long long n;
    cout << "Enter a binary number: ";
    cin >> n;
    cout << n << " in binary = " << binToDecimal(n) << " in decimal" << endl;
    return 0;
}

#include <iostream>
#include <cmath>
#include <string>
using namespace std;

// Function 1: Decimal to Binary
string decToBinary(int n) {
    string binary = "";
    while (n > 0) {
        binary = to_string(n % 2) + binary;
        n = n / 2;
    }
    return binary;
}
// Function 2: Binary to Decimal
int binToDecimal(string n) {
    int decimalNum = 0;
    int base = 1;
    int len = n.length();
    for (int i = len - 1; i >= 0; i--) {
        if (n[i] == '1')
            decimalNum += base;
        base = base * 2;
    }
    return decimalNum;
}
// Function 3: Decimal to Hexadecimal
string decToHex(int n) {
    string hex = "";
    char hexChars[] = {'0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'A', 'B', 'C', 'D', 'E', 'F'};
    while (n > 0) {
        hex = hexChars[n % 16] + hex;
        n = n / 16;
    }
    return hex;
}
// Function 4: Hexadecimal to Decimal
int hexToDecimal(string hex) {
    int decimalNum = 0;
    int base = 1;
    int len = hex.length();
    for (int i = len - 1; i >= 0; i--) {
        if (hex[i] >= '0' && hex[i] <= '9') {
            decimalNum += (hex[i] - 48) * base;
        } else if (hex[i] >= 'A' && hex[i] <= 'F') {
            decimalNum += (hex[i] - 55) * base;
        }
        base = base * 16;
    }
    return decimalNum;
}

int main() {
    int decimal;
    string binary, hex;
    // Decimal to Binary
    cout << "Enter a decimal number: ";
    cin >> decimal;
    cout << decimal << " in decimal = " << decToBinary(decimal) << " in binary" << endl;

    // Binary to Decimal
    cout << "Enter a binary number: ";
    cin >> binary;
    cout << binary << " in binary = " << binToDecimal(binary) << " in decimal" << endl;

    // Decimal to Hexadecimal
    cout << "Enter a decimal number: ";
    cin >> decimal;
    cout << decimal << " in decimal = " << decToHex(decimal) << " in hexadecimal" << endl;

    // Hexadecimal to Decimal
    cout << "Enter a hexadecimal number: ";
    cin >> hex;
    cout << hex << " in hexadecimal = " << hexToDecimal(hex) << " in decimal" << endl;

    return 0;
}
 



