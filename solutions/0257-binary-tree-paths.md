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
  List<String> binaryTreePaths(TreeNode? root) {
      if (root == null) {
          return [];
      }
      final result = <String>[];
      
      void helper(TreeNode node, String temp) {
          if (node.left == null && node.right == null) {
              result.add(temp);
              return;
          }
          if (node.left != null) {
              helper(node.left!, temp + '->${node.left!.val}');
          }
          if (node.right != null) {
              helper(node.right!, temp + '->${node.right!.val}');
          }
      }
      helper(root, root.val.toString());
      return result;
  }
}
```
