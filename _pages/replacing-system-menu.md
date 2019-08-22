---
title: "Замена системного меню"
permalink: /replacing-system-menu.html
author_profile: true
---

{% include toc title="Содержание" %}

У вас уже должны быть установлены [**Unlaunch**](get-started) и [**HiyaCFW**](installing-hiyaCFW)
{: .notice--warning}

Произойдет замена системного меню на приложение TWiLightMenu++, которое будет запускаться автоматически при включении консоли.

Замена системного меню на TWiLightMenu++ даст ряд преимуществ:
- TWiLightMenu++ позволит иметь большее количество DSiWare приложений
- TWiLightMenu++ , в большинстве случаев, позволяет использовать sd карту больше 2гб
	- Вы можете просто перенести содержимое Вашей старой SDNAND карты на бОльшую и все будет работать
- TWiLightMenu++ предоставляет унифицированный интерфейс для запуска NES, GB/GBC, DS и DSiWare тайтлов

Таким образом, TWiLightMenu++ выступает в качестве эффективной альтернативы системному меню с открытым исходным кодом.

## Что понадобится
- Свежая версия [TWiLightMenu++](https://github.com/RocketRobz/TWiLightMenu/releases){:target="_blank"}
- [launcharggen](files/manual/launcharggen.zip)
	- Пользователи Windows запускают `.exe` файл
	- Пользователи других систем запускают `.py` (необходимо наличие [Python 2 или 3](https://www.python.org/downloads/){:target="_blank"})

## Подготовка
Если у вас уже установлено TWiLightMenu++ , переходите к пункту 4
{: .notice--info}

1. Распакуйте архив `TWiLightMenu.7z`
2. Скопируйте содержимое папки `CFW - SDNAND root` в корень SD-карты
3. Скопируйте папки `_nds`, `roms` и файл `BOOT.NDS` в корень SD-карты
4. Скопируйте содержимое папки `DSiWare (your region)` в `roms/dsiware` на Вашей SD-карте
5. Скопируйте файл `autoboot.bin` из папки `Autoboot for HiyaCFW` в папку `hiya` на Вашей SD-карте
6. Откройте папку `shared1` на SD-карте
7. Задайте файлам `TWLCFG0.dat` и `TWLCFG1.dat` атрибут "Только чтение"
	- На Windows - правый клик мышки > свойства
	- Это позволит обойти баг, способный сломать SDNAND
	- Если вы захотите изменить системные настройки, нужно будет временно снять этот аттрибут
8. Перейдите в папку `title/00030004` на SD-карте
9. Скопитуйте содержимое архива `launcharggen.zip` в папку `title/00030004` на SD-карте
10. запустите launcharggen
	- создастся папка `dsiware`
	- в ней содержаться файлы, указывающие DSIMenu++ расположение dsiware приложений.
11. Переместите эту папку `dsiware` в папку `roms` на SD-карте
	- при запросе, объедините папки
12. Извлеките SD-карту из компьютера и вставьте её в DSi

## Инструкции
1. Включите консоль, зажав ![]({{ "/images/buttons/SELECT.png" | absolute_url }})
2. Если пункт `Autoboot title` не отмечен, отметьте его нажатием ![]({{ "/images/buttons/A.png" | absolute_url }})
3. Нажмите start для сохранения настроек и продолжения загрузки
	- Появится TWiLightMenu++ 

TWiLightMenu++ теперь будет Вашим системным меню. Перейдите в roms > dsiware для доступа к DSiWare приложениям.

____

[**Полезные инструкции**](addons)
{: .notice--success}

