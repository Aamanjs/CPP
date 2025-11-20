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
Q4. Increment i directly (i++) and indirectly ((*iptr)++). Compare results.
```cpp

```

