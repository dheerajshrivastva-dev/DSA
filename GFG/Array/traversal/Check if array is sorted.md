Given an array  **arr[]** , check whether it is sorted in non-decreasing order. Return true if it is sorted otherwise false.

**Examples:**

```
Input: arr[] = [10, 20, 30, 40, 50]
Output: true
Explanation: The given array is sorted.
```

```
Input: arr[] = [90, 80, 100, 70, 40, 30]
Output: false
Explanation: The given array is not sorted.
```

**Expected Time Complexity:** O(n)
**Expected Auxiliary Space:** O(1)

**Constraints:**
1 ≤ arr.size ≤ 10^6^

- 10^9^ ≤ arr[i] ≤ 10^9^


Solution:

```java
//{ Driver Code Starts
import java.util.*;


// } Driver Code Ends
// User function Template for Java

class Solution {
    public boolean arraySortedOrNot(List<Integer> arr) {
        // code here
        if (arr.size() == 1) return true;
        if (arr.size() == 0) return false;
        int first = arr.get(0);
        for (int i = 1; i < arr.size(); i++) {
            if (first > arr.get(i)) {
                return false;
            } else {
                first = arr.get(i);
            }
        }
        return true;
    }
}

//{ Driver Code Starts.

class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int t = Integer.parseInt(scanner.nextLine());

        while (t-- > 0) {
            String line = scanner.nextLine();
            String[] numStrings = line.split(" ");
            List<Integer> nums = new ArrayList<>();
            for (String numString : numStrings) {
                nums.add(Integer.parseInt(numString));
            }
            Solution ob = new Solution();
            boolean ans = ob.arraySortedOrNot(nums);
            System.out.println(ans ? "true" : "false");
        }
        scanner.close();
    }
}
// } Driver Code Ends
```
