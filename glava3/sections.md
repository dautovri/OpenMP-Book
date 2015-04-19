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
