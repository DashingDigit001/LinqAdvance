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
想從陣列中取得多少物件

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
想從陣列中取得特定條件下的物件

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
想從陣列中跳過多少物件

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
想從陣列中跳過特定條件下的物件
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
如何將兩個Table(或陣列)合併處理
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
決定陣列中物件的(升序)
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
決定陣列中物件的(降序)
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

- Select  
  依照你的條件指定陣列中的元素 

  ```C#
    private class Person
          {
              public string Name { get; set; }
              public int Age { get; set; }
          }
    private static void Sample_Select_Lambda_Objects()
          {
              Person[] persons = {
          new Person { Name = "Mike", Age = 25 },
          new Person { Name = "Joe", Age = 43 },
          new Person { Name = "Nadia", Age = 31 }
      	};
  
              var result = persons.Select(p => p.Name);
  
              Console.WriteLine("只要顯示person Name");
              foreach (string person in result)
                  Console.WriteLine(String.Format("My name is {0}", person));
          }
  ```

- Where  
  依照你的條件篩選陣列中的元素 

  ``` c#
   private class Person
          {
              public string Name { get; set; }
              public int Age { get; set; }
          } 
   private static void Sample_Where_Lambda_Objects()
          {
              Person[] persons = {
          new Person { Name = "Mike", Age = 25 },
          new Person { Name = "Joe", Age = 43 },
          new Person { Name = "Nadia", Age = 31 }
          };
  
              var result = persons.Where(p => p.Age >= 31);
  
              Console.WriteLine("Finding persons who are 30 years old or older:");
              foreach (Person person in result)
                  Console.WriteLine(String.Format("{0}: {1} years old", person.Name, person.Age));
          }
  ```

- FirstOrDefault  
  取出陣列中第一個值

```c#
  private static void Sample_FirstOrDefault_Lambda()
        {
            string[] countries = { "Denmark", "Sweden", "Norway" };
            string[] empty = { };

            var result = countries.FirstOrDefault();

            var resultEmpty = empty.FirstOrDefault();

            Console.WriteLine("First element in the countries array contains:");
            Console.WriteLine(result);

            Console.WriteLine("First element in the empty array does not exist:");
      		Console.WriteLine(resultEmpty == null);
  		}
```

- ToList  
  將陣列轉成List

```C#
private static void Sample_ToList_Lambda()
        {
            string[] names = { "Brenda", "Carl", "Finn" };

            List<string> result = names.ToList();

            Console.WriteLine(String.Format("names is of type: {0}", names.GetType().Name));
            Console.WriteLine(String.Format("result is of type: {0}", result.GetType().Name));
        }
```

