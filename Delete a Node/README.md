# [Delete a Node in Single LinkedList]

```
Delete the node at a given position in a linked list and return a reference to the head node. The head is at position 0. The list may be empty after you delete the node. In that case, return a null value.

Example



After removing the node at position , .

Function Description

Complete the deleteNode function in the editor below.

deleteNode has the following parameters:
- SinglyLinkedListNode pointer llist: a reference to the head node in the list
- int position: the position of the node to remove

Returns
- SinglyLinkedListNode pointer: a reference to the head of the modified list

Input Format

The first line of input contains an integer , the number of elements in the linked list.
Each of the next  lines contains an integer, the node data values in order.
The last line contains an integer, , the position of the node to delete.



```

# [Solution in Java]

```
public static SinglyLinkedListNode deleteNode(SinglyLinkedListNode llist, int position) {
        if (llist == null) return null;
        //if position = 0 -> return llist.next
        if (position == 0) return llist.next;
        
        //0->1->2->->3, will stop at postion-1 to get node(pos-1).next = node(pos-1).next.next
        SinglyLinkedListNode nodeBeforePosition = llist;
        int index = 0;
        while (index < position-1) {
            nodeBeforePosition = nodeBeforePosition.next;
            index++;
        }
        //when i am here the node = pos-1;
        nodeBeforePosition.next = nodeBeforePosition.next.next;
        return llist;
    }

```