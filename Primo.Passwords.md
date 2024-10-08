# Описание пакета Primo.Passwords

Пакет **Primo.Passwords** предоставляет инструменты для автоматизации работы с паролями, которые могут быть использованы для различных сервисов и приложений. Библиотека помогает в генерации новых паролей, что особенно актуально для автоматизированных систем, где требуется регулярное обновление учетных данных.

## Общие сведения

В условиях, когда пароли имеют ограниченный срок действия и требуют регулярного обновления, **Primo.Passwords** автоматизирует этот процесс, создавая новые пароли в соответствии с заданными требованиями. Это особенно полезно в сценариях, где роботы используют учетные записи для доступа к приложениям, и необходима регулярная смена пароля для безопасности.

## Инструкции по началу работы

Чтобы установить пакет **Primo.Passwords**, воспользуйтесь Менеджером зависимостей в Primo RPA Studio или посетите [NuGet.org](https://www.nuget.org/).

### Шаги для установки

1. **Откройте Менеджер зависимостей:**
   - В главном меню Primo RPA Studio выберите `Управление зависимостями`.
   - Или щелкните правой кнопкой в панели проекта и выберите в отобразившемся меню пункт «Зависимости».

2. В открывшемся окне перейдите в раздел **NuGet.org** и введите **Primo RPA** в строку поиска.

3. Нажмите на значок с воронкой для отображения списка доступных библиотек. Найдите **Primo.Passwords** и нажмите **Установить**.

4. Нажмите **Сохранить**. 

5. В открывшемся модальном окне нажмите **Установить** и затем **Закрыть** для завершения установки. Пакет будет добавлен в ваш проект.

6. После установки библиотеки в панели элементов в группе **Криптография**, подгруппе **Пароли** появится элемент "Сгенерировать случайный пароль".

## Документация

Для более подробной информации о настройке и использовании **Primo.Passwords** посетите [документацию на нашем сайте](https://docs.primo-rpa.ru/primo-rpa/g_elements/el_extra/els_passwords).

## Состав библиотеки

Библиотека включает в себя элемент "Сгенерировать случайный пароль".  Применение элемента упрощает работу с процессами, в которых требуется генерация новых паролей по истечении срока действия старых.

Требования к новому паролю необходимо указать в свойствах элемента:

1. **Вывод**:
   - Пароль – сгенерированный пароль.
2. **Общие** (с описанием общих свойств можно ознакомиться на нашем сайте [здесь](https://docs.primo-rpa.ru/primo-rpa/primo-rpa-studio/process/elements)):
   - Наименование
   - Отключение логирования
   - Пауза до/после
   - Продолжение при ошибке
   - Скриншот завершения
   - Скриншот ошибки
   - Тайм-аут
3. **Пароль**:
   - Верх. регистр — минимальные требования к количеству букв в верхнем регистре.
   - Допустимые спецсимволы – допустимые спецсимволы в пароле. Например, знаки препинания и математических действий, различные скобки, знаки `#`, `@` и т. п. Пример заполнения: `@#+`.
   - Макс. длина — максимальная длина пароля.
   - Мин. длина — минимальная длина пароля.
   - Необходимо цифр — минимальные требования к количеству цифр в пароле.
   - Ниж. регистр — минимальные требования к количеству букв в нижнем регистре.
   - Спецсимволов — минимальные требования к количеству спецсимволов.

## Обратная связь

Если у вас возникли вопросы или предложения, пожалуйста, свяжитесь с нами по адресу [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
