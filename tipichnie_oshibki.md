# Типичные ошибки

## _Самая большая ошибка — думать, что никогда не ошибёшься._

### Томас Карлейль

* **Ошибки корректности**:  все ошибки влияющие на корректность работы программы. 
* **Ошибки производительности**:  все ошибки влияющие на скорость работы программы, при этом программа работает правильно и выдает корректный результат.

| **№** | **Ошибка** |
| :--- | :--- |
|  | **Корректность** |
| 1 | Неправильный доступ к общей переменной |
| 2 | Использование замков \(**lock**\) без дерективы **flush** |
| 3 | Чтение общей переменной без дерективы **flush** |
| 4 | Забытый **private** |
| 5 | Использование клаузы **ordered** без кострукции **ordered** |
| 6 | Переменная цикла с  **\#pragma omp parallel for** как  **shared** |
| 7 | Забытый **for** для конструкции цикла  **\#pragma omp parallel for** |
| 8 | Попытка изменить количиство потоков внутри паралельного региона |
| 9 | Вызов  **omp\_unset\_lock\(\)**  из потока который не владеет замком |
| 10 | Попытка изменить переменную цикла при  **\#pragma omp parallel for** |
|  | **Производительность** |
| 11 | Использование **critical** когда эффективнее использовать **atomic** |
| 12 | Большие объемы работ внутри **critical** секции |
| 13 | Использование не нужной **critical** секции |
| 14 | Использование не нужного **flush**  |

