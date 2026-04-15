# Binary Tree Level Order Traversal
# Level Order Traversal using BFS (queue) — process nodes level by level, pushing children into the queue and collecting values per level.
# Time Complexity:
O(n) — each node is visited exactly once

# Space Complexity:
O(n) — queue + result storage in worst case (last level)
# CODE
class Solution {

    public List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> result=new ArrayList<>();

        if(root==null) return result;

        Queue<TreeNode> queue =new LinkedList<>();
        queue.offer(root);

        while(!queue.isEmpty()){
            int size=queue.size();
            List<Integer> level= new ArrayList<>();

            for(int i=0;i<size;i++){
                TreeNode node=queue.poll();
                level.add(node.val);

                if(node.left !=null){
                    queue.offer(node.left);

                }
                if(node.right !=null){
                    queue.offer(node.right);

                }
            }
            result.add(level);
        }
        return result;

    }
}
<img width="777" height="471" alt="image" src="https://github.com/user-attachments/assets/277df00b-51fe-4d96-9440-d995f1b61294" />
