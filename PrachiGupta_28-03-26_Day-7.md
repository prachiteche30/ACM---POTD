#  Increasing Triplet Subsequence
# find smallest ,second smallest and then greater than these two in one pass , SC : O(1) ,TC : O(n)
# CODE
class Solution {

    public boolean increasingTriplet(int[] nums) {
        int first = Integer.MAX_VALUE;
        int second = Integer.MAX_VALUE;

        for (int num : nums) {
            if (num <= first) {
                first = num;  // smallest so far
            } 
            else if (num <= second) {
                second = num; // second smallest
            } 
            else {
                // num > first and num > second
                return true;
            }
        }
        return false;
    }
}
<img width="793" height="488" alt="image" src="https://github.com/user-attachments/assets/2d5d668f-39ca-44bf-9151-6e743acd9ef4" />


