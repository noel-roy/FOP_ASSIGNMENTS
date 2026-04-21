#include <stdio.h>
#include <string.h>

struct Employee {
    char name[50];
    char designation[50];
    char gender;
    char doj[20];
    float salary;
};

int main() {
    int n, i;
    scanf("%d", &n);

    struct Employee e[100];

    for(i = 0; i < n; i++) {
        scanf("%s", e[i].name);
        scanf("%s", e[i].designation);
        scanf(" %c", &e[i].gender);
        scanf("%s", e[i].doj);
        scanf("%f", &e[i].salary);
    }

    int male = 0, female = 0, highSalary = 0, asstManager = 0;

    for(i = 0; i < n; i++) {
        if(e[i].gender == 'M' || e[i].gender == 'm')
            male++;
        else if(e[i].gender == 'F' || e[i].gender == 'f')
            female++;

        if(e[i].salary > 10000)
            highSalary++;

        if(strcmp(e[i].designation, "AsstManager") == 0 || strcmp(e[i].designation, "Asst_Manager") == 0)
            asstManager++;
    }

    printf("%d\n", n);
    printf("%d %d\n", male, female);
    printf("%d\n", highSalary);
    printf("%d\n", asstManager);

    return 0;
}
