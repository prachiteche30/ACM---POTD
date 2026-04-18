 # Construct Binary Tree from Preorder and Inorder Traversal
 # Pick root from preorder, split inorder into left/right parts, recursively build subtrees , Time Complexity: O(n) , Space Complexity: O(n)

 # CODE 
 class Solution {
 
    int preIndex = 0;
    Map<Integer, Integer> map = new HashMap<>();

    public TreeNode buildTree(int[] preorder, int[] inorder) {
        for (int i = 0; i < inorder.length; i++) {
            map.put(inorder[i], i);
        }
        return helper(preorder, 0, inorder.length - 1);
    }

    private TreeNode helper(int[] preorder, int left, int right) {
        if (left > right) return null;

        int rootVal = preorder[preIndex++];
        TreeNode root = new TreeNode(rootVal);

        int mid = map.get(rootVal);

        root.left = helper(preorder, left, mid - 1);
        root.right = helper(preorder, mid + 1, right);

        return root;
    }
}
<img width="913" height="501" alt="image" src="https://github.com/user-attachments/assets/0bc82bfe-60b3-413b-b48a-bc953a8dcba3" />

 
 
