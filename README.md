# C-Sharp-snippets
Some interesting examples

## Method extension for LINQ
```csharp
using System;
using System.Collections.Generic;
using System.Linq;

namespace ConsoleApp4
{
    class Program
    {
        static void Main(string[] args)
        {
            int[] arr = new int[] { 34, 9, 7, 0, 18, 99, 1, 2, 5, 3, 25, 41, 6 };

            var res = arr.MyEnum(x => x % 2 == 0);


            Console.ReadLine();
        }
    }


    public static class MyExtensions
    {
        public static IEnumerable<T> MyEnum<T>(this IEnumerable<T> source, Func<T, bool> predicate)
        {
            int i = 0;
            foreach (var element in source)
            {
                if (predicate(element))
                {
                    yield return element;
                }

                i++;
            }
        }
    }
}
```
