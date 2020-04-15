# Check if two trees are Mirror

https://www.geeksforgeeks.org/check-if-two-trees-are-mirror/

https://practice.geeksforgeeks.org/problems/check-mirror-in-n-ary-tree/0


Given two Binary Trees, write a function that returns true if two trees are mirror of each other, else false. For example, the function should return true for following input trees.

## Solution

```java

class BinaryTree {
    
    static class Node {
        Node left,right;
        int data;
        public Node(int d) {
            left=null;right=null;
            data = d;
        }
    }
    
    public static boolean areMirror(Node a, Node b) {
        if (a == null && b == null ) return true;
        
        if (a==null && b!=null || b==null && a!=null) return false;
        
        return (a.data == b.data) &&
            areMirror(a.left, b.right) &&
            areMirror(a.right, b.left);
    }
    
	public static void main (String[] args) {
		BinaryTree tree = new BinaryTree(); 
        Node a = new Node(1); 
        Node b = new Node(1); 
        a.left = new Node(2); 
        a.right = new Node(3); 
        a.left.left = new Node(4); 
        a.left.right = new Node(5); 
  
        b.left = new Node(3); 
        b.right = new Node(2); 
        b.right.left = new Node(5); 
        b.right.right = new Node(4); 
  
        if (tree.areMirror(a, b) == true) 
            System.out.println("1"); 
        else
            System.out.println("0"); 
  
	}
}

```
