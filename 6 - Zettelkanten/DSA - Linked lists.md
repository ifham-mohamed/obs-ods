
2024-08-03 14:41

Status:

Tags: #UOM #L2S2-S4 #DSA 



> [!NOTE] Linked List
> Introduction to Linked List 
> Insertion 
> Deletion 
> Types of Linked List 
> Linked List vs Array

# DSA - Linked lists


What is a Linked List?

*A linked list is a linear data structure where each element contains a pointer to the next element in the sequence. The fundamental difference from other data structures is that linked lists do not require contiguous memory allocation.*

Like arrays, Linked List is a linear data structure.

Unlike arrays, linked list elements are not stored at a contiguous location;
the elements are linked using pointers.

![[Pasted image 20240803144657.png | 700]]

### Node

In a linked list, a node is a fundamental unit that contains data and a reference to the next node in the list. Unlike arrays, nodes in a linked list do not have a fixed position, allowing for more flexibility in data organization.

1. Pointer to next node (Reference)
- A reference is a number that refers to an object.
- It is the object’s address in the computer’s memory, but you don’t need to know its value. You just treat it as a number that tells you where the object is.

2. Data

![[Pasted image 20240803145009.png]]

```C
public class node(){
	int data; //data
	structy node *next; //reference to the next node
}
```
### Linked List

![[Pasted image 20240803145025.png]]

![[Pasted image 20240803152514.png]]

### <mark style="background: #FF5582A6;">Create Linked List</mark>

The process of "creating a single linked list" involves initializing an empty list and then adding new nodes one by one, with each new node containing some data and a reference to the next node in the list.

> [!NOTE] Create Linked List
> 
> 1. create a head pointer
> 
> head
> ![[Pasted image 20240803153004.png]]
> 
> 2. create a new node
> 
> ![[Pasted image 20240803153012.png]]
> 
> 3. Change head pointer value to new node’s memory address
> 
> ![[Pasted image 20240803153034.png]]
> 

![[Pasted image 20240803162832.png | 700]]

```C
#include <stdio.h>
#include <stdlib.h>
  
struct Node

{
    int data;
    struct Node *next;
};

int main()
{
    struct Node *head = NULL;

    head = (struct Node *)malloc(sizeof(struct Node));
    head->data = 1234;
    head->next = NULL;

    printf("%d\n", head->data);
    printf("%d\n", head->next);

    free(head);
    head = NULL;

    return 0;
}
```


![[Pasted image 20240803163225.png | 700]]

```C
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

int main()

{
    struct Node *head = NULL;

    head = (struct Node *)malloc(sizeof(struct Node));
    head->data = 1234;
    head->next = NULL;

    printf("%d\n", head->data);
    printf("%d\n", head->next);

    struct Node *second = NULL;

    second = (struct Node *)malloc(sizeof(struct Node));
    second->data = 5678;
    second->next = NULL;

    head->next = second;

    printf("%d\n", head->data);
    printf("%d\n", head->next);
    printf("%d\n", head->next->data);
    printf("%d\n", head->next->next);

    free(head);
    head = NULL;
    
    return 0;
}
```
\
<mark style="background: #FFB8EBA6;">Waste of create each reference for the new node</mark>
![[Pasted image 20240803163702.png | 700]]


![[Pasted image 20240803163850.png | 700]]

```C
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

int main()
{
    struct Node *head = NULL;
  
    head = (struct Node *)malloc(sizeof(struct Node));
    head->data = 1234;
    head->next = NULL;
    printf("%d\n", head->data);
    printf("%d\n", head->next);

    struct Node *current = NULL;
    current = (struct Node *)malloc(sizeof(struct Node));
    current->data = 5678;
    current->next = NULL;
    head->next = current;
    printf("%d\n", head->data);
    printf("%d\n", head->next);
    printf("%d\n", head->next->data);
    printf("%d\n", head->next->next);

    current = (struct Node *)malloc(sizeof(struct Node));
    current->data = 91011;
    current->next = NULL;
    head->next->next = current;
    printf("%d\n", head->data);
    printf("%d\n", head->next);
    printf("%d\n", head->next->data);
    printf("%d\n", head->next->next);
    printf("%d\n", head->next->next->data);
    printf("%d\n", head->next->next->next);
    
    free(head);
    head = NULL;

    return 0;
}
```


### <mark style="background: #FF5582A6;">Traversal</mark>

![[0_WvZvIY4C0lKE04Z_.gif]]

```C
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
}; 

//Traversal
count_of_nodes_fun(struct Node *head)
{
    int count = 0;
    if (head == NULL)
    {
        printf("Linked List is empty");
    }

    struct Node *ptr = NULL;
    ptr = head;
    while (ptr != NULL)
    {
        count++;
        ptr = ptr->next;
    }
    return count;
}

int main()
{
    struct Node *head = NULL;

    head = (struct Node *)malloc(sizeof(struct Node));
    head->data = 1234;
    head->next = NULL;
    printf("%d\n", head->data);
    printf("%d\n", head->next);

    struct Node *current = NULL;
    current = (struct Node *)malloc(sizeof(struct Node));
    current->data = 5678;
    current->next = NULL;
    head->next = current;
    printf("%d\n", head->data);
    printf("%d\n", head->next);
    printf("%d\n", head->next->data);
    printf("%d\n", head->next->next);

    current = (struct Node *)malloc(sizeof(struct Node));
    current->data = 91011;
    current->next = NULL;
    head->next->next = current;
    printf("%d\n", head->data);
    printf("%d\n", head->next);
    printf("%d\n", head->next->data);
    printf("%d\n", head->next->next);
    printf("%d\n", head->next->next->data);
    printf("%d\n", head->next->next->next);

    int count_of_nodes = count_of_nodes_fun(head);//Traversal
    printf("Total number of nodes in the linked list is %d\n", count_of_nodes);

    free(head);

    head = NULL;
    return 0;
}
```

```CMD
Result
1234
0

1234
11277808
5678
0

1234
11277808
5678
11277824
91011
0

Total number of nodes in the linked list is 3
```


### <mark style="background: #FF5582A6;">Insertion</mark>

#### <mark style="background: #FFB8EBA6;">At Beginning</mark>

> [!NOTE] At Beginning
> 1. Add a new node at the beginning
> ![[Pasted image 20240803162030.png | 500]]
> 
> 2. Create a new node
> ![[Pasted image 20240803162048.png | 500]]
> 
> 3. Assign first node’s address into new node’s next link
> ![[Pasted image 20240803162112.png | 500]]
> 
> 4. Point head to the new node
>  ![[Pasted image 20240803162134.png | 500]]
> ![[LinkedList_frontInsertion.gif | 500]]
> 


```C
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

count_of_nodes_fun(struct Node *head)
{
    int count = 0;
    if (head == NULL)
    {
        printf("Linked List is empty");
    }
    struct Node *ptr = NULL;
    ptr = head;
    while (ptr != NULL)
    {
        count++;
        ptr = ptr->next;
    }
    return count;
}

int main()
{
    struct Node *head = NULL;
    head = (struct Node *)malloc(sizeof(struct Node));
    head->data = 1234;
    head->next = NULL;
    printf("%d\n", head->data);
    printf("%d\n", head->next);

    struct Node *current = NULL;
    current = (struct Node *)malloc(sizeof(struct Node));
    current->data = 5678;
    current->next = NULL;
    head->next = current;
    printf("%d\n", head->data);
    printf("%d\n", head->next);
    printf("%d\n", head->next->data);
    printf("%d\n", head->next->next);

    current = (struct Node *)malloc(sizeof(struct Node));
    current->data = 91011;
    current->next = NULL;
    head->next->next = current;
    printf("%d\n", head->data);
    printf("%d\n", head->next);
    printf("%d\n", head->next->data);
    printf("%d\n", head->next->next);
    printf("%d\n", head->next->next->data);
    printf("%d\n", head->next->next->next);

    struct Node *temp = NULL;
    temp = (struct Node *)malloc(sizeof(struct Node));
    temp->data = 12;
    temp->next = head;
    head = temp;
    printf("%d\n", head->data);
    printf("%d\n", head->next);
    printf("%d\n", head->next->data);
    printf("%d\n", head->next->next);
    printf("%d\n", head->next->next->data);
    printf("%d\n", head->next->next->next);
    printf("%d\n", head->next->next->next->data);
    printf("%d\n", head->next->next->next->next);

    int count_of_nodes = count_of_nodes_fun(head);

    printf("Total number of nodes in the linked list is %d\n", count_of_nodes);

    free(head);
    head = NULL;
    return 0;
}
```


```CMD 
Result
12
8531792

1234
8525296

5678
8525312

91011
```

#### <mark style="background: #FFB8EBA6;">At End</mark>
To insert a new node at the end of a linked list, you can follow these steps:

1. **Create a new node** with the desired data.
2. **If the list is empty**, make the new node the head of the list.
3. **If the list is not empty**, traverse to the last node using a temporary pointer.
4. **Set the `next` pointer of the last node** to the new node.

> [!NOTE] At End
> 1. Create a new node and traverse to the last node
> ![[Pasted image 20240803171938.png | 500]]
> 
> 2. Point new node to the last node
> ![[Pasted image 20240803172007.png | 500]]
![[linkedlist-insertfromback1.gif | 500]]
> 



```C
#include <stdio.h>
#include <stdlib.h>  

struct Node
{
    int data;
    struct Node *next;
};

// Function to create a new node
struct Node *createNode(int data)
{
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the end
void insertAtEnd(struct Node **head, int data)
{
    struct Node *newNode = createNode(data);

    // If the list is empty, make the new node the head
    if (*head == NULL)
    {
        *head = newNode;
        return;
    }

    // Traverse to the last node
    struct Node *temp = *head;
    while (temp->next != NULL)
    {
        temp = temp->next;
    }

    // Insert the new node at the end
    temp->next = newNode;
}

// Function to print the linked list
void printList(struct Node *head)
{
    struct Node *temp = head;
    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main()
{
    struct Node *head = NULL;

    insertAtEnd(&head, 1);
    insertAtEnd(&head, 2);
    insertAtEnd(&head, 3);
    insertAtEnd(&head, 4);
    insertAtEnd(&head, 5);

    printf("Linked List: ");
    printList(head);
    return 0;
}
```


#### <mark style="background: #FFB8EBA6;">After a given location</mark>
To insert a new node after a given location in a linked list, you need to follow these steps:

1. **Create a new node** with the desired data.
2. **Traverse the list** to find the specified location (node) after which you want to insert the new node.
3. **Adjust the pointers**: Set the `next` pointer of the new node to the `next` pointer of the current node, and then set the `next` pointer of the current node to the new node.


```C
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

// Function to create a new node
struct Node *createNode(int data)
{
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node after a given position
// Function to insert a node after a given position
void insertAfter(struct Node *head, int data, int position)
{
    struct Node *current = head;

    // Traverse to the specified position
    for (int j = 1; j < position; j++)
    {
        if (current->next == NULL)
        {
            printf("Position is out of bounds.\n");
            return;
        }
        current = current->next;
    }

    // Create a new node
    struct Node *newNode = createNode(data);
    newNode->next = current->next; // Link the new node to the next node
    current->next = newNode;       // Link the current node to the new node
}

// Function to print the linked list
void printList(struct Node *head)
{
    struct Node *temp = head;
    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

// Function to create a linked list for demonstration
struct Node *createLinkedList()
{
    struct Node *head = createNode(1);
    struct Node *second = createNode(2);
    struct Node *third = createNode(3);

    head->next = second;
    second->next = third;

    return head;
}

int main()
{
    struct Node *head = createLinkedList();

    printf("Original Linked List: ");
    printList(head);

    // Insert a new node with data 4 after the second node (position 2)
    insertAfter(head, 4, 3);

    printf("Linked List after insertion: ");
    printList(head);

    return 0;
}
```


### <mark style="background: #FF5582A6;">Deletion</mark>
#### From the beginning


Step 1 – Create a pointer and point first node to it
![[Pasted image 20240803201611.png | 700]]

Step 2 – Point head to the second node and delete first node
![[Pasted image 20240803201642.png | 700]]

Step 3 – Delete the first node. (Free allocated space)
![[Pasted image 20240803201732.png | 700]]


#### From the end

Change the previous node’s link value to null and delete last node
![[Pasted image 20240803201816.png | 700]]

#### From the middle

Step 1 – Create a pointer and point target node to it
![[Pasted image 20240803201845.png | 700]]

Delete the target element
![[Pasted image 20240803201913.png | 700]]


### <mark style="background: #FF5582A6;">Types of Linked List</mark>

![[Pasted image 20240803202013.png | 700]]


### <mark style="background: #FF5582A6;">Arrays vs Linked List</mark>

-  Cost of accessing an element
-  Memory utilization
-  Memory requirement
-  Cost of insertion
-  Cost of searching


- Arrays are suitable for:
	1. Inserting/deleting an element at the end.
	2. Randomly accessing any element
	3. Searching the list for a particular value

- Linked lists are suitable for:
	1. Inserting an element
	2. Deleting an element.
	3. Applications where sequential access is required.    
	4. In situations where the number of elements cannot be predicted
	5. before.


**Big O comparison of Arrays and Linked lists**
![[Pasted image 20240803202235.png | 700]]


**Linked List vs Array**
![[Pasted image 20240803202309.png | 700]]


### <mark style="background: #FF5582A6;">Applications of Linked list in the real world</mark>

**Image viewer** – Previous and next images are linked and can be accessed by the next and previous buttons.

**Previous and next page in a web browser** – We can access the previous and next URL searched in a web browser by pressing the back and next buttons since they are linked as a linked list.

**Music Player** – Songs in the music player are linked to the previous and next songs. So, you can play songs either from starting or ending of the list.








# Reference