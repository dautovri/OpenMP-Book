# Векторизация

Использование **restrict**


```
#pragma omp ivdep
#pragma omp simd 
#pragma omp declare simd
#pragma omp parallel for simd
```
Парадигма SIMD – single instruction multiple data (одна инструкция множество данных)