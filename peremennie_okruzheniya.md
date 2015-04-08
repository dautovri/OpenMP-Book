# Переменные окружения

| Название | Возможные значения  | По умолчанию* |
| -- | -- | -- |
| OMP_NUM_THREADS   | неотрицательное целое  | 1 или кол-во ядер |
| OMP_SCHEDULE | 1:3 | 2:3 |
| OMP_DYNAMIC | TRUE FALSE | 2:4 |
| OMP_NESTED  | TRUE FALSE| 2:5 |
| OMP_STACKSIZE | 1:6 | 2:6 |
| OMP_WAIT_POLICY | 1:7 | 2:7 |
| OMP_MAX_ACTIVE_LEVELS | 1:6 | 2:6 |
| OMP_THREAD_LIMIT | 1:7 | 2:7 |
| OMP_PROC_BIND |  TRUE FALSE | 2:6 |
| OMP_PLACES | 1:7 | 2:7 |
| OMP_CANCELLATION |  TRUE FALSE | 2:6 |
| OMP_DISPLAY_ENV|  TRUE FALSE | 2:7 |
| OMP_DEFAULT_DEVICE| 1:7 | 2:7 |



Значения по умолчанию зависят от реализации.