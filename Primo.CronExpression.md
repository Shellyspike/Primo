# Primo.CronExpression

**Primo.CronExpression** — это мощная библиотека, предназначенная для работы с CRON-записями и выражениями, обеспечивающая простоту и гибкость в планировании и управлении задачами на основе CRON.

## Общие сведения

**Primo.CronExpression** предоставляет удобный API для разбора, анализа и вычисления времени выполнения задач на основе CRON-выражений. Библиотека поддерживает стандартные и расширенные CRON-форматы, обеспечивая разработчикам удобные инструменты для работы с расписаниями и автоматизацией задач в проектах на платформе Primo RPA.

### Основные возможности:
- **Разбор CRON-выражений:** Легкий и точный разбор CRON-выражений с поддержкой различных форматов.
- **Расчёт времени запуска:** Получение времени следующего запуска, интервалов и серии запусков.
- **Гибкость настроек:** Возможность указания временных интервалов, дат начала и окончания.

## Инструкции по началу работы

Чтобы установить пакет **Primo.CronExpression**, воспользуйтесь Менеджером зависимостей в Primo RPA Studio или посетите [NuGet.org](https://www.nuget.org/).

### Шаги для установки

1. **Откройте Менеджер зависимостей:**
   - В главном меню Primo RPA Studio выберите `Управление зависимостями`.
   - Либо щелкните правой кнопкой мыши в панели проекта и выберите в появившемся меню пункт «Зависимости».

2. В открывшемся окне перейдите в раздел **NuGet.org** и введите **Primo.CronExpression** в строку поиска.

3. Нажмите на значок фильтра для отображения списка доступных библиотек. Найдите **Primo.CronExpression** и нажмите **Установить**.

4. Нажмите **Сохранить**. 

5. В открывшемся модальном окне нажмите **Установить**, а затем **Закрыть** для завершения установки. Пакет будет добавлен в ваш проект.

## Документация

Для более подробной информации о настройке и использовании **Primo.CronExpression** посетите [документацию на нашем сайте](https://docs.primo-rpa.ru).

## Функциональность библиотеки

Библиотека включает в себя следующие основные элементы:

- **Получить интервалы запуска**: Вычисляет и возвращает все интервалы выполнения задачи на основе указанного CRON-выражения.
- **Получить следующие запуски**: Определяет и возвращает список следующих запусков задачи.
- **Получить следующий запуск**: Определяет время следующего выполнения задачи.

### Свойства элементов библиотеки

#### Общие

Раздел **Общие** присутствует у каждого элемента библиотеки и включает следующие свойства:

- **Наименование** — имя элемента.
- **Отключение логирования** — настройка, отключающая ведение журнала для элемента.
- **Пауза до/после** — задержка выполнения до или после действия.
- **Продолжение при ошибке** — позволяет продолжить выполнение процесса при возникновении ошибки.
- **Скриншот завершения** — создание скриншота после выполнения действия.
- **Скриншот ошибки** — создание скриншота при возникновении ошибки.
- **Тайм-аут** — максимальное время ожидания выполнения действия.

Подробнее ознакомиться с описанием общих свойств можно на нашем сайте [здесь](https://docs.primo-rpa.ru/primo-rpa/primo-rpa-studio/process/elements).

#### Получить интервалы запуска

лемент, возвращающий все интервалы запуска между заданными датами. Элемент включает в себя следующие свойства:

1. **Вывод**:
   - **Результат** — список временных интервалов, рассчитанных на основе указанного CRON-выражения.
2. **Параметры**:
   - **Выражение Cron** — CRON-выражение, используемое для расчета интервалов. Обязательно для заполнения.
   - **Дата начала** — начальная дата, с которой начинается расчёт интервалов. Обязательно для заполнения.
   - **Дата окончания** — конечная дата, до которой производится расчёт интервалов. Обязательно для заполнения.

#### Получить следующие запуски

Элемент, вычисляющий следующие запуски. Элемент включает в себя следующие свойства:

1. **Вывод**:
   - **Следующий запуск** — список следующих дат и времён запуска, рассчитанных на основе CRON-выражения.
2. **Параметры**:
   - **Выражение Cron** — CRON-выражение, используемое для расчёта следующих запусков. Обязательно для заполнения.
   - **Кол-во** — количество следующих запусков, которые необходимо рассчитать.
   - **После даты** — дата, начиная с которой будут рассчитываться следующие запуски.

#### Получить следующий запуск

Элемент, вычисляющий следующий запуск. Элемент включает в себя следующие свойства:

1. **Вывод**:
   - **Следующий запуск** — дата и время следующего запуска, рассчитанные на основе CRON-выражения.
2. **Параметры**:
   - **Выражение Cron** — CRON-выражение, используемое для расчета следующего запуска. Обязательно для заполнения.
   - **После даты** — дата, начиная с которой будет рассчитан следующий запуск.

## Обратная связь

Если у вас возникли вопросы или предложения, пожалуйста, свяжитесь с нами по адресу [support@primo-rpa.ru](mailto:support@primo-ru)
