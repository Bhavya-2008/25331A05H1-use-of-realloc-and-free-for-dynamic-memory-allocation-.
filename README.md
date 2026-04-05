# 25331A05H1-use-of-realloc-and-free-for-dynamic-memory-allocation-.
#include <stdio.h> 
#include <stdlib.h> 
int main() 
{ 
    int *ptr; 
    int i; 
    // Step 1: Allocate memory using calloc 
    ptr = (int*) calloc(3, sizeof(int)); 
    printf("Before realloc:\n"); 
    for(i = 0; i < 3; i++) 
    { 
        printf("%d ", ptr[i]);   // prints 0 0 0 
    } 
    // Step 2: Increase memory size using realloc 
    ptr = (int*) realloc(ptr, 5 * sizeof(int)); 
    // Step 3: Assign values to new memory 
    ptr[3] = 10; 
    ptr[4] = 20;
    printf("\nAfter realloc:\n"); 
    for(i = 0; i < 5; i++) 
    { 
        printf("%d ", ptr[i]); 
    } 
    // Step 4: Free memory 
    free(ptr); 
    return 0; 
} 
