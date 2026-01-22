[![API tests (Newman)](https://github.com/gulyazaikina-jpg/swapi-api-testing/actions/workflows/newman.yml/badge.svg)](https://github.com/gulyazaikina-jpg/swapi-api-testing/actions/workflows/newman.yml)

# SWAPI API Testing (Postman)

Учебный проект: тестирование публичного API **SWAPI (Star Wars API)** с использованием Postman.

**Base URL:** https://www.swapi.tech/api
- **Инструменты**: Postman (Collection Runner), Newman (CLI)
- **Артефакты**: Postman Collection + Environment, GitHub Actions (CI)
- 
  ## Содержание
- [Структура репозитория](#структура-репозитория)
- [Как запустить в Postman](#как-запустить-в-postman)
- [Как запустить через Newman](#как-запустить-через-newman)

  
## Структура репозитория
- [Тест-кейсы](docs/test-cases.md)
- [Краткий отчёт о тестировании](docs/test-report.md) 
- [Postman collection + environment для прогона](postman/)
- [CI прогон коллекции в GitHub Actions](.github/workflows/newman.yml)
  
## Как запустить в Postman
1. Открой Postman
2. Import → импортируй:
   - `postman/SWAPI.postman_collection.json`
   - `postman/SWAPI.postman_environment.json`
3. Выбери Environment (в правом верхнем углу)
4. Запусти коллекцию через **Collection Runner**

## Как запустить через Newman
Запуск выполняется через npm-скрипт (Newman установлен как devDependency).

### Локально
```bash
npm ci
npm run test:swapi



