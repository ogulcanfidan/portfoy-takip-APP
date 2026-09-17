# Pozisyon Defteri — Vadeli İşlem Günlüğü

Tek dosyalık (tek HTML) bir kripto vadeli işlem günlüğü. Kurulum ya da sunucu
gerektirmez — dosyayı tarayıcıda açman yeterli. Tüm veriler kendi
bilgisayarında kalır, hiçbir yere gönderilmez.

## Özellikler

- İşlem ekleme/düzenleme (giriş/çıkış fiyatı, yön, pozisyon büyüklüğü, tarih)
- Anlık bakiye takibi — kapanmış işlemlerin gerçekleşen K/Z'si + açık
  pozisyonların canlı K/Z'si (Binance Futures → CoinGecko → CryptoCompare
  fiyat zinciri ile)
- Günlük K/Z takvimi (ay görünümü, ısı haritası)
- Denklem eğrisi grafiği (SVG, harici kütüphane yok)
- Fiyat izleme / tekrar giriş uyarıları — kârla kapanmış işlemlerin giriş
  seviyesine fiyat geri döndüğünde bildirim
- Excel'e (.xlsx) dışa aktarma (SheetJS)
- Gece otomatik yedekleme (File System Access API ile bağlanan klasöre)

## Veri saklama

Tarayıcının File System Access API'si ile bir klasöre bağlanıp orada JSON
olarak saklıyor; bu API'yi desteklemeyen tarayıcılarda `localStorage`'a
düşüyor. Her iki durumda da veri sadece yerelde kalıyor.

## Kullanım

`islem-gunlugu.html` dosyasını herhangi bir modern tarayıcıda (Chrome/Edge
önerilir — File System Access API için) aç. İlk açılışta bir klasör
seçmeni isteyecek (verilerin saklanacağı yer).
