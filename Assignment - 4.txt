#include <stdio.h>

int main() {
    float basic, hra, ta, gross, tax, net;

    scanf("%f", &basic);

    hra = 0.10 * basic;
    ta = 0.05 * basic;
    gross = basic + hra + ta;
    tax = 0.02 * gross;
    net = gross - tax;

    printf("%f", net);

    return 0;
}
