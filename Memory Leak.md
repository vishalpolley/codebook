## What is Memory Leak? How can we avoid?

Memory leak occurs when programmers create a memory in heap and forget to delete it.
Memory leaks are particularly serious issues for programs like daemons and servers which by definition never terminate.

```cpp
/* Function with memory leak */
#include <stdlib.h>
 
void f()
{
   int *ptr = (int *) malloc(sizeof(int));
 
   /* Do some work */
 
   return; /* Return without freeing ptr*/
}
```
To avoid memory leaks, memory allocated on heap should always be freed when no longer needed.

```cpp
/* Function without memory leak */
#include <stdlib.h>;
 
void f()
{
   int *ptr = (int *) malloc(sizeof(int));
 
   /* Do some work */
 
   free(ptr);
   return;
}
```
