# Chapter 2 Algorithms and Recursions
## Algorithms
  Input: Number and type of input values must be made clear
  Precise specification of each step: each step or instruction must be feasible and unambiguously defined
  Finiteness: for all input possibilites, the algorithm must terminate in finite time
  Result: The objective of the algorithm must be made clear. There may be an output that spells out the execution of the program.
  
### Resources and Complexities
  Resources generallt attributed to a computer algorithm are space and running time.
  Space Complexity: amount of memory required
  Time complexity: Amount of time to complete execution
  Running time and space required are expressed as a function of the input size n
  Ex: algorithm which reads n numbers and prints them
    Time Complexity = n
    Space Complexity = 1
    
    
### Algorithms

Algorithm conists of a set of finite steps satisfying the following conditions:
  * Input: Number and type of input values must be made clear
  * Precise: specification fo each step: Each step or instruction must be feasible and unambiguously defined
  * Finiteness: For all input possibliities, the algorithm must terminate in finite time
  * Result: The objective of the algorithm must be made clear. Thre may be an output that spells out the execution of the algorithm

* Resources and Complexities
* Resources generally attributed to a computer algorithm are space and running time
***Space complexity*** : Amount of memory required
***Time complexity*** : Amount of time to complete execution


***Running time and space time required are expressed as a function of input size n***
* Example: Algorithm which reads n numbers and prints them
***Time Complexity = n ***
***Space complexity = 1 ***

* Algorithm Expressed in Pseudo-Language
* Example: ***Psuedo-language*** description for sorting an array A of n ingtegers in ascending order
* Let us use notaion A[i:n] to denote the set of array elements A[i],A[i+1],,...,A[n].
* We first find the minimum integer in the array A[1:n] and swqp it with the number in A[1]
* Then we find the minimum in the array A[2:n] and swap it with the number in A[2] and so on


* Simple Sort Algorithm

Algorithm Simplesort(A,n)
Input: An array A of n integers
Output : A sorted A in ascending order of the number it holds

FOR i<- to (n-1) do
Find the minimum integer in teh array A[i:n]
Let j be such tha A[j]=min A[i:n]
Swap A[i] with A[j]
ENDFOR


Measuring execution tim eofa program takes the following steps:
* Start a timer
* Run the program
* End the timer

Wall-clock time is inaccurate and not precise


***Primitive Operations***

* Assignment of a value to a variable
* Comparing two numbers
* Arithmetic operations such as addition, subtraction, multiplication etc. between two numbers


Primitive Operations:
* Assignment of a value to a variable
* Comparing two numbers
* Arithmetic operations such as addition, subtraction, multiplication, etc. between two numbers
* Invoking a function or a method and returning from a function or method.
* Indexing into an array
* Unconditional jumps from one step of the code to another

* The execution times of these operations depend on the architecture of the machine that impletments the algorithms


Example: Sum of n integers in an Array A


Input: An array A sorting n integers
Output: Sum of the integers in the array, i.e, A[1]+A[2]+...+A[n]
1. sum <- 0 // 1 primitive operation
2. i<-1 // 1 primitive operation
3. IF i>n THEN GO TO step 7 // 1*(n+1) + 1 primitive operations
4. sum <- sum+A[i] // 3*n primitive operation
5. i <- i+1 // 2*n primitive operations
6. GO TO step 3 // 1*n primitive operations
7. RETURN sum // 1 primitive operation


TOTAL NUMBER OF OPERATIONS = 7n+2+3
*We say the running time is proportional to 7n+5
*The Running time of the above algorihm is independent of the values that are stored in the array A


Analysis of Algorithm
*Algorithm can be analyzed in three different ways:
* Best case inputs
* Worst case inputs
* Average case inputs
* If the nature of the input is unknown, then worst case estimate is a better tool
to compare the performance of the algorithms than the best case estimate
* Analysis can be simplified by lumping a set of a primitive operations


*** Example: a = b*2 + A[i]*B[i] can be considered as one lumped up operation***

Asymptotic Notation and Big-Oh notation

* Let f(n) and g(n) be functions mapping nonnegative integers to real numbers

  Asymptomatic notation and Big-Oh notation cont.
  
  * fFor instance, if we had an algorithm with step count c_1n^2 + c_2n + c_3
  * We should avoid saying that the running time is **O(n^3)** although it is technically correct to say it
  * The "**big-Omega**" notation captures the "**greater than or equal to**"

Recursion

  * Direct Recursion: a function may call itself before it finsihed execution
  * Indirect Recursion: two functions calling each other
  * For recursion to be successful the recursive call msut be a smaller problem than the original
  * Any recurrsive program consists of two parts (base and recursive)

Ex:
Algotithm Factorial (n)
Input: a nonnegative interger in
Outpit: the factorial of n denoted by n! = n(n-1)(n-2)
1. IF (n = 0 or n = 1) THEN RETURN 1
2. RETURN n * Factorial(n-1)
* The time complexity of the above algorithm is O(n)

Greedy Algorithm
  * A greedy algorithm works by making a decision that seems most promising at any given time;
  * it never reconsiders this decision

Divide and conquer algorithms
  * Divide and conquer is a **top-down technique** for designing algorithms
  * It first decomposes an instance of a problem into a number of smaller sub-instances of the same problem, solving independently each of the solutions to obtain the solution of the original instance

Dynamic Programming
  * dynamic programming is **bottom-up technique**
  * We start by obtaining solutions to the smallest sub instances and repeatedly combine the solutions to get solutions for larger instances until finally we arrive at the solution of the original instance
  


