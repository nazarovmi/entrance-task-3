# Приложение для создания и редактирования информации о встречах сотрудников (Порядок выполнения работы представлен ниже)

## Задание на JS

Для разработки приложения был выбран фреймворк Vue.js

## Библиотеки

При разработке использовались библиотеки:
* vue - фреймворк, отлично подходит для одностраничных приложений
* vue-router - работа с роутами в vue
* vuex - хранилище данных для всех компонентов приложения
* axios - небольшая библиотека для HTTP запросов на Promise
* node-sass

## Запуск

Для работы приложения, серверная часть и клиент должны быть запущены одновременно.
Серверная часть должна быть доступна по адресу http://localhost:3000

``` bash
# Установка зависимостей
npm install

# Режим разработки
npm run dev

# Сборка
npm run build
```

## Разработка

### Компоненты

Разработка началась с создания простых, переиспользуемых компонентов, таких как:
* button - компонент кнопка
* rounded-button - круглая кнопка с иконкой
* input - поле ввода
* icon - иконка (для удобства работы все предоставленные иконки были обработаны и собраны в атлас, который находиться в самом низу файла index.html)
* scroll - скролл-панель (стилизация стандартного скролла)
* dropdown - выпадающий контент
* calendar - календарь
* date - поле ввода даты
* time - поле ввода времени
* datetime - поле ввода даты и времени (от и до)

Впоследствии из этих компонентов составлялись более сложные.
К примеру, так компонент datetime состоит из компонентов date и time, а компонент date из input, icon, dropdown и calendar.

### Хранилище данных

Для обмена информацией было подключено глобальное хранилище данных, в нём хранятся:
* данные о пользователях, комнатах и событиях
* начало и конец рабочего дня
* текущая дата
* выбранная дата

В хранилище есть множество функций-геттеров:
* для получения пользователей, комнат и событий по идентификатору
* для разчёта пустых слотов для конкретной комнаты
* а так же несколько функций для работы со временем

### Разное

В приложении необходимо много работать с датой, для этих целей был написан ряд вспомогательных функций
```
src/utils/date.js - различные функции для работы с датой
src/utils/date-const.js - константы
src/utils/date-filter.js - функция для форматирования даты
```

Для работы с формами был написан вспомогательный класс Form
```
src/utils/form.js
```
Формы поддерживают валидацию

