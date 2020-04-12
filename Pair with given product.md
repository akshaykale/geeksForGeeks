# Equal to product

https://www.geeksforgeeks.org/pair-with-given-product-set-1-find-if-any-pair-exists/

https://practice.geeksforgeeks.org/problems/equal-to-product/0

Given an array of positive integers. Check whether there are two numbers present with given product.

Input:
The first line of input contains an integer T denoting the number of test cases.
The first line of each test case is N and a product P.
The second line of each test case contain elements of array.

Output:
Print "Yes" (Without quotes) if two numbers product is equal to P else "No" (without quotes).

Constraints:
1 ≤ T ≤ 100
1 ≤ N ≤ 107
0 ≤ Ai ≤ 263 - 1
0 <= P <= 264 - 1

Example:
Input:
2
5 25
1 2 3 4 5
8 63
5 7 9 22 15 344 92 8

Output:
No
Yes




## Solution

 ```java

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		
		Scanner sc = new Scanner(System.in);
		int T = sc.nextInt();
		for (int i=0; i<T; i++) {
		    int N = sc.nextInt();
		    int P = sc.nextInt();
		    int[] arr = new int[N];
		    for( int j = 0;j<N;j++) {
		        arr[j] = sc.nextInt();
		    }
		    System.out.println(""+isProd(N,P,arr));
		}
	}
	
	public static String isProd(int N, int P, int[] arr) {
	    
	    HashMap<Float, Integer> map = new HashMap<>();
	    
	    for (int i=0; i<N; i++) {
	        if (arr[i] == 0) continue;
	        float d = (float) P / arr[i];
	        if(map.containsKey((float)arr[i])) {
	            return "Yes"; //pair at map.get(d) and i
	        }
	        map.put(d,i);
	    }
	    return "No";
	}
	
}

```
