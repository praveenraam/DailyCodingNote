

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

### [543. Diameter of Binary Tree](https://leetcode.com/problems/diameter-of-binary-tree/)

```Java
class Solution {
    int ans = 0;

    public int diameterOfBinaryTree(TreeNode root) {
        helper(root);
        return ans;
    }

    public int helper(TreeNode root){

        if(root == null) return 0;

        int right = helper(root.right);
        int left = helper(root.left);
        
        ans = Math.max(ans,right+left);

        return Math.max(right,left)+1;
    }
}
```

### [110. Balanced Binary Tree](https://leetcode.com/problems/balanced-binary-tree/)

```Java
class Solution {
    public boolean isBalanced(TreeNode root) {
        
        if(root == null) return true;
        
        boolean res = true;

        if(root.left == null && root.right != null){
            res = false;
        }else if(root.left != null && root.right == null){
            res = false;
        }
        if(root.left == null && root.right == null) return res;

        if(res == false) return res;
        return res && isBalanced(root.left) && isBalanced(root.right);
    }
}
```

### [572. Subtree of Another Tree](https://leetcode.com/problems/subtree-of-another-tree/)
```Java
class Solution {
    public boolean isSubtree(TreeNode root, TreeNode sr) {
        if(root == null) return false;
        if(isSame(root,sr)) return true;
        return isSubtree(root.left,sr) || isSubtree(root.right,sr);
    }
    public boolean isSame(TreeNode root,TreeNode sr){
        if(root == null && sr == null){
            return true;
        }else if(root == null || sr == null) return false;

        if(root.val != sr.val) return false;
        
        return isSame(root.right,sr.right) && isSame(root.left,sr.left);
    }
}
```

### [112. Path Sum](https://leetcode.com/problems/path-sum/)

```Java
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        return calculate(root,0,targetSum);
    }
    public boolean calculate(TreeNode root,int count,int targetSum){
        if(root == null) return false;
        count += root.val;
        if(count == targetSum && (root.left == null && root.right == null)) return true;

        return calculate(root.left,count,targetSum) || calculate(root.right,count,targetSum);
    }
}
```

### [3174. Clear Digits](https://leetcode.com/contest/biweekly-contest-132/problems/clear-digits/)
```Java
class Solution {
    public String clearDigits(String s) {
        
        Stack<Character> st = new Stack<>();

        for(char ch : s.toCharArray()){

            if('0' <= ch && ch <= '9'){
                if(!st.isEmpty()) st.pop();
            }else st.push(ch);

        }

        StringBuilder sb = new StringBuilder();

        while(!st.isEmpty()){
            sb.insert(0,st.pop());
        }
        return sb.toString();
    }
}
```

### [938. Range Sum of BST](https://leetcode.com/problems/range-sum-of-bst/)
```Java
class Solution {
    public int rangeSumBST(TreeNode root, int low, int high) {
        if(root == null) return 0;
        int sum = 0;
        if(low<=root.val && root.val <= high){
            sum += root.val;
        }
        return sum+(rangeSumBST(root.left,low,high)+rangeSumBST(root.right,low,high));

    }
}
```

### [2331. Evaluate Boolean Binary Tree](https://leetcode.com/problems/evaluate-boolean-binary-tree)
```Java
class Solution {
    public boolean evaluateTree(TreeNode root) {

        if(root.val == 1) return true;
        else if(root.val == 0) return false;

        if(root.val == 2){

            return evaluateTree(root.left) || evaluateTree(root.right);

        }else{

            return evaluateTree(root.left) && evaluateTree(root.right);

        }
    }
}
```

### [606. Construct String from Binary Tree](https://leetcode.com/problems/construct-string-from-binary-tree/)

```Java
class Solution {
    public String tree2str(TreeNode root) {
        StringBuilder sb = new StringBuilder();
        helper(root,sb);
        return sb.toString().substring(1,sb.length()-1);
    }
    public void helper(TreeNode root,StringBuilder sb){
        
        if(root == null) return;

        sb.append('(');
        sb.append(root.val);

        if(root.left == null && root.right != null){
            sb.append("()");
        }

        helper(root.left,sb);
        helper(root.right,sb);
        sb.append(')');
    }
}
```

### [617. Merge Two Binary Trees](https://leetcode.com/problems/merge-two-binary-trees/)

```Java
class Solution {
    public TreeNode mergeTrees(TreeNode root1, TreeNode root2) {
        
        if(root1 == null && root2 == null) return null;

        int val1 = root1 != null ? root1.val : 0;
        int val2 = root2 != null ? root2.val : 0;

        TreeNode rs = new TreeNode(val1+val2);

        rs.left = mergeTrees(
            (root1 != null && root1.left != null) ? root1.left : null,
            (root2 != null && root2.left != null) ? root2.left : null
        );

        rs.right = mergeTrees(
            (root1 != null && root1.right != null) ? root1.right : null,
            (root2 != null && root2.right != null) ? root2.right : null
        );
        
        return rs;
    }
}
```

### [235. Lowest Common Ancestor of a Binary Search Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)

```Java
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        
        while(root != null){
            if(root.val > q.val && root.val > p.val){
                root = root.left;
            }else if(root.val < q.val && root.val < p.val){
                root = root.right;
            }else return root;
        }
        return null;
    }
}
```

### [199. Binary Tree Right Side View](https://leetcode.com/problems/binary-tree-right-side-view)

```Java
class Solution {
    List<Integer> ls = new ArrayList<>();

    public List<Integer> rightSideView(TreeNode root) {
        helper(root,0);
        return ls;
    }
    public void helper(TreeNode root,int level){
        if(root == null) return;

        if(level == ls.size()) ls.add(root.val);

        if(root.right != null) helper(root.right,level+1);
        if(root.left != null) helper(root.left,level+1);
    }

}
```

### [102. Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/)

```Java
class Solution {

    List<List<Integer>> ls = new ArrayList<>();

    public List<List<Integer>> levelOrder(TreeNode root) {
        if(root == null) return ls;
        helper(root,0);
        return ls;
    }

    public void helper(TreeNode root,int level){
        if(ls.size() == level) ls.add(new ArrayList<Integer>());

        ls.get(level).add(root.val);

        if(root.left != null) helper(root.left,level+1);
        if(root.right != null) helper(root.right,level+1);

    }
}
```

### [701. Insert into a Binary Search Tree](https://leetcode.com/problems/insert-into-a-binary-search-tree)

```Java
class Solution {
    public TreeNode insertIntoBST(TreeNode root, int val) {
        
        if(root == null) return new TreeNode(val);

        TreeNode dup = root;

        while(true){
            if(root.val > val){
                if(root.left == null){
                    TreeNode newOne = new TreeNode(val);
                    root.left = newOne;
                    break;
                }
                root = root.left;

            }else if(root.val < val){
                if(root.right == null){
                    TreeNode newOne = new TreeNode(val);
                    root.right = newOne;
                    break;
                }
                root = root.right;
            }
        }
        return dup;
    }
}
```