# First qustion:

    #include <stdio.h>
    #include <stdlib.h>
    #include <time.h>

    void SWAP(int *a, int *b) {
        int temp;
        temp = *a;
        *a = *b;
        *b = temp;
    }
    int main() {
        int C;
        scanf ("%d", &C);
        int n, m;
        int p[1005] = {0}, h[1005] = {0};
        int i, j;
        double sum;
        while (C--) {
            i = 0; j = 0; sum = 0.0;
            scanf("%d%d", &n, &m);
            for (i = 0; i < m; i ++) {
                scanf ("%d%d", &p[i], &h[i]);
            }
            for (i = 0; i < m - 1; i++) {
                for (j = i + 1; j < m; j++) {
                    if (p[i] > p[j]) {
                        SWAP(&p[i], &p[j]);
                        SWAP(&h[i], &h[j]);
                    }
                }
            }
            for (i = 0; n != 0; i++) {
                if ((p[i] * h[i]) <= n) {
                    sum += h[i];
                    n -= p[i] * h[i];
                }
                else {
                    sum += ((double)n / (double)p[i]);
                    n = 0;
                }
            }
            printf ("%.2lf\n", sum);
        }
        return 0;
    }


# Answer:
![image](https://github.com/AAGame/summer/blob/Alan/first.png)
