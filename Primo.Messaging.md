# Описание пакета Primo.Messaging

Пакет **Primo.Messaging** предоставляет интеграцию с мессенджером Telegram и чат-ботом AutoFAQ, предлагая инструментарий для работы с этими платформами в рамках решения Primo RPA.

## Общие сведения

**Primo.Messaging** представляет собой удобный и мощный инструмент для автоматизации задач, связанных с обменом сообщениями в Telegram и AutoFAQ. Библиотека предоставляет доступ к ключевым функциям обеих платформ, позволяя отправлять и получать сообщения, управлять чатами и обрабатывать файлы. Интеграция с AutoFAQ помогает автоматизировать поддержку клиентов, а возможности Telegram упрощают работу с коммуникациями.

## Инструкции по началу работы

Чтобы установить пакет **Primo.Messaging**, воспользуйтесь Менеджером зависимостей в Primo RPA Studio или посетите [NuGet.org](https://www.nuget.org/).

### Шаги для установки

1. **Откройте Менеджер зависимостей:**
   - В главном меню Primo RPA Studio выберите `Управление зависимостями`.
   - Или щелкните правой кнопкой в панели проекта и выберите в отобразившемся меню пункт «Зависимости».

2. В открывшемся окне перейдите в раздел **NuGet.org** и введите **Primo RPA** в строку поиска.

3. Нажмите на значок с воронкой для отображения списка доступных библиотек. Найдите **Primo.Messaging** и нажмите **Установить**.

4. Нажмите **Сохранить**. 

5. В открывшемся модальном окне нажмите **Установить** и затем **Закрыть** для завершения установки. Пакет будет добавлен в ваш проект.

## Документация

Для более подробной информации о настройке и использовании **Primo.Messaging** посетите [документацию на нашем сайте](https://docs.primo-rpa.ru).

## Состав библиотеки

Библиотека включает в себя следующие возможности:

- **Интеграция с AutoFAQ**:
  - Соединение с AutoFAQ
  - Отправка текста
  - Получение списка чатов

- **Интеграция с Telegram**:
  - Отправка контакта
  - Отправка текста
  - Отправка файла
  - Отправка фото
  - Получение сообщений
  - Получение файла
  - Соединение с Telegram
  - Получение списка чатов

Для использования элемента необходимо перетащить его в рабочее поле проекта Primo RPA Studio.

## Свойства элементов библиотеки

### Общие

Раздел **Общие** есть у каждого элемента, в него входят следующие свойства:

- Наименование
- Отключение логирования
- Пауза до/после
- Продолжение при ошибке
- Скриншот завершения
- Скриншот ошибки
- Тайм-аут

С описанием общих свойств можно ознакомиться на нашем сайте [здесь](https://docs.primo-rpa.ru/primo-rpa/primo-rpa-studio/process/elements).

---

### Интеграция с AutoFAQ

Интеграция содержит следующие элементы:

#### Соединение с AutoFAQ

Элемент, осуществляющий подключение к сервисам AutoFAQ. Включает в себя следующие свойства:

1. **AutoFAQ** — свойства обязательны для заполнения:
   - ID сервиса
   - URL
   - Логин
   - Пароль
   - Тайм-аут

2. **Вывод**:
   - Соединение с AutoFAQ

#### Отправить текст

Элемент, отправляющий текстовое сообщение в чат AutoFAQ. Включает в себя следующие свойства:

1. **AutoFAQ**:
   - ID пользователя — обязательно для заполнения
   - Соединение с AutoFAQ
   - Текст — обязательно для заполнения. Текст сообщения

#### Список чатов

Элемент, получающий список чатов AutoFAQ. Включает в себя следующие свойства:

1. **AutoFAQ**:
   - Соединение с AutoFAQ

2. **Вывод**:
   - Чаты

3. **Фильтр**:
   - ID оператора
   - Дата по
   - Дата с
   - Размер
   - Статусы
   - Страница

---

### Интеграция с Telegram

Интеграция содержит следующие элементы:

#### Соединение с Telegram

Элемент, осуществляющий подключение к сервисам Telegram. Включает в себя следующие свойства:

1. **Telegram** — свойства обязательны для заполнения:
   - ID токена
   - Тайм-аут

2. **Вывод**:
   - Соединение с Telegram

#### Список чатов

Элемент, получающий список чатов Telegram. Включает в себя следующие свойства:

1. **Telegram**:
   - Соединение с Telegram

2. **Вывод**:
   - Чаты — список последних чатов

#### Отправить контакт

Элемент, отправляющий контакт в чат Telegram. Включает в себя следующие свойства:

1. **Telegram**:
   - ID чата — обязательно для заполнения.
   - Имя — имя контакта.
   - Ответ на сообщение — ID сообщения, на которое надо ответить.
   - Соединение с Telegram.
   - Телефон — телефон контакта.
   - Фамилия — фамилия контакта.

#### Отправить текст

Элемент, отправляющий текстовое сообщение в чат Telegram. Включает в себя следующие свойства:

1. **Telegram**:
   - ID чата — обязательно для заполнения.
   - Ответ на сообщение — ID сообщения, на которое надо ответить.
   - Соединение с Telegram.
   - Текст — обязательно для заполнения. Текст сообщения.

#### Отправить файл

Элемент, отправляющий файл в чат Telegram. Включает в себя следующие свойства:

1. **Telegram**:
   - ID чата — обязательно для заполнения.
   - Ответ на сообщение — ID сообщения, на которое надо ответить.
   - Соединение с Telegram.
   - Текст — текст сообщения.
   - Файл — обязательно для заполнения. Путь к файлу. По кнопке ![alt text](image-3.png) можно указать путь к файлу в окне Проводника.

#### Отправить фото

Элемент, отправляющий фото в чат Telegram. Включает в себя следующие свойства:

1. **Telegram**:
   - ID чата — обязательно для заполнения.
   - Ответ на сообщение — ID сообщения, на которое надо ответить.
   - Соединение с Telegram.
   - Текст — текст сообщения.
   - Файл — обязательно для заполнения. Путь к файлу. По кнопке ![alt text](image-3.png) можно указать путь к файлу в окне Проводника.

#### Получить сообщения

Элемент, получающий сообщения из чата Telegram. Включает в себя следующие свойства:

1. **Telegram**:
   - ID чата — обязательно для заполнения.
   - Буфер — обязательно для заполнения. Размер буфера сообщений.
   - Начиная с — получит сообщения, начиная с указанного времени.
   - Соединение с Telegram.

2. **Вывод**:
   - Сообщения — массив полученных сообщений.

#### Получить файл

Элемент, получающий файл из чата Telegram. Включает в себя следующие свойства:

1. **Telegram**:
   - ID файла.
   - Путь к файлу — обязательно для заполнения. Путь сохранения файла. По кнопке ![alt text](image-3.png) можно указать путь к файлу в окне Проводника.
   - Соединение с Telegram.

## Обратная связь

Если у вас возникли вопросы или предложения, пожалуйста, свяжитесь с нами по адресу [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
