
# Approach
Recursive Merge Sort 

# Complexity
- Time complexity:
$$O(n)$$ --> nlogn


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
    public ListNode sortList(ListNode head) {
        // we can use any of the sorting algs. here but here i choose merge
        if(head == null || head.next == null) return head;
        ListNode slow = head;
        ListNode fast = head;
        ListNode temp = slow;

        while(fast != null && fast.next != null){
            temp = slow;
            slow = slow.next;
            fast = fast.next.next;
        }
        temp.next = null;// end of the first half

        ListNode first = sortList(head);
        ListNode second = sortList(slow);

        return merge(first,second);
    }
    public ListNode merge (ListNode head, ListNode tail){
        ListNode result = new ListNode(0);
        ListNode curr = result;

        while(head != null && tail != null){
            if(head.val < tail.val){
                curr.next = head;
                head = head.next;
            }
            else{
                curr.next = tail;
                tail = tail.next;
            }
            curr = curr.next;
        }
//edge case check
        if(head != null){
            curr.next=head;
        }
        if(tail != null){
            curr.next=tail;
        }

        return result.next;
    }
}
```