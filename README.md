#include <stdio.h>
#include <math.h>

int countIntersectionPoints(int x1, int y1, int r1, int x2, int y2, int r2) {
    double distance = sqrt(pow((x2 - x1), 2) + pow((y2 - y1), 2));

    // Перевіряємо чи кола не перетинаються взагалі
    if (distance > r1 + r2) {
        return 0; // Кола не перетинаються
    } else if (distance < abs(r1 - r2)) {
        return 0; // Одне коло знаходиться всередині іншого
    } else if (distance == 0 && r1 == r2) {
        return -1; // Кола співпадають, безкінечна кількість точок перетину
    } else {
        return 2; // Кола перетинаються в двох точках
    }
}

int main() {
    int x1, y1, r1, x2, y2, r2;
    printf("Введіть координати та радіус першого кола (x1, y1, r1): ");
    scanf("%d %d %d", &x1, &y1, &r1);
    printf("Введіть координати та радіус другого кола (x2, y2, r2): ");
    scanf("%d %d %d", &x2, &y2, &r2);

    int intersectionPoints = countIntersectionPoints(x1, y1, r1, x2, y2, r2);

    printf("Кількість точок перетину: %d\n", intersectionPoints);

    return 0;
}
