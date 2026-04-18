# Subsets
# Use backtracking (pick / not pick) to generate all subsets.

Time Complexity: O(n * 2^n)
Space Complexity: O(n) (recursion stack, excluding output)

# CODE 
class Solution {

    public List<List<Integer>> subsets(int[] nums) {
      
        List<List<Integer>> ans = new ArrayList<>();
        List<Integer> sub=new ArrayList<>();
        solve(0,nums,sub,ans);
        return ans;
        



    }
    private void solve(int index, int[] nums, List<Integer> sub ,List<List<Integer>>ans){
        if(index == nums.length){
            ans.add(new ArrayList<>(sub));
            return;
        }
        sub.add(nums[index]);
        solve(index+1,nums,sub,ans);

        sub.remove(sub.size()-1);
        solve(index+1,nums,sub,ans);
        
    }
}
<img width="1064" height="487" alt="image" src="https://github.com/user-attachments/assets/7d12ce38-0b57-4fb5-a342-869d2ff08fa6" />


