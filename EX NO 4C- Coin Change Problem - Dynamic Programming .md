
# EX 4C Coin Change Problem - Dynamic Programming.
## DATE: 23-10-2025
## AIM:
To write a Java program to for given constraints.
You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

## Algorithm
1. Create an array dp of size amount + 1, where dp[i] stores the minimum coins needed to make amount i. Initialize all values with a large number (amount + 1), and set dp[0] = 0.
2. For each amount i from 1 to amount, try to compute the minimum coins required.
3. For every coin in coins, if the coin’s value ≤ i, update ``` dp[i] = min(dp[i], dp[i - coin] + 1).```
4. After filling the DP array, dp[amount] contains the minimum number of coins needed.
5. If dp[amount] is still greater than amount, return -1 (not possible). Otherwise, return dp[amount].

## Program:
```java
import java.util.*;

public class Solution {
    public int coinChange(int[] coins, int amount) {
        int max = amount + 1;
        int[] dp = new int[amount + 1];
        Arrays.fill(dp, max);
        dp[0] = 0;

        for (int i = 1; i <= amount; i++) {
            for (int coin : coins) {
                if (coin <= i) {
                    dp[i] = Math.min(dp[i], dp[i - coin] + 1);
                }
            }
        }
        return dp[amount] > amount ? -1 : dp[amount];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution solution = new Solution();
        String coinsLine = scanner.nextLine(); 
        String amountLine = scanner.nextLine();
        coinsLine = coinsLine.replaceAll("[^0-9,]", ""); 
        String[] coinsStr = coinsLine.split(",");
        int[] coins = new int[coinsStr.length];
        for (int i = 0; i < coinsStr.length; i++) {
            coins[i] = Integer.parseInt(coinsStr[i]);
        }
        int amount = Integer.parseInt(amountLine.replaceAll("[^0-9]", ""));
        int result = solution.coinChange(coins, amount);
        System.out.println(result);

        scanner.close();
    }
}

```

## Output:
<img width="313" height="172" alt="image" src="https://github.com/user-attachments/assets/5621d043-ff3e-49b5-9cd5-3d2f4141f6c4" />



## Result:
The program successfully implemented and the expected output is verified.

```
Developed by: ASWIN B
Register Number:  212224110007
```
