# Intuition
1- sort linkedlist and check if the values are doubled
2- use stack and queue pop and remove and check the values
3- reverse the half and check the matching ones

# Approach
3 was go to. We find the middle by using slow and fast params then reverse and in a while we check 

# Complexity
- Time complexity:
 $$O(n)$$ --> n

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
    public boolean isPalindrome(ListNode head) {
        //0
        //1 always true
        //B= sort and check if double or reverse half of the linked list and check or queue and stack
        //solution a = reverse and check
        
        ListNode slow=head,fast=head;
        
        while(fast!=null &&fast.next!=null){
            fast=fast.next.next;
            slow=slow.next;
        }

        slow=reverse(slow);
        fast=head;
        
        while(slow!=null){
            if(slow.val!=fast.val) return false;
            
            slow=slow.next;
            fast=fast.next;
        }
        return true;
    }
    public ListNode reverse(ListNode head){
        ListNode prev=null;
        while(head!=null){
            ListNode next=head.next;
            head.next=prev;
            prev=head;
            head=next;
        }
        return prev;
    }
}
```