# Векторизация

Спецификатор **restrict**  означает, что этот указатель единственное средство доступа к соответствующему объекту. Его можно применять только указателям. Наличие спецификатора расширяет возможности компилятора по оптимизации некоторых видов кода путём поиска сокращённых методов вычислений.

По своей сути мы обещаем, что этот указатель будет первым и  единственным способом доступа к соотвествующей области памяти в соотвествующем блоке (функции). В свою очередь, компилятор обещает его ускорить. 

Если спецификатор не установлен, то компилятор будет использовать пессимистичные оптимизации.

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
