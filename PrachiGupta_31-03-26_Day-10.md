#  Add Two Numbers
#  Add digits from both lists with carry → sum = x + y + carry, create node with sum % 10.
Update carry as carry = sum / 10 and continue till both lists end.
TC: O(max(n, m))
SC: O(max(n, m))

# CODE
class Solution {

    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy= new ListNode(0);
        ListNode curr= dummy;
        int carry =0;

        while(l1 !=null ||l2 != null){
            int x =(l1 != null) ?l1.val : 0;
            int y =(l2 !=null) ? l2.val : 0;
            int sum = x + y + carry;
            carry = sum / 10;
            curr.next = new ListNode(sum % 10);
            curr = curr.next;
            if(l1!= null) l1 =l1.next;
            if(l2!= null) l2 =l2.next;
        }
        if(carry> 0){
            curr.next =new ListNode(carry);
        }
        return dummy.next;
    }
}
<img width="985" height="486" alt="image" src="https://github.com/user-attachments/assets/f22ac5ba-7fa3-4f47-af01-e8c3156f9a6a" />

