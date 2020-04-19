# Count words that appear exactly two times in an array of words

https://practice.geeksforgeeks.org/problems/twice-counter/0

https://www.geeksforgeeks.org/count-words-appear-exactly-two-times-array-words/

Given an array of n words. Some words are repeated twice, we need count such words.

Input:
The first line of input contains an integer T denoting the number of test cases. Then T test cases follow. Each test case contains an integer n denoting the number of words in the string. The next line contains n space separated words forming the string.

Output:
Print the count of the words which are repeated twice in the string.

Constraints:
1<=T<=105  
1<=no of words<=105
1<=length of each word<=105

Example:
Input:
2
10
hate love peace love peace hate love peace love peace
8
Tom Jerry Thomas Tom Jerry Courage Tom Courage

Output:
1
2

## Solution

```java

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
		Scanner sc = new Scanner(System.in);
		int t = Integer.parseInt(sc.nextLine());
		for (int i=0;i<t;i++) {
		    int s = Integer.parseInt(sc.nextLine());
		    System.out.println(""+count(sc.nextLine().split(" "), s));
		}
	}
	
	static int count(String[] arr, int s) {
	    HashMap<String, Integer> map = new HashMap<>();
	    int res = 0;
	    for (int i=0; i < s; i++) {
	        map.put(arr[i], map.containsKey(arr[i])? map.get(arr[i])+1 : 1);
	    }
	    ArrayList<Integer> v = new ArrayList<>(map.values());
	    v.removeIf(val -> (val!=2));
	    return v.size();
	}
}

```
