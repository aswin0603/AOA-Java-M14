
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 27-10-2025
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
1. Create an array dp of size n, where each dp[i] represents the length of the LIS ending at index i. Initialize all values of dp to 1 (each element is a subsequence of length 1 by itself).
2. For each element nums[i] (from index 1 to n-1), check all previous elements nums[j] (from 0 to i-1).
3. If ```nums[i] > nums[j]```, then nums[i] can extend the subsequence ending at j. Update ```dp[i] = max(dp[i], dp[j] + 1).```
4. After filling the dp array, the maximum value in dp represents the length of the longest increasing subsequence.
5. Return the maximum value from the dp array as the final LIS length.

## Program:
```java
import java.util.*;

public class LongestIncreasingSubsequence {
    public static int lengthOfLIS(int[] nums) {
        int[] dp = new int[nums.length];
        Arrays.fill(dp, 1);

        for (int i = 1; i < nums.length; i++) {
            for (int j = 0; j < i; j++) {
                if (nums[i] > nums[j]) {
                    dp[i] = Math.max(dp[i], dp[j] + 1);
                }
            }
        }

        int longest = 0;
        for (int c : dp) {
            longest = Math.max(longest, c);
        }

        return longest;
    }

public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}

```

## Output:
<img width="1091" height="175" alt="image" src="https://github.com/user-attachments/assets/971e6a58-134e-492f-b735-15e05fdba38d" />



## Result:
The program successfully implemented and the expected output is verified.

```
Developed by: ASWIN B
Register Number:  212224110007
```
