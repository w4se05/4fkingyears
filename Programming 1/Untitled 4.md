# Programming 1: Pointers and Memory Management

## 1. Conceptual Section (Teach Mode)

### 1.1 Introduction to Pointers

> [!Definition] 📍 Pointer
> A **pointer** is a variable that stores the **memory address** of another variable. Unlike standard variables that store values (like `int a = 10`), pointers tell you *where* that value is located in the computer's memory.

#### Core Operators
[cite_start]To work with pointers, you need two fundamental operators [cite: 3-5]:

1.  **Reference Operator (`&`):** Returns the **address** of a variable.
    * Read as: "Address of..."
    * Example: `&myVar` gives the memory location of `myVar`.
2.  **Dereference Operator (`*`):** Accesses the **value** stored at the address held by the pointer.
    * Read as: "Value pointed to by..."
    * Example: `*myPointer` gives the value stored at that address.

> [!Syntax] Declaration & Initialization
> ```c
> int *ptr;      // Declaration: ptr is a pointer to an integer
> int val = 5;
> ptr = &val;    // Initialization: ptr now holds the address of val
> ```

> [!Note] 🛑 NULL Pointer
> Always initialize pointers. If you don't have an address yet, assign it to `NULL`.
> `int *ptr = NULL;` prevents the pointer from pointing to random, garbage memory.

---

### 1.2 Pointers and Arrays

Pointers and arrays are closely related in C. In fact, the name of an array acts very much like a pointer to its first element.

> [!Theorem] 🔗 Array-Pointer Relationship
> The name of an array (e.g., `arr`) is a constant pointer to the first element of the array.
> * `arr` is equivalent to `&arr[0]`.
> * `*arr` is equivalent to `arr[0]`.

#### Pointer Arithmetic
[cite_start]You can perform arithmetic operations on pointers to traverse arrays [cite: 75-76].
* **Increment (`ptr++`):** Moves the pointer to the **next element** (not the next byte). If it's an `int` pointer, it skips 4 bytes (or 2, depending on architecture).
* **Addition (`ptr + n`):** Points to the $n$-th element after the current one.
    * `*(arr + i)` is exactly the same as `arr[i]`.

---

### 1.3 Pointers to Pointers

> [!Definition] ⛓️ Pointer to Pointer
> A variable that stores the address of another pointer.
>
> **Syntax:** `int **ptr2ptr;`
>
> **Chain:** `Variable` $\leftarrow$ `Pointer` $\leftarrow$ `Pointer to Pointer`

---

### 1.4 Dynamic Memory Allocation

Static memory (arrays declared like `int arr[100]`) is fixed at compile time. **Dynamic Memory Allocation** allows you to request memory manually during **runtime** (execution time) from the **Heap**.

You must include `<stdlib.h>` to use these functions.

> [!Function] 📦 `malloc()` (Memory Allocation)
> Allocates a block of memory of specified size (in bytes).
> * **Syntax:** `ptr = (castType*) malloc(size);`
> * **Initialization:** Values are **uninitialized** (garbage).
> * **Returns:** Pointer to the first byte, or `NULL` if allocation fails.

> [!Function] 🧼 `calloc()` (Contiguous Allocation)
> Allocates multiple blocks of memory and **initializes them to zero**.
> * **Syntax:** `ptr = (castType*) calloc(n, element_size);`
> * **Use case:** Allocating arrays where you want clean (0) data.

> [!Function] 📏 `realloc()` (Re-allocation)
> Changes the size of previously allocated memory.
> * **Syntax:** `ptr = realloc(ptr, new_size);`
> * **Use case:** Resizing a dynamic array without losing existing data.

> [!Function] 🗑️ `free()` (De-allocation)
> Releases the dynamically allocated memory back to the system.
> * **Syntax:** `free(ptr);`
> * **Critical:** Failing to free memory causes **Memory Leaks**, eventually crashing the program.

---

## 2. 📘 Examples (Application Mode)

### Example 1: Basic Pointer Operations
**Concept:** Using `&` and `*` to manipulate values indirectly.

> [!Code] Pointer Basics
> ```c
> #include <stdio.h>
>
> int main() {
>     int var = 20;
>     int *ip;
>
>     ip = &var; // ip stores address of var
>
>     printf("Address of var variable: %p\n", &var);
>     printf("Address stored in ip variable: %p\n", ip);
>     
>     // Access value using pointer
>     printf("Value of *ip variable: %d\n", *ip); // Prints 20
>     
>     return 0;
> }
> ```

### Example 2: Swapping Values (Call by Reference)
**Concept:** Functions typically pass by value (copy). To modify the actual variables, we must pass their addresses (pointers).

> [!Code] Swap Function
> ```c
> void swap(int *x, int *y) {
>     int temp;
>     temp = *x; // Save value at address x
>     *x = *y;   // Put value at y into address x
>     *y = temp; // Put saved value into address y
> }
>
> int main() {
>     int a = 100, b = 200;
>     swap(&a, &b); // Pass ADDRESSES
>     printf("a: %d, b: %d", a, b); // Output: a: 200, b: 100
>     return 0;
> }
> ```



### Example 3: Dynamic Array using `malloc`
**Problem:** Create an array of size $N$ (determined by user input) and populate it. This is impossible with static arrays like `arr[N]`.

> [!Code] Dynamic Array
> ```c
> #include <stdio.h>
> #include <stdlib.h>
>
> int main() {
>     int n, i, *arr;
>
>     printf("Enter number of elements: ");
>     scanf("%d", &n);
>
>     // Dynamically allocate memory for n integers
>     arr = (int*) malloc(n * sizeof(int));
>
>     // Check if allocation succeeded
>     if (arr == NULL) {
>         printf("Memory not allocated.\n");
>         exit(0);
>     }
>
>     // Use pointer as an array
>     for (i = 0; i < n; ++i) {
>         arr[i] = i + 1; // Or *(arr + i) = i + 1
>     }
>
>     printf("Elements: ");
>     for (i = 0; i < n; ++i) {
>         printf("%d, ", arr[i]);
>     }
>
>     // IMPORTANT: Free memory
>     free(arr);
>
>     return 0;
> }
> ```

### Example 4: Bubble Sort with Pointers
**Concept:** Sorting an array using pointer arithmetic instead of array indexing `[]`.

> [!Code] Pointer Sort
> ```c
> void sort(int n, int *ptr) {
>     int i, j, temp;
>     for (i = 0; i < n; i++) {
>         for (j = i + 1; j < n; j++) {
>             // Use *(ptr + i) instead of ptr[i]
>             if (*(ptr + j) < *(ptr + i)) {
>                 temp = *(ptr + i);
>                 *(ptr + i) = *(ptr + j);
>                 *(ptr + j) = temp;
>             }
>         }
>     }
> }
> ```

---

## 3. Summary

* **Pointers** store memory addresses. Use `&` to get an address and `*` to read/write the value at that address.
* **Arrays** decay into pointers. `arr[i]` is syntactic sugar for `*(arr + i)`.
* **Pass by Reference:** To change a variable inside a function, pass its pointer.
* **Dynamic Memory:**
    * Use `malloc` for uninitialized memory.
    * Use `calloc` for zero-initialized memory.
    * **Always** `free()` dynamically allocated memory to avoid leaks.