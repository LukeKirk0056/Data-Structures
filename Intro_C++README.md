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

### Encapsulation
  
  * Encapsulation - also known as information hiding

* Information relating to an object is kept within it and accessed only by specific methods written for that purpose
* **The intent of encapsulation us to allow others to access the data in an object by a specified and unchanging interface**, not by knowledge of the current implementation

* This allows the class to which the object belongs to change its implementation quite radically, if neccesary. without disrupting those who use it
* If all accesses to certain data must pass through a specified interface, improper accesses can be prevented
