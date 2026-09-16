
# EX 2D Pattern Matching using Naive Approach.
## DATE: 15.09.2026
## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12
## Algorithm
1. Start and take the text and pattern as input.
2. Compare the pattern with the text starting from each possible index.
3. Compare the characters of the pattern one by one with the corresponding text characters.
4. If all pattern characters match, print the starting index of the pattern.
5. Continue until all positions are checked and end the search.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.Scanner;

public class NaivePatternSearch {
    //Type code here....
    public static void search(String text, String pattern) {

    int n = text.length();
    int m = pattern.length();

    for (int i = 0; i <= n - m; i++) {
        int j;

        for (j = 0; j < m; j++) {
            if (text.charAt(i + j) != pattern.charAt(j))
                break;
        }

        if (j == m) {
            System.out.println("Pattern found at index " + i);
        }
    }

    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String text = scanner.nextLine();
        String pattern = scanner.nextLine();

        // Search for pattern in the text
        search(text, pattern);

        scanner.close();
    }
}

```

## Output:
<img width="690" height="242" alt="image" src="https://github.com/user-attachments/assets/9ebb10af-c1ad-4fc9-a608-74f9ddb1f3f3" />



## Result:
The program successfully implemented and the expected output is verified.
