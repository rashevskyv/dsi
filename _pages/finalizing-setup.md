---
title: "Завершение установки"
permalink: /finalizing-setup.html
author_profile: true
---

{% include toc title="Содержание" %}


Если в разделе с установкой HiyaCFW был выделен пункт `Install latest TWiLight Menu++ on custom firmware`, то TWiLightMenu++ уже установлен и настроен на автозапуск. Переходите к разделу **Использование**.
{: .notice--info}

Сейчас мы установим TWiLightMenu++, приложение, позволяющее запускать программы и игры с карты памяти и имеющее несколько встроенных эмуляторов.

## Что понадобится
- Свежая версия [TWiLightMenu++](https://github.com/RocketRobz/TWiLightMenu/releases){:target="_blank"}

## Инструкции
1. Вставьте Вашу SD-карту в компьютер
2. Скопируйте содержимое папки `CFW - SDNAND root` из архива `TWiLightMenu.7z` в корень Вашей SD-карты
3. Скопируйте папки `_nds` и `roms` из архива `TWiLightMenu.7z` в корень Вашей SD-карты.
4. Извлеките SD-карту из компьютера и вставьте её в DSi.
5. Включите консоль
	- TWiLightMenu++ должно появиться в списке DSiWare приложений в главном меню, рядом с другими.

## Использование
1. Скопируйте ромы в соответствующие им папки:
	- Game Boy и Game Boy Color ромы поместите в папку `/roms/gb`
    - Nintendo DS ромы поместите в папку `/roms/nds`
    - NES ромы поместите в папку `/roms/nes`
    - Для Game Boy Advance ромов создайте в папке `roms` папку `GBA` и поместите ромы в нее
		- Для запуска GBA ромов нужен биос от GBA, помещенный в корень SD-карты под именем `"bios.bin"` (ищите в интернете сами).
2. Запустите TWiLightMenu++ из домашнего меню
3. Появится главное меню TWiLightMenu++
	- Нажмите на иконку ![]({{ "/images/buttons/rg.png" | absolute_url }}) чтобы открыть список игр 
		- Нажмите ![]({{ "/images/buttons/A.png" | absolute_url }}) чтобы запустить игры
		- Нажмите на иконку ![]({{ "/images/buttons/gba_icon.png" | absolute_url }}) чтобы запустить GBA игры через GBARunner2     
		- Нажмите на иконку ![]({{ "/images/buttons/home_icon.png" | absolute_url }}) чтобы вернуться к меню DSi
4. **[Опционально]** TWiLightMenu++ может полностью заменить системное меню. Это поможет избежать некоторых багов, связанных с размером SD карты и лимитом на количество DSiWare приложений. 
	- [Замена системного меню на TWiLightMenu++](replacing-system-menu)

____

[**Полезные инструкции**](addons)
{: .notice--success}