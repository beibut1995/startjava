> ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) — эта иконка означает, что рядом с ней находится ссылка, содержащая видеоурок


# ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) <a>[Занятие первое](https://drive.google.com/file/d/1l2g_mGPw3XEJ9OyURaXosRVqmeDz4kId/view?usp=sharing)</a>

## Темы занятия
1. [Подготовка рабочего окружения](#1)
1. [Первая программа](#2)
1. [Ручная компиляция и запуск программы](#3)
1. [Этапы компиляции и запуска](#4)
1. [Байт-код](#5)
1. [Переменные: примитивные типы данных](#6)
1. [Ветвление: if, if else](#7)
1. [Циклы: for, while, do while](#8)
1. [Система управления версиями Git](#9)
1. [Настройка локального репозитория](#10)
1. [Домашнее задание](#11)
1. [Советы для тех, кто выполняет домашнее задание](#12)

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 1. <a name="1">[Подготовка рабочего окружения](https://drive.google.com/file/d/1gWrBFrly3BdXKq868Xr0QkGtpM9FCmI4/view?usp=sharing)</a>
- Установите Java SE Development Kit 8:
  - для пользователей [Windows](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
  - для пользователей [Ubuntu Linux](http://help.ubuntu.ru/wiki/java)
- Откройте консоль и введите в ней `java -version`, а затем `javac -version`
- Если при этом возникнет ошибка `"java/javac" не является внутренней или внешней командой, исполняемой программой или пакетным файлом`, то
  - [занесите](https://youtu.be/EEqScHr_bec) в переменную окружения `PATH` полный путь до папки, где хранятся файлы `java` и `javac`. Перезапустите консоль
- Выведите в консоли значение переменной `PATH`: 
  - `echo %PATH%` (в win)
  - `$PATH` (в Linux)
- Убедитесь, что там присутствует путь до указанных выше файлов
- Установите систему контроля версий [Git](http://git-scm.com/downloads)
- Создайте аккаунт на [GitHub](https://github.com/)
- Для удобной навигации по файлам на GitHub установите расширение для браузера — [Octotree](https://habr.com/post/223527/)
- Установите [Sublime Text](https://www.sublimetext.com/3). Именно в нем мы будем писать наши программы
- Что бы табуляция при форматировании вашего кода на GitHub выглядела корректно, воспользуйтесь [этими](http://gearmobile.github.io/sublime-text-tabulation/) рекомендациями (стандарт — один tab равен 4 пробела)
- Для отображения непечатаемых символов (пробелов, табуляции) выполните [эти](https://renotes.ru/post-254/sulbime-text-pokazyvat-nepechatnye-simvoly) настройки

Использовать какую-либо из IDE — запрещено! Консоль, Sublime Text и "голый" Git — ваши лучшие друзья!

**Материалы:**
- [Что такое JDK? Введение в средства разработки Java](https://topjava.ru/blog/what-is-the-jdk)
- [Что такое JRE? Введение в среду выполнения Java](https://topjava.ru/blog/what-is-the-jre)
- [Что такое JVM? Знакомство с виртуальной машиной Java](https://topjava.ru/blog/what-is-the-jvm)
- [Популярность Java-технологий в 2018 году](https://topjava.ru/blog/java-in-2018)

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 2. <a name="2">[Первая программа](https://drive.google.com/file/d/1anXQBZ80wvfzozUNlfhy1wtS-eS50cZi/view?usp=sharing)</a>

Перепишите данный код в Sublime Text:

``` java
public class MyFirstApp {	
    public static void main(String[] args) {
        System.out.println("Hello, world");
    }
}
```
и сохраните его в файле под названием `MyFirstApp.java`

**Материалы:**
- [Обзор и настройка Sublime Text](https://xakep.ru/2014/07/28/sublime-text-not-for-coding/)
- [SublimeText - Terminal Access - Plugin](https://www.youtube.com/watch?v=4hZvb8sr1cE) (youtube)
- [Первая программа на Java – Hello World](http://pr0java.blogspot.com/2015/03/java-hello-world.html)
- ["Hello World!" Application](https://docs.oracle.com/javase/tutorial/getStarted/application/index.html)
- [Java "Hello World" Program](https://www.journaldev.com/481/java-hello-world-program)
- [Java main method](https://www.journaldev.com/12552/public-static-void-main-string-args-java-main-method)

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 3. <a name="3">[Ручная компиляция и запуск программы](https://drive.google.com/file/d/1u0jyGJkFFLUwfj0c21uY2i2louNtIm_3/view?usp=sharing)</a>
Для компиляции и запуска программы необходимо в консоли перейти в папку, в которой находится файл `MyFirstApp.java`, и ввести последовательно следующие команды:
- `javac MyFirstApp.java` — компиляция java-файла
- `java MyFirstApp` — запуск программы

Для того, что бы русский текст корректно отображался в консоли, программы необходимо компилировать с помощью специального ключа:
- `javac -encoding utf8 имя_класса.java`

**Материалы:**
- [Работа с командной строкой Windows](https://www.youtube.com/watch?v=8_tkUJhuogA) (youtube)
- [Введение в командную строку Windows](https://www.youtube.com/user/Iidsp/videos) (youtube)
- [Работа с Java в командной строке](https://habr.com/post/125210/)

## 4. <a name="4">Этапы компиляции и запуска</a>
![levels](https://user-images.githubusercontent.com/29703461/39407954-5ff88c7c-4bd7-11e8-96d6-1456d6673a45.png)

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 5. <a name="5">[Байт-код](https://drive.google.com/file/d/19Tl7dEpPszjQfulzQBEwyn9sQL0DK3ji/view?usp=sharing)</a>
Для отображения байт-кода класса необходимо в консоли перейти в папку, в которой находится файл `MyFirstApp.class`, и написать:
`javap -c -s -verbose MyFirstApp`

**Материалы:**
- [Java байт-код «Hello world»](https://habr.com/post/264919/)
- [javap — Disassembles one or more class files](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/javap.html)

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 6. <a name="6">[Переменные: примитивные типы данных](https://drive.google.com/file/d/1mrsKC-wU7NpxQiNt47rgfySsDGTwB8Wb/view?usp=sharing)</a>

**Материалы:**
- [Переменные в Java](https://vertex-academy.com/tutorials/ru/sozdanie-peremennyx-i-tipy-peremenny/)
- [Примитивные типы данных](http://developer.alexanderklimov.ru/android/java/types.php)
- [Variables](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/variables.html)
- [Primitive Data Types](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)

![var](https://user-images.githubusercontent.com/29703461/39386134-d0843ce6-4a7b-11e8-8a0f-94224b256386.png)

## Все домашние задания показывайте ментору по одному, не копите их!

**Домашнее задание:**
- Создайте класс **Variable** с методом **main**
- Объявите в методе переменные всех существующих в Java примитивных типов данных. Каждой переменной присвойте значение 
- В качестве значений используйте информацию о своем компьютере: количество ядер, частота процессора и тд.
- Выведите все значения переменных на консоль
- Разберитесь с [Git/GitHub](https://github.com/ichimax/startjava/blob/master/lesson%201.md#9), почитайте [рекомендации](https://github.com/ichimax/startjava/blob/master/lesson%201.md#12) о том, как с ними работать
- **Покажите Д/З наставнику**

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 7. <a name="7">[Ветвление: if, if else](https://drive.google.com/file/d/1r-UVn4Z9OhV-SUvJdMrC6EG_v9qowAJS/view?usp=sharing)</a>
![turpal](https://user-images.githubusercontent.com/29703461/39215173-9afa64b4-481f-11e8-9731-fa60a8439f71.jpg)

**Материалы:**
- [Ветвление в Java](https://vertex-academy.com/tutorials/ru/vetvlenie-v-java/)
- [Оператор if else](https://youtu.be/ryR033ld_N0) (youtube)
- [The if-then and if-then-else Statements](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/if.html)

**Домашнее задание:**
- Создайте класс **ConditionalStatement** с методом **main**
- Запишите следующие условия с помощью языка Java
- Используйте переменные и условные операторы
- Выведите сообщения на консоль

``` java
ЕСЛИ(возраст > 20) {
    выведите какое-то сообщение
}

ЕСЛИ(мужскойПол) {
    выведите какое-то сообщение
}

ЕСЛИ(неМужскойПол) {
    выведите какое-то сообщение
}

ЕСЛИ(рост < 1.80) {
    выведите какое-то сообщение
} ИНАЧЕ {
    выведите какое-то сообщение
}

ЕСЛИ(перваяБукваИмени == ‘M’) {
    выведите какое-то сообщение
} ИНАЧЕ ЕСЛИ(перваяБукваИмени == ‘I’) {
    выведите какое-то сообщение
} ИНАЧЕ {
    выведите какое-то сообщение
} 
```
- **Покажите Д/З наставнику**

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 8. <a name="8">Циклы: [for](https://drive.google.com/file/d/1MxaPlSwY6-Nv2zOrQGYy5lOSDjYTfnfU/view?usp=sharing), [while, do while](https://drive.google.com/file/d/1YQHY9C1QbueWYFMRBpHFTqg1wt9N_333/view?usp=sharing)</a>
![loop](https://user-images.githubusercontent.com/29703461/39228479-100883f2-4867-11e8-9d63-5d18e455aaa2.jpeg)

**Материалы:**
- [Циклы в Java](https://vertex-academy.com/tutorials/ru/cikly-v-java/)
- [Оператор while](https://youtu.be/15PjODTSTaw) (youtube)
- [Оператор for](https://youtu.be/UYbdAmgcNVc) (youtube)

**Домашнее задание:**
- Создайте класс **Cycle** с методом **main**
- Выведите на консоль с помощью цикла for все числа от [0, 20]
- Выведите на консоль с помощью цикла while все числа от [6, -6] (шаг итерации равен 2)
- Выведите на консоль с помощью цикла do-while сумму всех нечетных чисел от [10, 20]
- **Покажите Д/З наставнику**

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 9. <a name="9">[Система управления версиями Git](https://drive.google.com/file/d/1IMw7DA_lodW2GueWpU1nMUmYx0pnlPGA/view?usp=sharing)</a>
![image](https://cloud.githubusercontent.com/assets/18701152/15219746/9295a2fe-186d-11e6-876b-c61cc9be71e4.png)

**Материалы:**
  - [Система управления версиями](https://ru.wikipedia.org/wiki/Система_управления_версиями) (wiki)
  - [Базовый курс по обучению Git](https://www.youtube.com/playlist?list=PLIU76b8Cjem5B3sufBJ_KFTpKkMEvaTQR) (youtube)
  - [Git. Быстрый старт](https://www.youtube.com/watch?v=4-NX17Ip-xQ&list=PLmRNNqEA7JoM77hOJkPrLOfJQGizCLR3P) (youtube)
  - [Официальная книга про Git](https://git-scm.com/book/ru/v2)
  - [Git обучалка](https://githowto.com/ru)
  - [Интерактивная Git обучалка (в настройках выберите русский язык)](http://learngitbranching.js.org)
  
## 10. <a name="10">Настройка локального репозитория</a>
- Создайте в удобном для вас месте папку под названием `startjava`. В ней будет храниться ваш код
- Создайте на GitHub репозиторий с названием `startjava`
- Напишите в консоли (при этом консоль должна быть открыта в папке `startjava`): 
  - [`git init`](https://git-scm.com/book/ru/v1/Основы-Git-Создание-Git-репозитория#Создание-репозитория-в-существующем-каталоге)
  - [`git status`](https://git-scm.com/book/ru/v1/Основы-Git-Запись-изменений-в-репозиторий#Определение-состояния-файлов)
  - добавьте адрес созданного репозитория в git — [`git remote add origin url_на_ваш_startjava-репозиторий.git`](https://git-scm.com/book/ru/v1/Основы-Git-Работа-с-удалёнными-репозиториями)
  - проверьте, добавился он или нет — `git remote -v`

## ![video](https://cloud.githubusercontent.com/assets/13649199/13672715/06dbc6ce-e6e7-11e5-81a9-04fbddb9e488.png) 11. <a name="11">[Домашнее задание](https://drive.google.com/file/d/1Svgm_03td3Aj_MeVt-MBqSCv-PEhXD0A/view?usp=sharing)</a>

> Перед отправкой домашнего задания на проверку обращайте внимание на [`Советы для тех, кто выполняет домашнее задание`](https://github.com/ichimax/startjava/blob/master/lesson%201.md#12-советы-для-тех-кто-выполняет-домашнее-задание), которые содержат ряд полезных подсказок и разъяснений
- Прочитайте первую и третью (до стр 84) главы книги [Изучаем Java](https://www.ozon.ru/context/detail/id/7821666/)
- Прочитайте первые две главы книги [Pro Git](https://git-scm.com/book/ru/v2)
- Дополнительные книги:
  - [Программирование на Java для детей, родителей, бабушек и дедушек (есть русский перевод)](http://myflex.org/books/java4kids/java4kids.htm)
  - [Яша учится программировать](https://drive.google.com/file/d/1ukTlzMrFX3Zj8X9TXp6U-mJUH1fOKUED/view?usp=sharing)
- Реализуйте `Калькулятор`, который должен уметь выполнять математические операции (`+, -, *, /, ^, %`) над целыми положительными числами:
  - для проверки знака математической операции воспользуйтесь оператором `if else`
  - выведите на экран результат работы калькулятора с помощью `System.out.println()`
- Напишите игру `Угадай число`:
  - компьютер "загадывает" целое число от 0 до 100, которое вам необходимо угадать
  - после каждой неудачной попытки выводите подсказки: `System.out.println("Введенное вами число больше (меньше) того, что загадал компьютер")`
  - если число угадано — `System.out.println("Вы угадали!")`
  - игра продолжается до тех пор, пока число не будет угадано
- Выведите в цикле символы кодировки [Unicode](https://ru.wikipedia.org/wiki/Юникод) в диапазоне [9398, 10178]. Если выводятся кракозябры, то [33, 126]

## 12. <a name="12">Советы для тех, кто выполняет домашнее задание</a>
### Рекомендации по Git
1. Последовательность стандартных шагов при работе с Git:
   - [`git add Файл_с_кодом.java`](https://git-scm.com/book/ru/v1/Основы-Git-Запись-изменений-в-репозиторий#Отслеживание-новых-файлов) (файлы с расширением class не заносите)
   - [`git commit -m "описание изменений, которые вы внесли в программу"`](https://git-scm.com/book/ru/v1/Основы-Git-Запись-изменений-в-репозиторий#Фиксация-изменений)
   - [`git push -u origin master`](https://git-scm.com/book/ru/v1/Основы-Git-Работа-с-удалёнными-репозиториями#Push)
2. На GitHub отправляйте не только файлы с расширением `*.java`, но и папки, например, `Lesson 1`
3. Если вы хотите в Git добавить папку с файлами, но при этом какие-то файлы требуется проигнорировать (например `*.class`):
   - `git add "Lesson 1"`
   - `git reset "Lesson 1/имя файла, который необходимо проигнорировать"`

### Общие рекомендации по заданию
1. Учитесь грамотно формулировать свой вопрос: "у меня не работает" может иметь тысячи причин
2. Решите ДЗ, используя только те темы, которые изучаются в данном уроке
3. Все задания выполняйте в разных классах
4. Код пишите только **ВНУТРИ** метода `main` (для каждого класса метод `main` будет своим)
5. Ввод с клавиатуры и методы класса `Math` или `Random` пока не используйте
6. Символ `^` используется лишь для обозначения операции возведения в степень, но в Java он выполняет совсем иную функцию. Самостоятельно реализуйте операцию возведения в степень
7. Символ`%`, похожий на проценты, называется [оператором деления по модулю](https://vertex-academy.com/tutorials/ru/delenie-po-modulyu-v-java/). В калькуляторе не надо считать проценты! Считайте остаток от деления с помощью оператора `%`
8. Примерно так должна выглядеть структура ваших файлов и папок

![tree](https://user-images.githubusercontent.com/29703461/47957392-d92daa00-dfc5-11e8-8a5c-c767d0f2fa99.png)

## Немного мотивации
- [Shia LaBeouf Motivation for Coding](https://youtu.be/J1usv2Hn-pU)
- [Мотивация для программистов](https://www.youtube.com/watch?v=NOVaNe3jx6c)
- [Речь Стива Джобса Перед выпускниками Стенфорда](https://www.youtube.com/watch?v=WVz9E7o1mmk)
- [Мотивационный совет от Стива Джобса](https://www.youtube.com/watch?v=Z2qSUZ1o47U)
- [12 минут сильнейшей мотивации. Перелом сознания](https://www.youtube.com/watch?v=69MkvKrraC0)
