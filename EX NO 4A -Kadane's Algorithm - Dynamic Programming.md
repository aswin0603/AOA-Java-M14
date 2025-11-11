
# EX 4A Kadane's Algorithm - Dynamic Programming. 
## DATE: 23-10-2025
## AIM:
To Write a Java program to solve the below problem using Kadane's Algorithm.

A solar company installs solar panels around a circular grid of n buildings. Each building either generates or consumes net energy, represented by integers (+ve for generated, -ve for consumed).

The company wants to find a contiguous sequence of buildings (possibly wrapping around from the end to the beginning) that maximizes the total net energy.

Write a program to compute the maximum net energy that can be collected from any contiguous block of buildings on the circular grid.

Input Format:
First line: Integer n (number of buildings)

Second line: n space-separated integers: net energy for each building

Output Format:
A single integer: Maximum net energy collectable from a contiguous block (wrapping allowed)

Constraints:
1 <= n <= 10^6

## Algorithm
1. Compute the total sum of the array.
2. Use Kadane’s algorithm to find the maximum subarray sum in the linear array.
3. Use a modified Kadane’s algorithm to find the minimum subarray sum.
4. If the minimum subarray sum equals the total sum, return the maximum subarray sum (all elements are negative).
5. Otherwise, return the maximum of (maximum subarray sum) and (total sum − minimum subarray sum).

## Program:
```java
import java.util.*;

public class SolarEnergyMaximizer {

    public static int maxCircularEnergy(int[] energy) {
        int total = 0, currMax = 0, currMin = 0;
        int maxSum = energy[0], minSum = energy[0];
        for (int e : energy) {
            currMax = Math.max(e, currMax + e);
            maxSum = Math.max(maxSum, currMax);
            currMin = Math.min(e, currMin + e);
            minSum = Math.min(minSum, currMin);
            total += e;
        }
        if (minSum == total) return maxSum;
        return Math.max(maxSum, total - minSum);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] energy = new int[n];
        for (int i = 0; i < n; i++) energy[i] = sc.nextInt();
        System.out.println(maxCircularEnergy(energy));
    }
}

```

## Output:
<img width="395" height="171" alt="image" src="https://github.com/user-attachments/assets/85caa832-6690-4f8d-8f5e-f50e22a4fac4" />



## Result:
The program successfully Implemented and the output is verified. 

```
Developed by: ASWIN B
Register Number:  212224110007
```
