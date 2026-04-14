#  Number of Provinces
#  Count the number of connected components (provinces) in the graph using DFS on the adjacency matrix.
Time Complexity: O(n²)
Space Complexity: O(n) (visited + recursion stack)



# CODE 
class Solution {

    public int findCircleNum(int[][] isConnected) {
        int n =isConnected.length;
        boolean[] visited=new boolean[n];
        int count=0;

        for(int i=0;i<n;i++){
            if(!visited[i]){
                dfs(isConnected , visited, i);
                count++;
            }
        }
        return count;
        
    }
    private void dfs(int[][] isConnected,boolean[] visited,int i){
        visited[i]=true;
         int n =isConnected.length;
        for(int j=0;j<n;j++){
            if(isConnected[i][j]==1 && !visited[j] ){
                dfs(isConnected,visited,j);

            }
        }
    }  
}
<img width="873" height="500" alt="image" src="https://github.com/user-attachments/assets/e066ad8a-8de0-4234-a8ef-829c36c3a593" />
