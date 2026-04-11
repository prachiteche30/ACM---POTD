 # 132 Pattern
 # Traverse from right, use a stack to track possible nums[j], and maintain a variable third as nums[k] , Time: O(n) , Space: O(n)
 # CODE 
 class Solution {
 
    public boolean find132pattern(int[] nums) {
        int n = nums.length;
        int third = Integer.MIN_VALUE;
        Stack<Integer> st = new Stack<>();
        
        for (int i = n - 1; i >= 0; i--) {
            if (nums[i] < third) return true;
            
            while (!st.isEmpty() && st.peek() < nums[i]) {
                third = st.pop();
            }
            
            st.push(nums[i]);
        }
        
        return false;
    }
    

}
<img width="864" height="505" alt="image" src="https://github.com/user-attachments/assets/6480f009-0b46-4a4a-826e-23ed92bb330a" />
 
