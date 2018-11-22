---
title: "Hardmode"
permalink: /hardmode.html
author_profile: true
---

{% include toc title="Содержание" %}

ВНИМАНИЕ!!! Инструкция находится в тестовом режиме!!!
{: .notice--danger}

## Что понадобится
- Прямые руки и умение паять мелкие детали
- Картридер, способный считывать ММС (Transcend p8, Anker…)
- Переходник microSD – SD
- [Win32Diskimager](https://sourceforge.net/projects/win32diskimager/){:target="_blank"}
- [HxD](https://mh-nexus.de/en/downloads.php?product=HxD20){:target="_blank"}
- [Bruteforce.zip](files/Bruteforce.zip)
- [HiyaCFW Helper](https://github.com/mondul/HiyaCFW-Helper/releases){:target="_blank"}
	- Пользователи Windows запускают .exe файл
	- Пользователи других систем запускают .py (необходимо наличие [Python 2](https://www.python.org/downloads/){:target="_blank"})
	- Пользователям Windows дополнительно требуется свежая версия [OSFMount](https://www.osforensics.com/tools/mount-disk-images.html){:target="_blank"}
 


## Часть 1 – Получение NAND
1.	Припаиваем SD переходник по [схеме](images/hm/sd.jpg)
2.	Припаиваемся к плате
	- DSi [сторона А](images/hm/a.jpg), [сторона B](images/hm/b.png)
	- DSi XL [сторона B](images/hm/xl.png)
3.	Вставляем конструкцию в картридер
4.	Включаем консоль
5.	Вставляем картридер в крмпьютер
	 - После идентификации откроется окно с предложением отформатировать устройство. НИ В КОЕМ СЛУЧАЕ НЕ СОГЛАШАЕМСЯ И ЖМЕМ ОТМЕНУ!!!
6.	Запустите Win32DiskImager  и нажмите на иконку с папкой
7.	Выберите куда сохранить нанд, впешите имя "NAND_0.bin", а в расширениях выберите "*.*"
8.	Нажмите Open
9.	В поле Device выберите букву под которой определилась консоль
10.	Нажмите Read
11.	После завершения создайте еще две копии с именами NAND_1.bin, NAND_2.bin
12.	Сравните полученные копии нада в HxD (Analysis > Data comparison > Compare)
13.	Если все три копии идентичны переходите к следующей части.


## Часть 2 – Получение Console ID и eMMC CID

Внимание, похоже что bfCL плохо работает с видеокартами NVIDIA, по возможности используйте компьютер с AMD.

Откройте папку "Bruteforce" из архива bruteforce.zip, и в ней запустите командную строку (Shift + правая кнопка мыши, открыть окно команд).

На всех этапах использовался bfCL, если он не работает, попробуйте использовать TWLbf (намного медленнее).

Список наиболее важных команд:


`bfcL emmc_cid [Console ID] [EMMC CID] [offset] [src] [verify]`

`bfcL console_id [Console ID] [EMMC CID] [offset] [src] [verify]`

`bfcL console_id_bcd [Console ID] [EMMC CID] [offset] [src] [verify]`

`bfcl console_id_bcd [Console ID] [offset0] [src0] [verify0] [offset1] [src1] [verify1]`

### Получение Console ID:
Если вы не знаете и одного из ключей, используйте следующие в качестве шаблона:

`08A2000000000100` for DSi

`08A1900000000000` for some other DSi

`08A1500000000000` for some other DSi

`0820100000000100` for DSi XL

`bfcl console_id_bcd [Console ID] [offset0] [src0] [verify0] [offset1] [src1] [verify1]`


Поскольку у меня DSi XL, я использовал следующее:

[Console ID] – 0820100000000100

[offset0] = 001f 

[src0] = Откройте нанд в HxD. 16 символов в строке 000001F0 
 
[verify0] = 000000000000000000000000000055aa 

[offset1] = 0000 

[src1] = 16 символов в строке 00000000 в самом начале под строкой “Offset (h)”

[verify1] = 0000000000000000000000000000

Получаем и вставляем в командную строку:

В моем случае:

`bfcl console_id_bcd 0820100000000100 001f DB2D16975DACA90176014EB4CCCE87FB 000000000000000000000000000055aa 0000 98C486C82527322A237EDCE90DE43E7E 00000000000000000000000000000000`

Если все сделано верно, получим надпись – got a hit: [ваш полученный Console ID]

Сохраните его в надежном месте.


### Получение eMMC CID: 

Используем в качестве шаблона:

`MY ss ss ss ss 03 4D 30 30 46 50 41 00 00 15 00 `;DSi CID KMAPF0000M-S998

`MY ss ss ss ss 32 57 37 31 36 35 4D 00 01 15 00 `;DSi CID KLM5617EFW-B301


bfcL emmc_cid [Console ID] [EMMC CID] [offset] [src] [verify] 

Необходимо открыть консоль и прочитать 3 цифры на Нанд чипе 

Мои цифры – 943.

943 – значит 2009 год, 43 неделя. 43 неделя в 2009 это декабрь.

43 делим на 4, получаем 10.75, округляем до 11. Переводим в шестнадцатиричную систему, получаем В.(код месяца)

Для кода года смотрим схему:
- B - 2008 
- C - 2009 
- D - 2010 
- E - 2011 
- F - 2012  

- Получаем ВС – используем вместо “MY”. 
- S – заменяем на 0
- Поскольку у меня KMAPF… чип, получаем:

`BC00000000034D303046504100001500`

Подставив все значения получаем, вставляем в командную строку 

В моем случае:

`bfcl emmc_cid 0820154919126126 BC00000000034D303046504100001500 001f DB2D16975DACA90176014EB4CCCE87FB 000000000000000000000000000055aa`

Если все сделано верно, получим надпись – got a hit: [ваш полученный eMMC CID]
Сохраните его в надежном месте.

## Часть 3 – Подпись нанда
1.	Откройте HiyaCFW Helper с правами администратора
2.	Нажмите кнопку ... в поле NAND file with No$GBA footer
3.	Выбирите Ваш бекап NAND и нажмите open
4.	Нажмите на иконку с микрочипом, в окрывшемся окне с предупреждением нажмите ок
5.	Отметьте Add No$GBA footer, впишите ваши Console ID и eMMC CID
6.	Нажмите Start
7.	После появления надписи "Done!Modified NAND stored as хххххххххххххххх-footer.bin"
8. Нажмите Close и закройте программу








































































































