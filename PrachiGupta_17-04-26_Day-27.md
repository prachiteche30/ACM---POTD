#  Lowest Common Ancestor of a Binary Tree
# Use recursive DFS — if current node is null or equals p or q, return it; otherwise recurse left & right, and if both sides return non-null, current node is the LCA.

Time Complexity: O(n) (visit each node once)
Space Complexity: O(h) (recursion stack, where h = height of tree

# CODE
class Solution {

    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if (root == null || root == p || root == q) {
            return root;
        }

        TreeNode left = lowestCommonAncestor(root.left, p, q);
        TreeNode right = lowestCommonAncestor(root.right, p, q);

        if (left != null && right != null) {
            return root;
        }

        return (left != null) ? left : right;
    }
}
<img width="972" height="498" alt="image" src="https://github.com/user-attachments/assets/313c9e74-bf51-46d2-8b48-2e13a7089f26" />
