

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

### [104. Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)
```Java
class Solution {
    public int maxDepth(TreeNode root) {
        return counter(root,0);
    }
    public static int counter(TreeNode root,int count){
        if(root == null) return count;

        count++;
        int maxLeft = counter(root.left,count);
        int maxRight = counter(root.right,count);

        return Math.max(maxLeft,maxRight);
    }
}
```

### [226. Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/description/)

```Java
class Solution {
    public TreeNode invertTree(TreeNode root) {
        
        if(root == null) return null;

        swapper(root);

        return root;
    }
    public static void swapper(TreeNode root){
        if(root == null) return;

        TreeNode mytree = new TreeNode(root.val);
        mytree = root.right;
        root.right = root.left;
        root.left = mytree;

        swapper(root.right);
        swapper(root.left);
    }
}
```

### [100. Same Tree](https://leetcode.com/problems/same-tree/description/)

```Java
class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {

        if(p == null && q == null) return true;

        if(p == null || q == null || p.val != q.val) return false;

        return isSameTree(p.left , q.left) && isSameTree(p.right,q.right);

    }
}
```