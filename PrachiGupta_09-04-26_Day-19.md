#  Evaluate Reverse Polish Notation

# Use a stack to process tokens—push numbers, and for each operator pop two elements, apply the operation, and push the result back.
Time Complexity: O(n)
Space Complexity: O(n)

# CODE

class Solution {

    public int evalRPN(String[] tokens) {
        Stack<Integer> st = new Stack<>();

        for (int i = 0; i < tokens.length; i++) {
            if (!tokens[i].equals("+") && !tokens[i].equals("-") &&
                !tokens[i].equals("*") && !tokens[i].equals("/")) {

                st.push(Integer.parseInt(tokens[i]));
            } 
            else {
                int a = st.pop();
                int b = st.pop();

                if (tokens[i].equals("+")) {
                    st.push(b + a);
                } 
                else if (tokens[i].equals("-")) {
                    st.push(b - a);
                } 
                else if (tokens[i].equals("*")) {
                    st.push(b * a);
                } 
                else {
                    st.push(b / a);
                }
            }
        }


        return st.pop();
    }
}
<img width="857" height="489" alt="image" src="https://github.com/user-attachments/assets/d4e0301e-ad86-40ef-81d9-275acccf52c5" />
