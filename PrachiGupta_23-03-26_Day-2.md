# Subarray Sum Equals K
# Prefix Sum + HashMap
#CODE 

class Solution {
    public int subarraySum(int[] nums, int k) {
        HashMap<Integer, Integer> map = new HashMap<>();
        
        map.put(0, 1); 
        int sum = 0;
        int count = 0;
        
        for (int num : nums) {
            sum += num;
            
            if (map.containsKey(sum - k)) {
                count += map.get(sum - k);
            }
            
            map.put(sum, map.getOrDefault(sum, 0) + 1);
        }
        
        return count;
    }
}
<img width="898" height="493" alt="image" src="https://github.com/user-attachments/assets/6bacbaae-671f-4bf3-9d19-3c01e6ae5897" />

