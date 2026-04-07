| Критерий | OpenWeatherMap API | JSONPlaceholder API |
|----------|---------------------|-------------------|
| 1. Основные эндпоинты и поддерживаемые методы | GET /data/2.5/weather — текущая погода; GET /data/2.5/forecast — прогноз 5 дней; GET /data/3.0/onecall — комплексные данные; GET /data/2.5/air_pollution — качество воздуха; GET /geo/1.0/direct — геокодирование. HTTP-методы: Только GET | GET /posts — получение всех постов; POST /posts — создание поста; PUT /posts/{id} — обновление поста; DELETE /posts/{id} — удаление поста. HTTP-методы: GET, POST, PUT, DELETE, PATCH |
| 2. Форматы запроса и ответа | Формат ответа: JSON (по умолчанию), XML, HTML — переключение через параметр mode. Ключевые параметры запроса: lat, lon, appid (обязательные); mode, units, lang (опциональные). Пагинация: Параметр cnt — ограничение количества записей. Обработка ошибок: JSON: поля cod + message | Формат ответа: Только JSON. Ключевые параметры запроса: id (в пути для конкретного ресурса); для POST/PUT — тело запроса в JSON. Пагинация: _start, _limit. Обработка ошибок: Простые HTTP статусы, без детальных сообщений |
| 3. Особенности авторизации и версии API | Авторизация: API-ключ обязателен, передаётся только в URL: &appid={key}. Версионирование: Через URL-путь: /data/2.5/ и /data/3.0/. Rate Limiting: Обновление не чаще раза в 10 мин; One Call 3.0: 1 000 бесплатных вызовов/день | Авторизация: Не требуется (фейковый API). Версионирование: Нет. Rate Limiting: Нет ограничений |
| 4. Отличия в подходах к дизайну и структуре | Ресурсная модель: Плоская, по типу погодных данных (weather, forecast, air_pollution); множество специализированных эндпоинтов. Кастомизация ответа: Единицы измерения (units), язык описания (lang), формат (mode). HATEOAS: Нет. REST-зрелость: Уровень 2 (ресурсы + HTTP GET) | Ресурсная модель: Иерархическая, по ресурсам (posts, comments, users); поддержка CRUD операций. Кастомизация ответа: Фильтрация через параметры _start, _limit. HATEOAS: Нет. REST-зрелость: Уровень 2 (ресурсы + HTTP методы)

---
Ссылки на API:
1. https://openweathermap.org/api (Взят пример и анализ структуры)
2. https://jsonplaceholder.typicode.com/
---
## Пример JSON-ответа и анализ структуры

GET https://api.openweathermap.org/data/3.0/onecall/overview?lon=-11.8092&lat=51.509865&appid={API key} <br>
**Параметры запроса**:
1. lat - требуется -  Широта, десятичная (-90; 90) - float <br>
2. lon - требуется - Долгота, десятичная (-180; 180) - float <br>
3. appid - требуется - Ваш уникальный ключ API - string <br>
4. date - опционально - Дата, когда пользователь хочет получить сводку погоды в формате YYYY-MM-DD. Данные доступны на сегодня и завтра. Если не указано, текущая дата будет использоваться по умолчанию. Обратите внимание, что дата определяется часовым поясом, соответствующим координатам, указанным в запросе API  - string <br>
5. units - опционально - Единицы измерения. Доступны стандартные, метрические и имперские единицы. Если вы не используете параметр units, стандартные единицы будут применяться по умолчанию. - string <br>
---

{
   "lat": 51.509865,
   "lon": -0.118092,
   "tz": "+01:00",
   "date": "2024-05-13",
   "units": "metric",
   "weather_overview": "The current weather is overcast with a 
temperature of 16°C and a feels-like temperature of 16°C. 
The wind speed is 4 meter/sec with gusts up to 6 meter/sec 
coming from the west-southwest direction. 
The air pressure is at 1007 hPa with a humidity level of 79%. 
The dew point is at 12°C and the visibility is 10000 meters. 
The UV index is at 4, indicating moderate risk from the 
sun's UV rays. 
The sky is covered with overcast clouds, and there is 
no precipitation expected at the moment. 
Overall, it is a moderately cool and cloudy day 
with light to moderate winds from the west-southwest."
}

---

**Поля в ответе**:
1. lat - Широта, десятичная (-90; 90) - float <br>
2. lon - Долгота местоположения, десятичная (-180; 180) - float <br>
3. tz - Часовой пояс в формате ±XX:XX - string <br>
4. date - Дата, для которой формируется сводка в формате YYYY-MM-DD - string <br>
5. units - Единицы измерения, указанные в запросе - string <br>
6. weather_overview - AI сгенерировал обзор погоды за запрошенную дату - string <br>