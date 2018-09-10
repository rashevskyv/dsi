---
title: "Дампинг DSiWare приложений"
permalink: /dumping-dsiware.html
author_profile: true
---

{% include toc title="Содержание" %}


Это руководство требует наличия взломанной 3ds с установленными Luma3ds, GodMode и FBI. Следуйте [3ds.customfw.xyz](https://3ds.customfw.xyz){:target="_blank"} для взлома Вашей 3DS.
{: .notice--warning}


Это позволит создать дамп DSiWare для использования на DSi. Это возможно путем установки DSiWare на 3DS с последущим дампингом.


## Нахождение TittleID DSiWare
1. Запустите `FBI` на Вашей 3DS
2. Выделите `Tittles` и нажмите ![]({{ "/images/buttons/A.png" | absolute_url }})
3. Нажмите ![]({{ "/images/buttons/SELECT.png" | absolute_url }}) и кнопкой ![]({{ "/images/buttons/A.png" | absolute_url }}) выделите пункты “Show game card” и “Show SD”
4. Нажмите ![]({{ "/buttons/B.png" | absolute_url }}) и дождитесь построения списка
5. Пролистайте список до нужного Вам DSiWare приложения
6. Запишите Title ID приложения с верхнего экрана консоли
7. Выключите 3ds

## Дампинг DSiWare
1. Включите 3DS с зажатой кнопкой ![]({{ "/images/buttons/START.png" | absolute_url }}) для запуска меню chainloader.
2. Выделите `GodMode9`  и нажмите ![]({{ "/images/buttons/A.png" | absolute_url }})
3. Перейдите в `[2:] SYSNAND TWLN/title/00030004`
4. Найдите нужное Вам приложение по последним 8 знакам Title ID и остановитесь на нём
5. Нажмите ![]({{ "/buttons/R.png" | absolute_url }}) + ![]({{ "/images/buttons/A.png" | absolute_url }})
6. Выберите “Copy to 0:/gm9/out”
7. Нажмите ![]({{ "/buttons/A.png" | absolute_url }}) по окончании копирования
8. Выключите консоль

Дамп Вашего приложения будет на SD-карте приставки в папке gm9/out. Скопируйте его на Ваш компьютер.

___

[**Установка DSiWare приложений**](installing-dsiware)
{: .notice--success}
