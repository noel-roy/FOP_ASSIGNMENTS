#include <stdio.h>

long long factorial(int n) {
    long long f = 1;
    int i;
    for(i = 1; i <= n; i++)
        f *= i;
    return f;
}

long long power(int x, int y) {
    long long result = 1;
    int i;
    for(i = 1; i <= y; i++)
        result *= x;
    return result;
}

int main() {
    int choice;
    double a, b;

    scanf("%d", &choice);

    switch(choice) {
        case 1:
            scanf("%lf %lf", &a, &b);
            printf("%lf", a + b);
            break;
        case 2:
            scanf("%lf %lf", &a, &b);
            printf("%lf", a - b);
            break;
        case 3:
            scanf("%lf %lf", &a, &b);
            printf("%lf", a * b);
            break;
        case 4:
            scanf("%lf %lf", &a, &b);
            if(b != 0)
                printf("%lf", a / b);
            else
                printf("Division by zero");
            break;
        case 5: {
            int x, y;
            scanf("%d %d", &x, &y);
            printf("%lld", power(x, y));
            break;
        }
        case 6: {
            int n;
            scanf("%d", &n);
            printf("%lld", factorial(n));
            break;
        }
    }

    return 0;
}
