#include <stdio.h>
#include <string.h>

int main() {
    char str1[100], str2[100], temp[100];
    int i, len = 0, flag = 1;

    scanf("%s", str1);

    while(str1[len] != '\0')
        len++;

    printf("%d\n", len);

    for(i = 0; i < len; i++)
        temp[i] = str1[len - i - 1];
    temp[len] = '\0';

    printf("%s\n", temp);

    scanf("%s", str2);

    if(strcmp(str1, str2) == 0)
        printf("Equal\n");
    else
        printf("Not Equal\n");

    for(i = 0; i < len / 2; i++) {
        if(str1[i] != str1[len - i - 1]) {
            flag = 0;
            break;
        }
    }

    if(flag)
        printf("Palindrome\n");
    else
        printf("Not Palindrome\n");

    if(strstr(str1, str2) != NULL)
        printf("Substring Found");
    else
        printf("Substring Not Found");

    return 0;
}
