#include <stdio.h>

int main() {
    int n,i,j,tott=0,totc=0,totw=0,temp;
    printf("enter number of processes: ");
    scanf("%d",&n);
    int a[n],w[n],t[n],b[n],c[n],pid[n];
    for(i=0;i<n;i++){
        pid[i]=i+1;
        printf("enter at and bt for pid %d: ",pid[i]);
        scanf("%d %d",&a[i],&b[i]);
    }
   
    for(i=0;i<n-1;i++){
        for(j=0;j<n-i-1;j++){
            if(a[j]>a[j+1]){
                temp=a[j];
                a[j]=a[j+1];
                a[j+1]=temp;
                temp=b[j];
                b[j]=b[j+1];
                b[j+1]=temp;
                temp=pid[j];
                pid[j]=pid[j+1];
                pid[j+1]=temp;
               
            }
        }
    }
   
    for(i=0;i<n;i++){
        if(i==0){
            c[i]=a[i]+b[i];
           
        }
        else{
            if(c[i-1]>a[i]){
                c[i]=c[i-1]+b[i];
            }
            else{
                c[i]=a[i]+b[i];
            }
        }
       
        totc+=c[i];
       
        t[i]=c[i]-a[i];
        w[i]=t[i]-b[i];
        tott+=t[i];
        totw+=w[i];
    }
   
    printf("\nID  AT  BT  CT  TAT  WT\n");
    for (i = 0; i < n; i++) {
        printf("%d   %d   %d   %d   %d   %d\n", pid[i], a[i], b[i], c[i], t[i], w[i]);
    }

    printf("\nAverage CT: %.2f\n", (float)totc / n);
    printf("Average TAT: %.2f\n", (float)tott / n);
    printf("Average WT: %.2f\n", (float)totw / n);

    return 0;
}
