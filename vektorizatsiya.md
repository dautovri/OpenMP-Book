# Векторизация

Использование **restrict**


```

#pragma omp simd 
#pragma omp declare simd
#pragma omp parallel for simd

  #pragma omp simd  safelen(длина)
                    linear(list[:шаг])
                    aligned(list[:выравнивание])
                    private(list)
                    lastprivate(list)
                    reduction(операция:list)
                    collapse(n)
                    
                    list - список переменных


```

Парадигма SIMD – single instruction multiple data (одна инструкция множество данных).
