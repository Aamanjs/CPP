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

