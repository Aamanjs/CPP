```txt
Question 1

Create a base class Shape with a virtual method area(). Then, create two derived classes, Circle and
Rectangle, each overriding area() to compute and return their respective areas.

In Circle, the area should be calculated as π * radius ** 2.
In Rectangle, the area should be calculated as length * breadth.
Demonstrate dynamic binding by creating an array of Shape* pointers and call the area() method for
each shape.
```
```cpp
#include <iostream>
using namespace std;

class Shape
{
    public:
        virtual double area()
        {
            return 0;
        }

        virtual ~Shape() {}
};

class Circle : public Shape
{
    private:
        double radius;

    public:
        Circle(double r)
        {
            radius = r;
        }

        double area() override
        {
            return 3.14 * radius * radius;
        }
};

class Rectangle : public Shape
{
    private:
        double length, breadth;

    public:
        Rectangle(double l, double b)
        {
            length = l;
            breadth = b;
        }

    double area() override
    {
        return length * breadth;
    }
};

int main()
{
    int n;

    cout << "Enter the number of shapes to be entered: ";
    cin >> n;

    Shape* shapes[2];

    int r;
    int l,b;

    cout << "Enter the radius of the circle: " << endl;
    cin >> r;

    cout << "Enter the length and breadth of the Rectangle: " << endl;
    cin >> l >> b;

    shapes[0] = new Circle(r);
    shapes[1] = new Rectangle(l,b);

    for(int i=0; i<=n; i++){
        cout << "Area: " << shapes[i]->area() << endl;
    }

    //Free memory
    for(int i=0; i<n; i++){
        delete shapes[i];
    }

}
```

```txt
Question 2

Implement Integer class by overloading the comparison operators ==, !=, <, and > along with necessary
constructors.

Implement the == operator to compare two Integer objects for equality.
Implement the != operator to check if two Integer objects are not equal.
Implement the < and > operators to compare two Integer objects to see which one is greater or smaller.

Example usage:
Integer num1(10), num2(20);
if (num1 < num2) {
cout << "num1 is smaller than num2" << endl;
}
if (num1 == num2) {
'cout << "num1 is equal to num2" << 'endl;
}
```

```cpp
#include <iostream>
using namespace std;

class Integer{
    private:
        int value;

    public:
        Integer()
        {
            value = 0;
        }

        Integer(int v)
        {
            value = v;
        }

        bool operator==(const Integer& other) const
        {
            return value == other.value;
        }

        bool operator!=(const Integer& other) const 
        {
            return value != other.value;
        }

        bool operator>(const Integer& other) const
        {
            return value > other.value;
        }

        bool operator<(const Integer& other) const
        {
            return value < other.value;
        }
};

int main()
{
    int n1;
    int n2;

    cout << "Enter num1 and num2" << endl;
    cin >> n1 >> n2; 

    Integer num1(n1), num2(n2);

    if(num1 == num2)
    {
        cout << "num1 is equal to num2" << endl;
    } else {
        cout << "num1 is not equal to num2" << endl;
    }

    if(num1 > num2)
    {
        cout << "num1 is greater than num2" << endl;
    }

    if(num1 < num2)
    {
        cout << "num1 is less than num2" << endl;
    }

    return 0;
}
```
```txt
Question 3

Create two base classes Engine and Vehicle that have constructors that print "Engine initialized" and
"Vehicle initialized", respectively.
Create a derived class Car that inherits from both Engine and Vehicle and has a constructor that prints
"Car initialized".
Demonstrate how constructors are called when an object of Car is created 
```
```cpp
#include<iostream>
using namespace std;

class Engine
{
    public:
        Engine()
        {
            cout << "Engine initialized" << endl;
        }
};

class Vehicle 
{
    public:
        Vehicle()
        {
            cout << "Vehicle initailized" << endl;
        }
};

class Car : public Engine, public Vehicle
{
    public:
        Car()
        {
            cout << "Car initialized" << endl;
        }
};

int main()
{
    Car c;
    return 0;
}
```
```txt
Question 4

Create a class Integer that represents a simple integer.
• Overload the + operators to perform arithmetic operations on Integer objects.
• Ensure that when performing operations, the result remains within the bounds of the integer type (e.g.,
handle overflow for addition and multiplication).

Example usage:
Integer num1(10), num2(5);
Integer resOne = num1 + num2; // sum should be 15
Integer resTwo = num1 + 20; // sum should be 15
Integer resThree = 10 * num2; // sum should be 15 
```
```cpp
#include <iostream>
#include <limits>
using namespace std;

class Integer
{
    private:
        int value;

        static int safeAdd(int a, int b)
        {
            if(b>0 && a>numeric_limits<int>::max()-b)
                return numeric_limits<int>::max();

            if(b<0 && a<numeric_limits<int>::min()-b)
                return numeric_limits<int>::min();

            return a+b;
        }

        static int safeMultiply(int a, int b)
        {
            if(a == 0 || b ==0)
                return 0;

            if(a > numeric_limits<int>::max() / b)
                return numeric_limits<int>::max();

            if(a < numeric_limits<int>::min() / b)
                return numeric_limits<int>::min();

            return a * b;
        }

        public:
            Integer(int v = 0)
            {
                value = v;
            }

        Integer operator+(const Integer& other)const
        {
            return Integer(safeAdd(value, other.value));
        }

        Integer operator+(int other)const
        {
            return Integer(safeAdd(value, other)); 
        }

        friend Integer operator*(int lhs, const Integer& rhs)
        {
            return Integer(safeMultiply(lhs, rhs.value));
        }

        void show() const
        {
            cout << value << endl;
        }

};

int main()
{
    Integer num1(10), num2(5);

    Integer resOne = num1 + num2;
    Integer resTwo = num1 + 20;
    Integer resThree = 10 * num2;

    cout << "resOne: ";
    resOne.show();

    cout << "resTwo: ";
    resTwo.show();

    cout << "resThree: ";
    resThree.show();

    return 0;
}
```
```txt
Question 5

Scenario: Smart Home Appliance Inventory

Design a system to manage smart appliances in a tech store.

Base class Appliance:

Data members: applianceID, brand, price

Derived class SmartAppliance:

Additional members: connectivity Type (e.g., WiFi, Bluetooth), warranty Years

Use an array of SmartAppliance objects (minimum 3).

Functions to:

Input and display appliance details.

Display appliances with warranty > 2 years.
```
```cpp
#include <iostream>
#include <string>
using namespace std;

class Appliance
{
    protected:
        int applianceID;
        string brand;
        float price;

    public:
        void inputAppliance()
        {
            cout << "Enter Appliance ID: ";
            cin >> applianceID;

            cout << "Enter Brand: ";
            cin >> brand;

            cout << "Enter Price: ";
            cin >> price;
        }

        void displayAppliance() const
        {
            cout << "Appliance ID: " << applianceID << endl;
            cout << "Brand: " << brand << endl;
            cout << "Price: " << price << endl;
        }
};

class SmartAppliance : public Appliance 
{
    private:
        string connectivityType;
        int warrantyYears;

    public:
        void inputSmartAppliance()
        {
            inputAppliance();

            cout << "Enter Connectivity Type (WiFi/Bluetooth): ";
            cin >> connectivityType;

            cout << "Enter Warranty (Years): ";
            cin >> warrantyYears;
        }

        void displaySmartAppliance() const
        {
            displayAppliance();
            cout << "Connectivity Type: " << connectivityType << endl;
            cout << "Warranty Years: " << warrantyYears << endl;
            cout << "-----------------------------" << endl;
        }

        int getWarrantyYears() const
        {
            return warrantyYears;
        }

};

int main()
{
    const int SIZE = 3;
    SmartAppliance appliances[SIZE];

    cout << "Enter Smart Appliance Details\n";
    cout << "==============================\n";

    for (int i = 0; i < SIZE; i++)
    {
        cout << "\nAppliance " << i + 1 << ":\n";
        appliances[i].inputSmartAppliance();
    }

    cout << "\nAll Smart Appliances\n";
    cout << "==============================\n";

    for (int i = 0; i < SIZE; i++)
    {
        appliances[i].displaySmartAppliance();
    }

    cout << "\nAppliances with Warranty > 2 Years\n";
    cout << "==============================\n";

    for (int i = 0; i < SIZE; i++)
    {
        if (appliances[i].getWarrantyYears() > 2)
        {
            appliances[i].displaySmartAppliance();
        }
    }

    return 0;
}
```
```txt
Question 6

Topic: Operator Overloading.

Overload the operator to compare two Box objects by their volume.

Accept length, breadth, height for two boxes.

Compare and print which box has greater volume.
```
```cpp
#include <iostream>
using namespace std;

class Box
{
    private:
        float length, breadth, height;

    public:
        void input()
        {
            cout << "Enter length, breadth and height: ";
            cin >> length >> breadth >> height;
        }

        float volume() const
        {
            return length * breadth * height;
        }

        bool operator>(const Box& other) const
        {
            return this->volume() > other.volume();
        }
};

int main()
{
    Box b1, b2;

    cout << "Enter dimensions for Box 1\n";
    b1.input();

    cout << "\nEnter dimensions for Box 2\n";
    b2.input();

    cout << "\nVolume of Box 1 = " << b1.volume() << endl;
    cout << "\nVolume of Box 2 = " << b2.volume() << endl;

    if(b1 > b2){
        cout << "Box 1 has greater volume than Box 2" << endl;
    } else {
        cout << "Box 2 has greater volume than Box 1" << endl;
    }

    return 0;
}
```




