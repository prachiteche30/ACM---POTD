# product-of-array-except-self
# using prefix and suffix product, SC: O(1){excluding the resultant array} ,TC :O(2n)
# CODE
class Solution {

    public int[] productExceptSelf(int[] nums) {
    
        int n=nums.length;
        int[] product=new int[n];
        int idx=0;
        int left=1;
        for(int i=0;i<n;i++){
            product[idx]=left;
            left=left*nums[idx];
            idx++;
        }
        idx=n-1;
        int right=1;
        for(int i=n-1;i>=0;i--){
            product[idx]*=right;
            right=right*nums[idx];
            idx--;

        }
        return product;
    }
}
<img width="861" height="516" alt="image" src="https://github.com/user-attachments/assets/090b013a-ec23-4f20-aa04-0a9908bf8a52" />
