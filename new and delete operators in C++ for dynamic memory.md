## new and delete operators in C++ for dynamic memory

[GeeksforGeeks](http://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/)

Dynamic memory allocation in C/C++ refers to performing memory allocation manually by programmer. Dynamically allocated memory is allocated on Heap and non-static and local variables get memory allocated on Stack.

### How is memory allocated/deallocated in C++?

C uses [malloc() and calloc()](http://www.geeksforgeeks.org/calloc-versus-malloc/) function to allocate memory dynamically at run time and uses free() function to free dynamically allocated memory. C++ supports these functions and also has two operators new and delete that perform the task of allocating and freeing the memory in a better and easier way. 

### new operator

The new operator denotes a request for memory allocation on the Heap. If sufficient memory is available, new operator initializes the memory and returns the address of the newly allocated and initialized memory to the pointer variable.

* **Syntax to use new operator:** To allocate memory of any data type, the syntax is:

```cpp
pointer-variable = new data-type;
```
Here, pointer-variable is the pointer of type data-type. Data-type could be any built-in data type including array or any user defined data types including structure and class.

```cpp
// Pointer initialized with NULL
// Then request memory for the variable
int *p = NULL; 
p = new int;   

            OR

// Combine declaration of pointer 
// and their assignment
int *p = new int; 
```
* **Initialize memory:** We can also initialize the memory using new operator:

```cpp
pointer-variable = new data-type(value);
```
Example:

```cpp
int *p = new int(25);
float *q = new float(75.25);
```

* **Allocate block of memory:** new operator is also used to allocate a block(an array) of memory of type data-type.

```cpp
pointer-variable = new data-type[size];
```
where size(a variable) specifies the number of elements in an array.

Example:
```cpp
int *p = new int[10]
```
Dynamically allocates memory for 10 integers continuously of type int and returns pointer to the first element of the sequence, which is assigned to p(a pointer). p[0] refers to first element, p[1] refers to second element and so on.

### delete operator

Since it is programmer’s responsibility to deallocate dynamically allocated memory, programmers are provided delete operator by C++ language.
Syntax:
```cpp
// Release memory pointed by pointer-variable
delete pointer-variable; 
```
Here, pointer-variable is the pointer that points to the data object created by new.
Examples:
```cpp
delete p;
delete q;
```
To free the dynamically allocated array pointed by pointer-variable, use following form of delete:
```cpp
// Release block of memory 
// pointed by pointer-variable
delete[] pointer-variable;  

Example:
   // It will free the entire array
   // pointed by p.
   delete[] p;
```
--------

```cpp
// C++ program to illustrate dynamic allocation
// and deallocation of memory using new and delete
#include <iostream>
using namespace std;
 
int main ()
{
    // Pointer initialization to null
    int* p = NULL;
 
    // Request memory for the variable
    // using new operator
    p = new int;
    if (!p)
        cout << "allocation of memory failed\n";
    else
    {
        // Store value at allocated address
        *p = 29;
        cout << "Value of p: " << *p << endl;
    }
 
    // Request block of memory
    // using new operator
    float *r = new float(75.25);
 
    cout << "Value of r: " << *r << endl;
 
    // Request block of memory of size n
    int n = 5;
    int *q = new int[n];
 
    if (!p)
        cout << "allocation of memory failed\n";
    else
    {
        for (int i = 0; i < n; i++)
            q[i] = i+1;
 
        cout << "Value store in block of memory: ";
        for (int i = 0; i < n; i++)
            cout << q[i] << " ";
    }
 
    // freed the allocated memory
    delete p;
    delete r;
 
    // freed the block of allocated memory
    delete[] q;
 
    return 0;
}
```
