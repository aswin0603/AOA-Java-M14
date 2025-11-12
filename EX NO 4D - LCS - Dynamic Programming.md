
# EX 4D Longest Common SubSequence - Dynamic Programming.
## DATE: 25-10-2025
## AIM:
To write a Java program to for given constraints.
Given two strings text1 and text2, return the length of their longest common subsequence. If there is no common subsequence, return 0.
A subsequence of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.

For example, "ace" is a subsequence of "abcde".
A common subsequence of two strings is a subsequence that is common to both strings.

Input: text1 = "abcde", text2 = "ace" 

Output: 3  

Explanation: The longest common subsequence is "ace" and its length is 3.

Constraints:
1 <= text1.length, text2.length <= 1000
text1 and text2 consist of only lowercase English characters.

## Algorithm
1. Create a 2D array ```dp[m+1][n+1]```, where ```dp[i][j]``` stores the length of the LCS between the first i characters of text1 and the first j characters of text2.
2. Loop i from 1 to m (length of text1) and j from 1 to n (length of text2).
3. If ```text1.charAt(i-1) == text2.charAt(j-1)```, then ```dp[i][j] = dp[i-1][j-1] + 1``` (include this character in LCS).
4. If characters don’t match, take the maximum of excluding one character from either string: ```dp[i][j] = max(dp[i-1][j], dp[i][j-1]).```
5. The value ```dp[m][n]``` gives the length of the longest common subsequence between text1 and text2.

## Program:
```java
import java.util.Scanner;

public class Solution {
  public int longestCommonSubsequence(String text1, String text2) {    
    int m = text1.length(), n = text2.length();
    int[][] dp = new int[m + 1][n + 1];
    for (int i = 1; i <= m; i++) {
      for (int j = 1; j <= n; j++) {
        if (text1.charAt(i - 1) == text2.charAt(j - 1)) 
          dp[i][j] = dp[i - 1][j - 1] + 1;
        else 
          dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
      }
    }
    return dp[m][n];
  }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        String text1 = sc.nextLine().replaceAll("\"", "");
        String text2 = sc.nextLine().replaceAll("\"", "");

        int lcsLength = sol.longestCommonSubsequence(text1, text2);
        System.out.println("Length of Longest Common Subsequence: " + lcsLength);

        sc.close();
    }
}

```

## Output:
<img width="909" height="178" alt="image" src="https://github.com/user-attachments/assets/6751dc06-6ca3-4d5c-9f9c-88adb5a6cb01" />



## Result:
The program successfully implemented and the expected output is verified.

```
Developed by: ASWIN B
Register Number:  212224110007
```
