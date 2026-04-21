#include <stdio.h>

int main() {
    int n, temp, r, sum = 0;
    scanf("%d", &n);

    temp = n;

    while(temp > 0) {
        r = temp % 10;
        sum += r * r * r;
        temp /= 10;
    }

    if(sum == n)
        printf("Armstrong Number");
    else
        printf("Not an Armstrong Number");

    return 0;
}
