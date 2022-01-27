# Introduction to Object Oriented Programming in C++
## Topics
  
  * Encapsulation in C++
  * Inheritance in C++

### Goals of Object oriented Programming
  
  * **Isolation of sections of code** as much as possible so that errors and bugs can be easily located.
    * If we dont do this it makes life more difficult 

  * Errors and bugs in one section **will not propogate** to others

  * To allow and encourage others **reuse of code**

* To **simplify the programmers task** and **reduce the memory load**

## Encapsulation
  
  * Encapsulation - also known as information hiding
  * Information relating to an object is kept within it and accessed only by specific methods written for that purpose
  * **The intent of encapsulation us to allow others to access the data in an object by a specified and unchanging interface**, not by knowledge of the current implementation
  
  * This allows the class to which the object belongs to change its implementation quite radically, if neccesary. without disrupting those who use it
  * If all accesses to certain data must pass through a specified interface, improper accesses can be prevented
  
### Class Encapsulation
  
  * The language of **C++ provides several flexible schemes** to implement information hiding
  * Class members (fields and methods) can be defined to be **public, private, and protected**
  * members defined as ***public*** **are visible** (that can be accessed) **to everyone** that operated the object
  * members that are ***private*** are **truly encapsulated** and hence **not visible** to the outside
  * members declared ***protected*** are **visible only to methods defined in the class** and to methods in its subclass

  * the class structure in C++ is the mechanism to provide encapsualtion
  * consuder the following point class
```C++
  #include <iostream>
  using namespace std;
  class Point {
  private: 
    double _x;
    double _y;
    //the fields: _x and _y are not visible (that is not accessible outside of the class Point
  
  public:
    Point(); //Constructor
    Point(double c, double y); // constructor
    void display(); // accessor
    //Modifiers are called constructors
  };
  ```
  
  ``` C++
    Point:: Point() 
    {
      _x = 0;
      _y = 0;
    }

    Point::Point( double x, double y) 
    {
      _x = x;
      _y = y;
    }
    void Point::display() {
      cout << "x = " << _x << " y = " << _y << endl;
    }
    void main ()
    {
       Point p1;  //Consturctor with no arguments
       Point p2(5,10);
       p1.display();
       p2.display();
     }
     
     // Should print 
     // x = 0 y = 0
     //p2.display prints:
     // x = 5 y = 10
  ```
    
 ### Friend Function or class
  
  * there are many instances wherein two or more cooperating objects need to access the private fields and methods of each other
  * this is made possible with teh help of a **friend function or class**
  * A "friend function" of a class is a function which is entitled to **access the non-public parts of the class** as freely as the class itself
  * A friend of the class is, therefore, a very trusted friend, a friend who has been given the keys to the front door and invited to make it a home
  * they should use the non public parts of the class only when they must
  * friend functions will restrict themselves to using the values of **non-public fields**

## Inheritance
  * Inheritance is a mechanism for **allowing code reuse in a controlled and efficient manner**
  * Object- oriented programming attacks this problem by allowing the extension of the subclass: a class can be written to solve a generic problem; then extended by a subclass  to handle the quirks of a particular program without changing the original code
  * **A sublcass can have more than one parent class**

### Automobile
  * **imagine we have the class of ***automobile***** 
  * Subclass (also called a descendant class, derived class or child class) inherits all the behavior of the class( also called a base class or parent class, or the superclass of the subclass)< except those parts that it must modify to handle its particular problem.
  * The base class and its subclasses form a heirarchy with the class at the top and the subclasses below
  * Furthermore, each of the subclasses may, themselves, be base classes for their own subclasses, and so on

## Sample code
### Hello World

``` C++
#include <iostream>
using namespace std;

int main ()
{
  cout << "Hello World" << endl;
  return 0;
}
```

## C++ has 3 categories of data types

  ### Primitive types - bool/ean, char, signed char, unsigned char, short int, unsigned int, int, long, float, long double
    * In any language are defined by the people who constructed the language (cannot create a new primitive data type)
    * The **char, short, int, and long** are all integer types, which hold integer values within the range allowed by the storage space
    * The **char and short** types require less storage than an int but they are promoted to int if neccessary before use in any operations
    * Some C++ compilers dont have the **bool** type which holds **true or false** variables
      * So integer variables can be used to represent the boolean variables, with 0 representing false and anything else representing true.
    * every character of a char corresponds to some integer value (ascii)
    * Theres reserved words, and logical operators/ special characters
  
  ### Classes -
    *  **Classes** can be related in one or more **hierarchies** but primitive types do not belong to any heirarchy
  
  ### Pointers - piece of data that points to some place in memory
    * Pointers contain the memory addresses of the variables
      * it is possible to perform some arithmetic on pointers, bit in general they do not participate in most operations possible on
    * Pointers are stored on the stack, an objected pointed at by a pointer is created on the heap. 
      * See: https://tinyurl.com/4s878zdc

  ### Identifiers - the names given by programmers to objects in a program
    * In C++, identifiers can be of any length
    * They must start with a ***letter or an underscore***
    * if it started with a number the compiler would assume it is a number youre inputting
      * Digits are permitted after the first character but not as the first character 
    * C++ is case senstitive
      * So stack and Stack are distinct identifiers

  ### Variable Declaration
  * Variable -> type -> identifier --(initial Value)-> ; (repeat assigning new value) ->

### Function Definition
  * Function -> return type -> identifier -> (parameters) -> function body
  * Functions can return a value
  * The word return causes an immediate jump out of the method.
  * If the function is declared as a non-void type, then return must be followed by a value of the proper type; otherwise it must not.
  * Function declared as returning non-void type must terminate through a return statement.
  ```
  #include <iostream>
using namespace std;
void voidFunc1()
{
cout << "voidFunc1()" << endl
//it is ok to simply end
}
```
```
  #include <iostream>
using namespace std;
void voidFunc1()
{
cout << "voidFunc1()" << endl
return; // note you cannot return an integer value ( if the return type was int you could return an int value)
}
```
```
#include <iostream>
using namespace std;
int intFunc1()
{
cout << "voidFunc1()" << endl
return 0; // you can only return nothing in a void function
}
```
### Pass by copy
* the output from the above program shows that myval was not changed by changeFunc(), even tho it was passed to ChangeFunc() by main
* This is an example of pass-by-copy parameter passing
* myval is a local variable declared by the main function
* it should be noted that val and myval are distinct entities with seperate memory for them
* the only connection i sthat val got its value from my val
* thus, there is no reason why a change in val would have any effect on myval

### Pass by reference
* Pass by refernce is used to overcome the problems which were encountered when pass by copy was used
* in this case we want the function that is called

* Advantages
  * The effciency problem: 
       


