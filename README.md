Анализ количества внештатных событий и их влияние на задержку

Проведен анализ количества внештатных событий, влияющих на задержку, в зависимости от города. Для этого использовали данные из столбца "Activity" для определения внештатных событий и создали новый признак "Incidents", который обозначает количество внештатных событий в зависимости от города.

Методология

Фильтрация внештатных событий: отфильтровали строки, где значение столбца "Activity" не равно 'Take off', 'Landing', 'Off boarding', 'Check-in', 'Baggage claim', 'Boarding', чтобы исключить обычные события и оставить только внештатные.

Группировка и подсчет: Мы сгруппировали данные по городу и подсчитали количество внештатных событий для каждого города с помощью метода size(). Результатом является новый столбец "Incidents", содержащий количество внештатных событий.

Объединение данных: Мы объединили полученные данные с исходным датасетом с использованием операции объединения по столбцу "City".

Выводы

Анализ показал, что количество внештатных событий может различаться в зависимости от пункта назначения полета. Это важная информация, которая может влиять на задержку и надежность авиаперелетов. Наличие большего количества внештатных событий может указывать на потенциальные проблемы в определенных городах.

Дополнительный анализ может быть проведен для изучения взаимосвязи между количеством внештатных событий и временем задержки. Это может помочь в определении факторов, которые могут способствовать возникновению задержек и внесению улучшений для повышения надежности авиаперелетов.

Код и подробности анализа доступны в [Jupyter Notebook](https://github.com/KAzantceva/Flights-Delay/blob/main/flight_delay.ipynb), который представляет собой полный набор шагов, выполненных в процессе анализа данных.

Данный проект представляет собой анализ событий авиаперелетов с использованием данных, которые хранятся в Google BigQuery. В процессе анализа мы извлекаем facets из массива событий и проводим различные аналитические задачи.

Описание датасета

Датасет содержит информацию о событиях авиаперелетов, включая рейсы, деятельность, временные метки и города. Каждая запись представляет собой одно событие, связанное с авиаперелетом.

Структура датасета:
- Flight: Идентификатор рейса
- Activity: Действие, связанное с рейсом
- Timestamp: Временная метка события
- City: Город, связанный с событием
  
Использование Google BigQuery

Для выполнения запросов к данным и извлечения фасетов из массива, предлагается использовать Google BigQuery console.cloud.google.com/bigquery?ws=!1m4!1m3!3m2!1slong-carving-385411!2sflight_delay
  
   Установка и запуск
Склонируйте репозиторий на вашу локальную машину:

shell
Copy code
git clone https://github.com/your-username/flight-events-analysis.git

Установите необходимые зависимости, выполнив следующую команду:
shell
Copy code
pip install -r requirements.txt

Замените project.dataset.table в SQL-запросах на long-carving-385411.flight_delay.flights.
