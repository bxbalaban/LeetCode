# Intuition
I needed a paper and a pen for this.

# Approach
Firstly we are saving the head.next because it will be reversed and lost in the process. Secondlt we change what is to be previous node. And Lastly we change the head to be the new head.next

# Complexity
- Time complexity:
 e.g. $$O(n)$$ --> n

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
    public ListNode reverseList(ListNode head) {
        ListNode prev= null; // we need a new prev val at first which is null
        while(head!=null){
            ListNode next=head.next; //we need to save head.next because we will be changing head to be head.next in the future
            head.next=prev; //we are changing the link 
            prev=head; // we are changing what is to be prev next time
            head=next; //head is now iterated
        }
        return prev;
    }
}
```