#  Remove K Digits
# Use a monotonic increasing stack, greedily removing larger previous digits when a smaller digit appears to minimize the number , TC: O(n) , SC: O(n)
# CODE 
class Solution {

    public String removeKdigits(String num, int k) {
        Stack<Character> st = new Stack<>();
        for (char c : num.toCharArray()) {
            while (!st.isEmpty() && k > 0 && st.peek() > c) {
                st.pop();
                k--;
            }
            st.push(c);
        }
        while (k-- > 0) st.pop();
        StringBuilder sb = new StringBuilder();
        while (!st.isEmpty()) sb.append(st.pop());
        sb.reverse();
        int i = 0;
        while (i < sb.length() && sb.charAt(i) == '0') i++;
        String res = sb.substring(i);
        return res.length() == 0 ? "0" : res;
    }
}
<img width="927" height="489" alt="image" src="https://github.com/user-attachments/assets/71627159-d046-413c-9105-280fa46681a2" />

