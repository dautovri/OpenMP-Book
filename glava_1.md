# Глава 1

OpenMP дает возможность создавать параллельные приложения для систем с общей памятью. В данной главе мы рассмотрим какие изменения послужили причиной создания OpenMP и почему он столь популярен для высокопроизводительных вычислений. 

### Немного истории
 ![](http://habrastorage.org/files/84e/7e8/f1c/84e7e8f1c9a84ba0a2c6132ddc01722b.png)

В конце 80-x была создана группа Parallel Computing Forum (PCF). Основной задачей которой было согласовать ряд директив для распараллеливания циклов в языке программирования Fortran, уже 1991 году работа данной группы была опубликована. Официальный подкомитет Американского национального института стандартов(ANSI) называемый X3H5 был создан для разработки официального стандарта на базе документа PCF. 


Разработку спецификации ведут несколько крупных производителей вычислительной техники и программного обеспечения. Эта работа регулируется некоммерческой организацией, называемой OpenMP Architecture Review Board (ARB). 
Членами комитета по новым стандартом являются:

Постоянные члены ARB
* AMD (Greg Stoner)
* Convey Computer (Kirby Collins)
* Cray (James Beyer/Luiz DeRose)
* Fujitsu (Eiji Yamanaka)
* HP (Sujoy Saraswati)
* IBM (Kelvin Li)
* Intel (Xinmin Tian)
* NEC (Kazuhiro Kusano)
* NVIDIA (Jeff Larkin)
* Oracle Corporation (Nawal Copty)
* Red Hat (Matt Newsome)
* ST Microelectronics (Christian Bertin)
* Texas Instruments (Andy Fritsch)

Вспомогательные члены ARB


* ANL (Kalyan Kumaran)
* ASC/LLNL (Bronis R. de Supinski)
* BSC (Xavier Martorell)
* cOMPunity (Barbara Chapman/Yonghong Yan)
* EPCC (Mark Bull)
* LANL (David Montoya)
* NASA (Henry Jin)
* ORNL (Oscar Hernandez)
* RWTH Aachen University (Dieter an Mey)
* SNL-Sandia National Lab (Stephen Olivier)
* Texas Advanced Computing Center (Kent Milfeld)
* University of Houston (Barbara Chapman/Deepak Eachempati)

Стандарт по-прежнему развивается, обрастая новыми конструкциями и возможностями. Изначально выпуски новых стандартов для языков С/С++ и Фортран происходили раздельно, но с 2005 года стандарты выпускаются совместно.
### OpenMP - что это и как готовить?


OpenMP (Open Multi-Processing) — открытый стандарт для распараллеливания программ на языках Си, Си++ и Фортран. Описывает совокупность директив компилятора, библиотечных процедур и переменных окружения, которые предназначены для программирования многопоточных приложений на многопроцессорных системах с общей памятью.

OpenMP реализует параллельные вычисления с помощью многопоточности, в которой «главный» (master) поток создает набор подчиненных (slave) потоков, и задача распределяется между ними. Предполагается, что потоки выполняются параллельно на машине с несколькими процессорами (количество процессоров не обязательно должно быть больше или равно количеству потоков).
