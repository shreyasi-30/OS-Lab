#include <stdio.h>

int main() {
    int n, i, time = 0, completed = 0, min_bt, idx;
    printf("Enter number of processes: ");
    scanf("%d", &n);

    int id[n], at[n], bt[n], ct[n], tat[n], wt[n], is_completed[n];
    for (i = 0; i < n; i++) is_completed[i] = 0;

    for (i = 0; i < n; i++) {
        id[i] = i + 1;
        printf("Enter Arrival Time and Burst Time for P%d: ", id[i]);
        scanf("%d %d", &at[i], &bt[i]);
    }

    for (i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (at[i] > at[j] || (at[i] == at[j] && bt[i] > bt[j])) {
               
                int temp = at[i];
                at[i] = at[j];
                at[j] = temp;
               
                temp = bt[i]; 
                bt[i] = bt[j]; 
                bt[j] = temp;
               
                temp = id[i]; 
                id[i] = id[j]; 
                id[j] = temp;
            }
        }
    }

   
    int total_ct = 0, total_tat = 0, total_wt = 0;

 
    printf("\nID\tAT\tBT\tCT\tTAT\tWT\n");
    while (completed < n) {
        min_bt = 9999; idx = -1;
        for (i = 0; i < n; i++) {
            if (at[i] <= time && !is_completed[i]) {
                if (bt[i] < min_bt) {
                    min_bt = bt[i];
                    idx = i;
                }
            }
        }

        if (idx != -1) {
            
            time += bt[idx];
            ct[idx] = time;  
            tat[idx] = ct[idx] - at[idx]; 
            wt[idx] = tat[idx] - bt[idx];
            total_ct += ct[idx];
            total_tat += tat[idx];
            total_wt += wt[idx];
           
            
            is_completed[idx] = 1;
            completed++;

            // Print process details
            printf("%d\t%d\t%d\t%d\t%d\t%d\n", id[idx], at[idx], bt[idx], ct[idx], tat[idx], wt[idx]);
        } else {
            // If no process is ready, just increment time
            time++;
        }
    }

    // Print Average Times
    printf("\nAverage CT: %.2f", (float)total_ct / n);
    printf("\nAverage TAT: %.2f", (float)total_tat / n);
    printf("\nAverage WT: %.2f\n", (float)total_wt / n);

    return 0;
}
