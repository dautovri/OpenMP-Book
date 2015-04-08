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



Значения по умолчанию зависят от реализации.