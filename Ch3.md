# Arrays Strings Matricies and Vectors
Arrays -  are building blocks of many data structures
  * This primitive data structure is used to store sets of elements and represent sets of consecutive logical memory locations
  *
Strings - store a sequence of characters and are often implemented using arrays
Vectors - are array data structures that are dynamic (similar to lists)
New memory space can be created for additional storage and this can be added to existing storage

## Arrays
  Array of size 10 woth integer values stored in it
    * int A[10];
    * it contains the primitive operations that an array must be able to perform
    * complex operations needed for programs are built using these primitive data types
    Specification of an abstract data type for arrays
 ```
    create(n) // create an array of size n
    putObject(newObject, k) // place an object newObject at index position k
    getObject(k) //get the object at index position k
    size()// find the number of elements which can be accomdodated in the array
    
    //ex:
    int A[10];
    A[2] = 7;
 ```
