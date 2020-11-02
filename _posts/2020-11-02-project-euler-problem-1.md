---
title:  "Project Euler Problem - 1"
date:   2020-11-02 13:26:56 +0300
tages: [project euler c# problems]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısma hoşgeldiniz. Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem1.cs).

# Problem 1
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all the multiples of 3 or 5 below 1000.
<br>[Problem 1](https://projecteuler.net/problem=1).

## Çözüm Yorumum
- Bizden istediği 1000'e kadar olan doğal sayılar arasından 3 ve 5'in katlarını toplamamız.
- Alttaki kod bloğunda basit bir şekilde 1000e kadar çıkarken 3 yada 5'in katı olan sayıları genel toplamımıza ekliyoruz.
- Hangi sayıyı eklediğimizi ve en son toplamı ekrana yazdırıyoruz.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım 0.168 saniye sürdü.
- Sonuç **233168**

![return](https://i.imgur.com/M7XiDaq.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();
    int toplam = 0;
        for (int i = 0; i < 1000; i++)
        {
            if (i % 3 == 0 || i % 5 == 0)
            {
                Console.WriteLine("{0}", i);
                toplam += i;
            }
        }
clock.Stop();

Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
Console.WriteLine("{0}", toplam);
}
```