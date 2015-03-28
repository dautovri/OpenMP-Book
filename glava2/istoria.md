# История OpenMP




В конце 80-x была создана группа Parallel Computing Forum (PCF). Основной задачей которой было согласовать ряд директив для распараллеливания циклов в языке программирования Fortran, уже 1991 году работа данной группы была опубликована. Официальный подкомитет Американского национального института стандартов(ANSI) называемый X3H5 был создан для разработки официального стандарта на базе документа PCF. 
 
Однако, представленный в 1994 году стандарт не был принят. Неудача была временная, во второй половине 90-x усилия по созданию стандарта объединили ведущие производители SMP вычислительной техники. Группа продолжила работу, но уже с более ранней работы PCF. 

В 28 октября 1997 года был разработан окончательно индустриальный стандарт: OpenMP (Open Multi Processing) . Его сразу же поддержали все ведущие производители  Intel, HP, IBM, SUN, Copmpaq и другие. 

О выходе нового стандарта тогда написали в New York Times.

```
НОВЫЙ СТАНДАРТ ДЛЯ ПАРАЛЕЛЬНЫХ ВЫЧИСЛЕНИЙ 

Compaq, Digital, Intel, IBM и Silicon Graphics договорились о поддержке
стандарта OpenMP, новый стандарт, разработанный Silicon Graphics и
Kuck & Associates.Он позволяет программистам писать одну версию
программного обеспечения, котороя будет работать на параллельных
вычислительных комплексах с использованием операционных систем Unix
или Windows NT. Новый стандарт ускорит тенденцию, при которой ученые и
инженеры будут выбирать рабочие станций, а не суперкомпьютеры для сложных
вычислительных приложений. (28 Окт. 1997)
```



###Разработчики
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

Стандарт по-прежнему развивается, обрастая новыми конструкциями и возможностями. Выпуски новых стандартов для С/С++ и Фортран происходили раздельно, а с 2005 года стандарты выпускаются совместно.