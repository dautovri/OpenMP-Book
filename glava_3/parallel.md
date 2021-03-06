# parallel

## _Единственная причина для существования времени — чтобы все не случилось одновременно._

### Альберт Эйнштейн

Следующая директива определяет параллельную область. Область программы, которая выполняется несколькими потоками одновременно. Это фундаментальная конструкция, которая начинает параллельное выполнение.

```text
#pragma omp parallel [клауза [  клауза]...]

    // структурный блок кода, который будет выполнен параллельно
```

Клауза одна из следующих:

* **if \(скалярное выражение\)**
* **num\_threads \(целое число\)**
* **private \(список\)**
* **shared \(список\)**
* **default \(shared \| none\)**
* **firstprivate \(список\)**
* **reduction \(оператор : список\)**
* **copyin \(список\)**
* **proc\_bind \(master \| close \| spread\)**

Когда поток встречает параллельную конструкцию, то создаётся группа потоков в одном из следующих случаев:

* Не присутствует клауза **if**
* Значение скалярного выражения в клаузе **if** не равно нулю

Поток становится основным потоком группы, получает номер 0, и все потоки, включая основной, выполняют параллельно. Число потоков в группе управляется переменной окружения или библиотечной функцией. После создания параллельной области число, потоков на время выполнение этой области остается неизменным. После завершения этой области число потоков может быть изменено. Если выражение в клаузе **if** равно 0, то область выполняется последовательно.

Пример продемонстрирует использование условий.

```text
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

Результат работы:

```text
val = 0, serialized
val = 2, parallelized with 2 threads
```

В конце параллельной области осуществляется, не указанная явно, барьерная синхронизация.

Если поток в группе, выполняя параллельную область кода, встретит другую параллельную конструкцию, она создает новую группу и становится основным потоком в новой группе. Вложенные паралелльные области выполняются по умолчанию последовательно. И как следствие, по умолчанию вложенная параллельная область выполняется группой, состоящей из одного потока. Поведение по умолчанию может быть изменено путем применения библиотечной функции времени выполнения **omp\_set\_nested** или переменной среды **OMP\_NESTED**. Если вызывается библиотечные функции то нужно внести заголовочный файл **omp.h** .

```text
#include <omp.h>
#include <stdio.h>
void report_num_threads(int level)
{
    #pragma omp single
    {
         printf("Level %d: number of threads in the team - %d\n",
                      level, omp_get_num_threads());
    }
}
int main()
{
    omp_set_dynamic(0);
    #pragma omp parallel num_threads(2)
    {
        report_num_threads(1);
        #pragma omp parallel num_threads(2)
        {
            report_num_threads(2);
            #pragma omp parallel num_threads(2)
            {
                report_num_threads(3);
            }
        }
    }
    return 0;
}
```

Ниже приведён вывод при изменении переменной окружения:

```text
setenv OMP_NESTED TRUE

Level 1: number of threads in the team - 2
Level 2: number of threads in the team - 2
Level 2: number of threads in the team - 2
Level 3: number of threads in the team - 2
Level 3: number of threads in the team - 2
Level 3: number of threads in the team - 2
Level 3: number of threads in the team - 2

setenv OMP_NESTED FALSE

Level 1: number of threads in the team - 2
Level 2: number of threads in the team - 1
Level 3: number of threads in the team - 1
Level 2: number of threads in the team - 1
Level 3: number of threads in the team - 1
```

У директивы есть и ограничения по применению:

* Клауза **if** может встретиться только один раз.
* Не специцифицируется побочных эффектов, если присутствует выражение внутри **if**.
* Выполенение функции **throw**   внутри параллельной области должно предусматривать продолжение работы внутри того же структурного блока и должно быть захвачено тем же потоком, который породил исключительную ситуацию. 

OpenMP определяет следующие конструкции распределения работ:

* директива **for**
* директива **sections**
* директива **single**
* директива **workshare**

