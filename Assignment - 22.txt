#include <stdio.h>
#include <string.h>

int main() {
    int choice;
    char str1[100], str2[100];

    scanf("%d", &choice);

    switch(choice) {
        case 1:
            scanf("%s", str1);
            printf("%lu", strlen(str1));
            break;
        case 2:
            scanf("%s", str1);
            strrev(str1);
            printf("%s", str1);
            break;
        case 3:
            scanf("%s %s", str1, str2);
            if(strcmp(str1, str2) == 0)
                printf("Equal");
            else
                printf("Not Equal");
            break;
        case 4:
            scanf("%s %s", str1, str2);
            strcat(str1, str2);
            printf("%s", str1);
            break;
        case 5:
            scanf("%s %s", str1, str2);
            if(strstr(str1, str2) != NULL)
                printf("Found");
            else
                printf("Not Found");
            break;
    }

    return 0;
}
