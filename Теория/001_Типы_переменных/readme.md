## Типы данных

В коде мы используем переменные, что бы хранить в них данные. Считывать и записывать. Переменные есть двух типов и работают они не много по-разному и это надо учитывать. Есть примитивы и есть ссылочные типы. В чем разница?

### 1. Примитивы

Как работают примитивы. Задавая переменную примитивного типа мы резервируем ячейку в памяти и каждый раз при считывании мы используем **значение**, которое храниться в ячейки.

![Целочисленный примитив](/%D0%A2%D0%B5%D0%BE%D1%80%D0%B8%D1%8F/001_%D0%A2%D0%B8%D0%BF%D1%8B_%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D1%8B%D1%85/001_value_type_memory.png)

### 2. Ссылочные типы

Когда мы используем более сложные конструкции для описания типов данных - Классы, которые могут хранить в себе множество примитивов, а так же двух ссылочных типов. При создании экземпляра класса (проще говоря объекта) в памяти тоже резервируется место, но уже куда большее.

![Ссылочный обьект, экземпляр класса Person](/%D0%A2%D0%B5%D0%BE%D1%80%D0%B8%D1%8F/001_%D0%A2%D0%B8%D0%BF%D1%8B_%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D1%8B%D1%85/001_reference_type_memory.png)

При создании объекта в памяти резервируется место достаточное, что бы хранить все примитивы описанные в классе. В памяти создается специального объекта который называется "ссылкой". Ссылка содержит в себе информацию где в памяти зарезервировано место под этот конкретный объект. Отличие в том от примитивов в том, что когда обращаются к переменной то получают **ссылку** вместо самого **значения**. И далее передается ссылка и все места в коде работающие с этой ссылкой используют одно и то же место в памяти.

### 3. Когда это важно?

С переменными в коде можно делать две вещи:

1. Cчитывать значение и использовать в дальнейших операциях.
   В этом случае разницы особо нету, так как нас интересует только значение и мы не меняем его.
2. Изменять значение переменной.
   В этом случае и выявляется самое важное различие этих типов. В случае если значение примитива было сохранено в другую переменную и в последствии изменено, то это никак не влияет на изначальную переменную. В коде была переменная **х = 5** и задекларировали другую переменную под названием **y** и присвоили значение **x**:

   int y = x;

   В этом случае значение (5) переменной **x** скопировалось в переменную **y** и они не как не зависят друг от друга. Та же операция присвоения для перемменых ссылочного типа копирует не сам обьект а только ссылку на него и передает его в другое место.

   Person p2 = p;

   Если в другом месте произойдет изменение обьекта то будет использована ссылка указывающая на изначальное место в пямяти. А значит изменится значение обьекта для всех переменных которые хранят ссылку на обьект, так это один и тот же обьект в памяти.
