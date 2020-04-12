# Boolean Matrix Problem

https://www.geeksforgeeks.org/a-boolean-matrix-question/

https://practice.geeksforgeeks.org/problems/boolean-matrix-problem/0

Given a boolean matrix mat[M][N] of size M X N, modify it such that if a matrix cell mat[i][j] is 1 (or true) then make all the cells of ith row and jth column as 1.

Input:
The first line of input contains an integer T denoting the number of test cases.
The first line of each test case is r and c, r is the number of rows and c is the number of columns.
The second line of each test case contains all the elements of the matrix in a single line separated by a single space.

Output:
Print the modified array.

Constraints:
1 ≤ T ≤ 100
1 ≤ r, c ≤ 1000
0 ≤ A[i][j] ≤ 1

Example:
Input:
3
2 2
1 0
0 0
2 3
0 0 0 
0 0 1
4 3
1 0 0
1 0 0
1 0 0
0 0 0

Output:
1 1
1 0
0 0 1 
1 1 1
1 1 1
1 1 1
1 0 0

Explanation:
Testcase1: Since only first element of matrix has 1 (at index 1,1) as value, so first row and first column are modified to 1.


## Solution

```java

/*package whatever //do not write package name here */

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		
		Scanner sc = new Scanner(System.in);
		int T = sc.nextInt();
		for (int t=0; t<T; t++) {
		    int r = sc.nextInt();
		    int c = sc.nextInt();
		    int [][] matrix = new int[r][c];
		    for (int i=0; i< r; i++) {
		        for( int j=0; j< c; j ++) {
		            matrix[i][j] = sc.nextInt();
		        }
		    }
		    process(matrix, r, c);
		}
	}
	
	public static void process(int [][] m, int r, int c) {
	    
	    int[] row = new int[r];
	    int[] col = new int[c];
	    
	    for ( int i=0; i< r; i++) {
	        for (int j=0; j< c; j++) {
	            if (m[i][j] == 1) {
	                row[i] = 1;
	                col[j] = 1;
	            }
	        }
	    }
	    
	    for ( int i=0; i< r; i++) {
	        for (int j=0; j< c; j++) {
	            if (row[i] == 1 || col[j] == 1) {
	                m[i][j] = 1;
	            }
	            System.out.print(m[i][j]+" ");
	        }
	        System.out.println();
	    }
	}
}


```
