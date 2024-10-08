# Описание пакета Primo.MachineLearning

Пакет **Primo.MachineLearning** предоставляет мощный набор инструментов для работы с искусственным интеллектом на машине робота, включая классификацию и предсказание.

## Общие сведения

**Primo.MachineLearning** — это универсальная библиотека для работы с алгоритмами машинного обучения, предназначенная для использования в проектах на платформе Primo RPA Studio. Она поддерживает обучение моделей и выполнение задач по предсказанию и классификации данных, что позволяет автоматизировать сложные процессы с использованием современных методов анализа.

## Инструкции по началу работы

Чтобы установить пакет **Primo.MachineLearning**, воспользуйтесь Менеджером зависимостей в Primo RPA Studio или посетите [NuGet.org](https://www.nuget.org/).

### Шаги для установки

1. **Откройте Менеджер зависимостей:**
   - В главном меню Primo RPA Studio выберите `Управление зависимостями`.
   - Или щелкните правой кнопкой в панели проекта и выберите в контекстном меню пункт «Зависимости».

2. В открывшемся окне перейдите в раздел **NuGet.org** и введите **Primo.MachineLearning** в строку поиска.

3. Нажмите на значок фильтра для отображения списка доступных библиотек. Найдите **Primo.MachineLearning** и нажмите **Установить**.

4. Нажмите **Сохранить**.

5. В появившемся модальном окне нажмите **Установить**, затем **Закрыть** для завершения установки. Пакет будет добавлен в ваш проект.

## Документация

Для более подробной информации о настройке и использовании **Primo.MachineLearning** посетите [документацию на нашем сайте](https://docs.primo-rpa.ru).

## Состав библиотеки

Библиотека включает в себя следующие возможности:

- Классификация
- Обучение модели классификации
- Обучение модели предсказания
- Поиск изображений
- Предсказание

Для использования элемента необходимо перетащить его в рабочее поле проекта Primo RPA Studio.

## Примеры использования

На странице [Learning](https://github.com/PrimoRPA/Learning) доступен демонстрационный проект, показывающий работу с библиотекой. Скачайте архив с обучающими материалами по ссылке: [Скачать архив Learning](https://github.com/PrimoRPA/Learning/archive/refs/heads/master.zip). После этого распакуйте архив и откройте проект в Primo Studio.

Рекомендуется начать с процесса `Classification.ltw` для ознакомления с возможностями библиотеки.

## Свойства элементов библиотеки

### Общие свойства элементов библиотеки

Раздел **Общие** есть у каждого элемента, в него входят следующие свойства:

- Наименование
- Отключение логирования
- Пауза до/после
- Продолжение при ошибке
- Скриншот завершения
- Скриншот ошибки
- Тайм-аут

С описанием общих свойств можно ознакомиться на нашем сайте [здесь](https://docs.primo-rpa.ru/primo-rpa/primo-rpa-studio/process/elements).

### Классификация

Элемент осуществляет классификацию входных данных на основе обученной модели. Модель, которую вы будете использовать, предварительно обучают с помощью элемента **Обучение модели классификации**. Элемент **Классификация** включает следующие свойства:

1. **Входные данные** (обязательно для заполнения):
  - Данные — входные данные для классификации.
  - Путь к модели — путь к файлу модели. Пример: `System.IO.Path.Combine(_Workflow.ProjectPath, "Models\\model.ml")`.
2. **Вывод**:
  - Результат — результат классификации.

### Обучение модели классификации

Элемент позволяет обучить модель классификации данных. Модель обучается на основе входных данных (файл CSV), где должны быть заданы категории классификации и относящиеся к ним наборы данных. Для обучения модель будет использовать алгоритм, указанный в свойствах элемента.

В результате выполнения элемента буде получена обученная модель — файл, который способен распознавать определенные типы закономерностей. 

Элемент включает следующие свойства:

1. **Входные данные** (обязательно для заполнения):
  - Имя файла — путь к файлу CSV, содержащему данные для обучения. Пример: `System.IO.Path.Combine(_Workflow.ProjectPath, "Data\\file_name.csv")`.
  - Номера колонок данных — номера колонок, содержащих данные. Значение по умолчанию: `1-4`.
  - Номер основной колонки — номер колонки, содержащей категории классификации (классы). Значение по умолчанию: `0`.
  - Путь к модели — путь сохранения файла модели. Пример:`System.IO.Path.Combine(_Workflow.ProjectPath, "Models\\model.ml")`.
  - Разделитель — разделитель колонок CSV. Значение по умолчанию: `;`.
  - Тип алгоритма — тип алгоритма обучения модели. Чтобы выбрать нужный тип, кликните по списку значений параметра. Доступные значения:
    - Maximum_Entropy — значение по умолчанию. Максимальная энтропия — это метод машинного обучения, основанный на принципе максимизации энтропии (несоразмерности) для получения наиболее вероятностного распределения данных. Метод позволяет учесть все доступные данные при построении модели и делает ее более обобщенной. Алгоритм максимальной энтропии широко используется в области обработки естественного языка, классификации текстов, анализа тональности и других задач, где важна точность предсказания и учет всех доступных данных.
    - Naive_Bayes — метод машинного обучения, основанный на теореме Байеса. Использует вероятностные методы. Метод предполагает независимость между признаками (наивное предположение), что позволяет эффективно работать с данными, имеющими большое количество признаков. Применение алгоритма Naive Bayes широко распространено в задачах классификации текстов, фильтрации спама, анализе тональности текстов, а также в других областях, где важно эффективно работать с большим количеством признаков.
    - One_Versus_All_Averaged_Perceptron — метод «Один против всех, усредненный персептрон» используется для решения задач многоклассовой классификации и эффективен в случаях, когда количество классов велико. Этот алгоритм является модификацией классического алгоритма персептрона и позволяет работать с множеством классов, разделяя их на пары «один против всех». Метод позволяет строить несколько бинарных классификаторов, что упрощает задачу классификации объектов, относящихся к разным классам.
    - One_Versus_All_Fast_Forest — алгоритм обучения «Один против всех, быстрый лес» является модификацией алгоритма случайного леса, который используется для решения задач многоклассовой классификации. Сочетает в себе преимущества метода случайного леса (устойчивость к переобучению, способность работать с большими объемами данных) и метода One-Versus-All (эффективное решение задач многоклассовой классификации). Этот алгоритм может быть эффективным инструментом для решения сложных задач классификации с множеством классов.
2. **Вывод**:
  - Результат — результат обучения модели.

### Обучение модели предсказания

Элемент производит обучение модели предсказания данных. Модель обучается на основе входных данных (файл CSV), который указывается в свойствах элемента.

В результате выполнения элемента вы получите модель — файл, который обучен распознаванию определенных типов закономерностей.

Элемент включает следующие свойства:

1. **Входные данные** (обязательно для заполнения):
  - Имя файла — путь к файлу CSV, содержащему данные для обучения. Пример: `System.IO.Path.Combine(_Workflow.ProjectPath, "Data\\file_name.csv")`.
  - Номера колонок данных — номера колонок, содержащих данные. Значение по умолчанию: `1-4`.
  - Номер основной колонки — номер колонки, содержащей предсказываемое значение. Значение по умолчанию: `0`.
  - Путь к модели — путь сохранения файла модели. Пример:`System.IO.Path.Combine(_Workflow.ProjectPath, "Models\\model.ml")`.
  - Разделитель — разделитель колонок CSV. Значение по умолчанию: `;`.
  - Тип алгоритма — тип алгоритма обучения модели. Чтобы выбрать нужный тип, кликните по списку значений параметра. Доступные значения:
    - Poisson_Regression — значение по умолчанию. «Регрессия Пуассона» является статистическим методом, который используется для моделирования зависимости между независимыми переменными и целевой переменной, представляющей собой счетные данные. Часто применяется в случаях, когда целевая переменная представляет собой количество событий или частоту событий, такие как число заявок на сайте, количество аварий на дороге и т. д.
    - Online_Gradient_Descent — представляет собой метод оптимизации, который используется для обновления параметров модели по мере получения новых данных. Метод основан на итеративном обновлении весов модели с учетом градиента функции потерь по каждому примеру из обучающего набора данных.
    - Fast_Tree — метод обучения, который используется для построения ансамблей деревьев решений. Эффективный и быстрый алгоритм, который может быть использован для задач классификации и регрессии. Обычно используется в задачах с большими объемами данных или когда требуется быстрое обучение модели.
    - Fast_Forest — вариант алгоритма случайного леса, который используется для построения ансамблей деревьев решений. Метод включает в себя оптимизации и улучшения, которые позволяют ему работать быстрее и эффективнее, чем классический случайный лес.
2. **Вывод**:
  - Результат — результат обучения модели.

### Поиск изображений

Осуществляет поиск и классификацию знакомых изображений внутри изображения. Элемент включает следующие свойства (обязательно для заполнения):

1. **Входные данные**:
  - Путь к TensorFlow — путь к папке с обученной моделью TensorFlow.
  - Путь к файлу — путь к файлу изображения, в котором осуществляется поиск.
2. **Вывод**:
  - Результат — результат классификации.

### Предсказание

Элемент осуществляет предсказание на основе обученной модели. Модель предварительно обучают с помощью элемента **Обучение модели предсказания**. Элемент включает следующие свойства:

1. **Входные данные** (обязательно для заполнения):
  - Данные — входные данные для предсказания.
  - Путь к модели — путь к файлу модели. Пример:`System.IO.Path.Combine(_Workflow.ProjectPath, "Models\\model.ml")`.
2. **Вывод**:
  - Результат — результат предсказания.

## Обратная связь

Если у вас возникли вопросы или предложения, пожалуйста, свяжитесь с нами по адресу [support@primo-rpa.ru](mailto:support@primo-rpa.ru).

