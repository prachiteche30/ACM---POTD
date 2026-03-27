#  Check If N and Its Double Exist
#  Using HashSet ,SC : O(n) , TC : O(n)
#  CODE

class Solution {

    public boolean checkIfExist(int[] arr) {
        HashSet<Integer> set=new HashSet<>();
        for(int num : arr){
            if(set.contains(2*num)) return true;
            if((num%2==0) && set.contains(num/2)) return true;
            set.add(num);
        }
        return false;
    }
}
<img width="939" height="439" alt="image" src="https://github.com/user-attachments/assets/26c1a418-803f-45b3-a866-e843aa5727a5" />
