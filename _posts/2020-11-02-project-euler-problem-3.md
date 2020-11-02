---
title:  "Project Euler Problem - 3"
date:   2020-11-02 13:55:35 +0300
tages: [project euler c# problems problem 3]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 3**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem3.cs).

# Problem 3
The prime factors of 13195 are 5, 7, 13 and 29.

What is the largest prime factor of the number 600851475143 ?
<br>[Problem 3](https://projecteuler.net/problem=3).

## Çözüm Yorumum
- Burada bize verilen; önce 13195 sayısının asal bölenlerininden bahsetmiş.
- Bizden istediği; 600851475143 bu sayının en büyük asal böleni.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Sonuç **6857**.

![return](https://i.imgur.com/xDsOP3x.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();
bool asalmi(long x)
{
    bool asal = false;
    int bolensayisi = 0;
    for (int i = 1; i <= (x / 2) + 10; i++)
    {
        if (x % i == 0)
        {
            bolensayisi++;
            if (bolensayisi > 2)
            {
                asal = false;

            }
            else
            {
                asal = true;
            }
        }
    }
    return asal;
}

for (long i = 2; i < 300851475143; i++)
{
    if (asalmi(i))
    {

        if (600851475143 % i == 0)
        {
            Console.WriteLine("{0} asallar", i);
        }
    }
}

clock.Stop();
Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
}
```