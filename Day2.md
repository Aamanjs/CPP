## Practice Questions

Q1. Write a C++ program to demonstrate the operations on pointers.

```cpp
#include <iostream>
using namespace std;

int main(){

    int i = 5;
    int j = 6;
    int k = 7;
    
    int l;

    int *ipt;

    ipt = &i;
    

    cout << "i = " << i << endl;
    cout << "ipt = " << ipt << endl;
    cout << "&i = " << &i << endl;
    cout << "&ipt = " << &ipt << endl;
    cout << "*ipt = " << *ipt << endl; 

    cout << "\nipt + 1 = " << ipt+1 ;
    cout << "\n*(ipt + 1) = " << *(ipt + 1); 
    cout << "\n*ipt + 1 = " << *ipt+2; 

    cout << "\n*ipt++ = " << *ipt++;
    cout << "\n*++iptr = "  << *++ipt;
}

```
```text
Output:-
i = 5
ipt = 0x61ff04
&i = 0x61ff04
&ipt = 0x61ff00
*ipt = 5

ipt + 1 = 0x61ff08
*(ipt + 1) = 6
*ipt + 1 = 7
*ipt++ = 5
*++iptr = 6
```

Q2. Write a C++ program to swap two numbers using functions.

```cpp
#include <iostream>
using namespace std;

void Swap(int a, int b){
    int temp = a;
    a = b; 
    b = temp;

    cout << "After Swap : a = " << a << ", b = " << b << endl;
}

int main(){

    int a;
    int b; 

    cout << "Enter two numbers: ";
    cin >> a >> b;

    cout << "Before swap : a = "<< a << ", b = " << b << endl;

    Swap(a,b);

}


```

Q3.  Write a C++ program to create a menu driven calculator with the concept of switch case for menu and functions for operations.r
```cpp
#include <iostream>
using namespace std;

int add(int a, int b);
int substract(int a, int b);
int multiply(int a, int b);
int divide(int a, int b);

int main(){
    
    int num1;
    int num2; 
    int choice;

    do{
        cout << "\n---------- Calculator ----------\n" << endl;
        cout << "1. Add \n" << endl;
        cout << "2. Sub \n" << endl;
        cout << "3. Multiply \n" << endl;
        cout << "4. Divide \n" << endl;
        cout << "5. Exit \n" << endl;
        cout << "Enter your choice: ";
        cin  >> choice;

        if(choice >= 1 && choice <= 4){
            cout << "Enter two numbers: ";
            cin >> num1 >> num2;
        }

        switch(choice) {
            case 1:
                cout << "Result: " << add(num1, num2) << endl;
                break;
            case 2:
                cout << "Result: " << substract(num1, num2) << endl;
                break;
            case 3:
                cout << "Result: " << multiply(num1, num2) << endl;
                break;
            case 4:
                cout << "Result: " << divide(num1, num2) << endl;
                break;
            case 5:
                cout << "Exiting program...\n";
                break;

            default:
                cout << "Invalid choice! Please try again.\n";
        }


    } while (choice != 5);

    return 0;
}

int add(int num1, int num2){
    return num1 + num2;
}

int substract(int num1, int num2){
    return num1 - num2;
}

int multiply(int num1, int num2){
    return num1 * num2;
}

int divide(int num1, int num2){
    return num1 / num2;
}

```

Q4. Write a function to calculate factorial of a number.
```cpp
#include <iostream>
using namespace std;

int factorial(int num){

    //using for loop
    // int fact = 1;

    // for(int i=num ; i>0 ; i--){
    //     fact *= i;
    // }
    // return fact;

    //using recursion
    if(num == 0 || num == 1){
        return 1;
    }
    return num*factorial(num-1);
}

int main(){
    
    int n;
    cout << "Enter the number" << endl;
    cin >> n;

    cout << "Factorial of " << n << " is " << factorial(n);
}
```

Q5. Write a function to compute simple interest.
```cpp
#include <iostream>
using namespace std;

int SI(int p, int r, int t){

    int si = (p*r*t)/100;

    return si;

}

int main(){

    int p;
    int r;
    int t;

    cout << "Enter Principal Amount: ";
    cin >> p;

    cout << "Enter Interest Rate: ";
    cin >> r;

    cout << "Enter Time: ";
    cin >> t;

    cout << "Simple Interest is " << SI(p,r,t) << " rupees.";

}
```

Q6.  Write a function to determine the grade of a student based on marks and utilize it to calculate grade of one students.
```cpp
#include <iostream>
using namespace std;

string calcGrade(int marks);

int main(){

    int marks;
    cout << "Enter the marks: " ;
    cin >> marks;

    cout << "Student scored grade " << calcGrade(marks);

}

string calcGrade(int marks){

    if(marks >= 90){
        return "A";
    } else if(marks >= 80 && marks < 90) {
        return "B";
    } else if(marks >= 70 && marks < 80){
        return "C";
    } else if(marks >= 60 && marks < 70){
        return "D";
    } else if(marks >= 50 && marks < 60){
        return "E";
    } else {
        return "F";
    }
}
```

Q7. Write a function to print all numbers between two inputs.
```cpp
#include <iostream>
using namespace std;

void numbers(int n1, int n2);

int main(){

    int num1, num2;
    cout << "Enter number 1: " << endl;
    cin >> num1;
    cout << "Enter number 2: " << endl;
    cin >> num2;

    numbers(num1, num2);

    return 0;
}

void numbers(int n1, int n2){

    if(n1 < n2){
        
        cout << "Numbers between " << n1 << " and " << n2 << " are : ";
        for(int i=n1+1; i<n2; i++){
            cout << i << " ";
        }

    } else {
        cout << "Invalid input, Number 1 should be less than number 2!!!";
    }

}
```

Q8. Write a function to find the largest digit of a number.
```cpp
#include <iostream>
using namespace std;

int largestDigit(int num);

int main(){

    int num;
    cout << "Enter number: ";
    cin >> num;

    cout << "Largest digit in " << num << " is: " << largestDigit(num);

}

int largestDigit(int num){
    int maxDigit = 0;
    int remainder;

    while(num != 0){
        remainder = num % 10;
        if(remainder > maxDigit){
            maxDigit = remainder;
        }
        num /= 10;
    }

    return maxDigit;
}
```

Q9. Write functions for:
Reading units
Calculating bill based on slabs:
   0–100 → ₹3/unit
   101–200 → ₹4.5/unit
   200 → ₹6/unit
Adding fixed charges
Printing bill.
```cpp
#include <iostream>
using namespace std; 

int readUnits();
double calcBill(int u);
double addFixedCharges(double bill);
void printBill(int units, double total);

int main(){

    int units = readUnits();
    double bill = calcBill(units);
    double finalAmont = addFixedCharges(bill);

    printBill(units, bill);

    return 0;

}

int readUnits(){
    int u;
    cout << "Enter units consumed: ";
    cin >> u;
    return u;
}

double calcBill(int u){

    if(u>=0 && u<=100){
        return u*3;
    } else if (u>100 && u<=200){
        return (100*3)+(u-100)*4.5;
    } else {
        return (100*3) + (100*4.5) + (u-200)*6;
    }

}

double addFixedCharges(double bill){
    int charges = 50;
    return bill + charges;
}

void printBill(int units, double total){
    cout << "\n------ Electricity Bill ------" << endl;
    cout << "Units Consumed : " << units << endl;
    cout << "Total Bill     : " << total << " rupees " << endl; 
}
```
Q10. Use functions for:
checkBalance()
deposit()
withdraw()
miniStatement()
Main function should show a menu and call these functions.

```cpp
#include <iostream>
#include <string>
using namespace std;

double balance = 1000;
string lastTransaction = "No recent transactions";


void checkBalance();
void deposit();
void withdraw();
void miniStatement();


int main(){

    int choice;

    do {
        cout << "\n----- ATM Menu -----" << endl;
        cout << "1. Check Balance" << endl;
        cout << "2. Deposit" << endl;
        cout << "3. Withdraw" << endl;
        cout << "4. Mini Statement" << endl;
        cout << "5. Exit" << endl;

        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                checkBalance();
                break;

            case 2:
                deposit();
                break;

            case 3:
                withdraw();
                break;

            case 4:
                miniStatement();
                break;

            case 5:
                cout << "Exiting System!!" << endl;
                break;

            default:
                cout << "Invalid choice! Please try again." << endl;
        }
    } while (choice != 5);

    return 0;

}

void checkBalance() {
    cout << "Available Balance: " << balance << " rupees" << endl;
}

void deposit(){
    double amount;
    cout << "Enter amount to deposit: ";
    cin >> amount;

    if (amount > 0){
        balance += amount;
        lastTransaction = "Deposited " + to_string(amount);
        cout << "Amount deposited successfully!" << endl;
    } else {
        cout << "Invalid amount!" << endl;
    }
}

void withdraw(){
    double amount;
    cout << "Enter amount to withdraw: ";
    cin >> amount;

    if(amount > balance) {
        cout << "Insufficiet balance! " << endl;
    } else if (amount <= 0 ){
        cout << "Invalid amount! " << endl;
    } else {
        balance -= amount;
        lastTransaction = "Withdrawn " + to_string(amount);
        cout << "Amount withdrawn succesfully!" << endl;
    }
}

void miniStatement() {
    cout << "----- Mini Statement -----" << endl;
    cout << "Last Transaction: " << lastTransaction << endl;
    cout << "Current Balance: ₹" << balance << endl;
}
```
