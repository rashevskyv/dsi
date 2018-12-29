---
title: "Установка DSiWare приложений"
permalink: /installing-dsiware.html
author_profile: true
---

{% include toc title="Содержание" %}

У вас уже должны быть установлены [**Unlaunch**](get-started) и [**HiyaCFW**](installing-HiyaCFW)
{: .notice--warning}


Этот метод установит Ваши дампы 3DS DSiWare в главное меню DSi. Это преобразует 3DS DSiWare дампы в устанавливаемый формат с помощью инструмента "maketmd".


## Что понадобится
- Свежая версия [maketmd](https://github.com/Tuxality/maketmd/releases){:target="_blank"}

## Инструкция
1. Скопируйте содержимое архива `maketmd.zip` в папку на Вашем компьютере
2. Откройте папку с дампом dsiware
3. Перейдите в папку `content`
4. Удалите папку `cmd` и файл `.tmd`
5. Удилите фапйлы `.ctx` если присутствуют
6. Перетащите файл `.app` на программу maketmd
- создастся новый файл - `title.tmd`
7. Скопируйте папку с дампом в папку `/title/00030004` SD-карты Вашей DSi
- Если системное меню было заменено на TWiLightMenu++, нужно будет перезапустить `launcharggen` и поместить новые файлы `launcharg` в `roms/dsiware` еще раз
8. Включите Вашу DSi и "распакуйте" новое приложение
- если консоль загрузится в экран “error has occured”, значит вы привысили лимит установленных dsiware приложений
- TWiLightMenu++ может обойти этот лимит, прочтите [Замена системного меню на TWiLightMenu++](replacing-system-menu).

При дампинге некоторых игр в папке `content` будут находиться два `.app` файла. Удалите тот, который весит несколько байт, а оставшемуся измените название на `00000000.app` и следуйте инструкции. 
{: .notice--info}

Через TWiLightMenu++ можно запускать любое DSiWare приложение, сконвертированное в формат `.nds`, просто закинув его в папку с ромами, как и любую ds игру.
[Ссылка](https://mega.nz/#F!wEolnIII!sYQ3arxil3D0Hc6gGSbkzA){:target="_blank"} на сборник уже готовых к использованию ромов.
{: .notice--success}












































