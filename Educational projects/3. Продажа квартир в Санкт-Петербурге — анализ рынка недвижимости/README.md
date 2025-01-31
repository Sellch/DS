# Продажа квартир в Санкт-Петербурге — анализ рынка недвижимости

## Данные

__*Для исследования получен csv-файл `real_estate_data.csv`*__

* airports_nearest — расстояние до ближайшего аэропорта в метрах (м)
* balcony — число балконов
* ceiling_height — высота потолков (м)
* cityCenters_nearest — расстояние до центра города (м)
* days_exposition — сколько дней было размещено объявление (от публикации до снятия)
* first_day_exposition — дата публикации
* floor — этаж
* floors_total — всего этажей в доме
* is_apartment — апартаменты (булев тип)
* kitchen_area — площадь кухни в квадратных метрах (м²)
* last_price — цена на момент снятия с публикации
* living_area — жилая площадь в квадратных метрах (м²)
* locality_name — название населённого пункта
* open_plan — свободная планировка (булев тип)
* parks_around3000 — число парков в радиусе 3 км
* parks_nearest — расстояние до ближайшего парка (м)
* ponds_around3000 — число водоёмов в радиусе 3 км
* ponds_nearest — расстояние до ближайшего водоёма (м)
* rooms — число комнат
* studio — квартира-студия (булев тип)
* total_area — общая площадь квартиры в квадратных метрах (м²)
* total_images — число фотографий квартиры в объявлении

## Задача

__*В нашем распоряжении данные сервиса Яндекс Недвижимость — архив объявлений за несколько лет о продаже квартир в Санкт-Петербурге и соседних населённых пунктах.
Наша задача — найти интересные особенности и зависимости, которые существуют на рынке недвижимости.*__


## Используемые библиотеки
*Pandas*, *Matplotlib*, *Seaborn*

## Итоги исследования
<div style="border:solid orange 2px; padding: 5px">

<div class="alert alert-info"> <b>При проведении исследования (на основе полученных данных) выполнено:</b></div>

- Описание имеющихся параметров
- Оценка времени, затраченного на продажу квартиры:
   - Прослеживаются две моды на значениях 45 и 60 дней, данные временные лимиты установлены `Яндекс.Недвижимость` при публикации объявления бесплатного типа, по истечению которых объявление снимается с публикации.
   - Проанализировав скорость продаж по годам можно прийти к выводам, что происходил рост популярности площадки от года к году, а в 2016 году платформой были установлены новые правила размещения объявлений двух типов – бесплатные и платные. В первом типе объявлений есть лимит на срок размещения, это и оказывает решающее влияние на распределение времени продажи и формирует две обнаруженные моды.
- Рассмотрены факторы больше всего влияющие на общую (полную) стоимость объекта, выделим те, в которых отражены сильные зависимости, либо обнаружены интересные тенденции:
   - Влияние общей площади
   - Количество комнат
   - Тип этажа: заметно предпочтение людей к типу этажа — другой, первый и последний этаж в сравнении с другими не так привлекательны по ряду причин.
   - Месяц публикации объявления: обнаружена значительная просадка в районе июня, что как раз можно связать с некоторым падением активности на рынке недвижимости, вызванным, например летним сезоном отпусков.
   - При анализе среднего значения цены по годам и средней площади получили распределения значений, которые скошены вправо. Было установлено, что это произошло из-за малого количества объявлений, которые были выложены в первые два года (2014-2015). Когда количество объявлений в последующие годы увеличилось, мы получили распределение цен, среднее значений которых стремится к ожидаемому среднему общей генеральной совокупности.
- Посчитана средняя цена одного квадратного метра в 10 населённых пунктах с наибольшим числом объявлений и выделены населённые пункты с самой высокой и низкой стоимостью квадратного метра.
   - Выведен топ-10 населенных пунктов с наибольшим числом объявлений, для каждой позиции которого рассчитана средняя цена одного квадратного метра, выполнена сортировка от наибольшей средней стоимости одного квадратного метра к наименьшей.
   - Населённый пункт с самой высокой стоимостью квадратного метра: Зеленогорск - 115991 рублей.
   - Населённый пункт с самой низкой стоимостью квадратного метра: Совхозный - 12556 рублей.
- Оценена зависимость, как стоимость объектов зависит от расстояния до центра города (анализ проведен для города Санкт-Петербург):
   - Отображена зависимость цены от расстояния до центра города, которая сохраняется вплоть до 26 км. Проанализированы отклонения от обнаруженной зависимости.
