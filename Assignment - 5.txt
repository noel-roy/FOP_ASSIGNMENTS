#include <stdio.h>
#include <math.h>

int main() {
    int choice;
    scanf("%d", &choice);

    if(choice == 1) {
        int r, c, i, j;
        scanf("%d %d", &r, &c);
        int a[10][10], b[10][10], sum[10][10];

        for(i = 0; i < r; i++)
            for(j = 0; j < c; j++)
                scanf("%d", &a[i][j]);

        for(i = 0; i < r; i++)
            for(j = 0; j < c; j++)
                scanf("%d", &b[i][j]);

        for(i = 0; i < r; i++)
            for(j = 0; j < c; j++)
                sum[i][j] = a[i][j] + b[i][j];

        for(i = 0; i < r; i++) {
            for(j = 0; j < c; j++)
                printf("%d ", sum[i][j]);
            printf("\n");
        }
    }

    else if(choice == 2) {
        int n, i, j;
        scanf("%d", &n);
        int a[10][10];

        for(i = 0; i < n; i++)
            for(j = 0; j < n; j++)
                scanf("%d", &a[i][j]);

        for(i = 0; i < n; i++) {
            int min = a[i][0], col = 0;
            for(j = 1; j < n; j++) {
                if(a[i][j] < min) {
                    min = a[i][j];
                    col = j;
                }
            }
            int k, flag = 1;
            for(k = 0; k < n; k++) {
                if(a[k][col] > min) {
                    flag = 0;
                    break;
                }
            }
            if(flag) {
                printf("%d", min);
                return 0;
            }
        }
        printf("No Saddle Point");
    }

    else if(choice == 3) {
        int i, j;
        float a[2][2], det, inv[2][2];

        for(i = 0; i < 2; i++)
            for(j = 0; j < 2; j++)
                scanf("%f", &a[i][j]);

        det = a[0][0]*a[1][1] - a[0][1]*a[1][0];

        if(det == 0) {
            printf("Not Invertible");
        } else {
            inv[0][0] = a[1][1]/det;
            inv[0][1] = -a[0][1]/det;
            inv[1][0] = -a[1][0]/det;
            inv[1][1] = a[0][0]/det;

            for(i = 0; i < 2; i++) {
                for(j = 0; j < 2; j++)
                    printf("%f ", inv[i][j]);
                printf("\n");
            }
        }
    }

    else if(choice == 4) {
        int n, i, j;
        scanf("%d", &n);
        int a[10][10], sum = 0, flag = 1;

        for(i = 0; i < n; i++)
            for(j = 0; j < n; j++)
                scanf("%d", &a[i][j]);

        for(j = 0; j < n; j++)
            sum += a[0][j];

        for(i = 1; i < n; i++) {
            int rowsum = 0;
            for(j = 0; j < n; j++)
                rowsum += a[i][j];
            if(rowsum != sum)
                flag = 0;
        }

        for(j = 0; j < n; j++) {
            int colsum = 0;
            for(i = 0; i < n; i++)
                colsum += a[i][j];
            if(colsum != sum)
                flag = 0;
        }

        int d1 = 0, d2 = 0;
        for(i = 0; i < n; i++) {
            d1 += a[i][i];
            d2 += a[i][n-i-1];
        }

        if(d1 != sum || d2 != sum)
            flag = 0;

        if(flag)
            printf("Magic Square");
        else
            printf("Not Magic Square");
    }

    return 0;
}
