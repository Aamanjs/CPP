# Practice Questions

1. Greatest of Three Numbers
Read three integers and print the largest.
```cpp
#include <iostream>

using namespace std;

int main() {
    
    int a,b, c;
    
    cout << "Enter 3 numbers: ";
    cin >> a >> b >> c;
    
    if(a>b && a>c){
        cout << a << " is largest number.";
    } else if (b>a && b>c){
        cout << b << " is largest number.";
    } else {
        cout << c << " is largest number.";
    }

}

```
2. Sum of First N Natural Numbers
Use a while loop to compute the sum of first N natural numbers.
```cpp
#include <iostream>

using namespace std;

int main() {
    
    int a;
    
    cout << "Enter n numbers: ";
    cin >> a; 
    
    int sum = 0;
    for(int i=0; i<=a; i++){
        sum += i;
    }
    
    cout << "sum of "<< a << " numbers is "<< sum;

}
```
3. Count Digits in a Number
Input a number and print how many digits it has.
```cpp
#include <iostream>
using namespace std;

int countOfDigits(int num){
    
    if(num == 0){
        return 1;
    }
    
    int count = 0;
    
    while(num != 0){
        num /= 10;
        count++;
    }
    return count;
    
}

int main(){
    
    int a;
    
    cout << "Enter the number: ";
    cin >> a;
    
    cout << "Total digits: " << countOfDigits(a) ;
}
```
4. Factorial using Loop
Compute factorial of a number using a for loop.
```cpp
#include <iostream>
using namespace std;

int factorial(int num){
    
    int fact = 1;
    for(int i=num; i>0; i--){
        fact *= i;
    }
    return fact;
    
}

int main(){
    
    int a;
    
    cout << "Enter the number: ";
    cin >> a;
    
    cout << "Factorial of " << a << " is " << factorial(a) ;
}
```

5. Armstrong Number (for any number of digits)
Check whether a number is Armstrong sum of cube of digits is the number(e.g., 153, 9474).
```cpp
#include <iostream>
using namespace std;

int power(int base, int exp){
    int result = 1;
    for(int i=0; i<exp; i++){
        result *=  base;
    }
    return result;
}

bool isArmstrong(int num){
    int original = num;
    int digits = 0;

    //count digit
    int temp = num;
    while(temp != 0){
        temp /= 10;
        digits++;
    }

    //sum of powers
    int sum = 0;
    temp = num;
    while(temp != 0){
        int digit = temp % 10;
        sum += power(digit, digits);
        temp /= 10;
    }
    return sum == original;

}

int main(){

    int num;

    cout << "Enter number: ";
    
    cin >> num;

    if(isArmstrong(num)){
        cout << num << " is Armstrong number";
    } else {
        cout << num << " is not Armstrong number";
    }
}
```
6. Frequency of Each Digit
Print how many times each digit (0–9) occurs in a number.
```cpp
#include <iostream>
using namespace std;

int main(){

    int n;
    cout << "Enter the size of the array: ";
    cin >> n;

    int* arr =  new int[n] ;

    cout << "Enter values: \n";
    for (int i=0; i<n; i++){
        cin >> arr[i];
    }

    cout << "Data: ";
    for(int i=0; i<n; i++){
        cout << arr[i] << " ";
    }
    cout << endl;

    int value;
    cout << "Enter the value: ";
    cin >> value;

    int count = 0;
    for(int i=0; i<n; i++){
        if(arr[i] == value){
            count++;
        }
    }
    cout << "The frequency of " << value << " is " << count;

    return 0; 
}
```
7. Count the number of even and odd digits in a number:
Input: 4523212
Output: Even digits=4 Odd digits=3
```cpp
#include <iostream>
using namespace std;

int main() {
    long long num; //supports large number
    cout << "Enter a number: ";
    cin >> num;

    int evenCount = 0, oddCount = 0;

    while(num > 0){
        int digit = num % 10;
        if( digit % 2 == 0){
            evenCount++;
        } else {
            oddCount++;
        }
        num /= 10;
    }

    cout << "Even digits: " << evenCount << endl;
    cout << "Odd digits: " << oddCount;

    return 0;
}
```
8. Print Squares of a numbers from 1 to N where N is user input
Input: 5
Output: 1 4 9 16 25
```cpp
#include <iostream>
using namespace std;

int main(){

    int n;
    cout << "Input: ";
    cin >> n;

    int* arr = new int[n];

    int v = 1;
    for(int i=0; i<n; i++){
        arr[i] = v++;
    }

    int* sqr = new int[n];
    for(int i=0; i<n; i++){
        sqr[i] = arr[i] * arr[i];
    }

    cout << "Output: ";
    for(int i=0; i<n; i++){
        cout << sqr[i] << " ";
    }

}
```
9. Find power of a number using loop (a^b)
Input: a=2 b=5
Output: 32
```cpp
#include <iostream>
using namespace std;

int main(){

    int a;
    int b; 

    cout << "Input: a=" ;
    cin >> a;
    cout << " b=";
    cin >> b;

    int pow = 1;
    for(int i=0; i<b; i++){
        pow *= a;
    }

    cout << "Output: " << pow;

}
```
10. Find all the numbers divisible by 3 between 1 to N
Input: 20
Output: 3 6 9 12 15 18
```cpp
#include <iostream>
using namespace std;

int main(){

    int n;
    cout << "Input: ";
    cin >> n;

    int* arr = new int[n];
    for(int i=0; i<n; i++){
        arr[i] = i+1;
    }

    cout << "Output: ";
    for(int i=0; i<n; i++){
        if(arr[i] % 3 == 0){
            cout << arr[i] << " ";
        }
    }
    cout << endl;

    
}
```
11. Print the factors of a number
Input: 12
Output: 1 2 3 4 6 12
```cpp
#include <iostream>
using namespace std;

int main(){

    int a;
    cout << "Input: ";
    cin >> a;

    int* arr = new int[a];
    for(int i=0; i<a; i++){
        arr[i] = i+1;
    }

    cout << "Output: ";
    for(int i=0; i<a; i++){
        if(a % arr[i] == 0){
            cout << arr[i] << " ";
        }
    }

}
```
12. Find the GCD of two numbers
Input: 12 18
Output: 6
```cpp
#include <iostream>
using namespace std;

// euclidean theorem
int gcd(int a, int b){
    while (b!=0){
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

int main(){

    int a, b;
    cout << "Input: ";
    cin >> a >> b;

    cout << "Output: " << gcd(a, b) << endl;
    
}
```





