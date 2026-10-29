# İnternet Protokolleri — Etkileşimli Görsel Rehber

İnternetin nasıl çalıştığını Türkçe açıklamalar ve etkileşimli örneklerle öğrenmek için hazırlanmış, tarayıcıda çalışan bir rehber.

## Özellikler

- **Bir web isteğinin yolculuğu:** Telefondan DNS, yönlendiriciler ve sunucuya; ardından tarayıcıya dönüşü adım adım keşfet.
- **HTTP sürümleri:** HTTP/1.1, HTTP/2 ve HTTP/3 arasındaki taşıma ve sıralı teslim farklarını örneklerle incele.
- **Terim sözlüğü:** Ağ, yönlendirme, taşıma, web, sunucu ve tarayıcı kavramlarını ara ve kategorilere göre filtrele. Kartları açarak “Nedir?”, “Ne değildir?” ve “Örnek” açıklamalarını oku.
- **Mini test:** Sekiz soruyla bilgini test et; her cevabın ardından açıklamayı ve test sonunda puanını gör.
- **Uyumlu arayüz:** Mobil ve masaüstü ekranlara uyarlanan koyu tema; sözlük kartlarında klavye desteği.

## Kullanım

Proje dosyalarını bilgisayarına indir.

`index.html` dosyasını tarayıcında aç. Paket kurulumu, derleme adımı veya sunucu gerekmez. Dosya harici kaynak kullanmadığı için indirildikten sonra çevrimdışı da çalışır.

İstersen Python 3 ile yerel bir sunucu da başlatabilirsin:

```bash
python3 -m http.server 8000
```

Ardından [rehberi tarayıcıda aç](http://localhost:8000/index.html).

## Kullanılan teknolojiler

- HTML5
- CSS3
- Saf JavaScript

Sayfanın tasarımı, içeriği ve etkileşimleri tek HTML dosyasında bulunur. Herhangi bir framework veya harici kütüphane kullanılmaz.

## Dosya yapısı

```text
internet-protocols-visual-guide/
├── index.html                         # Etkileşimli rehber
└── README.md                          # Proje ve kullanım açıklamaları
```

## Geliştirme

İçeriği veya arayüzü değiştirmek için HTML dosyasını bir metin düzenleyicide açıp kaydetmen ve tarayıcıyı yenilemen yeterlidir. JavaScript içindeki `steps`, `entries` ve `questions` dizileri sırasıyla yolculuk adımlarını, sözlük terimlerini ve test sorularını içerir.

Değişikliklerden sonra yolculuk düğmelerini, HTTP sürümü seçimini, sözlük aramasını ve kategori filtrelerini, kartların açılıp kapanmasını ve testin tamamlanıp yeniden başlatılmasını kontrol et.

## Not

Rehber eğitim amaçlı sadeleştirilmiş örnekler içerir. Örnek IP adresleri açıklama amaçlıdır; gerçek ağlarda kullanılan protokoller ve izlenen yollar değişebilir.
