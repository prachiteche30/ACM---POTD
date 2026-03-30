#Linked List Cycle II

#Time Complexity (TC): O(n) , Space Complexity (SC): O(1) , Using Tortoise and Hare approach
# CODE 
public class Solution {


    public ListNode detectCycle(ListNode head) {
        if(head==null || head.next==null ) return null;
        ListNode slow= head;
        ListNode fast= head;
        while(fast!=null && fast.next!=null){
            slow=slow.next;
            fast =fast.next.next;

            if(slow==fast){
                ListNode start =head;
                while(start!=slow){
                    start=start.next;
                    slow=slow.next;

                }
                return start;
            }

        }
        return null;
        
<img width="841" height="487" alt="image" src="https://github.com/user-attachments/assets/441f05bc-b0eb-44af-a161-4f6903d17016" />

        
    }
}
