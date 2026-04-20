# Power of Two 
# A number is a power of 2 iff it has only one set bit → n > 0 && (n & (n - 1)) == 0.
Time Complexity: O(1) (single bitwise operation)
Space Complexity: O(1) 

# CODE 
class Solution {

    public boolean isPowerOfTwo(int n) {
        if(n<=0) return false;
        return ((n & (n-1))==0);
    }
}
<img width="713" height="515" alt="image" src="https://github.com/user-attachments/assets/bd19a647-a0cd-4e9e-a140-64031bab18e7" />

