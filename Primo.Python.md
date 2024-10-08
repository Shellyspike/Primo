# Описание пакета Primo.Python

Пакет **Primo.Python** предоставляет инструменты для взаимодействия со скриптами на Python, включая их запуск и получение данных. Поддерживается версия Python 3.9.

## Общие сведения

**Primo.Python** — это библиотека для интеграции Python-скриптов в проекты на базе Primo RPA. На машине робота должны быть установлены Python 3.9 и Pywin32 для корректной работы пакета.

## Инструкции по началу работы

Чтобы установить пакет **Primo.Python**, воспользуйтесь Менеджером зависимостей в Primo RPA Studio или посетите [NuGet.org](https://www.nuget.org/).

### Шаги для установки

1. **Откройте Менеджер зависимостей:**
   - В главном меню Primo RPA Studio выберите `Управление зависимостями`.
   - Или щелкните правой кнопкой в панели проекта и выберите «Зависимости».

2. В открывшемся окне перейдите в раздел **NuGet.org** и введите **Primo RPA** в строку поиска.

3. Нажмите на значок фильтра для отображения списка доступных библиотек. Найдите **Primo.Python** и нажмите **Установить**.

4. Нажмите **Сохранить**.

5. В модальном окне нажмите **Установить**, а затем **Закрыть** для завершения установки. Пакет будет добавлен в проект.

## Документация

Для подробной информации о настройке и использовании **Primo.Python**, посетите [документацию на нашем сайте](https://docs.primo-rpa.ru/primo-rpa/g_elements/el_extra/els_python).

## Состав библиотеки

Библиотека предоставляет следующие возможности:

- Python
- Выполнить скрипт
- Добавить функцию
- Получить объект

Для использования элемента перетащите его в рабочую область проекта Primo RPA Studio.

## Свойства элементов библиотеки

### Общие

Раздел **Общие** присутствует у каждого элемента и включает следующие свойства:

- Наименование
- Отключение логирования
- Пауза до/после
- Продолжение при ошибке
- Скриншот завершения
- Скриншот ошибки
- Тайм-аут

Описание общих свойств доступно на [нашем сайте](https://docs.primo-rpa.ru/primo-rpa/primo-rpa-studio/process/elements).

### Элемент "Python"

Элемент **Python** используется для установки соединения с Python. Кнопка **Проверить** на панели элемента позволяет протестировать настроенное соединение. 

Включает следующие свойства:

1. **Соединение**:
   - Консоль – если нужно показывать окно консоли, установите галочку.
   - Путь к Python – обязательно для заполнения. Укажите путь к файлу `python.exe`.
   - Размер буфера – размер буфера обмена. Значение по умолчанию: 65535.
   - Тайм-аут – тайм-аут соединения с Python в миллисекундах.

### Элемент "Выполнить скрипт"

Этот элемент выполняет указанный сценарий Python. 

Включает следующие свойства:

1. **Сценарий**:
   - Аргументы
   - Текст – обязательно для заполнения. Текст сценария.

### Элемент "Добавить функцию"

Добавляет функцию Python в проект. Если указан и путь к файлу со скриптом Python, и текст скрипта Python - предпочтении отдается значению из файла. 

Включает следующие свойства:

1. **Сценарий** (обязательно для заполнения):
   - Текст – обязательно для заполнения. Текст сценария.
   - Файл – путь к файлу сценария.

### Элемент "Получить объект"

Этот элемент позволяет получить объект Python. 

Включает следующие свойства:

1. **Вывод**:
   - Переменная – переменная для сохранения результата.
2. **Объект**:
   - Имя объекта – название объекта Python. Обязательно для заполнения.
   - Тип – тип данных объекта.
   
## Обратная связь

Если у вас возникли вопросы или предложения, свяжитесь с нами по адресу [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
