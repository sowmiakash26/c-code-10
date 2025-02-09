#include<stdio.h>
#define N 4
void rotate(int m[N][N]){
    for (int i = 0; i < N; i++){
        for (int j = i;j < N; j++){
            int temp = m[i][j];
            m[i][j] = m[j][i];
            m[j][i] = temp;
        }
    }
    for (int i = 0;i < N; i++){
        int start = 0, end = N-1;
        while(start < end){
            int temp = m[i][start];
            m[i][start] = m[i][end];
            m[i][end] = temp;
            start++;
            end--;
        }
    }
}
void printMatrix(int m[N][N]){
    for (int i = 0;i < N; i++){
        for (int j = 0;j < N; j++){
            printf("%d ", m[i][j]);
        }
        printf("\n");
    }
}
int main(){
    int m[N][N] = {{1, 2, 3, 4},{5, 6, 7, 8},{9, 10, 11, 12},{13, 14, 15, 16}};
    printf("Original Matrix:\n");
    printMatrix(m);
    rotate(m);
    printf("\nRotated Matrix 90-degree:\n");
    printMatrix(m);
    return 0;
}
