# Компиляторы

На данный момент основые компиляторы которые ведут поддрежку последних стандартов OpenMP.

[GNU GCC](https://ru.wikipedia.org/wiki/GNU_Compiler_Collection)

[Intel Composer C++](https://ru.wikipedia.org/wiki/Intel_Parallel_Composer)

Компилятор, который входит в состав [Microsoft Visual Studio](https://ru.wikipedia.org/wiki/Visual_Studio), поддерживает стандарт версии OpenMP 2.0. 


С полным списком компиляторов, которые поддерживают данную технологию вы можете ознакомится на [официальной странице OpenMP ARB](http://openmp.org/wp/openmp-compilers/). 

Простая программа для проверки вашего компилятора.

```
#include <iostream>
#include "omp.h"

int main()
{
    #pragma omp parallel
    {
        std::cout << ”Hello World\n”
    }
 return 0;
}

```
