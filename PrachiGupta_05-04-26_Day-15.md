#  Min Stack
We use two stacks: one to store all elements and another to track the minimum at each stage, updating it during push and pop to always have the current minimum on top.
Time Complexity: O(1) for push, pop, top, getMin  Space Complexity: O(n) for the extra min stack.
# CODE
class MinStack {

    Stack<Integer> stack;
    Stack<Integer> minStack;

    public MinStack() {
        stack = new Stack<>();
        minStack = new Stack<>();
    }
    
    public void push(int val) {
        stack.push(val);

        if (minStack.isEmpty() || val <= minStack.peek()) {
            minStack.push(val);
        }
    }
    
    public void pop() {
        if (stack.isEmpty()) return;

        if (stack.peek().equals(minStack.peek())) {
            minStack.pop();
        }
        stack.pop();
    }
    
    public int top() {
        if (stack.isEmpty()) return -1;  
        return stack.peek();
    }
    
    public int getMin() {
        if (minStack.isEmpty()) return -1;  
        return minStack.peek();
    }
}










<img width="915" height="488" alt="image" src="https://github.com/user-attachments/assets/17faaf2f-13c0-46b1-832c-143aa5c6634b" />
