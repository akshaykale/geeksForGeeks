# Sum Tree

https://practice.geeksforgeeks.org/problems/sum-tree/1

https://www.geeksforgeeks.org/check-if-a-given-binary-tree-is-sumtree/

Write a function that returns true if the given Binary Tree is SumTree else false. A SumTree is a Binary Tree where the value of a node is equal to sum of the nodes present in its left subtree and right subtree. An empty tree is SumTree and sum of an empty tree can be considered as 0. A leaf node is also considered as SumTree.

Following is an example of SumTree.

          26
        /   \
      10     3
    /    \     \
  4      6      3
  
  
  ## Solution
  
  ```java
  
  class Tree
{
    int sum(Node root) {
        if (root == null) {
            return 0;
        }
        return sum(root.left) + root.data + sum(root.right);
    }
    
	boolean isSumTree(Node node)
	{
	    if(node == null || (node.left == null && node.right == null)) {
	        return true;
	    }
	    
	    int ls = sum(node.left);
	    int rs = sum(node.right);
	    
	    if ((node.data == ls + rs) && isSumTree(node.left) && isSumTree(node.right) ){
	        return true;
	    }
	    return false;
	}
}
  
  ```
