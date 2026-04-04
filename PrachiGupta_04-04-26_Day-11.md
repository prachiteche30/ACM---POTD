 # Swap Nodes in Pairs
 # We swap nodes in pairs by adjusting pointers using a dummy node to handle edge cases cleanly.
Time Complexity: O(n), Space Complexity: O(1).
# CODE

class Solution {

    public ListNode swapPairs(ListNode head) {
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode curr = dummy;

        while (curr.next != null && curr.next.next != null) {
            ListNode first = curr.next;
            ListNode second = curr.next.next;

            first.next = second.next;
            second.next = first;
            curr.next = second;

            curr = first;
        }
        return dummy.next;
    }
}
<img width="969" height="524" alt="image" src="https://github.com/user-attachments/assets/faa1647b-b705-421d-a4ab-1e5ca8a99672" />
