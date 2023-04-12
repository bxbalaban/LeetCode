
# Approach
Using a carry value is the key here 

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
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode result = new ListNode(0);
        ListNode temp = result;
        int carry = 0;

        while(l1 != null || l2 != null){
            int l1_val = (l1 != null) ? l1.val : 0;
            int l2_val = (l2 != null) ? l2.val : 0;
            int sum = l1_val + l2_val + carry;

            carry = sum / 10;
            int last_digit = sum % 10;

            ListNode node = new ListNode(last_digit);
            result.next = node;
            result = result.next;

            if(l1 != null) l1 = l1.next;
            if(l2 != null) l2 = l2.next;
        }

        if(carry > 0){
            ListNode last = new ListNode(carry);
            result.next = last;
            result = result.next;
        }
        return temp.next;
    }
}
```