#include <stdio.h>

void birBuyukBirKucukSiralama(int dizi[], int boyut) {
    int temp, i, j;

    for (i = 0; i < boyut - 1; i++) {
        for (j = i + 1; j < boyut; j++) {
            if (dizi[i] < dizi[j]) {
                temp = dizi[i];
                dizi[i] = dizi[j];
                dizi[j] = temp;
            }
        }
    }
}

int main() {
    int dizi[] = { 25, 18, 23, 9, 7, 10, 3, 12, 29, 99, 77, 47, 59, 86 };
    int boyut = sizeof(dizi) / sizeof(dizi[0]);

    printf("Siralanacak dizi: ");
    for (int i = 0; i < boyut; i++) {
        printf("%d ", dizi[i]);
    }
    printf("\n");

    birBuyukBirKucukSiralama(dizi, boyut);

    printf("Siralanmis dizi: ");
    for (int i = 0; i < boyut / 2; i++) {
        printf("%d ", dizi[i]);
        printf("%d ", dizi[boyut - i - 1]);
    }

    if (boyut % 2 == 1) {
        printf("%d", dizi[boyut / 2]);
    }

    printf("\n");

    return 0;
}
