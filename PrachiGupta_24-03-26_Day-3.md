# Sort Colors 
# TC;o(n) , SC;O(n) , Using Dutch National Flag Algorithm
class Solution {
    public void sortColors(int[] nums) {
        int low = 0, mid = 0, high = nums.length - 1;

        while (mid <= high) {
            if (nums[mid] == 0) {
                int temp = nums[low];
                nums[low] = nums[mid];
                nums[mid] = temp;

                low++;
                mid++;
            } 
            else if (nums[mid] == 1) {
                mid++;
            } 
            else { 
                int temp = nums[mid];
                nums[mid] = nums[high];
                nums[high] = temp;

                high--;
            }
        }
    }
}
<img width="925" height="446" alt="image" src="https://github.com/user-attachments/assets/4ba06632-9689-408d-8002-dd750f3327e8" />

