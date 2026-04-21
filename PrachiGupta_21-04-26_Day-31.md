# Climbing Stairs
# Number of ways to reach step n = ways to reach (n-1) + (n-2) → classic Fibonacci using memoization.

Time Complexity: O(n) (each state computed once due to DP)
Space Complexity: O(n) (dp array + recursion stack)

# CODE 
class Solution {

    public int climbStairs(int n) {
        int[] dp = new int[n + 1];
        return solve(n,dp);
        
    }
    private int solve(int n,int[] dp){
        if (n<0) return 0;
        if(n==0) return 1;

        if(dp[n]!=0) return dp[n];

        int one_step=solve(n-1,dp);
        int two_step=solve(n-2,dp);


        dp[n]= one_step+two_step;
        return dp[n];
    }
    
}
<img width="685" height="512" alt="image" src="https://github.com/user-attachments/assets/54a7e595-d25f-491a-a723-c89cceff0364" />
