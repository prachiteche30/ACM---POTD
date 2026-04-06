 # Daily Temperatures
 # Use a monotonic decreasing stack to store indices of unresolved days; when a warmer temperature appears, resolve previous indices.
Each index is pushed and popped at most once → efficient single pass.
Time Complexity: O(n)
Space Complexity: O(n)
# CODE
class Solution {

    public int[] dailyTemperatures(int[] temperatures) {
        int n = temperatures.length;
        int[] answer = new int[n];
        Stack<Integer> stack = new Stack<>(); 
        
        for (int i = 0; i < n; i++) {
            while (!stack.isEmpty() && temperatures[i] > temperatures[stack.peek()]) {
                int prevIndex = stack.pop();
                answer[prevIndex] = i - prevIndex;
            }
            stack.push(i);
        }
        
        return answer;
    }
}
<img width="1045" height="477" alt="image" src="https://github.com/user-attachments/assets/f9a68cc8-ba49-4cad-944f-e62e203cfd05" />
