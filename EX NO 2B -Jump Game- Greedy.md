
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 15.09.2026
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. Start and initialize f = 0 to store the farthest reachable index.
2. Traverse the array from the first index to the second-last index.
3. If the current index i is greater than f, return false because it cannot be reached.
4. Update f = max(f, i + nums[i]) and check whether the last index is reachable.
5. If f reaches the last index, return true; otherwise return false.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.Scanner;

public class JumpGame {

    // Function to check if we can reach the last index
    public static boolean canReachLastIndex(int[] nums) {
        // Type Your Code Here.
        int f=0;
        for(int i=0;i<nums.length-1;i++){
            if(i>f)return false;
            f=Math.max(f,i+nums[i]);
            if(f>=nums.length-1) return true;
        }
        return false;
    }

    // Main method for input and calling the function
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Size of array
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt(); // Elements of array
        }

        System.out.println("Can reach last index: " + canReachLastIndex(nums));
    }
}

```

## Output:
<img width="687" height="212" alt="image" src="https://github.com/user-attachments/assets/ee0f013e-5129-43d9-b3f7-5cb270904c3b" />



## Result:
The program successfully implemented and the expected output is verified.
