# Dangling pointers
A pointer which points to a memory location which does not exist.

```c
int *p = (int*)(malloc(sizeof(int)) // allocating memory location to p
*p = 4;

free(p) // deallocating memory

printf("%d", p) //will result in segmentation fault
// segmentation fault occurs when we try to read or write into a illegal memory location

// solution for this
p = NULL
```
