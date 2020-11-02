---
title:  "Project Euler Problem - 9"
date:   2020-11-02 18:29:35 +0300
tages: [project euler c# problems problem 9]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 9**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem9.cs)

# Problem 9
A Pythagorean triplet is a set of three natural numbers, a < b < c, for which,

a^2 + b^2 = c^2
For example, 3^2 + 4^2 = 9 + 16 = 25 = 5^2.

There exists exactly one Pythagorean triplet for which a + b + c = 1000.
Find the product abc.
<br>[Problem 9](https://projecteuler.net/problem=9)

## Çözüm Yorumum
- Burada bize verilen; Pythagorean 3'lüsünün tanımını yapmış, tanımda kısaca her A B C sayısı için A < B < C olacak şekilde A ve B'nin karelerinin toplamı C'nin karesinin toplamına eşit olacak.
- Bizden istediği; Böyle sayı 3'lülerinden öyle bir üçlü varmış ki 3'ünün toplamı 1000 edecek, bu sayıların çarpımını istiyor.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım **117.943** saniye sürdü.
- Sonuç **200, 375 ve 400 üçlüsü**.Sırada bulduğu **31875000**

![return](https://i.imgur.com/EB6CrYe.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();
double a, b, c;
a = 1;
b = 1;
c = 1;
double sonuc = 0;
//200,375,425

for (a = 1; a < 1000; a++)
{
    for (b = 1; b < 1000; b++)
    {
        for (c = 1; c < 1000; c++)
        {

            if ((Math.Pow(c, 2) == Math.Pow(a, 2) + Math.Pow(b, 2)) && (a + b + c == 1000))
            {

                Console.WriteLine("{0} , {1}, {2}", a, b, c);
            }
        }
    }
}


sonuc = a * b * c;
clock.Stop();
Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
}
```