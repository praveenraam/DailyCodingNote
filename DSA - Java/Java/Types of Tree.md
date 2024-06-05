
### Binary Tree : 
It is very important as lot of question are asked from the binary tree.

### Terms : 
- **Root** : Head of the tree
- **Children** : The two nodes at the lower bond is parent
- **Lead Node** : The Node with no Children
- **Sub Tree** : Separating a branch, it is Sub tree
- **Parent** : The upper bond node is Parent
- **Ancestors** : Parent's Parent is Ancestor

![[Pasted image 20240605110412.png]]

### Types of Binary Tree

#### Full BT :
Either it has 2 children or 0 child
![[Pasted image 20240605110806.png]]

#### Complete BT :
- All the levels are filled except the last level
- The last node has all node m left possible
  ![[Pasted image 20240605111228.png]]

#### Perfect BT :
- All leaf node are at the same level
 ![[Pasted image 20240605111433.png]]

#### Balanced BT :
- Height of the tree is Log(N) (N is the input size)

#### Degenerate BT :
- All the node only have single child


### Representation of Tree in Java
![[Pasted image 20240605112312.png]]
This is done using List Nodes

### Traversing Techniques

Example Tree 1 :
![[Pasted image 20240605113103.png]]

Example Tree 2 : 
![[Pasted image 20240605113747.png]]
#### In order Traversal :
- Find the extreme left sub tree 
- Traverse in order of left -> root -> right 
Output of traversal of Example Tree 1 : 4 2 5 1 3 6 7
Output of traversal of Example Tree 2 : 4 2 8 5 1 6 3 9 7 10
#### Pre Order Traversal :
- Go to root -> left -> right
Output of traversal of Example Tree 1 : 1 2 4 5 3 6 7
Output of traversal of Example Tree 2 : 1 2 4 5 8 3 6 7 9 10

#### Post Order Traversal :
- Go to extreme left 
- Traverse in order of left -> right -> node
Output of traversal of Example Tree 1 : 4 5 2 6 7 3 1
Output of traversal of Example Tree 2 : 4 8 5 2 6 9 10 7 3 1

#### BFS (Breadth First Search)

Traversing  the Tree level by level from left to right 
Output of traversal of Example Tree 1 : 1 2 3 4 5 6 7
Output of traversal of Example Tree 2 : 1 2 3 4 5 6 7 8 9 10