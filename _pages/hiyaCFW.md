---
title: "Установка HiyaCFW"
permalink: /installing-hiyaCFW.html
author_profile: true
---

{% include toc title="Содержание" %}


У вас уже должен быть установлен [**Unlaunch**](get-started), перед продолжением
{: .notice--warning}

Не обновляйте систему после установки HiyaCFW!!!
{: .notice--danger}

Если TWiLightMenu++ не появится в главном меню, или вылезет экран “An error has occured” после замены системного меню на TWiLightMenu++, видимо, HiyaCFW Helper не правильно применил CFW патчи. Пожалуйста, подождите фиксов этой проблемы. 
{: .notice--warning}

HiyaCFW имеет ряд преимуществ, по сравнению с  просто установленным Unlaunch:
- Загрузка системных файлов с SD-карты
- Простая установка хоумбрю в системное меню
- Включение кастомных сплеш-скринов при загрузке
- Автоматическая загрузка в другие приложения, такие как TWiLightMenu++

## Что понадобится
- **[Опционально, но рекомендуется]** SD-карта на 2 гб или меньше. Карты памяти более 2 гб должны быть [размечены](https://hetmanrecovery.com/ru/recovery_news/how-to-split-a-usb-flash-drive-or-an-sd-card-using-disk-management-in-windows-10.htm){:target="_blank"}  таким образом, чтобы основной раздел на них был не более 2 гб.
	- Если Вы не можете или не хотите этого делать, переходите к разделу ["Замена системного меню на TWiLightMenu++"](replacing-system-menu){:target="_blank"} после завершения данной страницы.
- Бэкап NAND Вашей приставки, сделанный ранее
- [HiyaCFW Helper](https://github.com/mondul/HiyaCFW-Helper/releases){:target="_blank"}
	- Пользователи Windows запускают .exe файл
	- Пользователи других систем запускают .py (необходимо наличие [Python 2](https://www.python.org/downloads/){:target="_blank"})
	- Пользователям Windows дополнительно требуется свежая версия [OSFMount](https://www.osforensics.com/tools/mount-disk-images.html){:target="_blank"}

	
## Инструкция
1. Вставьте Вашу SD-карту в компьютер
2. Извлеите содержимое архива `HiyaCFW Helper.zip` в любую папку на Вашем компьютере
3. Перейдите к этой папке
4. Откройте HiyaCFW Helper с правами администратора
	- Пользователям Windows - правая кнпка мыши > ![]({{ "/images/uac.png" | absolute_url }}) запуск от имени администратора
5. Нажмите кнопку `...` в поле `NAND file with No$GBA footer`
6. Выбирите Ваш бекап NAND и нажмите `open`
7. **[Опционально]** Если хотите установить TWiLightMenu++ вместо системного меню DSi, отметьте галочкой `Install latest TWiLight Menu++ on latest firmware`
8. Нажмите `Start`
	- Процесс займет некоторое время
	- Когда появится надпись `Done!`, процесс будет завершен
9. Закройте HiyaCFW Helper
10. Скопируйте содержимое папки `out` из папки `HiyaCFW Helper` в корень Вашей SD-карты
11. Извлеките Вашу SD-карту и вставьте ее в DSi
12. Включите Вашу консоль
	- Появится экран настроек HiyaCFW
13. Отметьте необходимые вам опции и нажмите ![]({{ "/images/buttons/START.png" | absolute_url }})	
	- Если появится экран с надписью  “An error has occured”, скорее всего Ваша SD карта больше чем 2gb. Переходите в раздел ["Замена системного меню на TWiLightMenu++"](replacing-system-menu){:target="_blank"}, чтобы обойти это ограничение

Теперь система будет грузиться с SD-карты вместо внутренней NAND памяти консоли. Вы можете нажать ![]({{ "/images/buttons/A.png" | absolute_url }}) во время включения, чтобы обойти HiyaCFW и загрузиться с внутренней NAND памяти, используя Unlaunch.

___

[**Завершение установки**](finalizing-setup)
{: .notice--success}
