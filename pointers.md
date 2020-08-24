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

# Malloc
Malloc dynamically allocates a contiguous block of memory of the size specified <br/>
The pointer returned by malloc is a void pointer. That's why we typecast it. <br/>
Malloc stands for memory allocation.
```c
int *p = (int*) malloc(sizeof(int))
```

# Calloc
Calloc stands for contigious allocation. It is also used to dynamically allocate memory. <br/>
Calloc allocates multiple blocks of memory.
```c
int *p = (int*)calloc(10, sizeof(int))
int *p = (int*) malloc(10*sizeof(int))
```
Both statements are equicalent.

Memory allocated by calloc is initialised to 0. whereas memory allocated by malloc is initialised to some garbage value.
