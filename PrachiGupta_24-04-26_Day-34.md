# House Robber
# At every house i, we  have 2 choices:
Take the house → earn nums[i] and move to i + 2
Skip the house → move to i + 1
#  Time Complexity:O(n) ,  Space Complexity: O(n) (with memoization)
# CODE 
class Solution {

    public int rob(int[] nums) {
        int[] dp=new int[nums.length];
        Arrays.fill(dp,-1);

        return cost(nums,0,dp);
        
    }
    private int cost(int[] nums , int idx ,int[] dp){
        if(idx>=nums.length){
            return 0;
        }
        if (dp[idx]!=-1) return dp[idx];
        int take = nums[idx] + cost(nums, idx + 2, dp); // take current
        int skip = cost(nums, idx + 1, dp);             // skip current

        dp[idx] = Math.max(take, skip);
        return dp[idx];
    }
}
<img width="892" height="483" alt="image" src="https://github.com/user-attachments/assets/653b865c-7533-45d7-beb4-f29cc63d8f97" />
