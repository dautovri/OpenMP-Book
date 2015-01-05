#OpenMP


Открытая книга по технологии OpenMP. Технология которая позволяет расспараллеливать программы хирургическим способом не перестраивая архитектуру всего приложения, а расспареллелив только лишь высоконагруженные циклы и тяжелые задачи. Данная книга открыт для новых авторов. Мы не будем закрывать ее написание. Мы не станем требовать плату. Мы будем делать ее вместе.

#### Показания к применению:


**Целевая платформа является многопроцессорной или многоядерной**

*Создавая многопоточное приложение с OpenMP почти наверняка получите прирост производительности.*

**Приложение кроссплатформенное **

*
OpenMP кроссплатформенен с хорошо поддерживаемым API. Приложение скомпилируется если даже компилятор не имеет понятия о OpenMP стандарте. *

**Параллелизация циклов**

*OpenMP одно из лучших средств для распараллеливания циклов. Если приложение имеет циклы без зависимостей, использование OpenMP идеальное решение. *

**Срочная оптимизация**

*Так как OpenMP не требует перестройки архитектуры приложения, его особенность в том, что позволяет инкрементально изменять программу. Вам требуется всего лишь найти наиболее нагруженные участки кода и используя директивы распараллелить 
*