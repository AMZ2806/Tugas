#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>
int tambah(int a, int b) { return a + b; }
int kurang(int a, int b) { return a - b; }
int kali(int a, int b) { return a * b; }
int bagi(int a, int b) { return a / b; }

int faktorial(int n) {
    if (n <= 1) return 1;
    return n * faktorial(n - 1);}
int kpk(int a, int b) {
    int max = (a > b) ? a : b;
    for (; max % a != 0 || max % b != 0; ++max);
    return max;}
int fpb(int a, int b) {
    if (b == 0) return a;
    return fpb(b, a % b);}
void proses_input(char *input) {
    char operator[10];
    int a, b, hasil;
    sscanf(input, "%s %d %d", operator, &a, &b);
    if (strcmp(operator, "ADD") == 0) {
        hasil = tambah(a, b);
        printf("Hasil: %d\n", hasil);}
 else if (strcmp(operator, "SUB") == 0) {
        hasil = kurang(a, b);
        printf("Hasil: %d\n", hasil);}
 else if (strcmp(operator, "MULT") == 0) {
        hasil = kali(a, b);
        printf("Hasil: %d\n", hasil);}
 else if (strcmp(operator, "DIV") == 0) {
        hasil = bagi(a, b);
        printf("Hasil: %d\n", hasil);}
 else if (strcmp(operator, "FACT") == 0) {
        hasil = faktorial(a);
        printf("Hasil Faktorial dari %d: %d\n", a, hasil);}
 else if (strcmp(operator, "KPK") == 0) {
        hasil = kpk(a, b);
        printf("KPK dari %d dan %d: %d\n", a, b, hasil);}
 else if (strcmp(operator, "FPB") == 0) {
        hasil = fpb(a, b);
        printf("FPB dari %d dan %d: %d\n", a, b, hasil);}
 else if (strcmp(operator, "POW") == 0) {
        hasil = pow(a, b);
        printf("Hasil: %d\n", hasil);}}
int main() {
    char input[100];
    printf("Masukkan bilangan: ");
    fgets(input, sizeof(input), stdin);
    proses_input(input);
    return 0;}

