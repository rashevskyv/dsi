---
title: "Ручная установка HiyaCFW"
permalink: /installing-hiyaCFW-manual.html
author_profile: true
---

{% include toc title="Содержание" %}


У вас уже должен быть установлен [**Unlaunch**](get-started), перед продолжением
{: .notice--warning}

Не обновляйте систему после установки HiyaCFW!!!
{: .notice--danger}

HiyaCFW имеет ряд преимуществ, по сравнению с  просто установленным Unlaunch:
- Загрузка системных файлов с SD карты
- Простая установка хоумбрю в системное меню
- Включение кастомных сплеш-скринов при загрузке
- Автоматическая загрузка в другие приложения, такие как TWiLightMenu++

## Что понадобится
- SD-карта или microSD + переходник. Если объём карты памяти больше чем 2 гб, то нужно будет или устанавливать TWiLightMenu++ вместо системного меню DSi (об этом ниже), или же [размечать карту памяти](https://hetmanrecovery.com/ru/recovery_news/how-to-split-a-usb-flash-drive-or-an-sd-card-using-disk-management-in-windows-10.htm){:target="_blank"} таким образом, чтобы основной раздел на ней был не более 2 гб
- Свежая версия [fuse-3ds](https://github.com/ihaveamac/fuse-3ds/releases){:target="_blank"}
	- Пользователям windows необходимо иметь установленным [WinFsp](http://www.secfs.net/winfsp/download/){:target="_blank"}
- Свежая версия [OSFMount](https://www.osforensics.com/tools/mount-disk-images.html){:target="_blank"}
	- Может быть заменено утилитой **mount** на системах, отличных от Windows
- Свежая версия [HiyaCFW](https://github.com/RocketRobz/hiyaCFW/releases){:target="_blank"}
- [NUSDownloader](files/NUSDownloader.zip)
- Бэкап NAND Вашей приставки, сделанный ранее
- [HiyaCFW Helper](files/hiyacfw_helper.zip)
	- Пользователи Windows запускают .exe файл
	- Пользователи других систем запускают .py (необходимо наличие [Python 3](https://www.python.org/downloads/){:target="_blank"} и [WINE](https://www.winehq.org/){:target="_blank"})

## Подготовка к установке HiyaCFW 
1. Вставьте Вашу ранее подготовленную SD-карту в компьютер.
2. Создайте на компьютере `специальную пустую папку` (например, MyDSiFirmware), в которой будут проходить все дальнейшие действия.
3. Скопируйте содержимое архива `NUSDownloader.zip` в `специальную папку` на Вашем ПК.
4. Скопируйте содержимое архива `HiyaCFW.7z` в `специальную папку` на Вашем ПК.
5. Скопируйте содержимое архива `Hiyacfw_helper.zip` в папку `/Ваша специальная папка/HiyaCFW/for PC`
6. Запустите NUSDownloader
	- На системах, отличных от Windows, это может быть сделано через утилиту [Mono](http://www.mono-project.com/){:target="_blank"}.
7. Отметьте галочкой пункт "Create Decrypted Contents (.app)" и снимите ее с  "Keep Enc. Contents"
8. Нажмите Database > System (DSi) > System Menu (Launcher) > [ Ваш регион ] > v512 > Start NUS Download!
9. После завершения закройте NUS Downloader
10. Перейдите в следующие папки, находящиеся в папке с программой NUS Downloader: titles > 00030017484e41XX > 512.
	- XX зависит от региона приставки: 45 - **USA**, 50 - **EUR**, 4A - **JAP**, 55 - **AUS**
11. Скопируйте `00000002.app` из папки `512` в папку `/ваша специальная папка/HiyaCFW/for PC`
12. Скопируйте Ваш бэкап `NAND (nand.bin)` из папки `FWXXXXXXXXXXXX` Вашей SD-карты в папку `/Ваша специальная папка/HiyaCFW/for PC`
	- XXXXXXXXXXXX это случайные символы, специфичные для каждой консоли
13. В папке `/Ваша специальная папка/HiyaCFW/for PC` запустите hiyacfw_helper.exe
	- Пользователи систем, отличных от Windows, запускают `.py` (необходимо наличие [Python 3](https://www.python.org/downloads/){:target="_blank"} и [WINE](https://www.winehq.org/){:target="_blank"})

	
## Создание SDNAND
1. Запустите на компьютере fuse-3ds 
	- Если вылетает ошибка, обратитесь к [FAQ](faq){:target="_blank"}.
2. В поле "- Choose a type or drag a file/directory here -" выберите Nintendo DSi NAND backup ("nand_dsi.bin")
3. Перетащите `nand.bin` из папки `FWXXXXXXXXXXXX` на SD карте в поле программы "Drag a file here or browse..."
4. Создайте на ПК новую папку для монтирования бэкапа NAND и перетяните эту новую папку на пункт программы "Drag a directory here or browse..."
	- Убедитесь, что тип "Mount type" выставлен на "Directory" на Windows системах.
5. Нажмите кнопку Mount в окне программы.
	- Откроется смонтированная папка
    - Если вылетает ошибка, обратитесь к [FAQ](faq){:target="_blank"}.
6. Запустите на компьютере OSFMount
	- Может быть заменено утилитой **mount** на системах, отличных от Windows
7. В левом нижнем углу программы наджмите "Mount new..."
8. В окне под надписью “Image file” выбираем файл `twl_main.img` в смонтированной ранее программой fuse-3ds папке.
9. Нажмите "ОК"
	- Должен появиться новый смонтированный диск
10. Откройте этот диск
11. Скопируйте все его содержимое в корень Вашей SD-карты
12. В окне программы OSFMount нажмите "Dismount all and Exit", "Yes"
13. В окне программы fuse-3ds нажмите "Unmount" и закройте программу

## Завершение
1. Скопируйте содержимое папки `/Ваша специальная папка/HiyaCFW/for SDNAND SD/`  в корень Вашей SD-карты
	- Согласитесь на замену файлов
2. Откройте папку `/Ваша специальная папка/HiyaCFW/for pc/Modified Files/`
3. Скопируйте файл `bootloader.nds` в папку `Hiya` (Если папки нет, создайте самостоятельно) на SD-карте
4. Скопируйте `00000002.app` в папку `title > 00030017 > 484e41XX > content` на SD-карте
	- XX зависит от региона приставки: 45 - **USA**, 50 - **EUR**, 4A - **JAP**, 55 - **AUS**
5. Извлеките SD-карту и вставьте её в DSi.
6. Включите консоль
	- Если установлен Unlaunch версии **ниже 1.8**, появится экран настроек HiyaCFW
		- Отметьте необходимые вам опции и нажмите ![]({{ "/images/buttons/START.png" | absolute_url }})	
	- Если установлен Unlauch версии **1.8 и выше**, появится экран настроек Unlaunch
		- Выделите `OPTIONS` и нажмите ![]({{ "/images/buttons/A.png" | absolute_url }})
		- Нажмите ![]({{ "/images/buttons/A.png" | absolute_url }}) чтобы настроить приложение для автозагрузки
		- Выделите `HIYACFW` и нажмите ![]({{ "/images/buttons/A.png" | absolute_url }})
		- Выделите `SAVE & EXIT` и нажмите ![]({{ "/images/buttons/A.png" | absolute_url }})
		- Выключите консоль и включите ее снова
		- Появится экран настроек HiyaCFW
		- Отметьте необходимые вам опции и нажмите ![]({{ "/images/buttons/START.png" | absolute_url }})	
	- Если появится экран с надписью  “An error has occured”, скорее всего Ваша SD карта больше чем 2gb. Переходите в раздел ["Замена системного меню на TWiLightMenu++"](replacing-system-menu){:target="_blank"}, ранее указанный вверху страницы 

Теперь система будет грузиться с SD-карты вместо внутренней NAND памяти консоли. Вы можете нажать ![]({{ "/images/buttons/A.png" | absolute_url }}) во время включения, чтобы обойти HiyaCFW и загрузиться с внутренней NAND памяти, используя Unlaunch.


___

[**Завершение установки**](finalizing-setup)
{: .notice--success}
