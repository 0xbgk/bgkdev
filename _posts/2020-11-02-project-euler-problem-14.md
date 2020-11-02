---
title:  "Project Euler Problem - 14"
date:   2020-11-02 19:03:35 +0300
tages: [project euler c# problems problem 14]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 14**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem14.cs)

# Problem 14
The following iterative sequence is defined for the set of positive integers:

n → n/2 (n is even)
n → 3n + 1 (n is odd)

Using the rule above and starting with 13, we generate the following sequence:

13 → 40 → 20 → 10 → 5 → 16 → 8 → 4 → 2 → 1
It can be seen that this sequence (starting at 13 and finishing at 1) contains 10 terms. Although it has not been proved yet (Collatz Problem), it is thought that all starting numbers finish at 1.

Which starting number, under one million, produces the longest chain?

NOTE: Once the chain starts the terms are allowed to go above one million.
<br>[Problem 14](https://projecteuler.net/problem=14)

## Çözüm Yorumum
- Burada bize verilen; Burada hala kanıtlanamamış bir problem var. Bağsettiği şey kısa şekilde bir sayı çift ise **2**'ye bölünerek, tek ise **3** ile çarpılıp **1** eklenecektir. Bu şekilde sürekli devam edilirse en son 1 elde edilir. 1 elde etmede her yapılan işlem 1 chain anlamına geliyor.
- Bizden istediği; Bu verilenlere göre 1 milyonun altında en yüksek chain'i üreten sayıyı istiyor.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım **17.273** saniye sürdü.
- Sonuç **837799** sayımız, **525** chain(525 kere 2'ye bölünmüş yada 3 ile çarpılıp bir eklenmiş) ile en fazla chaini üreten sayı olmuş.

![return](https://i.imgur.com/Ci7FzvA.png)
<br>

```c#
{
Stopwatch clock = Stopwatch.StartNew();
           
int count;
long calc;
long temp = 0;
long tempo = 0;

for (int i = 835000; i <= 837800; i++)
{
    Console.Write(i + "->");

    calc = i;
    count = 0;                

    while (calc > 1)
    {
        if (calc % 2 == 0)
        {
            calc = calc / 2;
            count++;
            Console.Write(calc + "->");
        }

        else
        {
            calc = (calc * 3) + 1;
            count++;
            Console.Write(calc + "->");

        }
    }
    count++;
    Console.WriteLine("// " + count.ToString() + " chain");
    if (count > temp)
    {
        tempo = i;
        temp = count;
    }
}
clock.Stop();

Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds/1000);
Console.WriteLine(tempo.ToString()+" " +temp.ToString() + "max chain");
}
```