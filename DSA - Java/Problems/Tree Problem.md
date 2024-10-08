

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

### [101. Symmetric Tree](https://leetcode.com/problems/symmetric-tree/description/)

```Java
class Solution {
    public boolean isSymmetric(TreeNode root) {
        if(root == null) return true;
        return find(root.left,root.right);
    }
    public boolean find(TreeNode right,TreeNode left){
        if(left == null && right == null){
            return true;
        }
        if(left == null || right == null) return false;

        if(right.val == left.val) return find(left.right,right.left) && find(left.left,right.right);;
        return false;
    }
}
```

### [872. Leaf-Similar Trees](https://leetcode.com/problems/leaf-similar-trees/description/)

```Java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public boolean leafSimilar(TreeNode root1, TreeNode root2) {
        List<Integer> ls1 = new ArrayList<>();
        List<Integer> ls2 = new ArrayList<>();

        traverse(root1,ls1);
        traverse(root2,ls2);

        return ls1.equals(ls2);
    }
    public void traverse(TreeNode root,List<Integer> ls){
        if(root == null) return;

        if(root.left == null && root.right == null){
            ls.add(root.val);
        }

        traverse(root.left,ls);
        traverse(root.right,ls);
    }
}
```

### [108. Convert Sorted Array to Binary Search Tree](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/)

```Java
class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        int n = nums.length;

        if(n == 0) return null;
        if(n == 1) return new TreeNode(nums[0]);

        TreeNode head = buildTree(nums,0,n-1);
        return head;
    }
    public TreeNode buildTree(int[] num, int low, int high){
        if(low>high) return null;

        int mid = (low+high)/2;
        TreeNode node = new TreeNode(num[mid]);

        node.left = buildTree(num,low,mid-1);
        node.right = buildTree(num,mid+1,high);

        return node;
    }
}
```

### [1110. Delete Nodes And Return Forest](https://leetcode.com/problems/delete-nodes-and-return-forest/description/)

```Java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {

    Set<Integer> st = new HashSet<>();
    List<TreeNode> res = new ArrayList<>();

    public List<TreeNode> delNodes(TreeNode root, int[] to_delete) {
        for(int i : to_delete){
            st.add(i);
        }
        helper(root,true);
        return res;
    }
    public TreeNode helper(TreeNode node,boolean is_root){
        if(node == null) return null;

        boolean delete = st.contains(node.val);
        if(is_root && !delete) res.add(node);
        node.left = helper(node.left,delete);
        node.right = helper(node.right,delete);
        return delete ? null : node;
    }
}
```

### [783. Minimum Distance Between BST Nodes](https://leetcode.com/problems/minimum-distance-between-bst-nodes/description/)

```Java
class Solution {
    public int minDiffInBST(TreeNode root) {
        List<Integer> ls = inOrder(root);

        int min = Integer.MAX_VALUE;
        for(int i=1;i<ls.size();i++){
            min = Math.min(min,ls.get(i)-ls.get(i-1));
            System.out.println(min);
        }
        System.out.println(ls);
        return min;
    }
    public List<Integer> inOrder(TreeNode root){
        List<Integer> ls = new ArrayList<>();

        if(root == null) return ls;

        ls.addAll(inOrder(root.left));
        ls.add(root.val);
        ls.addAll(inOrder(root.right));

        return ls;
    }
}
```

### [103. Binary Tree Zigzag Level Order Traversal](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/)

```Java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    
    List<List<Integer>> ls = new ArrayList<>();

    public List<List<Integer>> zigzagLevelOrder(TreeNode root) {
        func(root,0);
        return ls;
    }
    public void func(TreeNode root,int level){

        if(root == null) return;

        if(level >= ls.size()){
            ls.add(new ArrayList<>());
        }
        
        List<Integer> nsLs = ls.get(level);
        if(level%2 == 1){
            nsLs.add(root.val);
        }else{
            nsLs.add(0,root.val);
        }

        func(root.right,level+1);
        func(root.left,level+1);
    }
}
```

### [652. Find Duplicate Subtrees](https://leetcode.com/problems/find-duplicate-subtrees/description/)

```Java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    HashMap<String,Integer> mp = new HashMap<>();
    List<TreeNode> ls = new ArrayList<>();

    public List<TreeNode> findDuplicateSubtrees(TreeNode root) {
        dfs(root);
        return ls;
    }
    public String dfs(TreeNode root){

        if(root == null) return "N";

        String left = dfs(root.left);
        String right = dfs(root.right);

        String curr = root.val + "," + left + "," + right;

        if(mp.containsKey(curr) && mp.get(curr) == 1){
            ls.add(root);
            mp.put(curr,mp.getOrDefault(curr,0)+1);
        }else{
            mp.put(curr,mp.getOrDefault(curr,0)+1);
        }
        return curr;
    } 
}
```

### [958. Check Completeness of a Binary Tree](https://leetcode.com/problems/check-completeness-of-a-binary-tree/description/)

```Java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public boolean isCompleteTree(TreeNode root) {
        Queue<TreeNode> q = new LinkedList<>();

        q.add(root);
        boolean flag = false;

        while(!q.isEmpty()){
            TreeNode temp = q.poll();
            if(temp == null) flag = true;
            else{
                if(flag) return false;
                q.add(temp.left);
                q.add(temp.right);
            }
        }
        return true;
    }
}
```

### [1448. Count Good Nodes in Binary Tree](https://leetcode.com/problems/count-good-nodes-in-binary-tree/description/)

```Java

class Solution {

    int res=0;

    public int goodNodes(TreeNode root) {
        dfs(root,root.val);
        return res;
    }
    public void dfs(TreeNode root,int max){

        if(root == null) return;

        if(root.val >= max) {
            res++;
            max = root.val;
        }
        dfs(root.right,max);
        dfs(root.left,max);
    }
}
```

### [98. Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree/description/)

```Java
class Solution {
    public boolean isValidBST(TreeNode root) {
        return check(root,null,null);
    }
    public boolean check(TreeNode root,Integer min,Integer max){
        if(root == null) return true;

        if((min!= null && min >= root.val) || (max!=null && max <= root.val)) return false;

        return check(root.left, min,root.val) && check(root.right,root.val,max);
    } 
}
```

### [230. Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/description/)

```Java
class Solution {    
    HashSet<Integer> st = new HashSet<>();

    public int kthSmallest(TreeNode root, int k) {
        dfs(root);
        ArrayList<Integer> ls = new ArrayList<>(st);
        return ls.get(k-1);
    }
    public void dfs(TreeNode root){
        if(root == null) return;
         
        st.add(root.val);
        
        dfs(root.left);
        dfs(root.right);
    }
}
```

### [129. Sum Root to Leaf Numbers](https://leetcode.com/problems/sum-root-to-leaf-numbers/description/)

```Java
class Solution { 
    int val = 0;

    public int sumNumbers(TreeNode root) {
        func(root,0);
        return val;
    }
    public void func(TreeNode root,int cur){
        if(root == null){
            return;
        }
        cur = cur*10 + root.val;
        if(root.right == null && root.left == null){
            val += cur;
            return;
        }
        func(root.right,cur); func(root.left,cur);
    }
}
```

### [515. Find Largest Value in Each Tree Row](https://leetcode.com/problems/find-largest-value-in-each-tree-row/description/)

```Java

class Solution {
    List<Integer> ls = new ArrayList<>();
    public List<Integer> largestValues(TreeNode root) {
        if(root == null) return new ArrayList<>();
        dfs(root,0);
        return ls;
    }
    public void dfs(TreeNode root,int level){
        if(root == null) return;

        if(ls.size()<=level){
            ls.add(root.val);
        }
        else{
            ls.set(level,Math.max(root.val,ls.get(level)));
        }

        dfs(root.left,++level);
        dfs(root.right,level);
    }
}
```

### [1609. Even Odd Tree](https://leetcode.com/problems/even-odd-tree/description/)

```Java
class Solution {
    List<Integer> ls = new ArrayList<>();

    public boolean isEvenOddTree(TreeNode root) {
        return dfs(root,0);
    }
    public boolean dfs(TreeNode root,int level){

        if(root == null) return true;

        if(level%2 == 0){

            if(root.val%2 == 0) return false;

            if(ls.size() <= level){
                ls.add(root.val);
            }
            else if(ls.get(level) >= root.val){
                return false;
            }
            ls.set(level,root.val);
        }else{

            if(root.val%2 == 1) return false;

            if(ls.size() <= level){
                ls.add(root.val);
            }
            else if(ls.get(level) <= root.val){
                return false;
            }
            ls.set(level,root.val);

        }
        return dfs(root.left,level+1) && dfs(root.right,level+1);
    }
}
```

### [538. Convert BST to Greater Tree](https://leetcode.com/problems/convert-bst-to-greater-tree/description/)

```Java
class Solution {
    int[] sum = {0};
    public TreeNode convertBST(TreeNode root) {
        dfs(root,sum);
        return root;
    }
    public void dfs(TreeNode root,int[] sum){
        if(root == null) return;
        dfs(root.right, sum);
        sum[0] += root.val;
        root.val = sum[0];
        dfs(root.left, sum);;
    }
}
```

### [1302. Deepest Leaves Sum](https://leetcode.com/problems/deepest-leaves-sum/description/)

```Java
class Solution {
    int sum = 0;
    int maxLevel = -1;
    public int deepestLeavesSum(TreeNode root) {
        dfs(root,0);
        return sum;
    }
    public void dfs(TreeNode root,int level){

        if(root == null) return;
        if(maxLevel < level){
            sum=0;
            maxLevel = level;
        }
        if(maxLevel == level){
            sum+=root.val;
        }
        

        dfs(root.left,level+1);
        dfs(root.right,level+1);
    }
}
```

### [654. Maximum Binary Tree](https://leetcode.com/problems/maximum-binary-tree/description/)

```Java
class Solution {
    public TreeNode constructMaximumBinaryTree(int[] nums) {
        return func(nums,0,nums.length-1);
    }
    public TreeNode func(int[] nums,int s,int e){

        if(s>e) return null;

        int max = Integer.MIN_VALUE;
        int maxInd = -1;

        for(int i=s;i<=e;i++){
            if(max < nums[i]){
                max = nums[i];
                maxInd = i;
            }
        }
        TreeNode res = new TreeNode(max);
        res.left = func(nums,s,maxInd-1);
        res.right = func(nums,maxInd+1,e);

        return res;
    }
}
```

### [1038. Binary Search Tree to Greater Sum Tree](https://leetcode.com/problems/binary-search-tree-to-greater-sum-tree/description/)

```Java
class Solution {
    List<Integer> ls = new ArrayList<>();

    public TreeNode bstToGst(TreeNode root) {
        dfs(root,0);
        System.out.println(ls);
        return root;
    }
    public int dfs(TreeNode root,int sum){

        if(root == null) return sum;
        sum = dfs(root.right,sum);
        sum += root.val;
        root.val = sum;
        
        sum = dfs(root.left,sum);

        return sum;
    }
}
```

### [107. Binary Tree Level Order Traversal II](https://leetcode.com/problems/binary-tree-level-order-traversal-ii/description/)

```Java
class Solution {
    List<List<Integer>> ls = new ArrayList<>();
    public List<List<Integer>> levelOrderBottom(TreeNode root) {
        bfs(root,0);
        Collections.reverse(ls);
        return ls;
    }
    public void bfs(TreeNode root, int level){

        if(root == null) return;

        if(ls.size() == level){
            ls.add(new ArrayList<>());
        }

        List<Integer> col = ls.get(level);
        col.add(root.val);

        bfs(root.left,level+1);
        bfs(root.right,level+1);
    }
}
```

### [1325. Delete Leaves With a Given Value](https://leetcode.com/problems/delete-leaves-with-a-given-value/description/)

```Java
class Solution {
    public TreeNode removeLeafNodes(TreeNode root, int target) {
        dfs(root,target);
        if(root.val == target && isLeaf(root)) return null;
        return root;
    }
    public void dfs(TreeNode root,int target){

        if(root == null) return;

        
        dfs(root.left,target);
        dfs(root.right,target);

        if(root.left != null && root.left.val == target && isLeaf(root.left)){
            root.left = null;
        }
        if(root.right != null && root.right.val == target && isLeaf(root.right)){
            root.right = null;
        }

    }
    public boolean isLeaf(TreeNode root){
        if(root == null) return false;
        if(root.right == null && root.left == null) return true;
        return false;
    }
}
```

### [2265. Count Nodes Equal to Average of Subtree](https://leetcode.com/problems/count-nodes-equal-to-average-of-subtree/description/)

```Java
class Solution {
    int res = 0;
    public int averageOfSubtree(TreeNode root) {
        dfs(root,0);
        return res;
    }
    public int[] dfs(TreeNode root,int level){
        if(root == null) return new int[] {0,0};

        int[] left = dfs(root.left,level+1);
        int[] right = dfs(root.right,level+1);        

        int sum = left[0]+right[0];
        int count = left[1]+right[1];
        sum+=root.val; count++;

        if(sum == 0) res++;
        else if(root.val == (sum/count)) {
            System.out.println(sum/count);
            res++;
        }

        return new int[] {sum,count};
    }
}
```

### [623. Add One Row to Tree](https://leetcode.com/problems/add-one-row-to-tree/description/)

```Java
class Solution {
    public TreeNode addOneRow(TreeNode root, int val, int depth) {
        if(depth == 1){
            TreeNode res = new TreeNode();
            res.val = val;
            res.left = root;
            return res;
        }
        bfs(root,1,val,depth);
        return root;
    }
    public void bfs(TreeNode root,int level,int val,int depth){

        if(root == null) return;

        if(level+1 == depth){

            TreeNode rightDup = root.right;
            TreeNode leftDup = root.left;

            TreeNode newOne = new TreeNode(val);
            TreeNode newTwo = new TreeNode(val);

            root.left = newOne;
            root.right = newTwo;

            root.left.left = leftDup;
            root.right.right = rightDup;
            return;
        }
        bfs(root.left,level+1,val,depth);
        bfs(root.right,level+1,val,depth);
    }
}
```

### [1305. All Elements in Two Binary Search Trees](https://leetcode.com/problems/all-elements-in-two-binary-search-trees/description/)

```Java
class Solution {
    List<Integer> ls = new ArrayList<>();

    public List<Integer> getAllElements(TreeNode root1, TreeNode root2) {

        dfs(root1);
        dfs(root2);
        
        Collections.sort(ls);
        return ls;
    }
    public void dfs(TreeNode root){

        if(root == null) return;
        ls.add(root.val);
        dfs(root.right); dfs(root.left);
    }
}
```

### [161. Maximum Level Sum of a Binary Tree](https://leetcode.com/problems/maximum-level-sum-of-a-binary-tree/)

```Java
class Solution {
    List<Integer> ls = new ArrayList<>();

    public int maxLevelSum(TreeNode root) {
        bfs(root,0);   
        int max = 0;

        for(int i=0;i<ls.size();i++){
            if(ls.get(max) < ls.get(i)){
                max = i;
            }
        }
        return max+1;
    }
    public void bfs(TreeNode root,int level){
        if(root == null) return;
        if(ls.size() <= level) ls.add(root.val);
        else{
            ls.set(level,ls.get(level)+root.val);
        }
        bfs(root.left,level+1);
        bfs(root.right,level+1);
    }
}
```

### [Flatten Binary Tree to Linked List](https://leetcode.com/problems/flatten-binary-tree-to-linked-list/)

```Java
class Solution {
    List<TreeNode> ls = new ArrayList<>();

    public void flatten(TreeNode root) {
        dfs(root);
        TreeNode dup = new TreeNode();

        for(int i=0;i<ls.size();i++){
            dup.right = ls.get(i);
            dup.left = null;
            dup = dup.right;
        }
        root = dup.right;
    }
    public void dfs(TreeNode root){
        if(root == null) return;

        ls.add(root);
        dfs(root.left);
        dfs(root.right);
    }
}
```

### [Populating Next Right Pointers in Each Node II](https://leetcode.com/problems/populating-next-right-pointers-in-each-node-ii/description/)

```Java

class Solution {
    List<List<Node>> ls = new ArrayList<>();

    public Node connect(Node root) {
        dfs(root,0);
        for(int i=0;i<ls.size();i++){
            int j=0;
            for(j=0;j<ls.get(i).size()-1;j++){
                ls.get(i).get(j).next = ls.get(i).get(j+1);
            }
            ls.get(i).get(j).next = null;
        }
        return root;
    }
    public void dfs(Node root,int level){
        if(root == null) return;

        if(ls.size() <= level){
            ls.add(new ArrayList<>());
        }

        ls.get(level).add(root);

        dfs(root.left,level+1);
        dfs(root.right,level+1);
    }
}
```

### [2196. Create Binary Tree From Descriptions](https://leetcode.com/problems/create-binary-tree-from-descriptions/description/)

```Java
class Solution {  
    public TreeNode createBinaryTree(int[][] d) {
        TreeMap<Integer,TreeNode> tm = new TreeMap<>();
        for(int i=0;i<d.length;i++){
            if(!tm.containsKey(d[i][0])){
                tm.put(d[i][0],new TreeNode(d[i][0]));
            }
            if(!tm.containsKey(d[i][1])){
                tm.put(d[i][1],new TreeNode(d[i][1]));
            }
        }

        for(int i=0;i<d.length;i++){
            if(d[i][2] == 1){
                tm.get(d[i][0]).left = tm.get(d[i][1]);
            }
            else{
                tm.get(d[i][0]).right = tm.get(d[i][1]);
            }
        }

        HashSet<Integer> st = new HashSet<>();
        for(int i=0;i<d.length;i++){
            st.add(d[i][1]);
        }
        for(int i=0;i<d.length;i++){
            if(!st.contains(d[i][0])) return tm.get(d[i][0]);
        }
        return null;
    }
}
```

### [2236. Root Equals Sum of Children](https://leetcode.com/problems/root-equals-sum-of-children/)

```Java
class Solution {
    public boolean checkTree(TreeNode root) {
        return root.val == (root.right.val + root.left.val);
    }
}
```

### [Reverse Odd Levels of Binary Tree](https://leetcode.com/problems/reverse-odd-levels-of-binary-tree/description/)

```Java
class Solution {
    List<List<Integer>> ls = new ArrayList<>();
    public TreeNode reverseOddLevels(TreeNode root) {
        dfs(root,0);
        reverse(root,0);
        return root;
    }
    public void dfs(TreeNode root,int level){
        if(root == null){
            return;
        }
        if(ls.size() >= level) ls.add(new ArrayList<>());
        ls.get(level).add(root.val);

        dfs(root.left,level+1);
        dfs(root.right,level+1);
    }
    public void reverse(TreeNode root,int level){

        if(root == null) return;

        if(level%2 == 1){
            int in = ls.get(level).size()-1;
            root.val = ls.get(level).get(in);
            ls.get(level).remove(ls.get(level).size()-1);

            reverse(root.left,level+1);
            reverse(root.right,level+1);
        }
        else{
            reverse(root.left,level+1);
            reverse(root.right,level+1);
            return;
        };
    }
}
```

### [Populating Next Right Pointers in Each Node](https://leetcode.com/problems/populating-next-right-pointers-in-each-node/description/)

```Java
class Solution {
    List<List<Node>> ls = new ArrayList<>();

    public Node connect(Node root) {
        dfs(root,0);
        for(int i = 0;i<ls.size();i++){
            for(int j=0;j<ls.get(i).size()-1;j++){
                ls.get(i).get(j).next = ls.get(i).get(j+1);
            } 
            ls.get(i).get(ls.get(i).size()-1).next = null;
        }
        return root;
    }
    public void dfs(Node root,int level){
        if(root == null) return;
        
        if(ls.size() <= level) ls.add(new ArrayList<>());
        ls.get(level).add(root);

        dfs(root.left,level+1);
        dfs(root.right,level+1);
    }
}
```

### [Find Elements in a Contaminated Binary Tree](https://leetcode.com/problems/find-elements-in-a-contaminated-binary-tree/)

```Java
class FindElements {
    HashSet<Integer> st = new HashSet<>();
    public FindElements(TreeNode root) {
        st.add(0);
        root.val = 0;
        func(root);
    }

    public void func(TreeNode root){
        if(root == null) return;
        
        if(root.left != null){
            int val = (2*root.val)+1;
            st.add(val); 
            root.left.val = val;
        }
        if(root.right != null){
            int val = (2*root.val)+2;
            st.add(val); 
            root.right.val = val;
        }

        func(root.right); func(root.left);
    }
    
    public boolean find(int target) {
        // System.out.println(st);
        return st.contains(target);
    }
}
```

### [222. Count Complete Tree Nodes](https://leetcode.com/problems/count-complete-tree-nodes/description/)

```Java
class Solution {
    int count = 0;
    public int countNodes(TreeNode root) {
        dfs(root);
        return count;
    }
    public void dfs(TreeNode root){
        if(root == null) return;
        count++;
        dfs(root.left);
        dfs(root.right);
    }
}
```

### [Linked List in Binary Tree](https://leetcode.com/problems/linked-list-in-binary-tree/)

```Java
class Solution {
    public boolean isSubPath(ListNode head, TreeNode root) {
        if(root == null) return false;
        if(func(head,root)) return true;
        return isSubPath(head,root.left) || isSubPath(head,root.right);
    }
    public boolean func(ListNode head,TreeNode root){
        if(head == null) return true;
        if(root == null || root.val != head.val) return false;
        return func(head.next,root.right) || func(head.next,root.left);
    }
}
```

### [501. Find Mode in Binary Search Tree](https://leetcode.com/problems/find-mode-in-binary-search-tree/description/)

```Java
class Solution {
    HashMap<Integer,Integer> mp = new HashMap<>();
    public int[] findMode(TreeNode root) {
    
        dfs(root);

        int count = 0,max=0;
        
        for(int n : mp.keySet()){
            int val = mp.get(n);

            if(max == val) count++;
            if(max < val) {
                count = 1;
                max = val;
            }
        }
        
        int[] res = new int[count]; int i=0;
        for(int n: mp.keySet()){
            
            if(mp.get(n) == max){
                res[i++] = n;
            }
        }
    
        return res;
    }

    public void dfs(TreeNode root){

        if(root == null) return;

        mp.put(root.val,mp.getOrDefault(root.val,0)+1);

        dfs(root.right);
        dfs(root.left);
    }
}
```

### [897. Increasing Order Search Tree](https://leetcode.com/problems/increasing-order-search-tree/description/)

```Java
class Solution {
    PriorityQueue<Integer> hp = new PriorityQueue<>();
    public TreeNode increasingBST(TreeNode root) {
        dfs(root);
        TreeNode res = new TreeNode(0);
        TreeNode dup = res;

        while(!hp.isEmpty()){
            TreeNode newOne = new TreeNode(hp.poll());
            dup.right = newOne;
            dup = newOne;
        }
        return res.right;
    }
    public void dfs(TreeNode root){

        if(root == null) return;

        hp.add(root.val);
        dfs(root.left);
        dfs(root.right);
    }
}
```