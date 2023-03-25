# Intuition
I wanted to count the nodes then make another loop until the half but it has too many space complexity and it is really complicated to understand

# Approach
Instead we use slow and fast pointer method. Once the fast one( jumps 2 nodes at a time) get to the end the slow one (jumps 1 node at a time) gets to the half and we return it.

# Complexity
- Time complexity:
$$O(n)$$ -->n 


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
    public ListNode middleNode(ListNode head) {
        ListNode fast=head;
        ListNode slow=head;

        while(fast!=null && fast.next!=null){
            fast=fast.next.next;
            slow=slow.next;
        }
        return slow;
        
    }
    public ListNode firstApproach(ListNode head) {
        if(head==null) return head;
        ListNode root=head;
        int i=0;
        while(root!=null){
            i++;
            root=root.next;
        }

        for(int j=0;j<i/2;j++){
            head=head.next;
        }
        return head;
    }
}
```