# Kth Smallest Element in a BST
# Perform inorder traversal (L → Root → R) of the BST and return the kth visited node.
Time Complexity: O(H + k) (worst case O(n))
Space Complexity: O(H) (recursion/stack)

# CODE 
class Solution {

    int count=0;
    int ans=0;
    public int kthSmallest(TreeNode root, int k) {
        inorder(root,k);
        return ans;
    }
    private void inorder(TreeNode root, int k){
        if(root==null) return ;

        inorder(root.left,k);
        if(count>k) return ;
        count++;
        if(count==k){
            ans=root.val;
            return;
        }
        inorder(root.right,k);
    }
}
<img width="883" height="505" alt="image" src="https://github.com/user-attachments/assets/a73725e7-d26a-4ff3-868f-64e0a6a95988" />
