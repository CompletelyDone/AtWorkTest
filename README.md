# Тестовое задание для At Work.
### 1. Опишите, что такое инкапсуляция, наследование и полиморфизм. Приведите примеры их применения в коде.<br />
  Инкапсуляция - это паттерн проектирования, при котором программист скрывает детали реализации(например поля и/или методы) от пользователя.<br />
  Наследование - это паттерн проектирования, который служит для сокращения повторяющегося кода путём заимствования полей и методов у родительского класса к дочерним.<br />
  В языке C# можно отнаследоваться только от 1 класса и множества интерфейсов. В C++ есть возможность множественного наследования.<br />
  Полиморфизм - это паттерн проектирования, который позволяет использовать методы, которые можно переопределять.
```
  public class Player(string _title) // Абстрактный класс(Пример наследования)
  {
      private string title = _title; // Приватное поле(Пример инкапсуляции данных)
      public string Title
      {
          get { return title; }
          set { title = value; }
      }
      public virtual void Play() // Виртуальный метод(Пример полиморфизма)
      {
          Console.WriteLine("Воспроизводим что-то");
      } 
  }
```
```
  public class AudioPlayer : Player // Наследование класса(Пример наследования)
  {
      public AudioPlayer(string _title) : base(_title) { }
  
      public override void Play() // Реализация виртуального метода(Пример полиморфизма)
      {
          Console.WriteLine("Воспроизводим аудио");
      }
  }
```
### 2. Опишите, как бы вы восстановили предыдущую версию кода в git после внесения ошибки
 ```
  git init
  echo "Hello World!" > readme.md
  git add .
  git commit -m "Add 'Hello World!'"
  echo "Внесение ошибки" >> readme.md
  git log // Ищем хэш-код коммита без ошибок
  git checkout <хэш-код коммита> // Переходим на коммит без ошибок
```
### 3. Напишите функцию на любом языке, которая проверяет, является ли строка палиндромом
  Я делал задание LeetCode с таким же [вопросом](https://github.com/CompletelyDone/BattleField/blob/master/LeetCode/Palindrome.cs).
```
  public class Palindrome
    {
        public static bool isPalindrome(int x)
        {
            string str = x.ToString();
            var strLen = str.Length;
            int counter = 0;
            int middle = strLen % 2 == 0 ? strLen / 2 : strLen / 2 + 1;
            while(counter <= middle && strLen != 1)
            {
                if (str[counter] != str[strLen - counter - 1]) return false;
                counter++;
            }
            return true;
        }
    }
```
### 4. Кратко расскажите о вашем опыте в IT и поделитесь ссылкой на проекты на GitHub, если они у вас есть.
  3 года пишу на языке C# с момента обучения в колледже. <br />
  Пол года писал на C++. <br />
  Немного писал на Unity(2 Курсовые работы). <br />
  Есть средние знания по вёрстке HTML + CSS <br />
  Последние полгода пишу на React + ASP.net(пишу pet-проекты). <br />

  Ссылка на [репозитории](https://github.com/CompletelyDone?tab=repositories). Там в основном тестовые задания для компаний.
