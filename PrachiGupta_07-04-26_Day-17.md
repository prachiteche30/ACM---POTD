# Next Greater Element I
# Use a monotonic decreasing stack to process nums2, mapping each element to its next greater element by popping smaller elements when a larger one appears, and store results in a hashmap. Then, build the answer for nums1 by directly fetching values from the map.

Time Complexity: O(n + m)
Space Complexity: O(n)
# CODE
class Solution {

    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
       Stack<Integer> st =new Stack<>();
       Map<Integer,Integer> map =new HashMap<>();

        for(int num: nums2){
            while(!st.isEmpty() && st.peek() < num){
                map.put(st.pop() , num);

            }
            st.push(num);
        }

        while(!st.isEmpty()){
            map.put(st.pop(),-1);
        }

        int[] ans=new int[nums1.length];
        for(int i=0;i<nums1.length;i++){
            ans[i]=map.get(nums1[i]);
        }

        return ans;
<img width="938" height="482" alt="image" src="https://github.com/user-attachments/assets/d25d358c-1b70-4e55-a0a1-13ff7b45d8a6" />



        
    
    }
}
