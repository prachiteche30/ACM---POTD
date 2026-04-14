 # Course Schedule
 # Treat courses as a directed graph and apply topological sort (BFS/Kahn’s Algorithm) by tracking indegrees ,
 If you can process all nodes (count == numCourses), return true; otherwise a cycle exists → return false.
Time Complexity: O(V + E) (V = numCourses, E = prerequisites)
Space Complexity: O(V + E) (graph + indegree + queue)

# CODE 
class Solution {

    public boolean canFinish(int numCourses, int[][] prerequisites) {
        List<List<Integer>> graph = new ArrayList<>();
        int[] indegree = new int[numCourses];

        for(int i = 0; i < numCourses; i++) {
            graph.add(new ArrayList<>());
        }

        for(int[] pre : prerequisites) {
            int a = pre[0];
            int b = pre[1];
            graph.get(b).add(a);
            indegree[a]++;
        }

        Queue<Integer> q = new LinkedList<>();

        for(int i = 0; i < numCourses; i++) {
            if(indegree[i] == 0) {
                q.add(i);
            }
        }

        int count = 0;

        while(!q.isEmpty()) {
            int curr = q.poll();
            count++;

            for(int nei : graph.get(curr)) {
                indegree[nei]--;
                if(indegree[nei] == 0) {
                    q.add(nei);
                }
            }
        }

        return count == numCourses;
    }
}
<img width="634" height="512" alt="image" src="https://github.com/user-attachments/assets/bc45dfc4-25ff-458b-8f59-4e84899678c8" />
