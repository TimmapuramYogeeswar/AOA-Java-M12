
# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 15.09.2026
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm
1. Start and initialize start and end to store the boundaries of the longest palindrome.
2. For each character, consider it as the center of a palindrome.
3. Expand around the center for both odd-length and even-length palindromes.
4. If the found palindrome is longer than the current one, update start and end.
5. Return and print the substring between start and end as the longest palindrome.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.Scanner;

public class Solution {
    public String longestPalindrome(String s) {
        //Type code here...
        if (s == null || s.length() < 2)
        return s;
        int start = 0, end = 0;
        for (int i = 0; i < s.length(); i++) {
            int l1 = expand(s, i, i);    
            int l2 = expand(s, i, i + 1);   
            int len = Math.max(l1, l2);
            if (len > end - start+1) {
                start = i - (len - 1) / 2;
                end = i + len / 2;
            }
        }
        return s.substring(start, end + 1);
    }
    private int expand(String s, int left, int right) {
        while (left >= 0 && right < s.length() &&
        s.charAt(left) == s.charAt(right)) {
            left--;
            right++;
        }
        return right - left - 1;
    }

    // Main method for user input
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

        Solution sol = new Solution();
        String result = sol.longestPalindrome(input);

        System.out.println("Longest Palindromic Substring: " + result);
        scanner.close();
    }
}

```

## Output:
<img width="802" height="172" alt="image" src="https://github.com/user-attachments/assets/dd7c91e2-0ebb-495f-b915-890ef66281c4" />



## Result:
The program successfully implemented and the expected output is verified.
