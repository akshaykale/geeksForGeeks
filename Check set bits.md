# Check if all bits of a number are set

https://practice.geeksforgeeks.org/problems/check-set-bits/0

https://www.geeksforgeeks.org/check-bits-number-set/


Given a number N. Write a program to check whether every bit in the binary representation of the given number is set or not.

Input:
First line of input contains a single integer T which denotes the number of test cases. T test cases follows. First line of each test case contains a single integer N which denotes the number to be checked.

Output:
For each test case, print "YES" without quotes if all bits of N are set otherwise print "NO".

Constraints:
1<=T<=1000
0<=N<=1000

Example:
Input:
3
7
14
4
Output:
YES
NO
NO

## Solution

```java

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		Scanner sc = new Scanner(System.in);
		int T = sc.nextInt();
		for (int t=0;t<T;t++) {
		    System.out.println(isSet(sc.nextInt()));
		}
	}
	
	public static String isSet(int n) {
	    if (n==0) return "NO";
	    if((n+1 & n) == 0) return "YES";
	    else return "NO";
	}
}

```
