---
title:  "Project Euler Problem - 7"
date:   2020-11-02 14:38:35 +0300
tages: [project euler c# problems problem 7]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 7**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem7.cs)

# Problem 7
By listing the first six prime numbers: 2, 3, 5, 7, 11, and 13, we can see that the 6th prime is 13.

What is the 10 001st prime number?
<br>[Problem 7](https://projecteuler.net/problem=7)

## Çözüm Yorumum
- Burada bize verilen; Asal sayılar ve 6. asal sayının 13 olduğundan bahsetmiş.
- Bizden istediği; 10001.Asal sayının ta kendisini istiyor.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım **20.152** saniye sürdü.
- Sonuç **104743**

![return](https://i.imgur.com/As5yK3f.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();

int asalmi = 1;
int bolen_sayisi = 0;
int maxasal = 0;
int count = 1;
do
{
    bolen_sayisi = 0;
    asalmi++;
    for (int i = 1; i <= asalmi; i++)
    {
        if (asalmi % i == 0)
        {
            bolen_sayisi++;
        }
    }
    if (bolen_sayisi > 2)
    {
    }
    else
    {
        Console.WriteLine("{0}.asal {1}", count, asalmi);
        maxasal = asalmi;
        count++;
    }
    if (count == 10002)
    {
        break;
    }
} while (true);

clock.Stop();
Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
}
```