# [Reverse a linkedList]

```
Given the pointer to the head node of a linked list, change the next pointers of the nodes so that their order is reversed. The head pointer given may be null meaning that the initial list is empty.

Example
 references the list

Manipulate the  pointers of each node in place and return , now referencing the head of the list .

Function Description

Complete the reverse function in the editor below.

reverse has the following parameter:

SinglyLinkedListNode pointer head: a reference to the head of a list
Returns

SinglyLinkedListNode pointer: a reference to the head of the reversed list
Input Format

The first line contains an integer , the number of test cases.

Each test case has the following format:

The first line contains an integer , the number of elements in the linked list.
Each of the next  lines contains an integer, the  values of the elements in the linked list.


```

# [Solution - Java]

```
public static SinglyLinkedListNode reverse(SinglyLinkedListNode llist) {
    // 1 -> 2 -> 3->null
        if (llist == null || llist.next == null) return llist;

        SinglyLinkedListNode previous = null;

        while (llist != null) {
            SinglyLinkedListNode temp = llist.next; //temp = 2->3 to keep for the next llist round
            llist.next = previous; //llist = 2->null ..2->1 ...3->2->1
            previous = llist; //previous=2
            llist = temp; //llist = 2->3
        }

        return previous;
    }


```
