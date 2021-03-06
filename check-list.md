0. Техническое
    
    Java core
    --

    0. Коллекции.
        0. Карта Map
            - Какие типы в Java вы знаете
                * [ ] HashMap
                * [ ] LinkedHashMap
                * [ ] TreeMap
                * [ ] HashTable
            - Какая разница между типами
                * [ ] HashMap не является синхронизированным и потокобезопасным, допускает хранение null ключей и значений
                * [ ] LinkedHashMap расширяет HashMap, хранит связанный список элементов в порядке вставки
                * [ ] TreeMap не является синхронизированным и потокобезопасным, допускает хранение null ключей(отсортированы, естественный порядок или компаратор не позволяет использовать null), не допускает хранение null значений
                * [ ] Hashtable является синхронизированным и потокобезопасным, не допускает хранение null ключей и значений, не допускает дублей ключей
            - Какой тип когда предпочтительнее использовать
                * [ ] HashMap в большинстве случаев
                * [ ] LinkedHashMap если необходим порядок вставки
                * [ ] TreeMap если необходима сортировка ключей
                * [ ] Hashtable при многопоточности
            - Характеристики ключа в HashMap/TreeMap, особенности hash
                * [ ] При добавлении новой пары ключ-значение, вычисляет хеш-код ключа, на основании которого вычисляется номер корзины (номер ячейки массива), в которую попадет новый элемент.
        0. Набор Sets
            - какие типы в Java вы знаете
                * [ ] HashSet
                * [ ] LinkedHashSet
                * [ ] SortedSet
                * [ ] TreeSet
        0. Списки List
            - какие типы в Java вы знаете
                * [ ] ArrayList
                * [ ] LinkedList
                * [ ] Vector
            - какая разница между типами
                * [ ] ArrayList реализацией (динамического массива перераспределения), производительность (вставка в конец)
                * [ ] LinkedList реализацией (двусвязный список), производительность (вставка в середину)
                * [ ] Vector синхронизирован, содержит много устаревших методов, которые не являются частью структуры коллекций.
            - Какой тип когда предпочтительнее использовать
                * [ ] ArrayList в большинстве случаев
                * [ ] LinkedList когда будут вставки в середину списка
                * [ ] Vector нужны устаревшие методы
        0. Очередь Queue
            - какие типы в Java вы знаете
                * [ ] Queue
                * [ ] Deque
                * [ ] Stack
                * [ ] PriorityQueue (senior level)
    0. Многопоточность Multi-threading
        0. Какова цель? Бывают ли случаи, когда производительность снижается? Что такое потокобезопасный код?
            * [ ] Повышение производительности.
            * [ ] Бывают.
            * [ ] Обеспечивает правильный доступ нескольких потоков к разделяемым данным.
        0. Способы создания потоков в Java
            * [ ] new MyFirstThread().start();
            * [ ] ThreadPoolExecutor — пул потоков, который содержит фиксированное количество потоков. Также этот пул можно создать с использованием конструктора через ключевое слово new.
            * [ ] Executors.newCachedThreadPool() возвращает пул потоков, если в пуле не хватает потоков, в нем будет создан новый поток.
            * [ ] Executors.newSingleThreadExecutor()  — пул потоков, в котором есть только один поток.
            * [ ] ScheduledThreadPoolExecutor  — пул потоков позволяет запускать задания с определенной периодичностью или один раз по истечении промежутка времени. 
        0. Проблемы использования
            * [ ] deadlocks(взаимная блокировка) - потоки блокируют друг друга при обращении к совместно используемым ресурсам.
            * [ ] race condition(состояние гонки) - работа системы или приложения зависит от того, в каком порядке выполняются части кода.
            * [ ] livelock(активная блокировка) - действие одного потока, является ответом на событие из другого потока и не могут продвинуться дальше в своём выполнении.
            * [ ] starvation(голодание) - поток не может получить доступ к совместно используемым ресурсам и не может продвинуться в своём выполнении дальше.
        0. Что может помочь
            - Подход стандартный
                * [ ] synchronize(синхронизировать) блоки синхронизации
                * [ ] immutability(неизменность) использование неизменяемых (immutable) классов
                * [ ] Модификатор volatile (всегда будет атомарно читаться и записываться, не будет помещать ее в кэш)
                * [ ] lock-free collections(не блокирующие коллекции, потокобезопасные) ConcurrentXXX
                * [ ] blocking queue(блокирующие очереди)
                * [ ] atomic operations(атомарные операции)
            - Мониторы, более точные инструменты (senior level)
                * [ ] read-write lock(блокирование на операции чтения записи)
                * [ ] semaphore(утилита синхронизации семафоры)
                * [ ] cyclic barriers(утилита синхронизации барьеры)
                * [ ] count down latch(утилита синхронизации обратный отсчет)
        0. fork-join/map-reduce
            * [ ] fork/join фреймворк для упрощения распараллеливания рекурсивных задач
            * [ ] map-reduce шаблон проектирования на первом шаге выполняются (параллельные) операции над набором, на втором шаге результаты первого шага объединяются
        0. futures
            * [ ] FutureTask
            * [ ] ForkJoinTask
            * [ ] RecursiveTask
            * [ ] RecursiveAction
        0. Timer vs ScheduledThreadPoolExecutor (senior level)
        0. Java 8 Concurrent collections
            * [ ] набор коллекций, более эффективно работающие в многопоточной среде
            * [ ] используются блокировки по сегментам данных или же оптимизируется работа для параллельного чтения данных по wait-free алгоритмам
        0. ForkJoinPool
            * [ ] представляет собой точку входа для запуска корневых (main) ForkJoinTask задач
            * [ ] подзадачи запускаются через методы задачи, от которой нужно отделить (fork)
    0. Exceptions
        0. Какие типы в Java вы знаете
            * [ ] Exception(checked): ArrayIndexOutOfBoundsException, NullPointerException
            * [ ] RuntimeException(unchecked): IOException, FileNotFoundException
            * [ ] Error(unchecked): StackOverflowError, NoClassDefFoundError
        0. Как их использовать?
            * [ ] Exception - нужно обрабатывать в коде программы
            * [ ] RuntimeException - можно обрабатывать в коде
            * [ ] Error - не обрабатываются, но можно
        0. Работа с ошибками: C-style vs Exceptions?
            * [ ] exit(код ошибки)
            * [ ] вернуть из функции код ошибки, проверять результат работы функции
            * [ ] прервать работу программы вызовом исключения, конструкции по обработке исключительных ситуаций
    0. Управление памятью
        0. Garbage collector.
            - Что это. Для чего это?
                * [ ] Сборщик мусора
                * [ ] Освобождает память от неиспользуемых объектов
            - Утечки памяти. Когда это происходит, как это предотвратить.
                * [ ] в куче присутствуют объекты, которые больше не используются, но сборщик мусора не может удалить их из памяти
                * [ ] static поля имеют срок службы, который обычно соответствует всему времени жизни запущенного приложения. Минимизировать использование
                * [ ] не закрытые и не используемые ресурсы. Зарывать ресурсы после окончания использования
                * [ ] неправильные equals() и hashCode() реализации
                * [ ] внутренние классы, которые ссылаются на внешние классы. Рассмотреть возможность превращения его в класс static
                * [ ] переопределён метод finalize(). Не переопределять метод
            - поколения, алгоритм сборки, отличия между java 6 and 8 (senior level)
                * [ ] New (Yang) Generation - объекты, которые считаются короткоживущими
                * [ ] Old Generation (Tenured) - объекты считаются долгоживущими
                * [ ] Алгоритм GC исходит из того предположения, что большинство java-объектов живут недолго. От них необходимо довольно оперативно избавляться, это происходит в New Generation. После создания объект попадает в New Generation и имеет шанс попасть в Old Generation по прошествии некоторого времени
                * [ ] G1 Garbage Collector, Parallel Garbage Collector
        0. Жизненный цикл объектов в Java. (senior level)
            - что делать в finalize? способность воскресить объект?
                * [ ] finalize вызывается в момент, когда сборщик мусора начинает утилизировать объект
                * [ ] предназначен этот метод для автоматического освобождения системных ресурсов, занимаемых объектом
                * [ ] объект с переопределенным методом finalize, помещается в очередь, которая обрабатывается специально созданным для этого потоком, может быть никогда не вызван
                * [ ] воскресить объект можно присвоив this какой-нибудь переменной
    0. Функции Java (главным образом senior level)
        0. Клонируемый(cloneable)
            * [ ] создание копии объекта и его полей
        0. Сериализуемый(serializable)/внешний(externalizable)
            * [ ] serializable - сериализует весь объект
            * [ ] externalizable - полностью контролируемый процесс сериализации
        0. Конструкторы по умолчанию(default constructors), статические конструкторы(static constructors)
            * [ ] default constructors - создаётся автоматически, если не указан не один конструктор
            * [ ] static constructors -
           ```java
            class Foo { static {} }
           ```
        0. Загрузчики классов(class loaders)
        0. Рекомендации Phantom/Soft/Weak. (очень необязательно)
            * [ ] GC помещает этот объект в специальную очередь(ReferenceQueue).
            * [ ] SoftReference — если GC видит что объект доступен только через цепочку soft-ссылок, то он удалит его из памяти. Потом. Наверно.
            * [ ] SoftReference - особенность, что JVM сама следит за тем нужно удалять из памяти объект или нет. И если осталось мало памяти, то объект будет удален. Используется для кэширования больших объёмов данных.
            * [ ] WeakReference — если GC видит что объект доступен только через цепочку weak-ссылок, то он удалит его из памяти.
            * [ ] WeakReference — алгоритм попадания в очередь, как у SoftReference. Используется для кэширования и цепочек связанных между собой объектов.
            * [ ] PhantomReference — если GC видит что объект доступен только через цепочку phantom-ссылок, то он его удалит из памяти. После нескольких запусков GC.
            * [ ] PhantomReference — имеет смысл использовать только вместе с ReferenceQueue. GC добавит phantom-ссылку в ReferenceQueue после того как выполниться метод finalize().
        0. new Long(ANY_NUMBER) vs Long.valueOf(ANY_NUMBER), сравнение обёрток для примитивов, auto-boxing.
            * [ ] valueOf - использует кэширование значения от -128 до 127
            * [ ] переменной класса-обертки можно присваивать значение примитивного типа
            * [ ] переменной примитивного типа можно присваивать объект класса-обертки
        0. String.intern()
            * [ ] при интернировании строк можно получить преимущество в использовании памяти
            * [ ] при использовании в памяти создаётся один экземпляр последовательности символов строки, независимо от того, сколько раз на эту последовательность ссылаются
            