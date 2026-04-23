# Min Cost Climbing Stairs
# From each step, choose min(one step, two steps) : cost[i] + min(f(i+1), f(i+2))
Time Complexity: O(n) (each index solved once)
Space Complexity: O(n) (dp array + recursion stack)
# CODE 
class Solution {

    public int minCostClimbingStairs(int[] cost) {
        int n = cost.length;
        int[] dp = new int[n];
        Arrays.fill(dp, -1);

        return Math.min(solve(cost, 0, dp), solve(cost, 1, dp));
    }

    private int solve(int[] cost, int i, int[] dp) {
        if (i >= cost.length) return 0;

        if (dp[i] != -1) return dp[i];

        int one = solve(cost, i + 1, dp);
        int two = solve(cost, i + 2, dp);

        dp[i] = cost[i] + Math.min(one, two);
        return dp[i];
    }
}
<img width="886" height="522" alt="image" src="https://github.com/user-attachments/assets/c0bbd521-f7ae-4ac7-98f2-d3bdbd2d90d8" />
