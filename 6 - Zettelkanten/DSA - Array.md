
2024-08-03 11:02

Status:

Tags: #UOM #L2S2-S4 #DSA



# DSA - Array

**Fundamentals of data structures for Arrays focus on the underlying principles that define an array, such as its fixed size and contiguous storage in memory, which differentiate it from other data structure types.**

**Arrays allow for efficient access to individual elements by their index, enabling quick retrieval and manipulation of data.**

**The memory representation of an array involves allocating a continuous block of memory to store all the elements, with each element occupying a fixed amount of space based on its data type.**

## **Type of Array**

### <mark style="background: #FF5582A6;">One dimensional array</mark> 

*The one-dimensional array stores the data elements in a single row or column*

Syntax:
```C
<data type> <array name>[size] ={values};

int arr[5] = {1, 2, 3, 4, 5};
```

![[Pasted image 20240803120549.png | 700]]

![[Pasted image 20240803121223.png | 800]]


### <mark style="background: #FF5582A6;">Two-dimensional array </mark>
*A two-dimensional array is a collection of elements placed in rows and columns.*

![[Pasted image 20240803121525.png | 700]]

Syntax:
``` C
<data type> <array name> [row size][column size];

int arr[2][3] = {{1, 2, 3}, {4, 5, 6}};
```

```C
int arr[2][3] = {1, 2, 3, 4, 5, 6};
```

![[Excalidraw/Drawing 2024-08-03 12.19.50.excalidraw.md#^group=k4bV7o2-lRt-1H8lWGq3a | 800]]


### <mark style="background: #FF5582A6;">Three-dimensional array</mark>

![[Pasted image 20240803122330.png | 700]]


### <mark style="background: #FF5582A6;">Multi dimensional arrays</mark>

An array haves 2 or more subscripts, that type of array is called multi dimensional array.

Syntax for 3D array
```C
<data type> <array name> [s1][s2][s3] = {values};
```

> [!Question] Multi Dimensional Represent
> ex: int arr  [3]  [3]  [3] ;
> - int shows that the 3D array is an array of type integer.
> - arr is the name of array.
> - first dimension represents the block size(total number of 2D arrays).
> - second dimension represents the rows of 2D arrays.
> - third dimension represents the columns of 2D arrays.




Operations performed on arrays are a fundamental aspect that distinguishes arrays from other data structures, such as allowing direct access to any element by index and efficiently performing operations like <mark style="background: #ADCCFFA6;">insertion</mark>, <mark style="background: #FFB8EBA6;">deletion</mark>, and <mark style="background: #BBFABBA6;">searching</mark>.

**Basic operations**

• **Insertion** - It is used to add an element at a particular index.
• **Deletion** - It is used to delete an element from a particular index.
• **Search** - It is used to search an element using the given index or by the value.
• **Traversing**: It prints all the array elements one after another.
### <mark style="background: #FF5582A6;">Insertion</mark>

*Inserting an element into an array involves shifting the existing elements to make space for the new element. The time complexity of insertion depends on the position where the element is inserted:*

- **Inserting at the beginning**: Shifting all elements to the right takes O(n) time.
- **Inserting at the end**: Takes constant time O(1) if the array has enough space.
- **Inserting at a specific index**: Shifting elements from that index to the end takes O(n) time.

Example in C:
```C
int arr[5] = {1, 2, 3, 4, 5}; 
int size = 4;// Current size of the array 

// Insert 10 at index 2 
for (int i = size; i > 2; i--) { 
	arr[i] = arr[i - 1]; 
} 
arr[2] = 10; 
size++;
```


### <mark style="background: #FF5582A6;">Deletion</mark>

*Deleting an element from an array involves shifting the elements after the deleted element to fill the gap. The time complexity of deletion depends on the position of the element:*

- **Deleting from the beginning**: Shifting all elements to the left takes O(n) time.
- **Deleting from the end**: Takes constant time O(1).
- **Deleting from a specific index**: Shifting elements from that index to the end takes O(n) time.

Example in C:
```C
int arr[5] = {1, 2, 3, 4, 5}; 
int size = 5; // Current size of the array 

// Delete element at index 2 
for (int i = 2; i < size - 1; i++) { 
	arr[i] = arr[i + 1]; 
} 

size--;
```


![[Pasted image 20240803120904.png]]


### <mark style="background: #FF5582A6;">Searching</mark>

*Searching in an array can be done using the index or the value of the element:*

- **Searching by index**: Takes constant time O(1) as you can directly access the element using the index.
- **Searching by value**: Linear search takes O(n) time in the average case, as you need to iterate through the array to find the element.

Example in C:
```C
int arr[5] = {1, 2, 3, 4, 5}; // Search for element 3 for 

(int i = 0; i < 5; i++) { 
	if (arr[i] == 3) { 
		printf("Element found at index %d\n", i); 
		break; 
	} 
}
```


### <mark style="background: #FF5582A6;">Traversal</mark>

*Traversal simply means iterating through all the elements of the array and performing some operation on them. It takes O(n) time as you need to visit each element once.*

Example in C:

```C
int arr[5] = {1, 2, 3, 4, 5}; // Traverse the array and print the elements 

for (int i = 0; i < 5; i++) { 
	printf("%d ", arr[i]); 
} 

printf("\n");
```

![[Pasted image 20240803121050.png]]


### <mark style="background: #FF5582A6;">Pros & Cons</mark>

#### Pros

- Constant time Access
![[Pasted image 20240803125058.png]]

- Simplicity of implementation
![[Pasted image 20240803125131.png | 700]]


- Hardware support
![[Pasted image 20240803125151.png | 700]]

#### Cons

- Fixed size
![[Pasted image 20240803125234.png | 700]]

- Inefficient insert / deletion
![[Pasted image 20240803125300.png | 700]]

- Waste of memory

### <mark style="background: #FF5582A6;">Application & Use Case</mark>

- Database indexing
![[Pasted image 20240803125352.png | 700]]

- Caching & Memorization
![[Pasted image 20240803125418.png  | 700]]

- Searching & Sorting Algo
# Reference