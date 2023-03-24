# Intuition
node manipulation

# Approach
You can check my two different solution down below
1-ArrayList creation and a new LinkedList operation
2-Node manipulation with two new LinkedList named odd and even


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
    public ListNode oddEvenList(ListNode head) {
       if(head==null) return head;
       ListNode odd=head;
       ListNode even=head.next;
       ListNode headEven=even;

       while(odd.next!=null && even.next!=null){
           odd.next=even.next;
           odd=even.next;
           even.next=odd.next;
           even=odd.next;
       }

       odd.next=headEven;
       return head;
    }
    public ListNode firstApproach(ListNode head){
        if(head==null) return head;
        int count=0;
        ListNode root=head,r2=head;
        
        ArrayList<Integer> even= new ArrayList<Integer>();
        ArrayList<Integer> odd= new ArrayList<Integer>();

        while(root!=null){

            if(count%2==0) odd.add(root.val);
            else even.add(root.val);
            
            root=root.next;
            count+=1;
        }
        odd.addAll(even);
        
        for(int i=0;i<count;i++){
            r2.val=odd.get(i);
            r2=r2.next;
        }
        return head;
    }
}
```