# Векторизация

Использование **restrict**


```

#pragma omp simd 
    Дополнительные опции
              simd  safelen(длина)
                    linear(list[:шаг])
                    aligned(list[:выравнивание])
                    private(list)
                    lastprivate(list)
                    reduction(операция:list)
                    collapse(n)
                    
                    list - список переменных
                    
                    
#pragma omp declare simd
    Дополнительные опции
      declare simd simdlen(length)
                    linear(argument-list[:constant-linear-step])
                    aligned(argument-list[:alignment])
                    uniform(argument-list)
                    inbranch
                    notinbranch

#pragma omp parallel for simd


```

Парадигма SIMD – single instruction multiple data (одна инструкция множество данных).
