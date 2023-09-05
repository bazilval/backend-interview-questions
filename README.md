# Go Interview Questions
Идея данного репозитория возникла во время подготовки к собеседованиям на позицию Backend разработчика на языке Go.  
В данном Readme собраны частые и не очень вопросы и ответы к ним. Они условно делятся на общие вопросы и вопросы непосредственно по самому языку Go.

Настоятельно рекомендую, прежде чем открывать ответ на вопрос попробовать ответить на него самостоятельно.

---

# Категории вопросов

<!-- Golang -->
<details>
  <summary>Golang</summary>  

- <details>
    <summary>Общая информация</summary>  

    - [Расскажи кратко о языке Go](#go-intro)
    - [Как реализовано хранилище памяти в Go?](#go-store)
    - [Какие типы данных есть в языке Go?](#go-types)
    - [Что такое пакеты в go?](#package)
    - [Что такое глобальная переменная?](#global)
    - [Что такое константы и можно ли их изменять?](#const)
    - [Зачем фигурные скобки с не объявленным оператором внутри функции?](#scope)
    - [В go есть оператор switch case, можно ли выполнить несколько условий в одном объявленном операторе?](#switch)
    - [Что такое iota?](#iota)
    - [Как вручную задать количество процессоров для приложения?](#process)
    - [Как принудительно переключить контекст?](#contekst)
    - [Что такое graceful shutdown?](#gracefull)
    - [Что обозначает * и &?](#pointers)
    - [Как происходит передача параметров в функцию?](#func-args)
    - [Есть ли особенности поведения при передаче map и slice в функцию?](#map-slice-args)
    - [Как функции делятся памятью?](#func-storage)
  </details>

- <details>
    <summary>Численные типы</summary>  

    - [Какие численные типы есть?](#ints)
    - [Какой результат получим если разделить int на 0 и float на 0?](#division)
  </details>

- <details>
    <summary>Строки</summary>  

    - [Что представляют собой строки в go?](#go-str)
    - [Как преобразовать строку в int и наоборот? Можно ли сделать int(string) и string(int) соответственно?](#str-int)
  </details>

- <details>
    <summary>Интерфейсы</summary>  

    - [Интерфейсы: Что такое интерфейс в Go? Зачем нужен на практике? Примеры задач где стоит ввести?](#interface)
    - [Что такое пустой интерфейс?](#nil-interface)
    - [Как устроен внутри nil интерфейс vs nil внутри интерфейса?](#nil-interface1)
    - [Как определить тип интерфейса?](#interface-type)
    - [В каком пакете лучше объявлять интерфейсы и почему?](#interface-package)
  </details>

- <details>
    <summary>Массивы и слайсы</summary>  

    - [Что такое слайс и чем он отличается от массива?](#slice)
    - [Какой размер массива выделяется под слайс при его расширении за рамки его емкости?](#arr-slice)
  </details>

- <details>
    <summary>Map</summary>  

    - [Как реализована map(карта) go?](#map)
    - [Почему нельзя брать ссылку на значение, хранящееся по ключу в map?](#map1)
    - [Что такое эвакуация, и в каком случае она будет происходить?](#map2)
    - [Какие есть особенности синтаксиса получения и записи значений в map??](#map3)
    - [Как происходит поиск по ключу в map?](#map4)
  </details>

- <details>
    <summary>Defer</summary>  

    - [Зачем используется ключевое слово defer в go?](#defer)
    - [Каков порядок возврата при использовании несколько функций с defer в рамках одной внешней функции?](#defer-order)
    - [Как передаются значения в функции, перед которыми указано ключевое слово defer?](#defer-value)
  </details>

- <details>
    <summary>Горутины</summary>  

    - [Что такое поток и горутина?](#goroutin)
    - [Сколько можно запустить потоков и горутин?](#goroutine-count)
    - [Каков минимальный и максимальный вес горутин?](#goroutin-wight)
    - [Что будет если размер горутины превысил допустимый максимум?](#goroutin-wight-max)
    - [Какие есть способы остановить все горутины в приложении?](#goroutin-cancel)
    - [Как наладить связь между горутинами?](#sync-goruotins)
  </details>

- <details>
    <summary>Примитивы синхронизации</summary>  

    - [Какие есть примитивы синхронизации? Расскажи немного про каждый](#primitivs)
    - [Что такое channel?](#channel)
    - [Что такое буферизированный и небуферизированный channel?](#buf-channel)
    - [Какие действия можно произвести с каналом?](#chanel-use)
    - [Что будет если писать/читать в nil channel?](#nil-channel)
    - [Что будет если писать/читать в/из закрытый channel?](#close-channel)
    - [Как закрыть channel? Что с ним происходит?](#close-channel1)
    - [Какие есть инструкции для чтения из channel?](#channel-ass)
  </details>

- <details>
    <summary>Switch/Select/Case</summary>  

    - [Как сделать select неблокирующим?](#select-block)
    - [Какой порядок исполнения операций case в select?](#select-block-case)
  </details>

- <details>
    <summary>Context</summary>  

    - [Что такое context в GO?](#go-context)
    - [Для чего применяется context?](#context-useful)
    - [Чем отличается context.Background от context.TODO?](#ctx-back)
    - [Как передавать значения и вычитывать их из context?](#ctx-val)
    - [Каковы отличия context.WithCancel, context.WithDeadline, context.WithTimeout?](#ctx-deadline)
    - [Как обрабатывать отмену context?](#ctx-cancelation)
  </details>

- <details>
    <summary>Garbage collector</summary>  

    - [Что такое сборщик мусора и по какому алгоритму он реализован в Go?](#garbage)
    - [Расскажите про алгоритм mark and sweep](#mark-sweep)
    - [Когда запускается сборщик мусора?](#gc-time)
    - [Сколько ресурсов потребляет сборщик мусора?](#gc-resource)
  </details>

</details>

---

# Вопросы и ответы

<!-- ОБЩЕЕ -->
<details>
    <summary><h2><i>Общее</i></h2></summary>

---

Вопрос №1: [ Что такое микросервисы? ]

<details>
  <summary>Ответ</summary>

    - Микросервисы — это подход к разработке программного обеспечения, при котором большое приложение разбивается на меньшие, автономные компоненты. 
    Каждый микросервис представляет собой отдельный модуль, который реализует определенный функционал и может работать независимо от других модулей. 
    Эти модули обычно взаимодействуют друг с другом через API или событийно-ориентированную архитектуру.

</details>

---

Вопрос №2: [ Какие преимущества у микросервисной архитектуры по сравнению с монолитом? А какие недостатки? ]

<details>
  <summary>Ответ</summary>

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

Вопрос №3: [ Что использовать для трассировки сервисов? Для мониторинга? А для логирования? ]

<details>
  <summary>Ответ</summary>

    - Трассировка: Jaeger, Zipkin.
    - Мониторинг: Prometheus, Grafana, Zabbix.
    - Логирование: ELK Stack (Elasticsearch, Logstash, Kibana), Grafana Loki.
</details>

---

Вопрос №4: [ Как быть с консистентностью данных между несколькими микросервисами? ] <a name="micro2"></a>

<details>
  <summary>Ответ</summary>

    - Консистентность данных в микросервисной архитектуре — сложная задача. Один из подходов — использование распределенных транзакций, но это может привести к проблемам производительности и доступности. 
      Другой подход — "eventual consistency", где система стремится обеспечить консистентность данных в течение некоторого времени. 
      Для этого часто используют шины сообщений и системы очередей, такие как Kafka или RabbitMQ, чтобы синхронизировать данные между сервисами.
</details>

---

Вопрос №5: [ Что такое сине-зеленый деплой (Blue-Green Deployment)? ]

<details>
  <summary>Ответ</summary>

    - Сине-зеленый деплой — это метод развертывания приложений, при котором создается полностью независимое окружение (зеленое), идентичное текущему
    продуктивному(синему). После проверки новой версии приложения в зеленом окружении, трафик переключается на это окружение, сделав его новым продуктивным. 
    Этот метод позволяет мгновенно откатываться к предыдущей версии, если что-то пошло не так, так как синее окружение остается нетронутым.
    
    Преимущества:
      - Быстрый откат: Если в новой версии есть проблемы, можно быстро вернуться к старой версии.
      - Нулевое время простоя: Переключение трафика происходит мгновенно, что исключает простои.
</details>

---

Вопрос №6: [ Что такое системы оркестрации контейнеров? ]

<details>
  <summary>Ответ</summary>

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

Вопрос №7: [ Что такое рефлексия? ]

<details>
  <summary>Ответ</summary>

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

Вопрос №8: [ Что такое асинхронность? ]

<details>
  <summary>Ответ</summary>

    - Вычисления в системе могут идти двумя способами:
        - синхронно - это когда код выполняется последовательно;
        - асинхронно - это когда операцию мы можем выполнять не дожидаясь результата на месте. Обычно подразумевается, что операция может быть выполнена кем-то на стороне.
</details>

---

Вопрос №9: [ Что такое параллельность? ]

<details>
  <summary>Ответ</summary>

    - Вычисления будут являться параллельным только в том случае, если они выполняются одновременно. 
      Как пример можно привести процесс ремонта в доме. У нас есть несколько мастеров-универсалов, 
      каждый из которых выполняет работы на своем объекте под ключ. При этом производительность мастеров не зависит друг от друга, 
      так как их работа не пересекается.
</details>

---

Вопрос №10: [ Что такое конкурентность? ]

<details>
  <summary>Ответ</summary>

    - Конкурентность обеспечивает выполнение нескольких задач посредством переключения контекста. 
      Конкурентные вычисления реализуются на одном ядре системы. Как пример приведем тот же процесс ремонта, но с другими вводными условиями. 
      Теперь мы имеем один объект, на который привлекаем специалистов разного профиля: по демонтажным работам, электрике, подготовке стен и полов, отделке. 
      При этом у нас часто возникают ситуации, когда хозяин уже в процессе подготовки стен, решает, что вот эта стена ему все же не нужна, и на сцену опять выходят демонтажники. 
      Такой процесс организации работ можно назвать конкурентным, так как наши мастера уступают место друг другу, одновременно клеить обои и ломать стены они не могут.
</details>

---

</details>

<!-- Сеть и всё что с ней связано -->
<details>
    <summary><h2><i>Сеть и всё что с ней связано</i></h2></summary>

---

Вопрос №1: [ В чем отличие протоколов TCP и UDP? ]

<details>
   <summary>Ответ</summary>

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

Вопрос №2: [ Какие еще протоколы существуют? ]

<details>
  <summary>Ответ</summary>

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

</details>

<!-- Операционная система -->
<details>
    <summary><h2><i>Операционная система</i></h2></summary>

---

Вопрос №1: [ Можно ли убить поток внутри определенного процесса командой kill? ]

<details>
  <summary>Ответ</summary>

    - Обычно команда kill убивает процессы, а не отдельные потоки. В Linux потоки являются частью процесса и не могут быть убиты независимо от него командой kill.
</details>

---

</details>

<!-- Базы данных -->
<details>
    <summary><h2><i>Базы данных</i></h2></summary>

---

Вопрос №1: [ Какая разница между реляционными vs не реляционными СУБД? ]

<details>
  <summary>Ответ</summary>

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

</details>

<!-- Golang -->
<details>
    <summary><h2><i>Golang</i></h2></summary>

- <details>
    <summary><h3><i>Общие вопросы по языку Go</i></h3></summary>

     - Вопрос №1:
    
        <details>
          <summary>Ответ</summary>

        - asd
        </details>
  </details>

</details>

<!-- Алгоритмы -->
<details>
    <summary><h2><i>Алгоритмы</i></h2></summary>

---

Вопрос №1: [ Как отсортировать файл на 100GB с 1GB ОЗУ? ]

<details>
  <summary>Ответ</summary>

    - Используйте внешнюю сортировку:
    - Разделите большой файл на меньшие части размером < 1GB.
    - Отсортируйте каждую часть в памяти и сохраните на диск.
    - Объедините отсортированные части, считывая и сравнивая первые элементы каждого файла. 
</details>

---

</details>





<!-- Шаблон -->

---

Вопрос №1:

<details>
  <summary>Ответ</summary>

</details>

---


