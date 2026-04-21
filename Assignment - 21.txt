#include <stdio.h>

int main() {
    FILE *f1, *f2;
    char ch;

    char source[100], dest[100];

    scanf("%s", source);
    scanf("%s", dest);

    f1 = fopen(source, "r");
    f2 = fopen(dest, "w");

    if(f1 == NULL || f2 == NULL)
        return 0;

    while((ch = fgetc(f1)) != EOF)
        fputc(ch, f2);

    fclose(f1);
    fclose(f2);

    return 0;
}
