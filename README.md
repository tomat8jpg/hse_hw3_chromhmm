# hse_hw3_chromhmm
Коллаб - https://colab.research.google.com/drive/1ZB94LUqHySARJtR8hPoRcP8SENkIYm2b?usp=sharing  
Клеточная линия - H1 (H1-hESC)  
| Линия | Метка | Файл с меткой | Файл с контролем |
| ---- | ------- | ------------ | --------------- | 
| H1 | Ctcf | Ctcf.bam | Control.bam |
| H1 | H3k09me3 | H3k09me3.bam | Control.bam |
| H1 | H3k4me1 | H3k4me1.bam | Control.bam |
| H1 | H3k9ac | H3k9ac.bam | Control.bam |
| H1 | H3k27ac | H3k27ac.bam | Control.bam |
| H1 | H4k20me1 | H4k20me1.bam | Control.bam |
| H1 | H3k79me2 | H3k79me2.bam | Control.bam |
| H1 | H3k36me3 | H3k36me3.bam | Control.bam |
| H1 | H3k27me3 | H3k27me3.bam | Control.bam |
| H1 | H3k4me3 | H3k4me3.bam | Control.bam |   
# ChromHMM  
transition  
![transitions_10](https://user-images.githubusercontent.com/60805733/160275060-d892eafa-2198-4ad3-a443-f5eb5c92e407.png)  
emmission  
![emissions_10](https://user-images.githubusercontent.com/60805733/160275064-4646f49d-8ec0-44b0-ac83-7f816b87038c.png)  
overlap  
![H1_10_overlap](https://user-images.githubusercontent.com/60805733/160275068-fbc8f342-5f46-48e2-beab-56ecf82d2373.png)  
RefSeqTSS  
![H1_10_RefSeqTSS_neighborhood](https://user-images.githubusercontent.com/60805733/160275074-9669ab24-8d49-4528-bf99-c7eb232a81f3.png)  
RefSeqTES  
![H1_10_RefSeqTES_neighborhood](https://user-images.githubusercontent.com/60805733/160275089-7ddded3d-0d95-4aa2-91df-9872e32ff9f5.png)  

# Эпигенетические состояния
# Сводная таблица по регионам.
| Номер | Название | Метки |
| --- | -------- | ------------------- |
| 1 | Неактивный промотор | H3K27me3 |
| 2 | Слабый промотор | H3K4me3, H3K9ac |
| 3 | Активный промотор | H3K4me3, H3K9ac |
| 4 | Слабый промотор | H3K79me2, H3K4me3 |
| 5 | Сигнал перехода к элонгации | H3K79me2 |
| 6 | Активная элонгация | H3K36me3 |
| 7 | Инсулятор | CTCF | 
| 8 | Энхансер | H3K4me1 |
| 9 | Слабая элонгация | ..... |
| 10 | Слабый энхансер в гетерохроматине | H3K9me3 |  

## Можно сделать вывод, что эпигенетическое состояние хроматина определяется целым набором модификаций гистонов

# Далее прикреплены скрины и рассуждения по каждому эпигенетическому состоянию
# №1. Состояние 1   
Чаще всего пересекается с аннотацией  неактивного промотора (3). Также по аннотациям можно заметить, что сегменты №1 часто встречаются в репрессированных генах, находящихся в гетерохроматине (DMRT1, DMRT2, DMRT3) в данной клеточной линии   
![image](https://user-images.githubusercontent.com/60805733/160276724-d6629abb-dd81-4e8a-8317-8dcde7384bb4.png)  
Пики "состояния 1" наблюдаются при анализе меток H3K27me3, слабее - CTCF, H3K4me3  
![image](https://user-images.githubusercontent.com/60805733/160276854-b44f528c-1709-4755-9d7a-8b449a6bb3e8.png)  
# №2. Состояние 2  
Пересекается с аннотацией активного(1) и слабого промотора(2) (чаще - слабого). Сегменты номер 2 встречаются перед стабильно экспрессирующимися (JAK2, CD274) в данной линии генами (многие гены могут находиться под совместной регуляцией нескольких промоторов для активации за счет различных транскрипционных факторов - это важно. т.к. сигнальные каскады в клетке часто пересекаются)
![image](https://user-images.githubusercontent.com/60805733/160277138-e942cc92-9aa5-4530-9e37-a3dfe4b153a9.png)
Пики "состояния 2" наблюдаются при анализе меток H3K4me3, H3K9ac, cлабее - CTCF, H3K27ac, H3K4me1. Это логично, ведь ацетилирование (ac) скорее приводит к расплетанию хроматина и активации транскрипции.  
![image](https://user-images.githubusercontent.com/60805733/160277471-f3d41539-f788-440f-a2e1-ef0a48b24a8d.png)  
# №3. Состояние 3 
Полностью соответствует состоянию активного промотора (1). Находится перед конститутивно экспрессирующимися генами (UHFR2, RANBP6)  
![image](https://user-images.githubusercontent.com/60805733/160277640-47f03164-ab38-466f-a432-cf23e3bd7b16.png)
Пики "состояния 3" наблюдаются при анализе меток H3K4me3, H3K9ac, H3K27ac. Согласуется с биологической функцией модификаций. Отсутствие модификаций CTCF - инсуляторного фактора, также подтверждает догадку о соответствии активному промотору.
![image](https://user-images.githubusercontent.com/60805733/160277724-ebca6a18-3580-41d4-843a-2ab29df78d69.png)  
# №4. Состояние 4 
Чаще всего соответствует только какой-то части слабого промотора(2).   
![image](https://user-images.githubusercontent.com/60805733/160278027-bee017de-111c-4d47-85d4-10927588fcab.png)  
Пики "состояния 4" наблюдаются при анализе меток H3K79me2, H3K4me3, H3K4me1(слабые пики), для метки H3K9ac - также есть пики, однако они не специфичны для данного региона
![image](https://user-images.githubusercontent.com/60805733/160278225-53df50fd-6f7a-47e3-a364-1ea49d5450a0.png)  
# №5. Состояние 5 
Наблюдается очень редко, соответствует аннотациям Txn_transition (9). Судя по статьям и положению в начале рамки считывания после промотора данный регион отвечает за инициацию транскрипции и переход к трансляции. Вероятно такой регион располагается в генах домашнего хозяйства, обеспечивающих базовые функции жизни клетки (на скрине - ген CAMSAP1, который регулирует сборку микротрубочек, для стволовых, постоянно лелящихся клеток линии H1-hESC перестройка микротрубочек является одним из ключевых процессов)  
![image](https://user-images.githubusercontent.com/60805733/160279008-27ba1646-89dd-48de-96e0-1daa7814a0fc.png)  
Пик наблююдается для метки H3K79me2  
![image](https://user-images.githubusercontent.com/60805733/160279040-0397064b-1d41-4148-af31-5c2e0cac38b4.png)  
# №6. Состояние 6   
Соответствует аннотации областей элонгации (10). Видимо такое состояние модификаций характерно для активно экспрессирующихся генов, т.к. рассмотренный ген CD46 является одним ои основных маркеров линии эмбриональных стволовых клеток человека, это подтверждается высокой плотность РНК-секвенирования в области данного гена.   
![image](https://user-images.githubusercontent.com/60805733/160279435-2a7bde56-28a2-4ee4-9030-7027ffca988c.png)  
Небольшой пик наблююдается для метки H3K36me3, менее специфично, но тоже выражена метка H3K79me2, слабо - H4K20me1  
![image](https://user-images.githubusercontent.com/60805733/160279461-b51feb74-8158-4cbb-9bd3-00238939fbaf.png)  
# №7. Состояние 7  
Соответствует инсуляторным областям (8) в гетерохроматине. Экспрессия с данного региона низкая. 
![image](https://user-images.githubusercontent.com/60805733/160279724-02d80f9d-70c0-42b5-93dd-52b46e1af627.png)  
Как и ожидалось, данное состояние соответствует сильным пикам только CTCF - основной ремоделирующий хроматин агент, обладающий инсуляторной и репрессирующей активностью.  
![image](https://user-images.githubusercontent.com/60805733/160279780-3a62ad50-1271-403e-a254-a913519bf7ae.png)  
# №8. Состояние 8 
Соответствует энхансерной области (7/6). Слабые промоторы могут быть окружены несколькими энхансерами для большего контроля экспрессии.  
![image](https://user-images.githubusercontent.com/60805733/160280106-b3af1345-8bac-4f97-b540-0029e45e5362.png)  
Соответствует пикам меток H3K4me1, слабо - H3K9ac, H3K27ac
![image](https://user-images.githubusercontent.com/60805733/160280152-44532cb1-401b-4dc6-be01-444f08e1a55d.png)  
# №9. Состояние 9 
Наиболее стандартное состояние слабо-средне экспрессирующихся генов (10 - области элонгации, 11 - слабая транскрипция), которые могут находиться в гетерохроматине. 
![image](https://user-images.githubusercontent.com/60805733/160280269-289b2cce-4cfe-486e-9b2d-39a17c7fbe87.png)  
Соответствует отсутствию или незначительному уровню рассматриваемых меток (возможно это состояние определяется другими модификациями, которые я не рассматривала)
![image](https://user-images.githubusercontent.com/60805733/160280309-21fd234d-207d-4108-96c7-63a2dfcfefb6.png)  
# №10. Состояние 10  
Вероятно, соответствует слабым энхансерам или другим структурам молчащих регионов геторохроматина. Ассоциирован с ламиной, поэтому репрессирован.  
![image](https://user-images.githubusercontent.com/60805733/160281159-3e7368ad-dd42-4c25-8577-c7c976a95bf5.png)
Слабо определяется меткой H3K9me3  
![image](https://user-images.githubusercontent.com/60805733/160281192-5dba182a-e5da-4051-bbce-438fb4cc8ff2.png)

# Использованные команды 
```python
!curl -O https://raw.githubusercontent.com/deepjavalibrary/d2l-java/master/tools/fix-colab-gpu.sh && bash fix-colab-gpu.sh  
!curl -O https://raw.githubusercontent.com/deepjavalibrary/d2l-java/master/tools/colab_build.sh && bash colab_build.sh  
!java --list-modules | grep "jdk.jshell"  
! wget http://compbio.mit.edu/ChromHMM/ChromHMM.zip  
!unzip /content/ChromHMM.zip  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescControlStdAlnRep1.bam -O Control.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescCtcfStdAlnRep1.bam -O Ctcf.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH3k09me3StdAlnRep1.bam -O H3k09me.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH3k4me1StdAlnRep1.bam -O H3k4me1.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH3k9acStdAlnRep1.bam -O H3k9ac.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH3k27acStdAlnRep1.bam -O H3k27ac.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH4k20me1StdAlnRep1.bam -O H4k20me1.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH3k79me2StdAlnRep1.bam -O H3k79me2.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH3k36me3StdAlnRep1.bam -O H3k36me3.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH3k27me3StdAlnRep1.bam -O H3k27me3.bam  
! wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneH1hescH3k4me3StdAlnRep1.bam -O H3k4me3.bam  
!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar BinarizeBam -b 200  /content/ChromHMM/CHROMSIZES/hg19.txt /content/ cellmarkfiletable.txt   binarizedData  
!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar LearnModel -b 200 /content/binarizedData/ /content/output/ 10 hg19  
from google.colab import drive  
drive.mount('/content/gdrive')  
!mv /content/output /content/gdrive/MyDrive/HW3  
from google.colab import drive  
drive.mount('/content/gdrive')  
```
