#include <stdio.h>

// Функція для обчислення НСД двох чисел
int gcd(int a, int b) {
    if (b == 0)
        return a;
    else
        return gcd(b, a % b);
}

// Функція для обчислення НСК двох чисел
int lcm(int a, int b) {
    return (a * b) / gcd(a, b);
}

// Функція для знаходження НСК довільного числа чисел
int find_lcm(int arr[], int n) {
    int result = arr[0];

    for (int i = 1; i < n; i++) {
        result = lcm(result, arr[i]);
    }

    return result;
}

int main() {
    int p;
    scanf("%d", &p);

    int numbers[p];
    for (int i = 0; i < p; i++) {
        scanf("%d", &numbers[i]);
    }

    int lcm_result = find_lcm(numbers, p);
    printf("Найменше спільне кратне: %d\n", lcm_result);

    return 0;
}
