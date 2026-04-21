#include <stdio.h>

int main() {
    int a, b, i, gcd, scd = -1;
    scanf("%d %d", &a, &b);

    int min = (a < b) ? a : b;

    for(i = 2; i <= min; i++) {
        if(a % i == 0 && b % i == 0) {
            scd = i;
            break;
        }
    }

    while(b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    gcd = a;

    if(scd == -1)
        printf("No common divisor other than 1\n");
    else
        printf("%d\n", scd);

    printf("%d", gcd);

    return 0;
}
