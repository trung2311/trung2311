#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
int main()
{
    float a[50][50], d=1, t;
    int n, i, j, k;
    printf("nhap cap cua ma tran vuong A\n"); scanf("%d",&n);
    
    for(i=0; i<n; i++){
        for(j=0; j<n; j++){
                printf("a[%d][%d]= ", i, j);
                scanf("%f", &a[i][j]);
        }
        printf("\n");
    }
    
    for(i=0; i<n-1; i++){
        for(k=i+1; k<n; k++){
            if(a[k][i]==0) continue;
            if(a[k][i]!=0) {
                    for(j=0; j<n; j++){
                        a[k][j]=-a[k][j]*(a[i][i]/a[k][i]);
                        a[i][j]=a[i][j]+a[k][j];
                        t=a[k][j];
                        a[k][j]=-a[i][j];
                        a[i][j]=t;
                    }
                }
        }
    }
    printf("ma tran tam giac la:\n");
    for(i=0; i<n; i++){
        for(j=0; j<n; j++){
            printf("%.2f\t",a[i][j]);
        }
        printf("\n");
    }
    
    for(i=0; i<n; i++){
        d=d*a[i][i];
    }
    printf("dinh thuc cua ma tran A= %.2f", d);
    getch();
    return 0;

        }
