# Тест-кейсы: SWAPI API

**Base URL:** https://www.swapi.tech/api  
**Инструменты:** Postman (Collection Runner)

| ID | Название | Предусловия | Входные данные | Шаги | Ожидаемый результат |
|---|---|---|---|---|---|
| TC-API-001 | Получение персонажа Luke Skywalker по ID | API доступен | `GET /people/1` | 1) Отправить запрос 2) Проверить код ответа 3) Проверить обязательные поля | `200 OK`; `name=Luke Skywalker`; поля `height/mass/gender/birth_year/homeworld` присутствуют и не пустые; `films` — массив |
| TC-API-002 | Получение персонажа Darth Vader по ID | API доступен | `GET /people/4` | 1) Отправить запрос 2) Проверить код ответа 3) Проверить обязательные поля | `200 OK`; `name=Darth Vader`; поля `height/mass/gender/birth_year/homeworld` присутствуют и не пустые; `films` — массив |
| TC-API-003 | Обработка ошибки: несуществующий персонаж | API доступен | `GET /people/9999` | 1) Отправить запрос 2) Проверить код ответа 3) Проверить тело ошибки | `404 Not Found`; есть описание ошибки (`message/detail/error`); объект персонажа отсутствует |
| TC-API-004 | Планеты, где был Luke (через фильмы) | Выполнен TC-API-001; известен список `films[]` | `GET /people/1` → `GET /films/{id}` → `GET /planets/{id}` | 1) Получить `films[]` 2) Для каждого фильма получить `planets[]` 3) Для каждой планеты проверить `name/climate/terrain` | Все связанные запросы — `200 OK`; список планет не пустой; у каждой планеты есть `name/climate/terrain` |
| TC-API-005 | Получение фильма по ID и проверка обязательных полей | API доступен | `GET /films/1` | 1) Отправить запрос 2) Проверить код ответа 3) Проверить обязательные поля и массивы ссылок | `200 OK`; есть `title/episode_id/director/release_date`; `characters/planets/starships/vehicles` — массивы |
| TC-API-006 | Получение транспорта (Vehicle) по ID и проверка контракта | API доступен | `GET /vehicles/14` | 1) Отправить запрос 2) Проверить код ответа 3) Проверить поля `name/model/vehicle_class` | `200 OK`; поля `name/model/vehicle_class` присутствуют; `name` — непустая строка |
| TC-API-007 | Получение звездолёта (Starship) по ID и проверка контракта | API доступен | `GET /starships/12` | 1) Отправить запрос 2) Проверить код ответа 3) Проверить поля `name/model/starship_class` | `200 OK`; поля `name/model/starship_class` присутствуют; `name` — непустая строка |
