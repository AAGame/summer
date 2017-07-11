# Third question:

    #include <stdio.h>
    #include <stdlib.h>

    void decToInvertBin(int invertBin[], int bin[][7], int C) {
        for (int i = 0; i < C * 5; i++) {
            for (int j = 0; j < 7; j++) {
                bin[i][j] = invertBin[i] % 2;
                invertBin[i] /= 2;
            }
        }
    }
    int main() {
        int T, C;
        int invertBin[480] = {0};
        int bin[480][7] = {0};
        int i, j;
        scanf ("%d", &T);
        int t = 0;
        while (T--) {
           t++;
           scanf ("%d", &C);
           for (i = 0; i < C * 5; i++) {
               scanf ("%x", &invertBin[i]);
           }
           decToInvertBin(invertBin, bin, C);
           printf ("Case %d :\n\n", t);
           for (i = 0; i < 7; i++) {
               for (j = 0; j < C * 5; j++) {
                   if (bin[j][i] == 1) putchar('#');
                   else putchar(' ');
                   if ((j + 1) % 5 == 0) putchar(' ');
               }
               putchar('\n');
           }
        }
        return 0;
    }


# Answer:
![image](https://github.com/AAGame/summer/blob/Alan/3.png)
