# Check if string is rotated by two places

https://www.geeksforgeeks.org/check-string-can-obtained-rotating-another-string-2-places/


Given two strings a and b. The task is to find if a string 'a' can be obtained by rotating another string 'b' by 2 places.

Input:
The first line of input contains an integer T denoting the no of test cases. Then T test cases follow. In the next two line are two string a and b.

Output:
For each test case in a new line print 1 if the string 'a' can be obtained by rotating string 'b' by two places else print 0.

Constraints:
1 <= T <= 50
1 <= length of a, b < 100

Example:
Input:
2
amazon
azonam
geeksforgeeks
geeksgeeksfor

Output:
1
0

Explanation:
Testcase 1: amazon can be rotated anti-clockwise by two places, which will make it as azonam.

Testcase 2: geeksgeeksfor can't be formed by any rotation from the given word geeksforgeeks.


## Solution

```java

/*package whatever //do not write package name here */

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		int num;
		Scanner sc = new Scanner(System.in);
		num = sc.nextInt();
		String input = sc.nextLine();
		for(int i=0; i<num; i++) {
		    System.out.println(""+canForm(sc.nextLine(), sc.nextLine()));
		}
	}
	
	public static int canForm(String s1, String s2) {
	    if(s1.length() != s2.length()) return 0;
	    if(s1.length() == 2 && s1 == s2) return 1;
	    
	    String x = s1.substring(s1.length()-2, s1.length());
	    String cwS1 = s1.substring(0, s1.length()-2) ;
	    cwS1 = /*x.substring(1,2) + x.substring(0,1)*/ x + cwS1;
	    if (cwS1.equals(s2)) {return 1;}
	    
	    String ccwS1 = s1.substring(2, s1.length()) ;
	    ccwS1 = ccwS1 + s1.substring(0, 2);
	    if (ccwS1.equals(s2)) {return 1;}
	    return 0;
	    
	}
}

```
