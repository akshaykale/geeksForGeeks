#  How to check if given four points form a square

https://www.geeksforgeeks.org/check-given-four-points-form-square/

Given four different points in space. Find whether these points can form a square or not.

Input:
The first line of input contains an integer T denoting the number of test cases.The first line of each testcase contains x1, y1, x2, y2, x3, y3, x4, y4(four points coordinates) separated by space.

Output:
Print "Yes"(without quotes) if it is square else "No"(without quotes).

Constraints:
1 ≤ T ≤ 30
1 ≤ x1, x2, x3, x4, y1, y2, y3, y4 ≤ 100

Example:
Input:
1
20 10 10 20 20 20 10 10
Output:
Yes

Given coordinates of four points in a plane, find if the four points form a square or not.
To check for square, we need to check for following.
a) All fours sides formed by points are the same.
b) The angle between any two sides is 90 degree. (This condition is required as Quadrilateral also has same sides.
c) Check both the diagonals have the same distance


## Solution

```java

/*package whatever //do not write package name here */

import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
    
    static class Point {
        int x,y;
        
        public Point(String x1, String y1) {
            this.x = Integer.parseInt(x1);
            this.y = Integer.parseInt(y1);
        }
        
        public int getSqDistance(Point p){
            return (p.x-this.x)*(p.x-this.x) + (p.y-this.y) * (p.y-this.y);
        }
    }
    
	public static void main (String[] args) {
		int num;
		Scanner sc = new Scanner(System.in);
		num = sc.nextInt();
		String input = sc.nextLine();
		for(int i=0; i<num; i++) {
		    isSquare(sc.nextLine().split(" "));
		}
	}
	
	public static void isSquare(String[] arr) {
	    Point p1 = new Point(arr[0], arr[1]);
	    Point p2 = new Point(arr[2], arr[3]);
	    Point p3 = new Point(arr[4], arr[5]);
	    Point p4 = new Point(arr[6], arr[7]);
	    
	    //distance from p1-p2
	    int d2 = p1.getSqDistance(p2);
	    int d3 = p1.getSqDistance(p3);
	    int d4 = p1.getSqDistance(p4);
	    
	    if(d2==0||d3==0||d4==0) {
	        System.out.println("No");
	        return;
	        
	    }
	    
	    if((d2 == d3) && (d4 == 2*d2)
	        && 2*p2.getSqDistance(p4) == p2.getSqDistance(p3)) {
	        System.out.println("Yes");
	        return;
	    }
	    
	    if((d3 == d4) && (d2 == 2*d3)
	        && 2*p3.getSqDistance(p2) == p3.getSqDistance(p4)) {
	        System.out.println("Yes");
	        return;
	    }
	    
	    if((d2 == d4) && (d3 == 2*d2)
	        && 2*p2.getSqDistance(p3) == p2.getSqDistance(p4)) {
	        System.out.println("Yes");
	        return;
	    }
	    
	    System.out.println("No");
	    
	}
}

```
