# Прогнозирование количества заказов такси на следующий час

## Данные

Данные лежат в файле `taxi.csv`. Количество заказов находится в столбце `num_orders` (от англ. *number of orders*, «число заказов»).

## Задача

Разработка системы предсказания объема заказа.

## Используемые библиотеки
*Pandas*, *NumPy*, *matplotlib.pyplot*,  *Scikit-Learn*, *CatBoost*, *LightGBM*, *statsmodels*, *os.path*

## Итоги исследования
<div style="border:solid orange 2px; padding: 5px">

<div class="alert alert-info"> <b>При проведении исследования (на основе полученных данных) выполнено:</b></div>

- Проведено ресемплирование данных по одному часу.
- Произведен графический анализ временного ряда, разложенного на тренд, сезонность и шум на различных временных интервалах.
    - Проанализировав весь df мы можем сделать вывод, что мы имеем восходящий тренд, а также увеличивающая дисперсия в шумах к концу августа месяца.
    - Анализируя данные в разрезе одного месяца: августа, мы также наблюдаем восходящий тренд, заметна четкая сезонность по дням недели и наличие выраженных шумов с середины и до конца месяца.
    - Анализируя последнюю доступную неделю мы видим еще раз в более близком приближении сезонность по дням недели и продолжение восходящего тренда.

- Созданы дополнительные признаки, необходимые для прогнозирования временного ряда.
- Проведены кросс-валидационные тесты на тренировочной выборке и выбрана модель с наилучшей предсказательной способностью по заданной метрике RMSE - LassoRegressor с показателем 22.39.
- Проведено тестирование выбранной модели на тестовой выборке, получен показатель RMSE - 34.51.
- Проведена проверка на адекватность, включающая в себе проверку на двух dummy-моделях, одна из которых построена на прогнозировании с помощью предыдущего значения, а вторая с использованием среднего значения тестовой выборки. Выбранная нами модель успешно прошла проверку на адекватность.