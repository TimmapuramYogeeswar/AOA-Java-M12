
# EX 1C Job Sequencing using Greedy Approach
## DATE: 15.09.2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm
1. Start and sort all jobs in descending order of profit.
2. Find the maximum deadline and create an array to track available time slots.
3. For each job, check the slots from its deadline backwards.
4. If a free slot is found, schedule the job, increase the job count, and add its profit.
5. Return and print the total number of scheduled jobs and the maximum total profit.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.*;

public class JobScheduling {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static int[] jobScheduling(Job[] jobs, int n) {
        // Type Your Code Here.
        Arrays.sort(jobs,(a,b) -> b.profit-a.profit);
        int maxdeadline=0;
        for(Job job:jobs){
            maxdeadline=Math.max(maxdeadline,job.deadline);
        }
        boolean[] slot=new boolean[maxdeadline+1];
        int jbdone=0,tp=0;
        for(Job job:jobs){
            for(int j=job.deadline;j>0;j--){
                if(!slot[j]){
                    slot[j]=true;
                    jbdone++;
                    tp+=job.profit;
                    break;
                }
            }
        }
        return new int[]{jbdone,tp};
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();
            jobs[i] = new Job(id, deadline, profit);
        }

        int[] result = jobScheduling(jobs, n);
        System.out.println(result[0] + " " + result[1]);
    }
}

```

## Output:

<img width="356" height="370" alt="image" src="https://github.com/user-attachments/assets/1b913bf0-efce-4c22-9872-2b3a20b220ed" />


## Result:
The program successfully implemented and the expected output is verified.
