# Исследование рынка видеоигр

## Данные

__*Для исследования получен csv-файл `games.csv`*__

* Name — название игры
* Platform — платформа
* Year_of_Release — год выпуска
* Genre — жанр игры
* NA_sales — продажи в Северной Америке (миллионы проданных копий)
* EU_sales — продажи в Европе (миллионы проданных копий)
* JP_sales — продажи в Японии (миллионы проданных копий)
* Other_sales — продажи в других странах (миллионы проданных копий)
* Critic_Score — оценка критиков (максимум 100)
* User_Score — оценка пользователей (максимум 10)
* Rating — рейтинг от организации ESRB (англ. Entertainment Software Rating Board). Эта ассоциация определяет рейтинг компьютерных игр и присваивает им подходящую возрастную категорию.

## Задача

Выявить определяющие успешность игры закономерности. Это позволит сделать ставку на потенциально популярный продукт и спланировать рекламные кампании.


## Используемые библиотеки
*Pandas*, *Plotly.Express*, *NumPy*, *SciPy*, *matplotlib.pyplot*, *Math*

## Итоги исследования
<div style="border:solid orange 2px; padding: 5px">

<div class="alert alert-info"> <b>При проведении исследования (на основе полученных данных) выполнено:</b></div>


- Проанализировано сколько игр выпускалось в разные годы.
  - Обнаружена тенденция к росту количества вышедших игр, начиная с 1991 года вплоть до 2008 года, где тренд сменился на противоположный – нисходящий, сформулированы предположения возникновения этих тенденций.
  - Выбран период для более детального рассмотрения.


- Произведена оценка изменения продаж по платформам:
  - Выделены TOP-10 платформ за все время по объему проданных копий игр.
  - Построен график и произведена оценка распределения продаж по годам для топ 6 платформ за все время по количеству продаж.
    - Для данных платформ среднее время жизни платформы (актуальность) составляет 11 лет.
  - Обнаружено среднее время жизни платформы за все время, которое составляет 7 лет.
  - Рассчитано и графически отображено время жизни для каждой из платформ.


- Произведен поиск актуального периода, необходимого для точной оценки текущих трендов на игровом рынке:
  - Приняв во внимание то, что тренд на количество вышедших игр за год изменился на нисходящий, данные первично были рассмотрены с 2010 года, за период в 6 лет, что практически совпадает со средним показателем жизни платформ за все время.
  - Проанализировав жизненные циклы платформ с 2010 года мы отметили появление нового поколения консолей от двух мастодонтов игрового рынка - Sony и Microsoft. Отмечаем выход их платформ в один год - 2013. Игровые разработчики предполагают примерное время выхода консолей нового поколения, но точные даты знают, вероятнее всего, только партнеры. Поэтому 2014 год, как раз тот год, когда начинается массовый выпуск новых релизов игр на PS4 и XOne. Для того, чтобы отразить более актуальные тренды, которые происходят на стремительно меняющемся игровом рынке выбрали временной интервал с 2014 по последнюю имеющуюся у нас дату, так мы учтли и начало новой эры игровых консолей двух влиятельных фигур этого рынка и у нас получилось образить наиболее актуальные тренды.


* Построены Box-plot распределения по глобальным продажам игр в разбивке по платформам, из которых сделаны следующие выводы:
  - Для лидера рынка (PS4) по прибыли большую часть дохода формируют тайтлы, которые являются ничем иным, как выбросами по отношению к основному распределению доходов со всех остальных игр.
  - У XOne очень схожая ситуация и по основному распределению 99% значений они практически идентичны по выручке, но за счет больших значений продаж популярных серий Sony вырывает лидерство.
  - У 3DS можно отметить плачевную ситуацию, где еще больший процент дохода формируют известные игры-серии.
  - Удивительные результаты показывает платформа Wii (2006 г. выпуска), обходя более новые платформы от Nintendo (WiiU – 2012 г. и 3DS – 2011 г.), но и современные платформы от Sony и Microsoft по 99% диапазону. Такое распределение возникло из-за малого количества игр, которые были реализованы на `Wii`.


* Оценено влияние на продажи внутри одной популярной платформы и на продажи внутри остальных платформ отзывов пользователей и критиков:
  - Описание значений корреляции с отзывами пользователей:
    - для платформы Wii существует всего два значения, на основе которых и высчитывается данное значение корреляции, поэтому получается такое значение.
    - отмечена слабая корреляция для платформы WiiU c показателем 0.4.
    - очень слабая корреляция для платформы 3DS 0.21.
  - Описание значений корреляции с отзывами критиков:
    - Отмечена слабая положительная корреляция с отзывами критиков для платформы PS4.
    - самый сильный коэффициент корреляции равный 0.52 и соответствующий средней корреляции характерен для платформы X360.
    - по остальным платформам отображена слабая корреляция в диапазоне 0.3 - 0.5 или очень слабая в диапазоне от 0 до 0.3.


- Проанализировано распределение игр по жанрам за актуальный период.


- Посчитан общий доход с каждого жанра за актуальный период.


- Посчитано распределение жанров для каждой из платформ с учетом дохода с каждого жанра за актуальный период.
  * Топ - 1 по количеству вышедших игр этого жанра  - Action, но данный жанр даже не присутствует в списке топ-5 жанров по показателю общего медианного дохода. Показатель того, что рынок перегрет играми такого жанра.
  * Наилучшие результаты показывают два жанра - shooter и sports, где прослеживается отличная полученная прибыль в расчете на одну выпущенную игру, особенно жанр shooter с медианным показателем прибыли 0.515 млн. на одну игру. Может служить хорошей рекомендацией, к выбору потенциального жанра для игры, но для более точной оценки желательно провести анализ с учетом платформ и региона.


- Составлен портрет пользователя для каждого региона:
  - Обозначены самые популярные платформы (топ-5) для каждого региона
    * В регионе NA в равной степени доминируют консоли от Microsoft и Sony, занимая по 32% и 39% от рынка соответственно в сравнении с остальными платформами из топ-5. Лучший показатель для платформы XOne отмечен именно в этом регионе. Также предыдущее поколение от Microsoft(X360) 11.2% в этом регионе преобладает над платформой Sony (PS3) с 8.7%
    * Для Европы характерна еще большее доминирование консоли от Sony, где она занимает 55% от рынка в сравнении с остальными платформами из топ-5, XOne удерживает 19.6%.
    * Для Японии ситуация характерным образом отличается, где сильным доминированием на рынке отличается платформа 3DS с 47.9%. PS4 набирает лишь 16.3%, а XOne вообще не присутствует в топ-5.
    * Все остальные страны, которые попадают в категорию Other, отличаются сильнейшим предпочтением платформы PS4 с 59.8% (наибольшее доминирование среди всех платформ отмечена для PS4 именно в данном регионе). Для XOne ситуация не столь оптимистична, где всего 16.8%, почти сравнявшись с показателем консоли предыдущего поколения от Sony с 12.6%.
  - Обозначены TOP-5 жанров для каждого региона
    * Можно отметить очень схожие вкусовые предпочтения для регионов EU и Other, где отличается только пятая позиция из топ-5 жанров. Схожее распределение показывает регион NA, с тем исключением, что там топ-1 по проданным копиям игры жанра Shooter с 32.1%. (Наивысший показатель для этого жанра среди всех регионов)
    * Существенные отличия показывает игровой рынок Японии, где основное предпочтение отдают играм жанра Role-Playing c 40.2% от топ-5 жанров. Второе место в регионе занимает жанр Action с 38.1% от топ-5. Итого на два жанра приходится почти 80% от всех жанров в этом регионе.
  - Построено распределение возрастного рейтинга для каждого региона:
    * Распределение величин проданных копий для всех регионов, кроме Японии выглядит полностью идентичными с отклонением в +- пару процентов для каждой из категорий.
    * Япония показывает совершенно другую картингу и можно предположить две гипотезы, с чем это может быть связано:
      1. Проанализировав до этого жанровые предпочтения были обнаружены иные вкусовые предпочтения (Role-Play и Action занимают ~80% рынка Японии), можно предположить, что игры данных категорий чаще получают возрастной рейтинг Т или Е, чем рейтинг М.
      2. Средний возраст геймеров в Японии смещен к более низким значением, другими словами большая часть геймеров – дети и подростки. А в Европе, Северной Америке и группе Другие средний возраст выше, из этого и происходит преобладание возрастного рейтинга М.


- Проведена проверка гипотезы о равенстве средних пользовательских рейтингов платформ Xbox One и PC.
  - При взятом уровне значимости в 5% не удалось отвергнуть нулевую гипотезу. Сделан вывод о равенстве средних пользовательских рейтингов платформ Xbox One и PC.
- Проведена проверка гипотезы о неравенстве средних пользовательских рейтингов жанров Action и Sports.
  - При взятом уровне значимости в 0.01% удалось отвергнуть нулевую гипотезу. Сделан вывод о неравенстве средних пользовательских рейтингов жанров Action и Sports.
