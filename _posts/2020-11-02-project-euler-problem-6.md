---
title:  "Project Euler Problem - 6"
date:   2020-11-02 14:31:35 +0300
tages: [project euler c# problems problem 6]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 6**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem6.cs)

# Problem 6
The sum of the squares of the first ten natural numbers is,
1 ^ 2 + 2 ^ 2 + ... +10 ^ 2 = 385
The square of the sum of the first ten natural numbers is,
(1 + 2 + ... + 10)^2 = 55 ^ 2 = 3025
Hence the difference between the sum of the squares of the first ten natural numbers and the square of the sum is 3025 − 385 = 2640.
Find the difference between the sum of the squares of the first one hundred natural numbers and the square of the sum.
<br>[Problem 6](https://projecteuler.net/problem=6)

## Çözüm Yorumum
- Burada bize verilen; 1'den 10'a kadar sayıların teker teker kareleri toplamı 385 ve 1'den 10'a kadar sayıların toplamının karesi 3025.
- Bizden istediği; 1'den 100'e kadar olan sayıların toplamının karesinden, 1'den 100'e kadar sayıların teker teker karesinin toplamını çıkarmamızı istiyor.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım **0** saniye sürdü.
- Sonuç **25164150**

![return](https://i.imgur.com/K6yQILJ.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();

double total = 0;
double total_kare = 0;
double tekli_kare = 0;
total = (100 * 101) / 2;
total_kare = Math.Pow(total, 2);
for (int i = 1; i <= 100; i++)
{
    tekli_kare += Math.Pow(i, 2);
}

Console.WriteLine("{0}", total_kare);

Console.WriteLine("----------");

Console.WriteLine("{0}", tekli_kare);

Console.WriteLine("----------");

Console.WriteLine("{0}", total_kare - tekli_kare);

clock.Stop();
Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
}
```