# [Insert a Node at the Tail of a Linked List]

```
  You are given the pointer to the head node of a linked list and an integer to add to the list. Create a new node with the given integer. Insert this node at the tail of the linked list and return the head node of the linked list formed after inserting this new node. The given head pointer may be null, meaning that the initial list is empty.

Function Description

Complete the insertNodeAtTail function in the editor below.

insertNodeAtTail has the following parameters:

SinglyLinkedListNode pointer head: a reference to the head of a list
int data: the data value for the node to insert
Returns

SinglyLinkedListNode pointer: reference to the head of the modified linked list
Input Format

The first line contains an integer , the number of elements in the linked list.
The next  lines contain an integer each, the value that needs to be inserted at tail.
```

# Solution

```
static SinglyLinkedListNode insertNodeAtTail(SinglyLinkedListNode head, int data) {
        SinglyLinkedListNode newNode = new SinglyLinkedListNode(data);
        
        if (head == null) {
            head = newNode;
            return head;
        }
        
        SinglyLinkedListNode current = head;
        while (current.next != null) {
            current = current.next;
        }
        
        //now point newNode to null, then assign tail = newNode
        current.next = newNode;

        return head;
    }
```
