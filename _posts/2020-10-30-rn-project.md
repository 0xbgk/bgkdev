---
title:  "React Native Uygulama - Tahmin Et Genel Kültür"
date:   2020-10-30 12:24:56 +0300
categories: jekyll update
tages: [react native android game]
header: 
    images:

excerpt: ""
mathjax: "true"
---

React Native öğrenmek için geliştirdiğim bu projeyi aynı zamanda bitirip Google Play Store'a da koymuş bulunumaktayım.

# Tahmin Et Genel Kültür
![genel_pano](https://lh3.googleusercontent.com/COv9BAl9igvlx7faCWWlerOGYNe_G9JK_0jyUQuq1rXIDM_vbjM6jWFcJx5Ia4B_7Gw)


### Oyun Ana Menüsü
![ana_menu](https://lh3.googleusercontent.com/yYCXuOwKlXvAtbhLq0DxYvoX2kkMHy5H14vBdQpEpDvpU6oroi5w4TjusQmAyVS-4A)
Kategoriler, Puan Tablosu, Hakkında ve Çıkış. Hakkında bölümünde oyunun genel puanlama sistemine dair bilgiler öğrenilebilir. Puan tablosunda daha önce sizin yada bir başkasının yapmış olduğu scorelar görülebilir.

### Kategoriler
![menuler](https://lh3.googleusercontent.com/dMaHhuOf5tMc4N5s3zbfl_58HW8IpfJTTvMZr3565aUPg0qK17swJNIeK0CXh_aUPWY)
4 farklı **json** dosyasında bulunan kategoriler kategoriye göre çekilip anlık soru oluşturulmaktadır. Böylece tüm soru havuzu değil de kategori kategori çekileceğinden daha performans arttırımı gerçekleştirdim.

### Scoreboard
![scoreboard](https://lh3.googleusercontent.com/v75H3EN8cwYAJv0nlfUSv8LU7WT2wIKp1EaBEyJVXJZT1u7ev7pfiV0svQ8QL8SBJZ8)
Oyun sırasında 10 soruyu bitirip(her oyun 10 sorudan oluşmakta) son puanı ekranda gören kullanıcı aynı zamanda arka planda Firebase RealTime Database'in puanı veritabanına kaydetmesiyle, diğer oyuncular ile puan karşılaştırabilir.

### Gameplay Örneği
![soru_sayfası](https://lh3.googleusercontent.com/TvWilDRQytm2sA8QpVFCMIezjGEc6Nb4PMkVzdoyMIwZKUbo-UWlgou4ndxjdiq3U7E2)
Seçilen kategoride gelen soruya göre doğru cevap biliniyorsa, cevap bilinmiyorsa yaklaşık bir değer yazılıp tahminde bulunulur.

### Soru Cevaplama ve Puan
![tahmin](https://lh3.googleusercontent.com/pCaMxF6LzSBf_ixCcvXPHuXHcfA978t-1lMyDvRXpn-_F11OSr9kN-oRcASCHLSqfA)
Verilen cevaba göre tam tahmin ise 100 puan, değil ise yakınlık derecesine göre oranlı daha düşük bir puan kazanılır.

### Çok Uzakta Bir Tahmin
![oyun_sonu](https://lh3.googleusercontent.com/f97kCwYOkPTwUPBDtw4dJgREKPlRpEGHiETn2CMl8wnirokiAT5vODemru9m4kXBvA)
Ayrıca fark çok fazla ise eksi puanda alınabilir.

# Play Store
Oyun Play Store Linki[Tahmin Et Genel Kültür](https://play.google.com/store/apps/details?id=com.tahminetgenelkultur)