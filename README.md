# Go Interview Questions
Идея данного репозитория возникла во время подготовки к собеседованиям на позицию Backend разработчика на языке Go.  
В данном Readme собраны частые и не очень вопросы и ответы к ним. Они условно делятся на общие вопросы и вопросы непосредственно по самому языку Go.

Настоятельно рекомендую, прежде чем открывать ответ на вопрос попробовать ответить на него самостоятельно.

p.s Если вы заметили не точность или не соответствие информации - напишите не стесняйтесь.  
p.s.s Вы так же можете предложить свои вопросы, я обязательно их добавлю.

---

# Questions

<h2>Категории вопросов</h2>
  
<details>
  <summary>Сеть и всё что с ней связано</summary>  

  1. [В чем отличие протоколов TCP и UDP?](#tcp-udp)
</details>
  
<details>
  <summary>Операционная система</summary>  

  - [Ссылка на текст 3](#текст-3)
  - [Ссылка на текст 4](#текст-4)
  - [Ссылка на текст 4](#текст-4)
  - [Ссылка на текст 4](#текст-4)
</details>






***Общие вопросы***

2. [Какие еще протоколы существуют?](#protocols)
3. [Можно ли убить поток внутри определенного процесса командой kill?](#kill)
4. [Как отсортировать файл на 100GB с 1GB ОЗУ?](#ozu)
5. [Что такое микросервисы?](#micro)
6. [Какие преимущества у микросервисной архитектуры по сравнению с монолитом? А какие недостатки?](#micro1)
7. [Что использовать для трассировки сервисов? Для мониторинга? А для логирования?](#trac-log)
8. [Как быть с консистентностью данных между несколькими микросервисами ](#micro2)
9. [Что такое сине-зеленый деплой (Blue-Green Deployment)](#blue-green)
10. [Что такое системы оркестрации контейнеров?](#container)
11. [Какая разница между реляционными vs не реляционными СУБД?](#sql)
12. [Что такое рефлексия?](#reflex)
13. [Что такое асинхронность?](#async)
14. [Что такое параллельность?](#paralel)
15. [Что такое конкурентность?](#concurency)

---

***Вопросы по языку GO***
1. [Расскажи кратко о языке Go](#go-intro)
2. [Как реализовано хранилище памяти в Go?](#go-store)
3. [Какие типы данных есть в языке Go?](#go-types)
4. [Какие численные типы есть?](#ints)
5. [Какой результат получим если разделить int на 0 и float на 0?](#division)
6. [Что представляют собой строки в go?](#go-str)
7. [Как эффективно склеить множества строк?](#str-conc)
8. [Как преобразовать строку в int и наоборот? Можно ли сделать int(string) и string(int) соответственно?](#str-int)
9. [Интерфейсы: Что такое интерфейс в Go? Зачем нужен на практике? Примеры задач где стоит ввести?](#interface)
10. [Что такое пустой интерфейс?](#nil-interface)
11. [Как устроен внутри nil интерфейс vs nil внутри интерфейса?](#nil-interface1)
12. [Как определить тип интерфейса?](#interface-type)
13. [В каком пакете лучше объявлять интерфейсы и почему?](#interface-package)
14. [Что такое пакеты в go?](#package)
15. [Что такое глобальная переменная?](#global)
16. [Что такое константы и можно ли их изменять?](#const)
17. [Зачем фигурные скобки с не объявленным оператором внутри функции?](#scope)
18. [В go есть оператор switch case, можно ли выполнить несколько условий в одном объявленном операторе?](#switch)
19. [Что такое iota?](#iota)
20. [Что такое слайс и чем он отличается от массива?](#slice)
21. [Какой размер массива выделяется под слайс при его расширении за рамки его емкости?](#arr-slice)
22. [Как реализована map(карта) go?](#map)
23. [Почему нельзя брать ссылку на значение, хранящееся по ключу в map?](#map1)
24. [Что такое эвакуация, и в каком случае она будет происходить?](#map2)
25. [Какие есть особенности синтаксиса получения и записи значений в map??](#map3)
26. [Как происходит поиск по ключу в map?](#map4)
27. [Зачем используется ключевое слово defer в go?](#defer)
28. [Каков порядок возврата при использовании несколько функций с defer в рамках одной внешней функции?](#defer-order)
29. [Как передаются значения в функции, перед которыми указано ключевое слово defer?](#defer-value)
30. [Что такое поток и горутина?](#goroutin)
31. [Сколько можно запустить потоков и горутин?](#goroutine-count)
32. [Каков минимальный и максимальный вес горутин?](#goroutin-wight)
33. [Что будет если размер горутины превысил допустимый максимум?](#goroutin-wight-max)
34. [Какие есть способы остановить все горутины в приложении?](#goroutin-cancel)
35. [Как вручную задать количество процессоров для приложения?](#process)
36. [Как принудительно переключить контекст?](#contekst)
37. [Как наладить связь между горутинами?](#sync-goruotins)
38. [Какие есть примитивы синхронизации? Расскажи немного про каждый](#primitivs)
39. [Что такое graceful shutdown?](#gracefull)
40. [Что такое channel?](#channel)
41. [Что такое буферизированный и небуферизированный channel?](#buf-channel)
42. [Какие действия можно произвести с каналом?](#chanel-use)
43. [Что будет если писать/читать в nil channel?](#nil-channel)
44. [Что будет если писать/читать в/из закрытый channel?](#close-channel)
45. [Как закрыть channel? Что с ним происходит?](#close-channel1)
46. [Какие есть инструкции для чтения из channel?](#channel-ass)
47. [Как сделать select неблокирующим?](#select-block)
48. [Какой порядок исполнения операций case в select?](#select-block-case)
49. [Что такое context в GO?](#go-context)
50. [Для чего применяется context?](#context-useful)
51. [Чем отличается context.Background от context.TODO?](#ctx-back)
52. [Как передавать значения и вычитывать их из context?](#ctx-val)
53. [Каковы отличия context.WithCancel, context.WithDeadline, context.WithTimeout?](#ctx-deadline)
54. [Как обрабатывать отмену context?](#ctx-cancelation)
55. [Что обозначает * и &?](#pointers)
56. [Как происходит передача параметров в функцию?](#func-args)
57. [Есть ли особенности поведения при передаче map и slice в функцию?](#map-slice-args)
58. [Как функции делятся памятью?](#func-storage)
59. [Что такое сборщик мусора и по какому алгоритму он реализован в Go?](#garbage)
60. [Расскажите про алгоритм mark and sweep](#mark-sweep)
61. [Когда запускается сборщик мусора?](#gc-time)
62. [Сколько ресурсов потребляет сборщик мусора?](#gc-resource)

---

# Answers

### Вопрос: [В чем отличие протоколов TCP и UDP?] <a name="tcp-udp"></a>

<details>
  <summary>Ответ <- Click</summary>

    - TCP (Transmission Control Protocol)
       - Ориентирован на установление надежного соединения.  
       - Ошибки корректируются; потерянные или поврежденные пакеты пересылаются.  
       - Поддерживает управление потоком и перегрузкой.  
       - Нормально работает в условиях высокой задержки.
       
    - UDP (User Datagram Protocol)
       - Безусловный протокол, не устанавливает соединение.  
       - Ошибки не корректируются; потерянные пакеты не восстанавливаются.  
       - Не поддерживает управление потоком и перегрузкой.  
       - Обычно быстрее, чем TCP.  
       
    - Когда UDP предпочтительнее:  
       - Потоковое медиа, онлайн-игры, VoIP — там, где задержка критична и потеря пакетов допустима.  
</details>

---

### Вопрос: [Какие еще протоколы существуют?] <a name="protocols"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Транспортный уровень (как TCP и UDP):
        - SCTP (Stream Control Transmission Protocol) — протокол, предназначенный для передачи данных с поддержкой множественных потоков и устойчивый к ошибкам.
        - CCP (Datagram Congestion Control Protocol) — протокол, предназначенный для передачи потоковых медиа.
        
    - Сетевой уровень:
        - IP (Internet Protocol) — протокол маршрутизации.
        - ICMP (Internet Control Message Protocol) — протокол управляющих сообщений.
        - OSPF (Open Shortest Path First) — протокол динамической маршрутизации.

    - Канальный уровень:
        - Ethernet — наиболее распространенный протокол канального уровня.
        - Wi-Fi — набор стандартов для беспроводных локальных сетей.

    - Прикладной уровень:
        - HTTP/HTTPS (HyperText Transfer Protocol/Secure) — протокол передачи гипертекста.
        - FTP (File Transfer Protocol) — протокол передачи файлов.
        - SMTP (Simple Mail Transfer Protocol) — протокол для передачи электронной почты.
        - DNS (Domain Name System) — система преобразования доменных имен в IP-адреса.
        - MQTT (Message Queuing Telemetry Transport) — протокол мессенджинга для IoT устройств.
        - Это далеко не исчерпывающий список, и существует множество других протоколов для различных специфических задач и сценариев использования.

</details>

---

### Вопрос: [Можно ли убить поток внутри определенного процесса командой kill?] <a name="kill"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Обычно команда kill убивает процессы, а не отдельные потоки. В Linux потоки являются частью процесса и не могут быть убиты независимо от него командой kill.

</details>

---

### Вопрос: [Как отсортировать файл на 100GB с 1GB ОЗУ?] <a name="ozu"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Используйте внешнюю сортировку:
    - Разделите большой файл на меньшие части размером < 1GB.
    - Отсортируйте каждую часть в памяти и сохраните на диск.
    - Объедините отсортированные части, считывая и сравнивая первые элементы каждого файла. 
</details>

---

### Вопрос: [Что такое микросервисы?] <a name="micro"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Микросервисы — это подход к разработке программного обеспечения, при котором большое приложение разбивается на меньшие, автономные компоненты. 
    Каждый микросервис представляет собой отдельный модуль, который реализует определенный функционал и может работать независимо от других модулей. 
    Эти модули обычно взаимодействуют друг с другом через API или событийно-ориентированную архитектуру.

</details>

---

### Вопрос: [Какие преимущества у микросервисной архитектуры по сравнению с монолитом? А какие недостатки?] <a name="micro1"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Преимущества:
        - Гибкость: Можно использовать разные технологии и языки программирования для разных микросервисов.
        - Масштабируемость: Легче масштабировать отдельные компоненты.
        - Распределение работы: Разные команды могут работать над разными сервисами параллельно.
        - Быстрый цикл разработки: Изменения в одном микросервисе могут быть развернуты независимо от других.
        
    - Недостатки:
        - Сложность: Взаимодействие между микросервисами может стать сложным и трудным для управления.
        - Проблемы с данными: Труднее обеспечить консистентность данных между сервисами.
        - Сложность тестирования: Тестирование может быть сложнее, особенно для сценариев, которые требуют взаимодействия между множеством сервисов.
</details>

---

### Вопрос: [Что использовать для трассировки сервисов? Для мониторинга? А для логирования?] <a name="trac-log"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Трассировка: Jaeger, Zipkin.
    - Мониторинг: Prometheus, Grafana, Zabbix.
    - Логирование: ELK Stack (Elasticsearch, Logstash, Kibana), Grafana Loki.
</details>

---

### Вопрос: [Как быть с консистентностью данных между несколькими микросервисами?] <a name="micro2"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Консистентность данных в микросервисной архитектуре — сложная задача. Один из подходов — использование распределенных транзакций, но это может привести к проблемам производительности и доступности. 
      Другой подход — "eventual consistency", где система стремится обеспечить консистентность данных в течение некоторого времени. 
      Для этого часто используют шины сообщений и системы очередей, такие как Kafka или RabbitMQ, чтобы синхронизировать данные между сервисами.
</details>

---

### Вопрос: [Что такое сине-зеленый деплой (Blue-Green Deployment)?] <a name="blue-green"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Сине-зеленый деплой — это метод развертывания приложений, при котором создается полностью независимое окружение (зеленое), идентичное текущему
    продуктивному(синему). После проверки новой версии приложения в зеленом окружении, трафик переключается на это окружение, сделав его новым продуктивным. 
    Этот метод позволяет мгновенно откатываться к предыдущей версии, если что-то пошло не так, так как синее окружение остается нетронутым.
    
    Преимущества:
      - Быстрый откат: Если в новой версии есть проблемы, можно быстро вернуться к старой версии.
      - Нулевое время простоя: Переключение трафика происходит мгновенно, что исключает простои.
</details>

---

### Вопрос: [Что такое системы оркестрации контейнеров?] <a name="container"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Системы оркестрации контейнеров, такие как Kubernetes, Docker Swarm или Mesos, используются для автоматизации развертывания, масштабирования 
      и управления контейнеризованными приложениями.

    Для чего они нужны:
      - Автоматизация развертывания: Один раз описав как должен работать ваш сервис, вы можете автоматически развернуть его на любом числе машин.
      - Масштабирование: Вам не нужно вручную добавлять или удалять контейнеры. Оркестратор может делать это автоматически, в зависимости от нагрузки.
      - Балансировка нагрузки: Оркестраторы могут автоматически распределять входящий трафик между контейнерами одного сервиса.
      - Высокая доступность: Оркестраторы могут перезапускать упавшие контейнеры и перемещать их между хостами.
      - Обновление и откат: Оркестраторы могут обновлять приложения с минимальными простоями, а также откатывать их до предыдущих версий.

    Эти возможности делают системы оркестрации ключевым компонентом для современных облачных и микросервисных архитектур.
</details>

---

### Вопрос: [Какая разница между реляционными vs не реляционными СУБД?] <a name="sql"></a>

<details>
  <summary>Ответ <- Click</summary>

    - SQL:
        Плюсы:
          - Строгая схема: Помогает в поддержании целостности данных.
          - ACID-свойства: Поддержка транзакций с гарантированной Атомарностью, Согласованностью, Изолированностью и Долговечностью.
          - SQL: Богатый язык запросов, хорошо подходящий для сложных запросов.
          - Широкая поддержка: Огромное сообщество, много документации и инструментов.
          - Зрелость: Проверенные временем, надежные решения.
        Минусы:
          - Горизонтальное масштабирование: Обычно сложнее масштабировать горизонтально по сравнению с NoSQL.
          - Сложность: SQL и реляционные схемы могут быть сложными для новичков.
          - Стоимость: Коммерческие решения могут быть дорогими.

    - NoSQL:
        Плюсы:
          - Масштабируемость: Обычно проще масштабировать горизонтально.
          - Гибкость схемы: Можно легко добавлять поля в данные.
          - Высокая производительность: Оптимизированы для больших данных и реального времени.
          - Разнообразие моделей данных: ключ-значение, документ-ориентированные, колоночные и графовые базы данных.
        Минусы:
          - Недостаток стандартизации: Множество разных систем с разными API.
          - Сложность: Распределенные системы приносят собой сложности в управлении и обслуживании.
          - Недостаточная поддержка транзакций: Не все NoSQL-системы поддерживают ACID-транзакции.
        
    - Когда выбрать NoSQL?
        - При необходимости горизонтального масштабирования.
        - Когда схема данных непостоянна или развивается со временем.
        - Для больших данных и обработки в реальном времени.

    - Какие NoSQL решения знаешь?
        - MongoDB, Cassandra, Redis, и Couchbase.
        
    - Трудности при работе с NoSQL:
        - Сложность управления распределенной системой.
        - Отсутствие стандартизированного языка запросов, как SQL.
        - Вопросы консистентности данных, особенно в распределенных системах.
</details>

---

### Вопрос: [Что такое рефлексия?] <a name="reflex"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Рефлексия в программировании — это механизм, который позволяет программам исследовать информацию о типах и структурах данных во время выполнения. 
      В Go рефлексия основана на двух ключевых типах: Type и Value, которые определены в пакете reflect.
      
    С помощью рефлексии можно:
      - Определять тип переменной во время выполнения.
      - Исследовать структуры и их поля, интерфейсы, значения массивов и множество других аспектов данных.
      - Создавать новые значения, изменять их и вызывать методы на них динамически.

    Зачем это нужно?
    Рефлексия часто используется в ситуациях, где типы данных неизвестны до времени выполнения. Например, она полезна при работе с библиотеками для маршалинга
    и анмаршалинга данных (например, JSON, XML), создании ORM, фреймворков для тестирования и многом другом.

    Осторожно!!!
    Несмотря на свою мощь, рефлексию следует использовать осторожно:
      - Производительность: Рефлексивные операции обычно медленнее, чем их нерефлексивные аналоги.
      - Читаемость кода: Рефлексия может сделать код сложнее для понимания и поддержки.
      - Типобезопасность: Рефлексия может привести к ошибкам во время выполнения из-за неправильного использования типов или несуществующих полей/методов.

    Таким образом, рефлексия — мощный, но "острый" инструмент, и его следует использовать разумно.
</details>

---

### Вопрос: [Что такое асинхронность?] <a name="async"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Вычисления в системе могут идти двумя способами:
        - синхронно - это когда код выполняется последовательно;
        - асинхронно - это когда операцию мы можем выполнять не дожидаясь результата на месте. Обычно подразумевается, что операция может быть выполнена кем-то на стороне.
</details>

---

### Вопрос: [Что такое параллельность?] <a name="paralel"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Вычисления будут являться параллельным только в том случае, если они выполняются одновременно. 
      Как пример можно привести процесс ремонта в доме. У нас есть несколько мастеров-универсалов, 
      каждый из которых выполняет работы на своем объекте под ключ. При этом производительность мастеров не зависит друг от друга, 
      так как их работа не пересекается.
</details>

---

### Вопрос: [Что такое конкурентность?] <a name="concurency"></a>

<details>
  <summary>Ответ <- Click</summary>

    - Конкурентность обеспечивает выполнение нескольких задач посредством переключения контекста. 
      Конкурентные вычисления реализуются на одном ядре системы. Как пример приведем тот же процесс ремонта, но с другими вводными условиями. 
      Теперь мы имеем один объект, на который привлекаем специалистов разного профиля: по демонтажным работам, электрике, подготовке стен и полов, отделке. 
      При этом у нас часто возникают ситуации, когда хозяин уже в процессе подготовки стен, решает, что вот эта стена ему все же не нужна, и на сцену опять выходят демонтажники. 
      Такой процесс организации работ можно назвать конкурентным, так как наши мастера уступают место друг другу, одновременно клеить обои и ломать стены они не могут.
</details>

---

### Вопрос: [] <a name=""></a>

<details>
  <summary>Ответ <- Click</summary>

    - текст

</details>

---

