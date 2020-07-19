---
title:  "Github Pages + Jekyll Blog Sayfası Oluşturma"
date:   2020-07-19 14:15:00 +0300
tages: [github pages jekyll blog create how diy]
header: 
    images:

excerpt: ""
mathjax: "true"

---

Blog oluştururken içerisini özellikle şu içerikle doldururum dediğim ana bir konu aslında tam olarak olmadı, genel olarak project eulerde çözdüğüm problemlerin mantığını ve benim onları çözerken nasıl düşündüğümü aktarabileceğim bir sayfa olsun istemiştim. Ama şimdi bu blogu oluşturduğumda aklıma bir sürü paylaşmak istediğim ve sizlere de faydalı olabileceğini düşündüğüm içerik geliyor; günlük kullandığım websitelerinden bir blog yazabileceğim gibi, daha önce bitirmiş olduğum projenin incelemesini, film yada müzik paylaşımımı burada bulabilirsiniz. Burada derken gelelim Github Pages ve Jekyll ile Blog kurma işlemine.

## Ortamın Kurulması
### Git
Öncelikle github pages ile çalışacağımızdan bilgisayarda git özelliklerini kullanabilmek için vermiş olduğum linkten giti indiriyoruz.

[git-scm.com](https://git-scm.com/)

### Jekyll
Jekyll bizim saf metin yazılarımızı arkaplanda kütüphanelerle işlemler sonucu bunları statik websitelerine çevirecek kurtarıcımız.

[jekyll](https://jekyllrb.com/docs/installation/)

### VS Code
Editor olarak Visual Studio Code ilerde blog sayfası oluşturmada, githuba push commit atmada kolaylık sağlayacak ayrıca ücretsiz, cross platform ve kişiselleştirilebilir.

[VS Code](hhttps://code.visualstudio.com/)


### Github Üyelik, Repository Oluşturma
Şimdi Github üzerinden üyeliğimiz ile giriş yaparak yeni repository oluşturuyoruz, public yada private istediğiniz olabilir.
İsmini my-blog verebilirsiniz.
[Github New Repository](https://github.com/new)

![new repo](/images/creating-blog/19.07.1.jpg)

Repository oluşturduktan sonra Ayarlardan Github Pages Kısmında Source kısmını **master branch** seçiyoruz.

![master branch](/images/creating-blog/19.07.2.jpg)

Ve Bu işlem de bittikten sonra artık github pages sayfasına bu link ile ulaşabilirsiniz.
```
xxx.github.io/my-blog/
```

### VS Code ile Locale Github Repository'yi Alma
Vs Code'da **ctrl+shift+p** ye basıyoruz ve **clone** yazıp entera basıyoruz.
![clone](/images/creating-blog/19.07.3.jpg)

Daha sonra gelen pencereye Github Repositoryimizin **url**'sini giriyoruz, nereye oluşturulacağını seçtikten sonra clonelanma işi tamamdır. 

### Jekyll ile Clone içine Dosyaları ekleme
Klonlamış olduğumuz projemizde şuanda yalnızca readme.md dosyası bulunmakta ve Dosya konumu VS Code'da açılıyken
```
jekyll new . --force
```
komutunu çalıştırıyoruz. Bu komut bize **_config.yml**, **Gemfile**, **Gemfile.lock**, **index.markdown** gibi dosyaları kuruyor, gerekli ayarlamaları yapıyor.

![files](/images/creating-blog/19.07.4.jpg)

**_config.yml** dosyası içinde **baseurl** ve **url** bulup repositorymize göre adlarını değiştiriyoruz.

```
url                      : "https://xxx.github.io/"
baseurl                  : "/my-blog"
```

### Siteyi Localde Çalıştırma
Oluşturulan dosyalar arasında Gemfile dosyası içinde de görüleceği gibi yorum satırı şeklinde

```
#bundle exec jekyll serve
```
komutu bulunmakta. VS Code'da **ctrl+shift+é** kombinasyonu ile terminali açıp bu komut satırını çalıştırıyoruz.

![local-website](/images/creating-blog/19.07.5.jpg)

### Github'a Commit ve Push
Şu ana kadar localde çalışan bir blogumuz var ve bunu github pages üzerine aktarma işlemine gelirsek.


Yine Vs Code'da **ctrl+shift+p** ye basıyoruz ve bu sefer **commit** yazıp entera basıyoruz. `my-blog created` tarzı bir commit sonrası

![website-commit]({{ site.url }}/images/creating-blog/19.07.6.jpg)

Son olarakta **ctrl+shift+p** ve bu sefer **sync** enter.
Bu şekilde ilk oluşturduğumuz link üzerinden blog sayfamızı görüntüleyebiliriz.

![website-sync-push]({{ site.url }}/images/creating-blog/19.07.7.jpg)

```
xxx.github.io/my-blog/
```