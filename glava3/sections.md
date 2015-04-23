# sections

##### *Краткость — сестра таланта.*
###### А.П. Чехов

Директива **parallel sections** обеспечивает краткое определение параллельной области, которая содержит одну единственную директиву **sections**. Семантика этой директивы идентична явно специфицированной директиве **parallel** непостредственно следующей директивой **sections**. Синтаксис директивы следующий:
```
#pragma omp parallel sections [клауза [ клауза]]
{
    [#pragma omp section]
      структурированный блок
    [#pragma omp section]
      структурированный блок
}
```
Клаузы одни из следующих:

* **private (список)**   
* **firstprivate (список)**  
* **lastprivate (список)**
* **reduction (оператор : список)**
* **nowait**

Если клауза **nowait** не укзана, то конструкция **sections** неявно завершится барьерной синхронизацией. Каждой секции предшествует **section**, хотя в первой секции директива **section** может отсутвовать. В отличие от планирования циклов, распределение нагрузки между потоками при обработке параллельных разделов кода осуществляется и контролируется OpenMP. Программисту остается только выбрать, какие переменные будут общими, а какие индивидуальными, и предусмотреть выражения уменьшения аналогично сегменту с организацией циклов.

* Структурные блоки кода выделенные **section** выполняются одним потоком один раз.


```
#pragma omp parallel sections
{
    #pragma omp section
    {
        printf ("section 1 id = %d, \n", omp_get_thread_num()); 
    }
    #pragma omp section
    {
        printf ("section 2 id = %d, \n", omp_get_thread_num());
    }
    #pragma omp section
    {
        printf ("section 3 id = %d, \n", omp_get_thread_num());
    }
}
```
```
section 1 id = 4,
section 3 id = 3,
section 2 id = 1,
```
* Структурные блоки двух подряд идущих **sections** будут выполнятся в непоределенном порядке. Сначала будут выполнены в произвольном порядке блоки первой **sections**, а затем второй **sections**. Это произойдёт по причине неявного барьера. В конце первой секции все потоки, которые завершили работу, будут ждать пока остальные завершат свои блоки кода. Только после завершения работы всеми потоками они приступят к выполнению второй **sections**.

```
//Первые секции
#pragma omp parallel sections
{
    #pragma omp section
    {
        printf ("section 1 id = %d, \n", omp_get_thread_num()); 
    }
    #pragma omp section
    {
        printf ("section 2 id = %d, \n", omp_get_thread_num());
    }
    #pragma omp section
    {
        printf ("section 3 id = %d, \n", omp_get_thread_num());
    }
}
//Вторые секции
#pragma omp parallel sections
{
    #pragma omp section
    {
        printf ("section 1 id = %d, \n", omp_get_thread_num()); 
    }
    #pragma omp section
    {
        printf ("section 2 id = %d, \n", omp_get_thread_num());
    }
    #pragma omp section
    {
        printf ("section 3 id = %d, \n", omp_get_thread_num());
    }
}
```

```
section 1 id = 4,
section 3 id = 3,
section 2 id = 1,

section 1 id = 4,
section 3 id = 3,
section 2 id = 1,
```
* Порядок выполнения зависит от реализации, поэтому мы не можем контролировать какой поток какую секцию получит внутри **sections**.

# single

Директива **single** специфицирует конструкцию, которая определяет, что связанный с этой конструкцией структурированный блок выполняется только одним потоком в группе (не обязательно основным). Синтаксис директивы следующий:


```
#pragma omp single  [клауза [ клауза]]
 структурированный блок
```
