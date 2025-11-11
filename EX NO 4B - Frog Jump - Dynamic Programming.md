
# EX 4B Frog Jump - Dynamic Programming.
## DATE: 23-10-2025
## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.
Problem Statement:

A frog is at the bottom of the stairs with n steps. It can jump either 1 or 2 steps at a time. Write a program to find the number of distinct ways the frog can reach the top (n-th step).

Input Format:

A single integer n (1 ≤ n ≤ 45) – number of steps.
 Output Format:

A single integer – number of distinct ways to reach step n.

## Algorithm
1. Read the integer n.
2. If n is 1 or 2, return n directly.
3. Initialize two variables representing ways to reach steps n−2 and n−1.
4. Iteratively compute the next value as the sum of the previous two.
5. Return the last computed value as the total number of ways.

## Program:
```java
import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        scanner.close();
        System.out.println(countWays(n));
    }

   
    public static int countWays(int n) {
       if (n <= 2) return n;
        int a = 1, b = 2, c = 0;
        for (int i = 3; i <= n; i++) {
            c = a + b;
            a = b;
            b = c;
        }
        return b;
       
    }
}

```

## Output:
<img width="304" height="133" alt="image" src="https://github.com/user-attachments/assets/dfc5bead-b3e0-4893-91b0-144bd96a5f9e" />



## Result:
The program successfully implemented and the expected output is verified.

```
Developed by: ASWIN B
Register Number:  212224110007
```

