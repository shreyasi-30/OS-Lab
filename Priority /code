#include <stdio.h>

int main() {
    int n, i, current_time = 0, completed = 0, idx;
    
    printf("Enter number of processes: ");
    scanf("%d", &n);

    int id[n], at[n], bt[n], pri[n], ct[n], tat[n], wt[n], rt[n], is_completed[n];

    
    for (i = 0; i < n; i++) {
        id[i] = i + 1;
        printf("Enter AT, BT & Priority for P%d: ", id[i]);
        scanf("%d %d %d", &at[i], &bt[i], &pri[i]);
        rt[i] = bt[i]; 
        is_completed[i] = 0; 
    }

    int total_ct = 0, total_tat = 0, total_wt = 0;

    printf("\nID\tAT\tBT\tPri\tCT\tTAT\tWT\n");

    while (completed < n) {
        int min_pri = 9999;
        idx = -1;

        // Find highest priority process at current time
        for (i = 0; i < n; i++) {
            if (at[i] <= current_time && rt[i] > 0) {
                if (pri[i] < min_pri || (pri[i] == min_pri && at[i] < at[idx])) {
                    min_pri = pri[i];
                    idx = i;
                }
            }
        }

        if (idx != -1) {
            rt[idx]--; // Execute the process for 1 unit time
            current_time++;

            // If process is finished
            if (rt[idx] == 0) {
                ct[idx] = current_time;
                tat[idx] = ct[idx] - at[idx];
                wt[idx] = tat[idx] - bt[idx];

                total_ct += ct[idx];
                total_tat += tat[idx];
                total_wt += wt[idx];

                is_completed[idx] = 1;
                completed++;

                // Print process info once it's completed
                printf("%d\t%d\t%d\t%d\t%d\t%d\t%d\n", id[idx], at[idx], bt[idx], pri[idx], ct[idx], tat[idx], wt[idx]);
            }
        } else {
            current_time++; 
        }
    }

    printf("\nAvg CT: %.2f\nAvg TAT: %.2f\nAvg WT: %.2f\n",
        (float)total_ct / n, (float)total_tat / n, (float)total_wt / n);

    return 0;
}
