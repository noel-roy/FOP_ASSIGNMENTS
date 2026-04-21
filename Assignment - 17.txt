#include <stdio.h>
#include <math.h>

int main() {
    int n, i;
    double x, sum = 0, term;

    scanf("%lf", &x);
    scanf("%d", &n);

    x = x * M_PI / 180;

    for(i = 0; i < n; i++) {
        int sign = (i % 2 == 0) ? 1 : -1;
        int fact = 1, j;
        for(j = 1; j <= 2*i + 1; j++)
            fact *= j;
        term = sign * pow(x, 2*i + 1) / fact;
        sum += term;
    }

    printf("%lf", sum);

    return 0;
}
