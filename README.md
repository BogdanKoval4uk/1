# Лабораторная работа номер 1

## Цели работы:
1. Научиться работать с переменными разных типов данных CTS средствами языка C#.
2. Научиться создавать классы и поля классов, инициализировать свойства классов.
3. Научиться создавать перегруженные конструкторы классов.
4. Научиться создавать тесты для реализованных методов и классов.


## Задания
#### Задание№1
Выведите на консоль минимальные и максимальные значения для предопределенных типов данных CTS.

####№ Выполнение задние номер 1

    using System;    //включаем работу с консолью

    namespace LABA1C_
    {
        internal class Program
        {
            static void Main(string[] args)   //Вход в программу
            {
                Console.WriteLine("Минимальные и максимальные значения предопределенных типов данных CTS:");

                // Целочисленные типы данных
                Console.WriteLine($"byte: min = {byte.MinValue}, max = {byte.MaxValue}");
                Console.WriteLine($"sbyte: min = {sbyte.MinValue}, max = {sbyte.MaxValue}");
                Console.WriteLine($"short: min = {short.MinValue}, max = {short.MaxValue}");
                Console.WriteLine($"ushort: min = {ushort.MinValue}, max = {ushort.MaxValue}");
                Console.WriteLine($"int: min = {int.MinValue}, max = {int.MaxValue}");
                Console.WriteLine($"uint: min = {uint.MinValue}, max = {uint.MaxValue}");
                Console.WriteLine($"long: min = {long.MinValue}, max = {long.MaxValue}");
                Console.WriteLine($"ulong: min = {ulong.MinValue}, max = {ulong.MaxValue}");

                // Типы данных с плавающей точкой
                Console.WriteLine($"float: min = {float.MinValue}, max = {float.MaxValue}");
                Console.WriteLine($"double: min = {double.MinValue}, max = {double.MaxValue}");
                Console.WriteLine($"decimal: min = {decimal.MinValue}, max = {decimal.MaxValue}");

                // Логический тип данных
                Console.WriteLine($"bool: true / false");

                // Символьный тип данных
                Console.WriteLine($"char: min = {char.MinValue}, max = {char.MaxValue}");

                // Структуры
                Console.WriteLine($"DateTime: min = {DateTime.MinValue}, max = {DateTime.MaxValue}");
                Console.WriteLine($"TimeSpan: min = {TimeSpan.MinValue}, max = {TimeSpan.MaxValue}");

                // Тип значений null
                Console.WriteLine($"Nullable<T>: null");

                Console.ReadKey(); //Ожидание ввода пользователем в консоль
            }
        }
    }

 ##### Вывод консоли
 ![image](https://github.com/BogdanKoval4uk/1/blob/main/Снимок%20экрана%202023-09-05%20235249.png)


#### Задание№2
Создайте класс с именем Rectangle.
В теле класса создайте два поля, описывающие длины сторон double side1, side2.
Создайте пользовательский конструктор Rectangle(double sideA, double sideB), в теле которого поля sideA и sideB инициализируются значениями аргументов.
Создайте два private метода, вычисляющие площадь прямоугольника - double CalculateArea() и периметр прямоугольника - double CalculatePerimeter ().
Создайте два свойства double Area и double Perimeter с одним методом доступа get, вызывающим созданные ранее методы.
Напишите программу, которая принимает от пользователя длины двух сторон прямоугольника и выводит на экран периметр и площадь. Покройте тестами методы класса Rectangle.

##### Выполнения задания номер 2

     using System;

     namespace LABA1C__2._0
        {
        class Rectangle
        {
            private double side1;
            private double side2;

            public Rectangle(double sideA, double sideB)
            {
                side1 = sideA;
                side2 = sideB;
            }

            private double CalculateArea()
            {
                return side1 * side2;
            }

            private double CalculatePerimeter()
            {
                return 2 * (side1 + side2);
            }

            public double Area
            {
                 get {  return CalculateArea(); }                 //get - метод, который возвращает значение свойства
            }

            public double Perimeter
            {
                get { return CalculatePerimeter(); }
            }
        }
        class Program
        {
            static void Main()
            {
                Console.WriteLine("Введите длину первой стороны прямоугольника:");
                double sideA = double.Parse(Console.ReadLine());           //parse - конвертация из строки в double

                Console.WriteLine("Введите длину второй стороны прямоугольника:");
                double sideB = double.Parse(Console.ReadLine()); 

                Rectangle rectangle = new Rectangle(sideA, sideB);

                Console.WriteLine($"Площадь прямоугольника: {rectangle.Area}");
                Console.WriteLine($"Периметр прямоугольника: {rectangle.Perimeter}");

                Console.ReadKey();
            }
        }
    }
##### Вывод консоли


#### Задание №3
Создайте классы Point и Figure.
Класс Point должен содержать два целочисленных поля с координатами точки.
Создайте два свойства с одним методом доступа get.
Создайте пользовательский конструктор, в теле которого проинициализируйте поля значениями аргументов.
Класс Figure должен содержать конструкторы, которые принимают от 3-х до 5-ти аргументов типа Point, а также строковое автосвойство для хранения названия фигуры.
Создайте два метода: double LengthSide(Point A, Point B), который рассчитывает длину стороны многоугольника; void PerimeterCalculator(), который рассчитывает периметр многоугольника.
Напишите программу, которая выводит на экран название и периметр многоугольника. Покройте тестами методы класса Figure.

Примечание: Избегайте повторения кода при реализации перегруженных конструкторов, используйте реализованные ранее конструкторы с помощью ключевого слова this.


