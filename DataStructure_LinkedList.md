## Introduction of LinkedList
LinkedList is a linear data structure, in which the elements are not stored in contigous memory addresses. Instead, the elements in a LinkedList are linked using pointers.

## Concepts of LinkedList
1. Node </br>
   Each element of a LinkedList is called a 'Node'.
2. Head </br>
   The first node of a LinkedList is called 'Head'.
3. Next </br>
   The pointer/reference of each node that points to the next node.
4. Tail </br>
   The last node of a LinkedList. It's next pointer points at null.

## Advantanges and Disadvantages of LinkedList
LinkedList is one of the simplest and most common data struture. It has advantanges and disadvantages comparing with Array.
- Advantages
  * Quick for insertion and deletion.
  * Size of LinkedList increases or decreases dynamically.
- Disadvantages
  * Does not allow random access. It takes linear time to visit an element.
  * Use more memory than Array because of the storage used by pointers.
  * Difficult for reverse traversing.

## Sentinel Node
A sentinel node is a dummy node that allows us to simplify boundary conditions. It doesn't hold or reference any data manged by the data structure.

### Delete node
* Without sentinel node
```C#
    public ListNode RemoveElements(ListNode head, int val) {
        
        if(head == null)
            return null;
        
        ListNode curr = head;
        
        while(curr != null && curr.val == val)
        {
            curr = curr.next;
            head = curr;
        }
        
        while(curr != null && curr.next != null)
        {
            if(curr.next.val == val)
                curr.next = curr.next.next;
            else
                curr = curr.next;
        }
        
        return head;
    }
```
* With sentinel node
```C#
    public ListNode RemoveElements(ListNode head, int val) {
        
        if(head == null)
            return null;
        
        ListNode dummy = new ListNode(-1);
        dummy.next = head;
        ListNode curr = dummy;
        
        while(curr != null && curr.next != null)
        {
            if(curr.next.val == val)
                curr.next = curr.next.next;
            else
                curr = curr.next;
        }
        
        return dummy.next;
    }
```
### Insert node
