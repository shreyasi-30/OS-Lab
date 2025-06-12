#include <stdio.h>
#include <unistd.h>

int main() {
    int p1, p2, p3;
    p1 = fork();
    if (p1 > 0) {
            sleep(3);
        printf("P1 %d, %d\n", getpid(), getppid());
    } else {
        p2 = fork();
        if (p2 > 0) {
            sleep(2);
            printf("P2 %d, %d\n", getpid(), getppid());
        } else {
            p3 = fork();
            if (p3 > 0) {
                sleep(1);
                printf("P3 %d, %d\n", getpid(), getppid());
            } else {
                sleep(0);
                printf("P4 %d, %d\n", getpid(), getppid());
            }
        }
    }
}
