# Print all possible strings that can be made by placing spaces

https://www.geeksforgeeks.org/print-possible-strings-can-made-placing-spaces/

https://practice.geeksforgeeks.org/problems/permutation-with-spaces/0

Given a string you need to print all possible strings that can be made by placing spaces (zero or one) in between them.
Input:  str[] = "ABC"
Output: ABC
        AB C
        A BC
        A B C

# Solution

```java

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		
		Scanner sc = new Scanner(System.in);
		int T = Integer.parseInt(sc.nextLine());
		
		for (int i=0; i< T; i++) {
		    permutate(sc.nextLine());
		    System.out.println();
		}
		
	}
	
	public static void permutate(String str) {
	    
	    System.out.print(str +" ");
	    
	    if (str.length() == 1)
	    {
	        return;
	    }
	    
	    permutate(str.substring(0, str.length()/2));
	    permutate(str.substring(str.length()/2, str.length()));
	}
}

```
