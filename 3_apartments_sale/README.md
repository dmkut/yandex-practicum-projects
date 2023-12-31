﻿# Исследование объявлений о продаже квартир

**Инструменты**

Python, Pandas, Matplotlib, исследовательский анализ данных, визуализация данных, предобработка данных

Данное исследование проводилось с целью построения автоматизированной системы по отслеживанию аномалий и мошеннических действий, а также найти интересные особенности и зависимости. 

**Работа проводилась в несколько этапов, которые включали в себя:**
- Изучение данных;
- Предобработку данных;
- Исследовательский анализ данных.

**Анализ плказал что наибольшее количество пропусков наблюдается в столбцах:**
- is_apartment - 80%;
- parks_nearest - 65%;
- ponds_nearest - 61%;
- balcony - 48%.

Наибольшую обеспокоенность вызывают именно пропуски в информации об апартаментах. Учитывая тот факт, что апартаменты имеют несколько отличный правовой статус, то утаивание информации о том, что это апартаменты, может свидетельствовать о возможных мошеннических действиях, как минимум по продаже апартаментов под видом жилого помещения. Также из-за низкой стоимости апартаметнов, их могут размещать без указания этого статуса для привлечения внимания к объявлению, чаще всего это происходит среди аккаунтов агентств недвижимости. В связи с чем рекомендую сделать эту графу оязательной для заполнения без возможности разместить объявление без этой информации.

Пропущенные показатели в столбцах parks_nearest, ponds_nearest говорят о несовершенстве автоматической системы по определению катрографических данных, однако эти данные можно исключить из исследования, т.к. наличие парка или водоёма не оказывает существенного врияния на стоимость.

Рекомендация: Сделать заполнение всех полей обязательным для пользователя, без возможности разместить оъявление без данных. Также стоит установить ограничить максимальную высоту потолков при вводе во избежание таких значений как 18 или 25 м. Можно поставить лимит на 10 м. Возможно стоит создать базу данных, которая будет содержать в себе тип и параметры дома на основании информации из открытых источников.

**В ходе исследования было выдинуто несколько гипотез:**
1. Наибольшее предложение имеется среди малогабаритных квартир 1-2 комнаты.
2. В данных имеются аномалии, например, всплески на графике количества этажей. Это может быть связано с типовой застройкой зданиями 5 и 9 этажей.
3. Продать чаще всего пытаются квартиры на нижних этажах.
4. Большинство предложений закрываются за первые 250 дней публикации

**Гипотеза 1 - подтверждена.**
В результате построения гистограммы по данным сводной таблицы, на рынке преобладают 1 и 2-комнатные квартиры, с относительно небольшими кухнями. 8004 объявления - однокомнатные, 7897 объявлений - двухкомнатные.
По стоимости наблюдается нормальное распределение Пуассона, наибольшее количество объявлений находится в промежутке от 2,5 до 5 млн. рублей, данная стоимость как раз приходится на диапазон 1 и 2 комнатных квартир.

**Гипотеза 2 - подтверждена.**
Наиболее распространенные типы домов в Ленинградской области 5 и 9-ти этажные здания. Что подтверждается гистограммой.
Тройку лидеров составляют:
- 5	- 5775 объявлений.
- 9	- 3758 объявлений.
- 16- 1375 объявлений.

**Гипотеза 3 - подтверждена частично.**
В Ленинградской области преобладают объвления о продаже квартир в пятиэтажных домах, что отражается на статистики продаж нижних этажей. Также оказалось, что активнее продается не первый этаж, а второй и третий.
По цифрам результат следующий:
- 2-й этаж	- 3351 объявлений.
- 3-й этаж	- 3061 объявлений.
- 1-й этаж	- 2909 объявлений.

**Гипотеза 4 - подтверждена.**
В результате исследования бало выявлено, что среднее значение продажи квартиры составляет 95 дней. 250 находится за пределами третьего квартиля, это говорит на м о том, что в рамках данной площадки 250 дней продажи считается долгим сроком.

Помимо проверки гипотез был составлен топ самых дорогих и бюджетных населенных пунктов в Ленинградской области:

Тройку лидеров составляют:

- СПБ - 104774 за м2;
- Зеленогорск - 101666 за м2;
- Пушкин - 100000 за м2.

Тройка лидеров с конца:

- Деревня Вахнова Кара - 11688 за м2;
- Поселок Свирь - 11481 за м2;
- Деревня Старополье - 11000 за М2;

Также были сделаны промежуточные выводы о влиянии на стоимость жилья таких факторов как площадь кваритры, жилая площадь, площадь кухни, удаленность о центра.

Коэффициент корреляции Пирсона показал:
- больше всего стоимость квартиры зависит от площади - коэфф. 0.65;
- чем ближе к центру тем выше цена, но это не самый влиятельный критерий - коэфф. -0.20;
- жилая площадь взаимосвязана с ценой чуть меньше, чем общая площадь, но тоже весомый фактор - коэфф. 0.55;
- площадь кухни не самый важный показатель при формировании стоимости - коэфф. 0.45

Поэтому, площадь квартиры - приоритетный показатель при формировании стоимости предложения.

Возвращаясь к цели исследования можно утверждать, что для работы алгоритма выявления потнциальных мошеннических схем следует ограничить пользователя в возможности пропускать отдельные графы при заполнении информации об объявлении, а также стоит уделить особое внимание объявлениям значительно отколоняющимся от медианного значения стоимости квадратного метра с учетом удаления недвижимости от центра города.
