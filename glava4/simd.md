# SIMD

##### *Я не могу долго быть одна. Когда я одна — я ничто. Просто набор скверных качеств.*
######Эрих Мария Ремарк "Земля обетованная"

Парадигма SIMD – single instruction multiple data (одна инструкция множество данных).
```
#pragma omp simd 
```
Клаузы:
* safelen(длина)
* linear(список[:шаг])
* aligned(список[:выравнивание])
* private(список)
* lastprivate(список)
* reduction(операция:список)
* collapse(n)


```
#pragma omp declare simd
```

Клаузы:
* simdlen(длина)
* linear(список[:шаг])
* aligned(список[:выравнивание])
* uniform(список)
* inbranch
* notinbranch

```
#pragma omp parallel for simd
```