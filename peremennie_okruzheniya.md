# Переменные окружения

| Название | Возможные значения  | По умолчанию* |
| -- | -- | -- |
| OMP_NUM_THREADS   | неотрицательное целое  | 1 или кол-во ядер |
| OMP_SCHEDULE | тип планирования [размер] | static |
| OMP_DYNAMIC | TRUE FALSE | TRUE |
| OMP_NESTED  | TRUE FALSE| FALSE |
| OMP_STACKSIZE | "размер [B K M G]" | - |
| OMP_WAIT_POLICY | ACTIVE PASSIVE | PASSIVE |
| OMP_MAX_ACTIVE_LEVELS | неотрицательное целое | - |
| OMP_THREAD_LIMIT | неотрицательное целое | 1024 |
| OMP_PROC_BIND |  TRUE FALSE | FALSE |
| OMP_PLACES | порядок размещения | - |
| OMP_CANCELLATION |  TRUE FALSE | FALSE |
| OMP_DISPLAY_ENV|  TRUE FALSE | FALSE |
| OMP_DEFAULT_DEVICE| неотрицательное целое | - |



Значения по умолчанию зависят от реализации. В таблице приведены чаще встречающиеся значения.

```

//=============
#if defined _OPENMP
  #define X_OMP_SUPPORT 1
  #define X_OMP_DATE _OPENMP
  #if X_OMP_DATE == 199710
    #define X_OMP_VERSION 100 //1.0
  #elif X_OMP_DATE == 200203
    #define X_OMP_VERSION 200 //2.0
  #elif X_OMP_DATE == 200805
    #define X_OMP_VERSION 300 //3.0
  #elif X_OMP_DATE == 201107
    #define X_OMP_VERSION 310 //3.1
  #elif X_OMP_DATE == 201307
    #define X_OMP_VERSION 400 //4.0
  #endif
#endif

//Или можно применить вывод информации о версии OpenMP

#if defined(_OPENMP)
  fprintf(stderr, "OPENMP VERSION      = %d\n", _OPENMP);
#endif```
