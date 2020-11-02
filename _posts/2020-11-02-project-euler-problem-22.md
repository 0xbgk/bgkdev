---
title:  "Project Euler Problem - 22"
date:   2020-11-02 19:19:35 +0300
tages: [project euler c# problems problem 22]
header: 
    images:

excerpt: ""
mathjax: "true"
---
Project Euler üzerinde çözdüğüm soruları yayınladığım kısımda **Problem 22**'e hoşgeldiniz. 
Birlikte algoritma kurma yeteneğimizi eğlenceli matematik problemleri ile güçlendirelim. 
Bu blog yazılarında genel olarak sorulara nasıl yaklaştığım ve çözüm için uyguladığım kodları paylaşacağım.
Bütün çözümleri github repomda daha detaylı bulabilirsiniz.
<br>[Github](https://github.com/ibgk883/projecteuler/blob/master/ConsoleApp3/Problem22.cs)

# Problem 22
Using names.txt (right click and 'Save Link/Target As...'), a 46K text file containing over five-thousand first names, begin by sorting it into alphabetical order. Then working out the alphabetical value for each name, multiply this value by its alphabetical position in the list to obtain a name score.

For example, when the list is sorted into alphabetical order, COLIN, which is worth 3 + 15 + 12 + 9 + 14 = 53, is the 938th name in the list. So, COLIN would obtain a score of 938 × 53 = 49714.

What is the total of all the name scores in the file?
<br>[names.txt](https://projecteuler.net/project/resources/p022_names.txt)
<br>[Problem 22](https://projecteuler.net/problem=22)

## Çözüm Yorumum
- Burada bize verilen; namex.txt dosyası üzerinde 5000 adet ismin nasıl puanlanacağından bahsetmiş.
- Bizden istediği; Bu verilenlere göre names.txt dosyasındaki tüm isimlerin puanlarının toplamını sormakta.
- Ayrıca programın kaç saniye sürdüğünü öğrenmek için bir sayaç tanımlıyoruz.
- Benim programım **2.497** saniye sürdü.
- Sonuç **871198282**.

![return](https://i.imgur.com/wTZVcG3.png)
<br>

```c#
{
string filename;
string temp;
string tempnocomma;
string temporaryname;
string line;
int value;
long sum;
List<string> names = new List<string>();
List<int> values = new List<int>();
void getfile()
{
    filename = "p022_names.txt";
    StreamReader sr = new StreamReader(filename);

    while ((line = sr.ReadLine()) != null)
    {
        temp += line;                
    }
}
void clearcommas()
{
    for (int i = 0; i < temp.Length; i++)
    {
        if (temp[i] == ',')
        {
            tempnocomma += ' ';
        }
        else if (temp[i] == '"')
        {
            tempnocomma += ' ';
        }
        else
        {
            tempnocomma += temp[i];
        }             
    }
}

void seperatenames()
{
    temporaryname = "";
    for (int i = 1; i < tempnocomma.Length; i++)
    {
        if (tempnocomma[i] == ' ')
        {
            names.Add(temporaryname.Trim());
            temporaryname = "";
        }
        else
        {
            temporaryname += tempnocomma[i];
        }
    }            
    for (int i = 0; i < names.Count; i++)
    {
        if (names[i] == "")
        {
            names.RemoveAt(i);
        }
        else if (names[i] == " ")
        {
            names.RemoveAt(i);
        }                
    }
    for (int i = 0; i < names.Count; i++)
    {
        if (names[i] == "")
        {
            names.RemoveAt(i);
        }
        else if (names[i] == " ")
        {
            names.RemoveAt(i);
        }
    }

}        
void valuenames()
{
    string temp;            

    names.Sort();

    for (int i = 0; i < names.Count; i++)
    {
        value = 0;
        temp = names[i];
        for (int j = 0; j < temp.Length; j++)
        {
            if (temp[j] == 'A')
            {
                value += 1;
            }
            else if (temp[j] == 'B')
            {
                value += 2;
            }
            else if (temp[j] == 'C')
            {
                value += 3;
            }
            else if (temp[j] == 'D')
            {
                value += 4;
            }
            else if (temp[j] == 'E')
            {
                value += 5;
            }
            else if (temp[j] == 'F')
            {
                value += 6;
            }
            else if (temp[j] == 'G')
            {
                value += 7;
            }
            else if (temp[j] == 'H')
            {
                value += 8;
            }
            else if (temp[j] == 'I')
            {
                value += 9;
            }
            else if (temp[j] == 'J')
            {
                value += 10;
            }
            else if (temp[j] == 'K')
            {
                value += 11;
            }
            else if (temp[j] == 'L')
            {
                value += 12;
            }
            else if (temp[j] == 'M')
            {
                value += 13;
            }
            else if (temp[j] == 'N')
            {
                value += 14;
            }
            else if (temp[j] == 'O')
            {
                value += 15;
            }
            else if (temp[j] == 'P')
            {
                value += 16;
            }
            else if (temp[j] == 'Q')
            {
                value += 17;
            }
            else if (temp[j] == 'R')
            {
                value += 18;
            }
            else if (temp[j] == 'S')
            {
                value += 19;
            }
            else if (temp[j] == 'T')
            {
                value += 20;
            }
            else if (temp[j] == 'U')
            {
                value += 21;
            }
            else if (temp[j] == 'V')
            {
                value += 22;
            }
            else if (temp[j] == 'W')
            {
                value += 23;
            }
            else if (temp[j] == 'X')
            {
                value += 24;
            }
            else if (temp[j] == 'Y')
            {
                value += 25;
            }
            else if (temp[j] == 'Z')
            {
                value += 26;
            }
        }
        values.Add(value);
    }

    
}

public void problem22()
{
    Stopwatch clock = Stopwatch.StartNew();

    getfile();
    clearcommas();

    seperatenames();
    names.Sort();

    valuenames();

    for (int i = 0; i < values.Count; i++)
    {
        sum += (i + 1) * values[i];
    }
    for (int i = 0; i < names.Count; i++)
    {
        Console.WriteLine((i+1)+"." + names[i] +","+ values[i]);
    }
    Console.WriteLine("SUM = "+sum);
    

    clock.Stop();
    Console.WriteLine("Solution took {0} seconds", (double)clock.ElapsedMilliseconds / 1000);
}
}
```