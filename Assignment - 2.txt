#include <stdio.h>

int main() {
    int choice;
    float a, b;

    scanf("%d", &choice);
    scanf("%f %f", &a, &b);

    switch(choice) {
        case 1:
            printf("%f", a + b);
            break;
        case 2:
            printf("%f", a - b);
            break;
        case 3:
            printf("%f", a * b);
            break;
        case 4:
            if (b != 0)
                printf("%f", a / b);
            else
                printf("Division by zero");
            break;
    }

    return 0;
}
