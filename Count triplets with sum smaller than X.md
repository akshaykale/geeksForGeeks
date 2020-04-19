# Count triplets with sum smaller than X

https://practice.geeksforgeeks.org/problems/count-triplets-with-sum-smaller-than-x/0

https://www.geeksforgeeks.org/count-triplets-with-sum-smaller-that-a-given-value/

Given an array A of distinct integers and a sum value X. Find count of triplets with sum smaller than given sum value X.

Input:
First line consists of T test cases. First line of every test case consists of N and X, denoting the number of elements in array and Sum Value respectively. Second line consists of array elements.

Output:
For each testcase, output the count of Triplets.

Constraints:
1 <= T <= 100
1 <= N <= 107
1 <= Ai <= 108
1 <= X <= 1010

Example:
Input:
2
4 2
-2 0 1 3
5 12
5 1 4 3 7

Output:
2
4

Explanation:
Testcase 1: -2, 0, 1 and -2, 3, 0 makes triplets with sum less than 2.

## Solution
```java

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		Scanner sc  = new Scanner(System.in);
		int t = sc.nextInt();
		for (int i=0;i<t;i++) {
		    int s = sc.nextInt();
		    int n = sc.nextInt();
		    int[] arr = new int[s];
		    for (int j=0;j<s;j++) {
		        arr[j] = sc.nextInt();
		    }
		    System.out.println(triplets(arr,s,n)+"");
		}
	}
	
	static int triplets(int[] arr, int s, int n) {
	    
	    Arrays.sort(arr);
	    int count = 0;
	    for (int i=0; i<s-2;i++) {
	        int j=i+1;
	        int k=s-1;
	        while(j<k) {
	            if(arr[i] + arr[j] + arr[k] >= n) {
	                k--;
	            } else if(sm < n) {
	                count+=(k-j);
	                j++;
	            }
	        }
	    }
	    return count;
	    
	}
}

```
