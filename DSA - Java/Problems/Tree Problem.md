

### [144. Binary Tree Preorder Traversal](https://leetcode.com/problems/binary-tree-preorder-traversal/)

```Java
class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> ls = new ArrayList<>();

        if(root == null) return ls;

        ls.add(root.val);
        ls.addAll(preorderTraversal(root.left));
        ls.addAll(preorderTraversal(root.right));

        return ls;
    }
}
```

### [94. Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/description/)

```Java
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> ls = new ArrayList<>();

        if(root == null) return ls;

        ls.addAll(inorderTraversal(root.left));
        ls.add(root.val);
        ls.addAll(inorderTraversal(root.right));

        return ls;
    }
}
```

### [145. Binary Tree Postorder Traversal](https://leetcode.com/problems/binary-tree-postorder-traversal/description/)

```Java
class Solution {
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> ls = new ArrayList<>();

        if(root == null) return ls;

        ls.addAll(postorderTraversal(root.left));
        ls.addAll(postorderTraversal(root.right));
        ls.add(root.val);

        return ls;

    }
}
```