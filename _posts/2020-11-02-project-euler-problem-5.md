---
title:  "Project Euler Problem - 5"
date:   2020-11-02 14:12:35 +0300
tages: [project euler c# problems problem 5]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 5**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem5.cs)

# Problem 5
2520 is the smallest number that can be divided by each of the numbers from 1 to 10 without any remainder.

What is the smallest positive number that is evenly divisible by all of the numbers from 1 to 20?
<br>[Problem 5](https://projecteuler.net/problem=5)

## Çözüm Yorumum
- Burada bize verilen; 2520 sayısı için 1'den 10'a kadar tüm sayılara kalansız bölündüğünden bağsetmiş.
- Bizden istediği; 1'den 20'ye kadar tüm sayılara kalansız bölünen en küçük positif tam sayıyı istemiş.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım **1.502** saniye sürdü.
- Sonuç **232792560**

![return](https://i.imgur.com/LA2jFpj.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();
int a = 1;            
bool kontrol = true;

do
{
    if (a % 1 == 0 &&
        a % 2 == 0 &&
        a % 3 == 0 &&
        a % 4 == 0 &&
        a % 5 == 0 &&
        a % 6 == 0 &&
        a % 7 == 0 &&
        a % 8 == 0 &&
        a % 9 == 0 &&
        a % 10 == 0 &&
        a % 11 == 0 &&
        a % 12 == 0 &&
        a % 13 == 0 &&
        a % 14 == 0 &&
        a % 15 == 0 &&
        a % 16 == 0 &&
        a % 17 == 0 &&
        a % 18 == 0 &&
        a % 19 == 0 &&
        a % 20 == 0)
    {
        kontrol = false;
    }
    else
    {
        a++;
    }
} while (kontrol);

Console.WriteLine("{0}", a);
clock.Stop();
Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
}
```