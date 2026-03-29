# Remove Nth Node From End of List
# CODE 
class Solution {

    public ListNode removeNthFromEnd(ListNode head, int n) {
        
        if(head == null) return null;
        int len = 0;
        ListNode temp = head;

        while(temp != null){
            len++;
            temp = temp.next;
        }

        if(len == n){
            return head.next;
        }

        ListNode curr = head;
        for(int i = 1; i < len - n; i++){
            curr = curr.next;
        }
        
        curr.next = curr.next.next;
        return head;
    }
}
<img width="875" height="494" alt="image" src="https://github.com/user-attachments/assets/134b66af-22d9-4e2f-a615-c19c49c5a555" />
