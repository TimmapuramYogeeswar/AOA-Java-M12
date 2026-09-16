
# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE: 15.09.2026
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1. Start and sort the children’s greed array g and cookie size array s in ascending order.
2. Initialize two pointers i = 0 for children and j = 0 for cookies.
3. If s[j] >= g[i], assign the cookie to the child and increment i.
4. Move j to the next cookie and continue until all children or cookies are checked.
5. Return i, which represents the maximum number of content children.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        // Type Your Logic Here.
        Arrays.sort(g);
        Arrays.sort(s);
        int i=0,j=0;
        while(i<g.length && j<s.length){
            if(s[j]>=g[i])i++;
            j++;
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}

```

## Output:
<img width="290" height="293" alt="image" src="https://github.com/user-attachments/assets/47614950-baae-48bf-8d9f-6d6f9973f775" />



## Result:
The program successfully print all the numbers from 1 to N. 
