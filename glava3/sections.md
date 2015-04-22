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

```
#pragma omp parallel     
{ 
    #pragma omp for 
    for (i=0; i<x; i++)
        Fn1();
    
    #pragma omp sections  
    { 
        #pragma omp section  
        {  
            TaskA(); 
        }  
        #pragma omp section 
        { 
            TaskB(); 
        } 
        #pragma omp section 
        { 
            TaskC();  
        }
    } 
} 
```


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
