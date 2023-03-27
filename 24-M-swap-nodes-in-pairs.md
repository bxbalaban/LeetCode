# Intuition
it was not to use a recursive solution and iterate through the list but then i found this shorter way

# Approach
You basicly need three variables to make swapping this spesific way. 
1- hold head (prev)
2- hold head next (curr)
3- hold head next next (next)

head = curr
head.next = prev


# Complexity
- Time complexity:
$$O(n)$$ --> n


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
    public ListNode swapPairs(ListNode head) {
        if(head == null || head.next == null) return head;

        ListNode prev = head;
        ListNode curr = head.next;
        ListNode next = head.next.next;
        
        head = curr;
        head.next = prev;
        head.next.next = swapPairs(next);        
        return head;
    }
    
}
 
```