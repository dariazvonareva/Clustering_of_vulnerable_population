#  Дипломный проект. Бриф «Лаборатории исследований гражданского общества». Определение уязвимых групп населения

## Оглавление
[1. Описание проекта](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Описание-проекта) 

[2. Какой кейс решаем?](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Какой-кейс-решаем?)

[3. Краткая информация о данных](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Краткая-информация-о-данных)

[4. Этапы работы над проектом](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Этапы-работы-над-проектом)

[5. Результат](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Результат)

[6. Выводы](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Выводы)

### Описание проекта

Согласно опросу «инФОМ» от декабря 2021 года, у 27 % россиян хватает денег только на еду, а ещё 9 % не могут позволить себе полноценное питание. Эти люди особенно внимательно следят за ценами, а темп роста цен на продукты обычно превышает средний темп инфляции. В России проживает большое количество людей, и многие из них находятся в тяжелых жизненных условиях. 

Задачу, описанную в брифе, поставила молодая НКО, которая хочет помогать малообеспеченным людям. Чтобы делать это эффективно, НКО нужно понять, где живут такие люди, и открыть там свои филиалы.

Кроме того, в НКО хотят выяснить, с какими факторами связана бедность и как эти факторы связаны между собой.

#### Какой кейс решаем?
С помощью методов машинного обучения выделить регионы наиболее остро нуждающиеся в социальной поддержке на основании общедоступных данных государственной статистики.

Основная задача:
- Кластеризовать регионы России и определить, какие из них наиболее остро нуждаются в помощи малообеспеченным/неблагополучным
слоям населения;
- Описать группы населения, сталкивающиеся с бедностью;
- Определить:
     - влияет ли число детей, пенсионеров и других социально уязвимых групп на уровень бедности в регионе;
     - связаны ли уровень бедности/социального неблагополучия с
     - производством и потреблением в регионе;
     - какие ещё зависимости можно наблюдать относительно социально незащищённых слоёв населения.

:arrow_up:[к оглавлению](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Оглавление)


### Краткая информация о данных

В ходе проекта использовались различные статистические, экономические и демографические данные госорганов по субъектам Российской Федерации за разные годы, полученные из открытых источников. Полный набор файлов содержится в папке social_russia_data/.

- child_mortality_rural_1990_2021.xls — - Число умерших на первом году жизни детей за год (человек) в сельской местности
- child_mortality_urban_1990_2021.xls - Число умерших на первом году жизни детей за год (человек) в городской местности
- disabled_total_by_age_2017_2022.csv - число людей с инвалидностью по регионам, по месяцам, по возрастным группам.
-  morbidity_2005_2020_age_disease.xls - заболеваемость на 100 тыс.человек населения, по возрастным группам и группам заболеваний.
- poverty_percent_by_regions_1992_2020.csv — процент людей, живущих за чертой бедности (с денежными доходами ниже величины прожиточного минимума), оценка за год по регионам.
- welfare_expense_share_2015_2020 — расходы на социальную политику от общих расходов бюджета региона, % в год*.
- cash_real_income_wages_2015_2020 — среднедушевые и реальные денежные доходы населения, номинальная и реальная начисленная
зарплата, по регионам.
- poverty_socdem_20*.xls — распределение малоимущего населения по социально-демографическим группам (дети, трудящиеся,
пенсионеры) за 2017–2020 гг., по регионам.
- housing_2020 — характеристика жилищных условий домохозяйств. Оценка домохозяйствами состояния занимаемого ими жилого помещения, обследование 2020 года.
- population.xlsx — численность населения по регионам и федеральным округам на 1 января каждого года за 1999–2022 гг.
- gross_regional_product_1996_2020.xls — валовой региональный продукт на душу населения, в рублях.
- regional_production_*_*.csv — объём отгруженных товаров собственного производства или работ/услуг, выполненных
собственными силами, по видам деятельности за 2005–2016 гг., 2017–2020 гг. (в тысячах рублей, значение показателя за год).
- retail_turnover_per_capita_2000_2021.xls — оборот розничной торговли на душу населения, в рублях.
- Папка crimes — сведения о преступлениях, совершённых отдельными категориями лиц за 2016–2022 гг., по месяцам, регионам, категориям лиц, категориям преступлений
- drug_alco.xlsx — сведения о заболеваемости алкоголизмом и наркоманией, на 100 тыс. населения (2005–2018)
- newborn_2006_2022_monthly.csv — рождённые в этом месяце, по регионам, без учёта мертворождённых.
- workers.csv — отношение числа занятых в экономике региона к численности населения региона в трудоспособном возрасте, %, 2012–2020 гг.

Источник датасета: (https://www.fedstat.ru/, https://tochno.st/problems, https://rosstat.gov.ru/folder/10705)

:arrow_up:[к оглавлению](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Оглавление)

### Этапы работы над проектом
1. Знакомство со структурой данных

- Импорт и приведение к единому виду столбцов
- Выбор необходимых регионов, приведение к единому виду названий
- Очистка от пропусков и дубликатов, заполнение пропусков
- Сведение в единый датасет
- Формирование датасетов по годам
- Создание новых признаков

2. EDA (Разведывательный анализ)

- Ключевые описательные статистики
- Выделение абсолютных и относительных величин
- Визуализация признаков
- Корреляционная матрица
- Анализ взаимозависимости признаков
- Анализ выбросов 

3. Кластеризация 

- Подготовка к кластеризации - стандартизация
- baseline
- Снижение размерности (с помощью алгоритмов T-SNE и PCA)
- Кластеризация с помощью алгоритмов: KMeans, GaussianMixture, AgglomerativeClustering, DBSCAN, SpectralClustering, а также расчет метрики для сравнения: коэффициент силуэта, метод локтя
- Выбор лучшей модели, сравнение с использованием индекса Дэвиса-Болдина и Калински-Харабаша
- Анализ кластеров 

4. Статистические тесты
- Критерий Крускала-Уоллиса
- Т-тест
- Анализ различий характеристик населения в разных кластерах, является ли разница статистически значимой

5. Кластеризация регионов отдельно за каждый год за период с 2016 по 2021 гг.

- Сравнение класторов за разные года

6. Кластеризация сводной таблицы за все годы наблюдений

- Сравнение кластеров по ключевым показателям
- Анализ состава кластеров по регионам

7. Дополнительные шаги

- Сведение задачи кластеризации к задаче классификации с помощью моделей: RandomForestClassifie, GradientBoostingClassifier, аdaBoostClassifier. Использование GridSearchCV для нахождения лучших параметров для алгоритмов
- Выбор и сохранение лучшего алгоритма для новых данных
- Тестирование сохраненой модели

8. Общие выводы

:arrow_up:[к оглавлению](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Оглавление)


### Результаты:
[Ноутбук с выполненными заданиями и выводами](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/population.ipynb)


:arrow_up:[к оглавлению](https://github.com/dariazvonareva/Clustering_of_vulnerable_population/blob/main/README.md#Оглавление)

### Выводы

1. Кластеризация регионов:

Кластеризация регионов позволила выделить три группы, каждая из которых характеризуется уникальными особенностями в уровнях доходов, социального благополучия, и других социально-демографических характеристиках. Важно отметить, что в каждой группе наблюдаются различия по уровням бедности и социальных расходов, что указывает на необходимость дифференцированного подхода в поддержке различных регионов.

2. Определение наиболее уязвимых групп населения:

Анализ показал, что наиболее уязвимыми группами в регионах являются: малообеспеченные дети, пенсионеры и трудящиеся, которые страдают от низкого уровня доходов и высокого уровня детской смертности. Группы населения с низким доступом к ресурсам (например, электроэнергия, промышленность), что также коррелирует с высоким уровнем бедности.

3. Влияние численности социальных групп на уровень бедности: 

Высокие показатели детей, пенсионеров и малообеспеченных трудящихся напрямую связаны с увеличением уровня бедности. В регионах с высокой концентрацией уязвимых групп социальные расходы значительно выше, что подтверждается значительными различиями в уровне социального неблагополучия.

4. Связь уровня бедности с производством и потреблением. 

В регионах с низкой долей полезных ископаемых, электроэнергии и промышленности наблюдается снижение уровня социального благополучия и рост социального неблагополучия. Это свидетельствует о зависимости между экономическим развитием и возможностью поддерживать социальные группы.

Кластеры показывают различия в степени зависимости от социальных мероприятий и экономической активности, что требует целенаправленных мер поддержки уязвимых групп населения. В целом, результат анализа подчеркивает необходимость создания комплексных стратегий поддержки для различных регионов, ориентированных на специфические потребности уязвимых групп населения.
