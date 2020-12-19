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

### Delete node [LC 27](https://leetcode.com/problems/remove-element/)
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
## Design LinkedList [LC707](https://leetcode.com/problems/design-linked-list/)
```C#
public class MyLinkedList {

    public class ListNode
    {
        public int val;
        public ListNode next;
        public ListNode(int val = 0, ListNode next = null)
        {
            this.val = val;
            this.next = next;
        }
    }
    
    public ListNode head;
    public int count;
    
    /** Initialize your data structure here. */
    public MyLinkedList() {
        
    }
    
    public int Get(int index) {
        
        if(index >= count)
            return -1;
        else
        {
            ListNode curr = head;
            while(index > 0)
            {
                curr = curr.next;
                index--;
            }
            
            return curr.val;
        }
    }
    
    public void AddAtHead(int val) {
        
        ListNode node = new ListNode(val);
        node.next = head;
        head = node;
        count++;
    }

    public void AddAtTail(int val) {
        
        if(head == null)
            head = new ListNode(val);
        else
        {
            ListNode curr = head;
            while(curr.next != null)
                curr = curr.next;
            
            ListNode node = new ListNode(val);
            curr.next = node;
        }
        count++;
    }
    
    public void AddAtIndex(int index, int val) {
        
        if(index > count)
            return;
        else if(index == count)
            AddAtTail(val);
        else
        {
            ListNode dummy = new ListNode(-1);
            dummy.next = head;
            ListNode prev = dummy;
            
            while(index > 0)
            {
                prev = prev.next;
                index--;
            }
            
            ListNode node = new ListNode(val);
            node.next = prev.next;
            prev.next = node;
            head = dummy.next;
            count++;            
        }
    }
    
    public void DeleteAtIndex(int index) {
        
        if(index >= count)
            return;
        else
        {
            ListNode dummy = new ListNode(-1);
            dummy.next = head;
            ListNode prev = dummy;
            
            while(index > 0)
            {
                prev = prev.next;
                index--;
            }
            
            prev.next = prev.next.next;
            head = dummy.next;
            count--;
        }
    }
}
```
