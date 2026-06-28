
2024-08-03 23:53

Status:

Tags: #UOM #L2S2-S4 #DSA



# DSA - Queue

*A queue is a linear list in which data can be inserted at one end, called the rear, and deleted from the other end, called the front.*

A queue is a data structure that follows the First-In-First-Out (FIFO) principle. Elements are added to the back (enqueue) and removed from the front (dequeue) of the queue. This allows for efficient processing of data in the order it was received. Queues are commonly used in computer systems for tasks like managing processes, handling network traffic, and implementing scheduling algorithms.


![[1672229254537.gif | 700]]


![[Pasted image 20240803235449.png | 700]]

It is a first in – first out (FIFO) restricted data structure.

Example
- A line at the supermarket


![[0_HUWegihFk4x2x5vS.gif | 700]]


## Operations on Queue

1. **Enqueue()** – add (store) an item to the queue.
2. **Dequeue()** – remove an item from the queue.
3. **Peek()/Queue front()** - Gets the element at the front of the queue without removing it.
5. **Queue rear()** – Gets the element at the rear of the queue without removing it.
7. **Isfull()** – Checks if the queue is full.
8. **Isempty()** – Checks if the queue is empty.


### Enqueue

1. Step 1 – Check if the queue is full.
2. Step 2 – If the queue is full, produce overflow error and exit.
3. Step 3 – If the queue is not full, increment rear pointer to point the next empty space.
4. Step 4 – Add data element to the queue location, where the rear is pointing.
5. Step 5 – return success.

![[Pasted image 20240804000445.png | 700]]


### Dequeue

1. Step 1 – Check if the queue is empty.
2. Step 2 – If the queue is empty, produce underflow error and exit.
3. Step 3 – If the queue is not empty, access the data where front is pointing.
4. Step 4 – Increment front pointer to point to the next available data element.
5. Step 5 – Return success .


![[Pasted image 20240804000535.png | 700]]


### Peek()/Queue front()

![[Pasted image 20240804000625.png | 700]]




### Queue rear()

![[Pasted image 20240804000729.png | 700]]




#### Queue Example

![[Pasted image 20240804000752.png | 700]]
![[Pasted image 20240804000811.png | 700]]





![[Pasted image 20240804000145.png]]



![[Pasted image 20240804000152.png]]



![[Pasted image 20240804000136.png]]
# Reference