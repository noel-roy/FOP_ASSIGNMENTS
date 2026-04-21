#include <stdio.h>

struct Student {
    char name[50];
    int roll;
    float marks[3], total, avg;
};

int main() {
    int n, i, j;
    scanf("%d", &n);

    struct Student s[100];

    for(i = 0; i < n; i++) {
        scanf("%s", s[i].name);
        scanf("%d", &s[i].roll);
        s[i].total = 0;

        for(j = 0; j < 3; j++) {
            scanf("%f", &s[i].marks[j]);
            s[i].total += s[i].marks[j];
        }

        s[i].avg = s[i].total / 3;
    }

    for(i = 0; i < n; i++) {
        printf("%s %d %.2f %.2f\n", s[i].name, s[i].roll, s[i].total, s[i].avg);
    }

    return 0;
}
