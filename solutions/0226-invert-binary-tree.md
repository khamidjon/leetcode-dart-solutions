```
/**
 * Definition for a binary tree node.
 * class TreeNode {
 *   int val;
 *   TreeNode? left;
 *   TreeNode? right;
 *   TreeNode([this.val = 0, this.left, this.right]);
 * }
 */
class Solution {
  TreeNode? invertTree(TreeNode? root) {
      if (root == null) {
          return null;
      }
      
      void helper(TreeNode node) {
          TreeNode? left = node.left;
          node.left = node.right;
          node.right = left;
          if (node.left != null) {
              helper(node.left!);
          }
          
          if (node.right != null) {
              helper(node.right!);
          }
      }
      helper(root);
      return root;
  }   
}
```
