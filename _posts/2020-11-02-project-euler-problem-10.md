---
title:  "Project Euler Problem - 10"
date:   2020-11-02 18:41:35 +0300
tages: [project euler c# problems problem 10]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 10**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem10.cs)

# Problem 10
The sum of the primes below 10 is 2 + 3 + 5 + 7 = 17.

Find the sum of all the primes below two million.
<br>[Problem 10](https://projecteuler.net/problem=10)

## Çözüm Yorumum
- Burada bize verilen; Alıştığımız asal sayılarla işlemler, 10'a kadar olan asalların toplamından bahsetmiş.
- Bizden istediği; 2 Milyon'un altında olan tüm asal sayıların toplamını soruyor.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım **893.511** saniye sürdü.
- Sonuç **142913828922**

![return](https://i.imgur.com/rxeLWM2.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();
long toplam = 0;
int sayi = 2;

bool asalmi(int x)
{
    int bolen_sayisi = 0;
    bool kontrol = false;

    for (int i = 1; i <= x; i++)
    {
        if (x % i == 0)
        {
            bolen_sayisi++;
        }
        if (bolen_sayisi > 2)
        {
            break;
        }
    }
    if (bolen_sayisi == 2)
    {
        kontrol = true;
    }
    return kontrol;
}

while (sayi < 2000000)
{
    if (asalmi(sayi))
    {
        toplam += sayi;
        sayi++;
        Console.WriteLine("{0}", toplam);
    }
    else
    {
        sayi++;
    }

}

clock.Stop();
Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
}
```