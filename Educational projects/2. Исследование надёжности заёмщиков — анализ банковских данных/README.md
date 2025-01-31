# Исследование надёжности заёмщиков — анализ банковских данных

## Данные

__*Для исследования получен csv-файл `data.csv`*__

- __*`children` — количество детей в семье*__
- __*`days_employed` — общий трудовой стаж в днях*__
- __*`dob_years` — возраст клиента в годах*__
- __*`education` — уровень образования клиента*__
- __*`education_id` — идентификатор уровня образования*__
- __*`family_status` — семейное положение*__
- __*`family_status_id` — идентификатор семейного положения*__
- __*`gender` — пол клиента*__
- __*`income_type` — тип занятости*__
- __*`debt` — имел ли задолженность по возврату кредитов*__
- __*`total_income` — ежемесячный доход*__
- __*`purpose` — цель получения кредита*__

## Задача

На основе статистики о платёжеспособности клиентов исследовать влияет ли семейное положение и количество детей клиента на факт возврата кредита в срок.

## Используемые библиотеки
*Pandas*


## Итоги исследования

<div style="border:solid orange 2px; padding: 5px">

<div class="alert alert-info"> <b>При проведении исследования по определенным критериям (количество детей, семейное положение, уровень дохода и цель кредита), было установлено, как различные значения в данных критериях влияют на надежность кредитуемого:</b></div>

- __*Кредитуемые, не имеющие детей на 1.69 % благонадежнее, чем те, у кого есть хотя бы один ребенок. Для дальнейшего исследования будет полезно проверить гипотезу уменьшения надежности кредитуемого с ростом количества детей. На основании предоставленных банком данных проверить данную гипотезу невозможно из-за малого количества данных в некоторых категориях.*__
- __*Люди, когда-либо официально заключавшие брак на 2.455 % более надёжные заёмщики.*__
- __*Чем выше платежеспособность человека, тем менее вероятна задолженность по кредиту. Установленная разница между двумя соседними категориями по ежемесячному заработку равняется 1.437 %.*__
- __*Со снижением целевой важности кредита, снижается надежность кредитуемых. При прямом сравнении двух групп: первая - с наибольшим приоритетом важности для человека(операции с недвижимостью), вторая - операции с автомобилем(что скорее является уже элементом роскоши) заметна разница надежности кредитуемых на 2.09 %.*__
