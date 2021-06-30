# [Get Node Value]

```
Given a pointer to the head of a linked list and a specific position, determine the data value at that position. Count backwards from the tail node. The tail is at postion 0, its parent is at 1 and so on.

Example
 refers to

Each of the data values matches its distance from the tail. The value  is at the desired position.

Function Description

Complete the getNode function in the editor below.

getNode has the following parameters:

SinglyLinkedListNode pointer head: refers to the head of the list
int positionFromTail: the item to retrieve
Returns

int: the value at the desired position
Input Format

The first line contains an integer , the number of test cases.

Each test case has the following format:
The first line contains an integer , the number of elements in the linked list.
The next  lines contains an integer, the data value for an element of the linked list.
The last line contains an integer , the position from the tail to retrieve the value of.

```

# [Solution - Java]

```

  public static int getNode(SinglyLinkedListNode llist, int positionFromTail) {
        //need to find how many node
        int count = 0;

        SinglyLinkedListNode dummy = llist;
        SinglyLinkedListNode current = dummy;
        while (current != null) {
            count++;
            current = current.next;
        }

        count -= positionFromTail + 1;
        while (count > 0) {
            llist = llist.next;
            count--;
        }
        return llist.data;
    }
```
