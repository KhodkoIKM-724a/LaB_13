#include <iostream>
#include <locale>
#include <windows.h>

double recursiveTerm(int n) {
    if (n == 1)
        return 0.4;
    return recursiveTerm(n - 1) / 10;
}

int main() {
    system("chcp 65001 > nul");
    setlocale(LC_ALL, "");

    int n;
    std::wcout << L"Введіть номер члена ряду n (1–12): ";
    std::wcin >> n;

    if (n < 1 || n > 12) {
        std::wcout << L"Некоректне значення n. Введіть від 1 до 12.\n";
    }
    else {
        double result = recursiveTerm(n);
        std::wcout << L"Член №" << n << L" ряду: " << result << std::endl;
    }

    return 0;
}
