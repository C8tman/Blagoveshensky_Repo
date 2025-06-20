# Blagoveshensky_Repo
- git add добавляет изменения в файлах
- git status даёт понимание, какие файлы были изменены, добавлены или удалены.
Не делает коммит.
- git commit -m "Описание изменений" фиксирует изменения в репозитории.
Сохраняет их в истории.
- git log выводит всю историю коммитов. Кто, что, когда изменил.
- git show даёт информацию о конкретном коммите. Дата, автор, что изменилось.
- git diff разница между текущими изменениями и последним коммитом.
Показывает, что именно изменилось в файлах.
- git restore отменяет все изменения в файлах, возвращает к состоянию последнего коммита.
- git rm удаляет файлы из Git, а так же из рабочей папки в случае необходимости.
- git reset отменяет все коммиты и возвращает проект к более раннему этапу.
- git branch показывает список веток.
- 1. git branch "имя ветки" создаём новую ветку.
- 2. git branch -d "Имя ветки" удаляем ветку с названием.
- git pull переносит актуальные изменения с гита на наш репозиторий.
Желательно находиться на на главной ветке в момент исполнения.
- git push отправляет изменения в удалённый репозиторий. Работает только после коммита.
- git help -a показывает все доступные команды Git
- git clone url Скопировать/Склонировать удалённый репозиторий.

### Понятие репозитория. Структура проекта.

Репозиторий - это, хранилище кода проекта, включающее:
1. Все файлы и папки проекта.
2. Историю изменений (коммиты).
3. Информацию о ветках, тегах и настройках.

Виды репозиториев:
1. Локальный репозиторий, хранится на компьюторе разработчика (папка .git).
2. Удалённый репозиторий, размещён на сервере (Github/Gitlab).

## Базовая структура проекта в Git.

Название проекта./     # Корневая папка проекта.
|
-.git/                  # Скрытая папка с данными Git (История, настройки).
|
-src/                   # Исходный код (например, main.py, index.js)
-docs/                  # Документация (README.md, API-описание)
-config/                # Файлы конфигурации (настройки сервера, БД)
-assets/                # Ресурсы (Изображения, шрифты)
|
-.gitignore             # файл, указывающий, какие файлы Git должен игнорировать.

## Жизненный цикл файлов Git.

Файлы в Git проходят несколько стадий:
1. Неотслеживаемые - Git о них не знает (gitignore).
2. Изменённые - это файлы, которые уже были в репозитории, но подверглись изменениям.
3. Индексированные - это файлы, которые подготовлены к коммиту (Была выполнена команда git add).
4. Зафиксированные - изменения сохранены в репозиторий ( git commit).

Важные правила при работе с Git:
1. Каждое изменение должно быть логически завершённым.
2. Gitignor обязателен, чтобы не засорять репозиторий ненужными файлами.
3. README - это лицо проекта, он должен содержать описание/установку и использование.

### Виды, цели и уровни интеграции программных модулей.

Интеграция программных модулей - это процесс объединения отдельных компонентов ПО в единую систему, обеспечивающую их совместимость

## Цель интеграции:
1) Обеспеченние взаимодействия модулей
2) Повышение надёжности и производительности системы
3) Упрощение разработки
4) Сопровождение ПО
5) Минимизация дублирования функционала

## Виды интеграции программных модулей

По способу взаимодействия:
1) Горизонтальная интеграция - объединение модулей одного уровня (например взаимодействие между сервисами в микросервисной архитектуре).
2) Вертикальная интеграция - объединение модулей разных уровней (например, клиент-серверное взаимодействие).

По степени связанности:
1) Слабая связанность, где модули взаимодействуют через стандартные интерфейсы (API и сообщения), что упрощает замену компонентов (например RestAPI, микросервис).
2) Сильная связанность, модули тесно зависят друг от  друга, изменение одного, требует модификации других (пример: монолитная архитектура).

По времени выполнения:
1) Статическая интеграция, где компоненты связываются на этапе компиляции.
2) Динамическая интеграция, где компоненты связываются во время выполнения (например плагины к-е загружаются в run-time).

## Уровни интеграции программных модулей

# Уровень API (сервисный уровень)
    Модули взааимодействуют через API (REST, GrahQL, gRPC).
    примеры:
         - Веб-сервисы (Spring Boot, Flask).
         - Микросервисная архитектура.

# Уровень пользовательского интерфейса
    Интеграция через единый интерфейс (веб. мобилные приложения)
    Примеры:
    - Single Page Application (React, Angular).
    - Desktop-приложения (Electron, Qt).

# Уровень бизнес-логики
    Интеграция на уровне общих бизнес-правил и процессов.
    Примеры:
    - ERP-системы (SAP, 1C).
    - Workflow-движки (Camunda, Airflow).

### Инструментальные средства интеграции

# Средства сборки и управления зависимостями
- npm, yarn (JavaScript).
- pip (Python).

# CI/CD-инструменты
- Gitlab CI, Github Actions - автоматизация сборки и тестирования.
- Docker, Kubernetes - контейнеризация и оркестрация.

# Middleware и брокеры сообщений
- RabbitMQ, Apache Kafka - асихронная интеграция.
- Redis - кеширование и Pub/Sub.

Автоматизация бизнесс-процессов - это исп-е технологий для выполнения повторяющихся задач,с целью минимизации ручного труда и повышения эффективности работы организации.

Цель автоматизации:
1) Ускорение выполнения операций
2) Снижение ошибок из-за чел фактора
3) оптимизация затрат
4) Повышение прозрачности и управляемости процессами 
5) масштабируемость бизнеса

Виды бизнесс-процессов по уровню сложности:
1) Простые процессы - это последовательные задачи без ветвлений.
2) Сложные процессы, они включают в себя условия, циклы, параллельные потоки (например: при согласовании договора).

Виды бизнесс-процессов по функциональным областям:
1) Управление документооборотом (пример: электронный архив).
2) ФИнансы и бухгалтерия (автоматизация расчётов и отчётности).
3) Логистика и склад (учёт товаров, маршрутизация доставок).
4) HR-процессы (рекрутинг и onboarding).
5) Тех. поддержка состоящая из ботов или каких-либо тикет систем.

Уровни автоматизации по сложности:
1) Базовый. Автоматизация простых задач(Рассылка email/смс и обработка данных).
2) Средний. Использование BPM-систем (Настройка маршрутов согласования).
3) Высокий. Использование роботизированной автоматизации процессов (имитация действий пользователя/использование ИИ для прогнозирования).

# Конфигурация Prettier
Комбинация клавиш для форматирования - shift + alt + f
{
    # "Ключ":Значение

// Максимальное количество символов в одной строке до переноса текста
    "printWidth":80

// Ширина отступа (количество пробелов)
    "tabWidth":4

// Использовать симмволы табуляции для отступов
    "useTabs": false

// Ставить ли точки с запятой в конце выражений  JS (True - да, False - нет)
    "semi":true

// Использовать одинарные или двойные кавычки
    "sigleQuote":false

// Правило постановки завершающей запятой (none, all, es5)
// none - не добавлять завершающую запятую.
// all - добавлять всегда.
// es5 - везде, где позволяет синтаксис.
    "traillingComma":"es5"

// Оставлять ли пустое пространство внутри квадратных или круглых скобках
    "bracketSpacing": false

// Всегда ли заключать аргументы в стрелочных функциях в круглые скобки
// "always" - всегда, "Avoid" - избегать круглых скобок при одном аргументе. 
    "arrowParens": "avoid"
}

### Тема

Источник данных - это объект/система, откуда поступают данные для обработки.
Приёмник данных - это объект/система, куда передаются обработанные данные.
Примеры источников данных:
1) Базы данных
2) Файлы
3) API
4) Потоки данных
Примеры приёмников данных:
1) БД
2) Отчёты и визуализации
3) Внешние системы
4) Облачные хранилища

Критерии выбора источников и приёмников данных.
При выборе учитывают:
1)	Формат данных (Структурированный, полуструктурированный, неструктурированный)
2)	Объём данных (Большие объёмы данных, требуют распределённых Систем.)
3)	Частоту обновления (realtime, пакетная обработка)
4)	Надёжность и доступность (!отказоустойчивость!)
5)	Безопасность (Шифрование и  доступ по ролям)
6)	Стоимость ()

Сопоставление объектов данных.
Сопоставление объектов данных – процесс преобразования данных, между источником и приёмником.
Этапы сопоставления:
1) Анализ структуры данных.
2) Преобразование типов.
3) Маппинг полей – это сопоставление названий столбцов.
4) Обработка отсутствующих данных.
5) Валидация – проверка на корректность.
Проблемы и решения:
1)	Если происходит несовпадение форматов, то надо использовать унифицированные форматы данных (например JSON)
2)	Если происходит потеря данных, т онужно использовать логгирование и мониторинг (Grafana)
3)	Если есть проблемы с производительностью, то необходимо оптимизировать запросы и реализовать кеширование.

Транспортные протоколы.
Транспортные протоколы определяют правила передачи данных между системами.
Основные транспортные протоколы:
1)	HTTP/HTTPS
- HTTP (Hyper Text Transmission Protocol) - протокол для передачи данных в веб-среде.
- HTTPS (HTTP Secure) – защищённыя версия с шифрованием.
Методы: GET, POST, PUT, DELETE.
Использование: REST API, веб-приложения.
2)	WebSocket
Двусторонний протокол для обмена сообщениями в реальном времени.
Преимущества: Низкие задержки, постоянное соединение.
Использование: чаты, онлайн-игры, биржевые котировки.
3)	TCP/IP и UDP
TCP (Transmission Control Protocol) – надёжная передача с подтверждением (гарантирует доставку).
Используется в http, ftp, smtp.
UDP (User Datagram Protocol) – быстрая передача без гарантии доставки.
Используется в VoIP, стрименге, DNS.
4)	MQTT (Message Queuing Telemetry Transport)
Протокл для IoT и устройств с ограниченными ресурсами.
Работает по модели издатель-подписчик (Pub/Sub).
5)	AMQP (Advanced Message Queuing Protocol)
Протокл для асихронного обмена сообщениями между системами.
Поддержка очередей (RabbitMQ, Apache Kafka)
6)	gRPC (Google Remote Procedure Call)
Высокопроизводительный RPC-протокол на основе HTTP/2.
Использует бинарный формат (Protocol Buffers).

Стандарты формирования сообщений:
1) Текстовый формат :
1. JSON (JavaScriptObjectNotation) – легковесный и легкочитаемый, структура {“ключ”:”значение”}, используется в REST API.
2. XML – структурированный с поддержкой схем, по структуре похож на html



<user>
	<name></name>
	<age></age>
</user>
Используется в SOAP и конфигурационных файлах.

3. YAML – имеет упрощённый синтаксис, удобен для конфигураций,используестя в Docker и  Kubernetes.
User:
	Name:John
	Age:30
2) Бинарные форматы

Выбор протокола и формата для web-API
HTTPS и JSON – для стриминга, чата и соц. сетей.
WebSocket + messagepack
Для тестирования API – PostMen и Swagger


Owl Carousel 2

### Отладка програмных продуктов

Отладка - процесс поиска и устранение ошибок в ПО.
Отладка критически нужна при разработке системного и прикладного ПО.

## Виды ошибок в ПО

1) Синтактическая - описание нарушения правил языка программирования, такая ошибка обнаруживается при компиляции.
2) Семантическая - некорректная логика, несоответствующая ожиданиям.
3) Логическая - программа работает, но результ работы программы не соответсвует ожиданиям.
4) Ошибка времени исполнения - возникает при делении на ноль; выход за пределы массива; обращение к недопустимым адресам.
5) Ошибки зависящие от архитектуры - возникает из-за различий в разрядности, кэше и многопоточности.


6) Ошибка связи архитектуры от аппартных средств - регистры процессора используются для отслеживания текущего процесса исполнения.
7) Памяти - необходимо учитывать особенности сегментации, адресации.
8) Кэш и кэширование - возможные ошибки из-за неучтённой инвалидации кэша.
9) Многопоточность и многозадачность - поведение CPU влияет на поведение программы.
10) Аппаратные прерывания - взаимодействие программ с внешними устройствами и их обработка.
11) Аппартные точки останова(breakpoints) - используется в низкоуровневой отладке.

## Методы отладки

1) Ручная отладка - анализ исходного кода, использование print-заявлений, проверка логики выполнения.
2) Отладка с использованием отладчиков - интерактивное выполнение кода, используются точки останова, используется пошаговое исполнение(step-in, step-out, step-over), прсматриваются и изменяются значения переменных, изучается стек вызовов
3) Логгирование - происходит запись хода выполнения программы в журнал или консоль, происходит анализ поведения без вмешательства процесса исполнения.
4) Автоматическое тестирование - написание unit-тестов, интеграционных и регрессивных тестов, также используется для выявления ошибок в логике программы.
5) Аппаратная отладка - отладка встроенных систем.

## Классификация инструментов отладки.

1. По уровню:
1) Высокоуровневые - работают с исходным кодом.
2) Низкоуровневые - работают с машинным кодом регистрами и памятью.
3) Аппартные - используют внешние средства и интерфейсы отладки.

2. По типу применения:
1) Интерактивные инструменты логгирования.
2) Системы трассировки.

Высокоуровнеые инструметы отладки:
1. Visual Studio Debugger
Работает с языками C#, VB.NET, F#, Python, JS/TS, HTML/CSS.
методы:
1) точки останова
2) шаги выполнения
3) инспекция переменных
4) анализ исключений
5) параллельная отладка
6) Отладка удалённого процесса
7) реактивная отладка

2. LLDB
Работает с языками C, C++, Objective-C, Swift, Rust, GO, Python, JS(WebAssembly).
Методы отладки:
1) Точки останова
2) шаги выполнения
3) инспекция переменных
4) управление пам ятью и объектами
5) Отладка многопоточных приложений
6) Расширенные техники диагностики

### Ручное и автоматизированное тестирование

Ручное тестирование - процесс выполнения тесткейсов вручную, без использования автоматизированных инструментов.
Особенности:
1) Тестировщик запускает программу, вводит данные и наблюдает за её поведением.
2) Часто применяется на этапе исследовательского тестирования.
3) Не требует навыков программирования.
Преимущества:
1) Гибкость и адаптивность к неожиданным ситуациям
2) Лучше подходит для UI/UX и сложных взаимодействий
3) Применяется на ранних этапах проекта
Недостатки:
1) Время-/ресурсозатратно
2) Подвержено человеческому фактору
3) Плохо масштабируется

Автоматизированное тестирование - подразумевается использование спецализированных скриптов/програм для выполнения тестов.
Инструменты:
1) Selenium - для тестированя web-интерфейсов.
2) GUnitPyTEst - юнит тестирования
3) TestEngine - 
4) MochaKypres - для JS и web-приложений
5) RobotFramework - поддерживает ключевое словоподобное ключевое тестирование.
6) Appium - для мобильных приложений.
Преимущества:
1) Быстрое выполнение повторяющихся тестов.
2) Высокая точность.
3) Легко интегрируется в CI/CD.
4) Подходит для регрессивного тестирования.
Недостатки:
1) Высокие затраты на внедрение.
2) Требуются навыки программирования.
3) Ограниченная гибкость.
4) Плохо работает с изменяющимся user-interface.
5) Поддержка автотестов со временем может стать дорогой.

|          характеристика           | ручное тестирование     | автоматизированное тестирование |
| 1. Повторяемость                  | низкая                  | высокая                         |
| 2. Скорость                       | низкая                  | высокая                         |
| 3. Подходит для UI/UX интерфейсов | да                      | частично                        |
| 4. Стоимость внедрения            | низкая                  | высокая на старте               |
| 5. Гибкость                       | высокая                 | средняя                         |
| 6. Точность                       | Зависит от тестировщика | высокая                         |
| 7. Масштабируемость               | Плохая                  | Хорошая                         |

## Подходы к выбору тестирования

|           условия проекта          |          рекомендуемый подход                   |
|     часто меняющийся интерфейс     | ручное тестирование                             |
| Большое число повторяющихся тестов | автоматизированное тестирование                 |
|        Краткий срок проекта        | ручное/частично автоматизированное тестирование |
|          Интеграция в CI/CD        | Автоматизированное                              |
|     Тестирование физ. устройства   | смешанный                                       |

### UnitTest
Это тест, который проверяет минимальную часть программый. Обычно одну функцию, , в изоляции от остального кода.
Цель UnitTest - это проверить работает ли конкретная единица кода правильно при различных входных данных и условиях.

### TestCase
Это описание одного сценария или тестирования.

### Скрипт
Это программа выполняющая автоматезированный тест

### регрессионное тестирование
Повторное тестирование после изменений

### Мок данный или же Мок объект

### CI/CD
Непрерывная интеграция и деплой

# Методы и средства организации тестирования

### Организация тестирования
Системный подход к планированию, выполнению и анализу тестов с использованием определённых методов (подходов), обеспечивающих качество прграммного продукта и его взаимодействия с аппаратной частью

|           МЕТОДЫ            |          ОПИСАНИЕ              
|          WhiteBox           |Тестировщик знает внутрению функцию устройства...                      
|          BlackBox           |Тестировщик не знает внутрению функцию устройства. Тестирует только...                                                                
|          GrayBox            |                                                        
|      Unit Тестирование      |Проверка...                            
|       Интеграционный        |Проверка взаимодействия модулей
|         Системный           |Проверка всей системы в сборке с программной и аппаратной частью
|       Функциональный        |Проверка соотсветствия требованием "Что делает система"
|                             |
|  регрессионное тестирование |
|                             |Проверка поведения и работоспособности на пиковых нагрузках

### Организация процесса тестирования
## Планирование
...
## Написание Тест кейсов
Происходит на основании требований как функиональных так и не функциональных
## Проведение теста
Как ручного так и автоматезированного 
## Анализ результатов
Состовляются отчёты, баг репорты
## Повторное тестирование (Регрессия)
Происходит после исправления ошибок

