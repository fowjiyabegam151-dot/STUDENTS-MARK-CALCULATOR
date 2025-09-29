#include <stdio.h>

struct Student {
    int roll;
    char name[50];
    float m1, m2, m3, total, percent;
};

int main() {
    int n;
    printf("Enter number of students: ");
    scanf("%d", &n);

    struct Student s[n];

    for (int i = 0; i < n; i++) {
        printf("\nStudent %d\n", i + 1);
        printf("Roll: ");
        scanf("%d", &s[i].roll);
        printf("Name: ");
        scanf(" %49[^\n]", s[i].name);
        printf("Enter 3 subject marks: ");
        scanf("%f %f %f", &s[i].m1, &s[i].m2, &s[i].m3);

        s[i].total = s[i].m1 + s[i].m2 + s[i].m3;
        s[i].percent = s[i].total / 3.0;
    }

    printf("\nRoll\tName\tTotal\tPercent\n");
    for (int i = 0; i < n; i++) {
        printf("%d\t%s\t%.2f\t%.2f\n", s[i].roll, s[i].name, s[i].total, s[i].percent);
    }
    return 0;
}
