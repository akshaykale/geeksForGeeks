
## Solution: Nearest smaller element in left side [O(N)] using stack
```java
class GFG {
	public static void main (String[] args) {
	int arr[] =  {1, 3, 0, 2, 5}; 
    printPrevSmaller(arr, arr.length); 
    }
	
	public static void printPrevSmaller(int[] arr, int length) {
	    Stack<Integer> st = new Stack<>();
	    for(int i=0; i<length;i++) {
	        
	        while (!st.isEmpty() && st.peek() >= arr[i]){
	            st.pop();
	        }
	        
	        if (st.isEmpty()) {
	            System.out.print("-1 ");
	        } else {
	            System.out.print(st.peek() +" ");
	        }
	        st.push(arr[i]);
	    }
	}
}
```


## Solution: Nearest smaller adjcent element on right side [O(N)]

```java
class GFG {
	public static void main (String[] args) {
	int num;
		Scanner sc = new Scanner(System.in);
		num = sc.nextInt();
		for(int i=0; i<num; i++) {
		    int length = sc.nextInt();
		    int[] arr = new int[length];
		    for(int j =0;j<length; j++) {
		        arr[j] = sc.nextInt();
		    }
		    solve(arr, length);
		}
    }
	
	public static void solve(int[] arr, int length) {
	    for (int i=0;i<length-1;i++) {
	            if (arr[i+1]<arr[i]) {
	                System.out.print(arr[i+1]+" ");
	            } else {
	                System.out.print("-1 ");
	            }
	    }
	    System.out.print("-1"); //last element
	    System.out.println();
	    
	}
}
```

## Solution: Nearest smaller element on right side

```java
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
	public static void main (String[] args) {
	int num;
		Scanner sc = new Scanner(System.in);
		num = sc.nextInt();
		for(int i=0; i<num; i++) {
		    int length = sc.nextInt();
		    int[] arr = new int[length];
		    for(int j =0;j<length; j++) {
		        arr[j] = sc.nextInt();
		    }
		    solve(arr, length);
		}
    }
	
	public static void solve(int[] arr, int length) {
	    int[] resArr = new int[length];
	    resArr[length-1] = -1;
	    for (int i=0;i<length;i++) {
	        
	        for (int j=i+1;j<length;j++) {
	            
	            if (arr[j]<arr[i]) {
	                resArr[i] = arr[j];
	                break;
	            } else {
	                resArr[i] = -1;
	            }
	        }
	    }
	    for (int k=0;k<length;k++) {
	        System.out.print(resArr[k]+" ");   
	    }
	    System.out.println();
	    
	}
}
```
