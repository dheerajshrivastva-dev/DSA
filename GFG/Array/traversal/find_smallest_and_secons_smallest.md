Given an array, **arr** of integers, your task is to return the smallest and second smallest element in the array. If the smallest and second smallest do not exist, return **-1.**

**Examples:**

```
Input: arr[] = [2, 4, 3, 5, 6]
Output: 2 3 
Explanation: 2 and 3 are respectively the smallest and second smallest elements in the array.
```

```
Input: arr[] = [1, 1, 1]
Output: -1
Explanation: Only element is 1 which is smallest, so there is no second smallest element.
```

**Expected Time Complexity:** O(n)
 **Expected Auxillary Space** **:** O(1)

**Constraints:**
1 <= arr.size <= 10^5^
1 <= arr[i] <= 10^5^


Solution

```java
//{ Driver Code Starts
// Initial Template for Java

import java.io.*;
import java.lang.*;
import java.util.*;

class GFG {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int t = Integer.parseInt(br.readLine().trim()); // Inputting the testcases
        while (t-- > 0) {
            String inputLine[] = br.readLine().trim().split(" ");
            int n = inputLine.length;
            int arr[] = new int[(int)(n)];
            for (int i = 0; i < n; i++) {
                arr[i] = (int)(Long.parseLong(inputLine[i]));
            }

            Solution obj = new Solution();
            int[] product = obj.minAnd2ndMin(arr);
            if (product[0] == -1)
                System.out.println(product[0]);
            else
                System.out.println(product[0] + " " + product[1]);
        }
    }
}

// } Driver Code Ends


// User function Template for Java

class Solution {
  
    public int[] minAnd2ndMin(int arr[]) {
        int small = Integer.MAX_VALUE;
        int small2 = Integer.MAX_VALUE;
        // code here
        for (int i = 0; i < arr.length ; i++) {
            // find second
            if (arr[i] < small2 && arr[i] != small) {
                small2 = arr[i];
            }
            // find first and swap with second
            if (small2 < small) {
                int temp = small;
                small = small2;
                small2 = temp;
            }
            // System.out.println(small);
            // System.out.println(small2);
        }
        int[] ans = new int[2];
        if (small2 < Integer.MAX_VALUE && small < Integer.MAX_VALUE) {
      
            ans[0] = small;
            ans[1] = small2;
        } else {
            ans[0] = -1;
        }
        return ans;
    }
}



```

End;
