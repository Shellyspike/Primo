# Описание пакета Primo.AHunter

Пакет **Primo.AHunter** представляет собой набор инструментов для интеграции с сервисом Ahunter, предназначенных для проверки, исправления и стандартизации почтовых адресов, телефонных номеров и ФИО в России.

## Общие сведения

**Primo.AHunter** позволяет легко подключить функции стандартизации адресов, телефонов и ФИО в проектах Primo RPA.

## Инструкции по началу работы

Чтобы установить пакет **Primo.AHunter**, воспользуйтесь Менеджером зависимостей в Primo RPA Studio или посетите [NuGet.org](https://www.nuget.org/).

### Шаги для установки

1. **Откройте Менеджер зависимостей:**
   - В главном меню Primo RPA Studio выберите `Управление зависимостями`.
   - Либо щелкните правой кнопкой мыши в панели проекта и выберите в появившемся меню пункт «Зависимости».

2. В открывшемся окне перейдите в раздел **NuGet.org** и введите **Primo.AHunter** в строку поиска.

3. Нажмите на значок фильтра для отображения списка доступных библиотек. Найдите **Primo.AHunter** и нажмите **Установить**.

4. Нажмите **Сохранить**. 

5. В открывшемся модальном окне нажмите **Установить**, а затем **Закрыть** для завершения установки. Пакет будет добавлен в ваш проект.

## Документация

Для более подробной информации о настройке и использовании **Primo.AHunter** посетите [документацию на нашем сайте](https://docs.primo-rpa.ru).

## Состав библиотеки

Библиотека включает в себя следующие возможности:

- **Стандартизация адреса**
- **Стандартизация телефона**
- **Стандартизация ФИО**

Для использования элемента необходимо перетащить его в рабочее поле проекта Primo RPA Studio.

## Свойства элементов библиотеки

### Общие

Раздел **Общие** присутствует у каждого элемента библиотеки и включает следующие свойства:

- **Наименование** — имя элемента.
- **Отключение логирования** — настройка, отключающая ведение журнала для элемента.
- **Пауза до/после** — задержка выполнения до или после действия.
- **Продолжение при ошибке** — позволяет продолжить выполнение процесса при возникновении ошибки.
- **Скриншот завершения** — создание скриншота после выполнения действия.
- **Скриншот ошибки** — создание скриншота при возникновении ошибки.
- **Тайм-аут** — максимальное время ожидания выполнения действия.

Подробнее ознакомиться с описанием общих свойств можно на нашем сайте [здесь](https://docs.primo-rpa.ru/primo-rpa/primo-rpa-studio/process/elements).

### Стандартизация адреса

Производит стандартизацию адреса. Элемент включает в себя следующие свойства:

1. **Вывод**:
   - Json – очищенный адрес в формате Json.
   - Результат – очищенный адрес.
2. **Запрос**:
   - Адрес – стандартизируемый адрес. Обязательно для заполнения.
   - Лимит – лимит адресов.
   - Тайм-аут – тайм-аут сервера.
   - Токен – токен API. Обязательно для заполнения.
   - Фильтр – фильтр адреса.

### Стандартизация телефона

Производит стандартизацию телефона. Элемент включает в себя следующие свойства:

1. **Вывод**:
   - Json – очищенный телефон в формате Json.
   - Результат – очищенный телефон.
2. **Запрос**:
   - Телефон – стандартизируемый телефон. Обязательно для заполнения.
   - Лимит – лимит телефонов.
   - Тайм-аут – тайм-аут сервера.
   - Токен – токен API. Обязательно для заполнения.

### Стандартизация телефона

Производит стандартизацию ФИО. Элемент включает в себя следующие свойства:

1. **Вывод**:
   - Json – очищенное ФИО в формате Json.
   - Результат – очищенное ФИО.
2. **Запрос**:
   - Лимит – лимит ФИО.
   - Тайм-аут – тайм-аут сервера.
   - Токен – токен API. Обязательно для заполнения.
   - ФИО – стандартизируемое ФИО. Обязательно для заполнения.

## Обратная связь

Если у вас возникли вопросы или предложения, пожалуйста, свяжитесь с нами по адресу [support@primo-rpa.ru](mailto:support@primo-ru).
