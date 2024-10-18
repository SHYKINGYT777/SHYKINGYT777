#include <stdio.h>
#include <math.h>
#define TRUE 1
#define FALSE 0
#define MAX 10

int x[MAX];  // This will store the positions of queens on the board

int feasible(int k, int j) {
    for (int i = 1; i <= k - 1; i++) {
        // Check if queens are in the same column or diagonal
        if (x[i] == j || abs(j - x[i]) == abs(k - i))
            return FALSE;
    }
    return TRUE;
}

void print_solution(int n) {
    for (int i = 1; i <= n; i++) {
        printf("%d ", x[i]);
    }
    printf("\n");
}

void recur_nqueens(int k, int n) {
    for (x[k] = 1; x[k] <= n; x[k]++) {
        if (feasible(k, x[k])) {
            if (k == n) {
                print_solution(n);  // Print the solution when a queen is placed in every row
            } else {
                recur_nqueens(k + 1, n);  // Recur to place the queen in the next row
            }
        }
    }
}

int main() {
    int n;
    printf("Enter the number of queens: ");
    scanf("%d", &n);
    recur_nqueens(1, n);  // Start from the first row
    return 0;
}
