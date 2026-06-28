
2024-08-03 20:43

Status:

Tags: #UOM #L2S2-S4 #DSA


# DSA - Stacks

*A stack is a fundamental data structure that follows the Last-In-First-Out (LIFO) principle. It allows elements to be added (pushed) and removed (popped) from the top of the stack.* 

![[1_K7IJgAGyj0e9K0FV39sxEA.gif | 700]]


![[Pasted image 20240803215221.png | 700]]


The most recently added element is always the first one to be removed. Stacks have a variety of applications, such as managing function calls in programming, evaluating mathematical expressions, and implementing undo/redo operations in software.



![[Pasted image 20240803213838.png | 700]]



> [!Example] Example
> Ex: If you insert a data series into a stack and then remove it, the order of the data is reversed.
> 
> Data input as {5, 10, 15, 20} is removed as {20, 15, 10, 5}

Stacks are commonly implemented using arrays or linked lists. They are used in many algorithms and applications, such as:

- Expression evaluation and conversion
- Backtracking
- Function calls
- Parentheses matching
- String reversal
## Basic Operations on Stacks

The fundamental operations of a stack data structure are push, which adds an element to the top of the stack, and pop, which removes the top element from the stack.

The main operations performed on stacks are:
1. **Push**: Inserts an element at the top of the stack
2. **Pop**: Removes the top element from the stack
3. **Peek**: Returns the top element of the stack without removing it
4. **isEmpty**: Checks if the stack is empty
5. **isFull**: Checks if the stack is full (only for fixed-size stacks)

  
### Push

*Push adds an item at the top of the stack*

- The only potential problem with this operation is that we must ensure that there is room for the new item.
- If there is not enough room, the stack is in an overflow state and the item cannot be added.

![[Pasted image 20240803220315.png | 700]]

![[Stack1.gif | 700]]

> [!Example] Example
> The **push** operation is used to insert an element at the top of the stack. It follows these steps:
> 
> 1. Check if the stack is full (only for fixed-size stacks)
> 2. If the stack is not full, increment the top pointer
> 3. Insert the new element at the position pointed to by the top pointer
> 
> Here's an example of pushing an element onto a stack:Push OperationIn this example, we push the element 3 onto the stack. The top pointer is incremented, and 3 is inserted at the position pointed to by top.

### Pop

*Remove the item at the top of the stack and return it to the user.*

- When the last item in the stack is deleted, the stack must be set to its empty state.
- If pop is called when the stack is empty, it is in an underflow state.

![[Pasted image 20240803220306.png | 700]]

![](https://gochronicles.com/content/images/2021/05/Stack2.gif | 700)

> [!Example] Example
> The **pop** operation is used to remove the top element from the stack. It follows these steps:
> 
> 1. Check if the stack is empty
> 2. If the stack is not empty, access the element at the position pointed to by the top pointer
> 3. Decrement the top pointer
> 4. Return the accessed element
> 
> Here's an example of popping an element from a stack:Pop OperationIn this example, we pop an element from the stack. The element at the position pointed to by top (which is 3) is accessed and returned. Then, the top pointer is decremented.

```C
push(element): 
	if stack is full: 
		return error 
	else: 
		top = top + 1 
		stack[top] = element 

pop(): 
	if stack is empty: 
		return error 
	else: 
	element = stack[top] 
	top = top - 1 
	return element 

peek(): 
	if stack is empty: 
		return error 
	else: 
		return stack[top] 

isEmpty(): 
	if top == -1: 
		return true 
	else: 
		return false 

isFull(): 
	if top == size - 1: 
		return true 
	else: 
		return false
```

### Peek/Top()

Get the top data element of the stack, without removing it

Stack top copies the item at the top of the stack; that is, it returns the
data in the top element to the user but does not delete it.

![[Pasted image 20240803220254.png]]

> [!Example] Example
> The **peek** operation is used to access the top element of the stack without removing it. It follows these steps:
> 
> 1. Check if the stack is empty
> 2. If the stack is not empty, access and return the element at the position pointed to by the top pointer
> 
> Here's an example of peeking at the top element of a stack:Peek OperationIn this example, we peek at the top element of the stack. The element at the position pointed to by top (which is 3) is accessed and returned without modifying the stack.

### isFull()

Check if stack is full

> [!Example] Example
> The **isFull** operation is used to check if the stack is full. It returns true if the stack is full and false otherwise. It follows these steps:
> 
> 1. Check if the top pointer is equal to the maximum size of the stack minus 1 (for a full stack)
> 2. If top is equal to the maximum size minus 1, return true, indicating a full stack
> 3. Otherwise, return false

### isEmpty()

Check if stack is empty

> [!Example] Example
> The **isEmpty** operation is used to check if the stack is empty. It returns true if the stack is empty and false otherwise. It follows these steps:
> 
> 1. Check if the top pointer is equal to -1 (for an empty stack)
> 2. If top is equal to -1, return true, indicating an empty stack
> 3. Otherwise, return false

**push(green) -> push(blue) ->**
**pop() -> push(red) ->**
**top() -> pop() ->**
**pop()**

![[Pasted image 20240803220958.png | 700]]


## Stack Implementation
1. Using Arrays
2. Using Linked List

### Using Arrays

![[Pasted image 20240803221120.png | 700]]



![[Pasted image 20240803221130.png | 700]]


![[Pasted image 20240803221135.png | 700]]


> [!Method] By Array
> *Implementing a stack using an array is a common approach. It involves using a fixed-size array to store the elements and a top pointer to keep track of the top element. Here's how it works:*
> 
> 1. **Initialize** the stack with a fixed size and set the top pointer to -1 (indicating an empty stack).
> 2. **Push** an element by incrementing the top pointer and inserting the element at the position pointed to by top.
> 3. **Pop** an element by accessing the element at the position pointed to by top, decrementing top, and returning the accessed element.
> 4. **Peek** an element by accessing the element at the position pointed to by top without modifying the stack.
> 5. **Check for stack overflow** (when trying to push to a full stack) by comparing top to the maximum size minus 1.
> 6. **Check for stack underflow** (when trying to pop from an empty stack) by checking if top is equal to -1.
> 
> Advantages:
> 
> - **Simple implementation**
> - **Constant-time access to the top element**
> - **Efficient memory usage for fixed-size stacks**
> 
> Disadvantages:
> 
> - **Fixed size limits the maximum number of elements that can be stored**
> - **Resizing the stack requires creating a new array and copying elements, which can be inefficient**

```C
#include <stdio.h>
#include <stdlib.h>
#define MAX 4 

int stack_arr[MAX];
int top = -1;

int push(int data)
{
    if (top == MAX - 1)
    {
        printf("stack overflow");
        return -1;
    }

    top = top + 1;
    stack_arr[top] = data;
    return 0;
}

int pop()
{
    int value;
    if (top == -1)
    {
        printf("stack is underflow");
        exit(1);
    }
  
    value = stack_arr[top];
  
    top = top - 1;
    return value;
}
  
int print()
{
    int i;
  
    if (top = -1)
    {
        printf("Stack overflow!");
        return -1;
    }
  
    for (i = top; i >= 0; i--)
    {
        printf("%d", stack_arr[i]);
    }
    printf("/n");
}

int main()
{
    int data;

    push(1);
    push(2);
    push(3);
    push(4);

    data = pop();
    printf("%d\n", data);
    print();

    return 0;
}
```
### Stack Implementation using Linked List

To implement the linked list stack, need two different structures,
a head and a data node.

![[Pasted image 20240803221311.png | 700]]



![[Pasted image 20240803221331.png | 700]]

- Allocate a node from dynamic memory.
- Once the memory is allocated, simply assign the data to the stack node and then set the link pointer to point to the node currently indicated as the stack top.
- Update the stack top pointer and add 1 to the stack count field.

![[Pasted image 20240803221402.png | 700]]

- Pop stack sends the data in the node at the top of the stack back to the calling algorithm.
- It then adjusts the pointers to logically delete the node.
- After the node has been logically deleted, it is physically deleted by recycling the memory, that is, returning it to dynamic memory.
- After the count is adjusted by subtracting 1.

![[Pasted image 20240803221414.png | 700]]


> [!Method] By Linked List
> *Implementing a stack using a linked list allows for a dynamic size and avoids the limitations of a fixed-size array. Here's how it works:*
> 
> 1. **Initialize** the stack with a head pointer set to null (indicating an empty stack).
> 2. **Push** an element by creating a new node with the element as its data and the next pointer pointing to the current head. Update the head pointer to point to the new node.
> 3. **Pop** an element by accessing the data of the node pointed to by the head, updating the head pointer to point to the next node, and returning the accessed data.
> 4. **Peek** an element by accessing the data of the node pointed to by the head without modifying the stack.
> 5. **Check for stack underflow** (when trying to pop from an empty stack) by checking if the head pointer is null.
> 
> Advantages:
> 
> - **Dynamic size allows for an unlimited number of elements**
> - **No need to worry about resizing the stack**
> 
> Disadvantages:
> 
> - **Additional memory overhead for the next pointers in each node**
> - **Slightly slower access to the top element compared to an array implementation**

## Applications of Stacks

1. **Expression Evaluation and Conversion**: Stacks are used to evaluate and convert expressions from infix to postfix or prefix notation.
2. **Backtracking**: Stacks are used in backtracking algorithms to keep track of previous states.
3. **Function Calls**: Stacks are used to keep track of function calls and their return addresses.
4. **Parentheses Matching**: Stacks are used to check if parentheses are properly matched in an expression.
5. **String Reversal**: Stacks can be used to reverse a string by pushing each character onto the stack and then popping them off.

## Best Practices for Using Stacks

1. **Choose the appropriate implementation**: Decide whether to use an array or a linked list based on the specific requirements of your application.
2. **Handle errors**: Always check for stack underflow (trying to pop from an empty stack) and stack overflow (trying to push to a full stack) and handle them appropriately.
3. **Use meaningful variable names**: Use descriptive names for your stack variables and methods to make your code more readable and maintainable.
4. **Write clear and concise comments**: Document your code with comments explaining the purpose of each method and any edge cases or assumptions.
5. **Test your code**: Write unit tests to ensure that your stack implementation works correctly for various scenarios, including edge cases.
6. **Use stacks in appropriate contexts**: Only use stacks when the LIFO principle applies to your problem. If you need a different order of access, consider using a queue or a different data structure.
7. **Optimize for performance**: If performance is critical, consider using a fixed-size array implementation of a stack to avoid the overhead of dynamic memory allocation.


# Reference