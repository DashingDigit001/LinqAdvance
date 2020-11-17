# 專案名稱

LinqEntityFramework

# 簡介

### 語言 : CSharp

### 主旨 :

Linq語法教學

# 快速開始

## 環境建立

1. VisualStudio

## 專案建立

1. 新增專案 -> 主控台應用程式(.NET Core)
2. 在 Program.cs 最上面加入 ```using System.Linq; ```

# 使用範例

-   Take

```C#
    private static void Sample_Take_Lambda()
        {
            int[] numbers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

            var result = numbers.Take(5);

            Console.WriteLine("Takes the first 5 numbers only:");
            foreach (int number in result)
                Console.WriteLine(number);
        }
```

-   TakeWhile

```C#
      private static void Sample_TakeWhile_Lambda()
        {
            int[] numbers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

            var result = numbers.TakeWhile(n => n<3);

            Console.WriteLine("Takes numbers one by one, and stops when condition is no longer met:");
            foreach (int number in result)
                Console.WriteLine(number);
        }
```

-   Skip

```c#
        private static void Sample_Skip_Lambda()
        {
            string[] words = { "one", "two", "three", "four", "five", "six" };

            var result = words.Skip(4);

            Console.WriteLine("Skips the first 4 words:");
            foreach (string word in result)
                Console.WriteLine(word);
        }
```

-   SkipWhile

```c#
     private static void Sample_SkipWhile_Lambda()
        {
            string[] words = { "one", "two", "three", "four", "five", "six" };

            var result = words.SkipWhile(w => w.Length == 3);

            Console.WriteLine("Skips words while the condition is met:");
            foreach (string word in result)
                Console.WriteLine(word);
        }
```

-   Join

```c#
   private static void Sample_Join_Lambda()
        {
            string[] warmCountries = { "Turkey", "Italy", "Spain", "Saudi Arabia", "Etiobia" };
            string[] europeanCountries = { "Denmark", "Germany", "Italy", "Saudi Arabia", "Portugal", "Spain" };

            var result = warmCountries.Join(europeanCountries, d => d, e => e, (d, e) => d);

            Console.WriteLine("Joined countries which are both warm and Europan:");
            foreach (var country in result) // Note: result is an anomymous type, thus must use a var to iterate.
                Console.WriteLine(country);
        }
```

-   OrderBy

```c#
private static void Sample_OrderBy_Lambda_Numbers()
        {
            int[] numbers = { 7, 9, 5 };

            var result = numbers.OrderBy(n => n);

            Console.WriteLine("Ordered list of numbers:");
            foreach (int number in result)
                Console.WriteLine(number);
        }
```

-   OrderByDescending

```c#
private static void Sample_OrderByDescending_Lambda()
        {
            string[] names = { "Ned", "Ben", "Susan" };

            var result = names.OrderByDescending(n => n);

            Console.WriteLine("Descending ordered list of names:");
            foreach (string name in result)
                Console.WriteLine(name);
        }
```
