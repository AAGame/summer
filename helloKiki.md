# Fifth question:


    #include <stdio.h>
    #include <stdlib.h>

    int main() {
        int T, n;
        scanf ("%d", &T);
        int M[7] = {0}, N[7] = {0};
        int i, j, t = 0, max, ans;
        int flag;
        while (T--) {
            t++;
            scanf ("%d", &n);
            for (i = 0; i < n; i++){
                scanf ("%d", &M[i]);
            }
            for (i = 0; i < n; i++){
                scanf ("%d", &N[i]);
            }
            for (flag = 0, max = M[0], i = 1; i < n; i++){
                if (max < M[i]) {
                    max = M[i];
                    flag = i;
                }
            }
            for (ans = max + N[flag], i = 1; i < 101; i++, ans = max * i + N[flag]) {
                for (j = 0; j < n && (ans % M[j]) == N[j]; j++);
                if (j == n) {
                    printf ("Case %d : %d\n", t, ans);
                    goto AAA;
                }
            }
            AAA : if (i == 101)  printf ("Case %d : -1\n", t);
        }

        return 0;
    }

# Answer:
![image](https://github.com/AAGame/summer/blob/Alan/5.png)
