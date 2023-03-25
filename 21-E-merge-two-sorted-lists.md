# Intuition
creating a new listnode

# Approach
we created a new list then compared two lists together until one list is empty. We checked the list if there is still something in we add the remainings to the end of new created list

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
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode temp = new ListNode(0);
        ListNode curr=temp;

        while(list1!=null && list2!=null){
            if(list1.val<list2.val){
               curr.next=list1;
               list1=list1.next;
            }
            else{
                curr.next=list2;
                list2=list2.next;
            }
            curr=curr.next;
        }

        //if there is still some nodes in list check them
        if(list1!=null) curr.next=list1;
        if(list2!=null) curr.next=list2;

        return temp.next;
    }
}
```