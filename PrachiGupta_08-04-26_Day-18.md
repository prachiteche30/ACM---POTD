# Next Greater Element II

# Approach
 Use a monotonic decreasing stack (storing indices) and traverse the array twice (2n) to simulate circular behavior.
 When a greater element is found, pop indices from the stack and update their next greater value.

Complexity:
Time: O(n)
Space: O(n)

# CODE
class Solution {

    public int[] nextGreaterElements(int[] nums) {
        int[] result=new int[nums.length];
        Arrays.fill(result,-1);
        int n=nums.length;
        Stack<Integer> st =new Stack<>();

        for(int i=0;i<2*n;i++){
            int num=nums[i%n];

            while(!st.isEmpty() && nums[st.peek()] < num){
                result[st.pop()]=num;
            }
            if(i<n){
                st.push(i);
            }

        }

       return result;
        
    }
}<img width="352" height="490" alt="image" src="https://github.com/user-attachments/assets/ac14cb6c-9559-46bf-a399-1bf67f7b494a" />


