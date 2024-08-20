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

