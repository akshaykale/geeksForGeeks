# Overlapping rectangles

https://www.geeksforgeeks.org/find-two-rectangles-overlap/

https://practice.geeksforgeeks.org/problems/overlapping-rectangles/0

Given two rectangles, find if the given two rectangles overlap or not. A rectangle is denoted by providing the x and y co-ordinates of two points: the left top corner and the right bottom corner of the rectangle. Two rectangles sharing a side are considered overlapping.

Note : It may be assumed that the rectangles are parallel to the coordinate axis.

rectanglesOverlap

Input:
The first integer T denotes the number of testcases. For every test case, there are 2 lines of input. The first line consists of 4 integers: denoting the co-ordinates of the 2 points of the first rectangle. The first integer denotes the x co-ordinate and the second integer denotes the y co-ordinate of the left topmost corner of the first rectangle. The next two integers are the x and y co-ordinates of right bottom corner. Similarly, the second line denotes the cordinates of the two points of the second rectangle in similar fashion.

Output:
For each testcase, output (either 1 or 0) denoting whether the 2 rectangles are overlapping. 1 denotes the rectangles overlap whereas 0 denotes the rectangles do not overlap.

Constraints:
1 <= T <= 10
-104 <= x, y <= 104

Example:
Input:
2
0 10 10 0
5 5 15 0
0 2 1 1
-2 -3 0 2

Output:
1
0

Explanation:
Testcase 1: According to the coordinates given as input ,two rectangles formed overlap with each other and thus answer returns 1.





# Solution

```java

/*package whatever //do not write package name here */

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
    
    static class Point {
        int x,y;
        public Point(int x1,int y1){
            this.x = x1;
            this.y = y1;
        }
        
    }
	public static void main (String[] args) {
		
		Scanner sc = new Scanner(System.in);
		int T = sc.nextInt();
		
		for (int i=0; i<T;i++) {
		    Point l1 = new Point(sc.nextInt(), sc.nextInt());
		    Point r1 = new Point(sc.nextInt(), sc.nextInt());
		    Point l2 = new Point(sc.nextInt(), sc.nextInt());
		    Point r2 = new Point(sc.nextInt(), sc.nextInt());
		    System.out.println(""+isRect(l1,r1,l2,r2));
		}
	}
	
	public static int isRect(Point l1, Point r1, Point l2, Point r2) {
	    
	    if(r1.x < l2.x || r2.x < l1.x) return 0;
	    if(l2.y < r1.y || l1.y < r2.y) return 0;
	    
	    return 1;
	    
	}
}
```
