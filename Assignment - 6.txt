#include <stdio.h>

long long fact_iter(int n) {
    long long f = 1;
    int i;
    for(i = 1; i <= n; i++)
        f *= i;
    return f;
}

long long fact_rec(int n) {
    if(n == 0 || n == 1)
        return 1;
    return n * fact_rec(n - 1);
}

int main() {
    int n;
    scanf("%d", &n);

    printf("%lld\n", fact_iter(n));
    printf("%lld", fact_rec(n));

    return 0;
}
