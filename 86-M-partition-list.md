# Intuition
I wanted to use a recursive way but it took so long I gave up

# Approach
We create two new listnodes. Iterate the head check if the value is bigger or less than x value. Add them accordingly then merge them.

# Complexity
- Time complexity:
$$O(n)$$ -->n

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode partition(ListNode head, int x) {
        if(head == null) return head;
        ListNode before = new ListNode();
        ListNode b = before;
        ListNode after = new ListNode();
        ListNode a = after;


        while(head != null){   
            if(head.val < x){
                before.next = head;   
                before=before.next;               
            }
            else{
                after.next = head;   
                after=after.next;               
            }
            head=head.next;
        }

        after.next=null;
        before.next=a.next;    
         
        return b.next;
    }
}
```