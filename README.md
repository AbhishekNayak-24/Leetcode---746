# Leetcode---746
Min Cost Climbing Stairs
//code in java
public class Solution {
    public int minCostClimbingStairs(int[] cost) {
        int n = cost.length;
        int[] dp = new int[n + 1];
        
        for (int i = 2; i <= n; i++) {
            dp[i] = Math.min(dp[i - 1] + cost[i - 1], dp[i - 2] + cost[i - 2]);
        }
        
        return dp[n];
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        int[] cost1 = {10, 15, 20};
        int[] cost2 = {1, 100, 1, 1, 1, 100, 1, 1, 100, 1};
        
        System.out.println(solution.minCostClimbingStairs(cost1)); // Output: 15
        System.out.println(solution.minCostClimbingStairs(cost2)); // Output: 6
    }
}
