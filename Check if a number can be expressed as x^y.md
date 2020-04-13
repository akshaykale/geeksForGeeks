# Check if a number can be expressed as x^y

https://practice.geeksforgeeks.org/problems/check-if-a-number-can-be-expressed-as-xy/0

https://www.geeksforgeeks.org/check-if-a-number-can-be-expressed-as-xy-x-raised-to-power-y/


## Solution

```java

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		
		Scanner sc = new Scanner(System.in);
		int T = sc.nextInt();
		for (int i=0;i<T;i++) {
		    System.out.println(""+isPow(sc.nextInt()));
		}
	}

	public static int isPow(int n) {
	    if (n==1 || n==0) return 1;
	    if (n==2) return 0;
	   
	    for (int x=2; x<=n/2; x++) {
	        
	        int y=2;
	        int res =x;
	        
	        while(res<n) {
	            res = res * x;
	            if(res == n) return 1;
	            if(res > n) break;
	            y++;
	        }
	        
	    }
	    
	    return 0;
	}
}

```
