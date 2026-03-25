# Two Sum II - Input Array Is Sorted
# Using two pointers , SC :  O(1) , TC : O(n)
# CODE
# class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int left=0;
        int right=numbers.length-1;
        while(left < right){
            if(numbers[left]+numbers[right]==target){
                return new int[]{left+1,right+1};
            }
            else if(numbers[left]+numbers[right]>target){
                right-=1;
            }
            else{
                left+=1;
            }
        }
        return new int[]{-1,-1};
        
    }
}
<img width="1083" height="524" alt="image" src="https://github.com/user-attachments/assets/7500e329-a06d-48b4-9e5b-c135f5a0b32b" />
