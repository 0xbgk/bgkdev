---
title:  "Project Euler Problem - 4"
date:   2020-11-02 14:12:35 +0300
tages: [project euler c# problems problem 4]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 4**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem4.cs)

# Problem 4
A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 × 99.

Find the largest palindrome made from the product of two 3-digit numbers.
<br>[Problem 4](https://projecteuler.net/problem=4)

## Çözüm Yorumum
- Burada bize verilen; bir Palindromic sayının her iki taraftanda simetrik olarak aynı olduğunu söylemiş.
- Bizden istediği; 3 Digit 2 sayı için oluşturabilecekleri en büyük Palindromic sayıyı istemiş.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım **1.903** saniye sürdü.
- Sonuç **906609**

![return](https://i.imgur.com/mZ8VtMV.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();
int carpim = 0;
string hesapla;
int hesapla_uzunluk;
int buyuk = 1;

for (int x = 1; x < 1000; x++)
{
    for (int z = 1; z < 1000; z++)
    {
        carpim = (x * z);

        hesapla = carpim.ToString();
        hesapla_uzunluk = hesapla.Length;

        if (carpim.ToString().Length % 2 == 0)
        {
            string ilk_parca, son_parca;
            ilk_parca = hesapla.Substring(0, hesapla_uzunluk / 2);
            son_parca = new string(hesapla.Substring(hesapla_uzunluk / 2, hesapla_uzunluk / 2).ToCharArray().Reverse().ToArray());

            if (Convert.ToInt32(ilk_parca) == Convert.ToInt32(son_parca))
            {
                Console.WriteLine("{0}, {1}", x, z);
                if (buyuk < carpim)
                {
                    buyuk = carpim;
                }
                Console.WriteLine("{0}", buyuk);
            }
        }
    }
}

clock.Stop();
Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
}
```