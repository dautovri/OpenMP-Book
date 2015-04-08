# Переменные окружения

| Название | Возможные значения  | По умолчанию* |
| -- | -- | -- |
| OMP_NUM_THREADS   | неотрицательное целое  | 1 или кол-во ядер |
| OMP_SCHEDULE | 1:3 | 2:3 |
| OMP_DYNAMIC | TRUE FALSE | TRUE |
| OMP_NESTED  | TRUE FALSE| FALSE |
| OMP_STACKSIZE | 1:6 | 2:6 |
| OMP_WAIT_POLICY | ACTIVE PASSIVE | PASSIVE |
| OMP_MAX_ACTIVE_LEVELS | неотрицательное целое | 2:6 |
| OMP_THREAD_LIMIT | неотрицательное целое | 1024 |
| OMP_PROC_BIND |  TRUE FALSE | 2:6 |
| OMP_PLACES | 1:7 | 2:7 |
| OMP_CANCELLATION |  TRUE FALSE | 2:6 |
| OMP_DISPLAY_ENV|  TRUE FALSE | 2:7 |
| OMP_DEFAULT_DEVICE| неотрицательное целое | 2:7 |



Значения по умолчанию зависят от реализации.