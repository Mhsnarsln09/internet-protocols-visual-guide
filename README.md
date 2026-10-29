# İnternet Protokolleri — Etkileşimli Görsel Rehber

İnternetin nasıl çalıştığını Türkçe açıklamalar ve etkileşimli örneklerle öğrenmek için hazırlanmış, tarayıcıda çalışan bir rehber.

## Özellikler

- **Bir web isteğinin yolculuğu:** Telefondan DNS, yönlendiriciler ve sunucuya; ardından tarayıcıya dönüşü adım adım keşfet.
- **HTTP sürümleri:** HTTP/1.1, HTTP/2 ve HTTP/3 arasındaki taşıma ve sıralı teslim farklarını örneklerle incele.
- **Terim sözlüğü:** Ağ, yönlendirme, sinyal, taşıma, web, sunucu, tarayıcı, **Backend (Sunucu Tarafı)**, **Database (Veritabanı)**, **Web Güvenliği (Web Security)**, **DevOps ve Deployment**, **Cloud ve Altyapı (Cloud & Infrastructure)** kavramlarını ara ve kategorilere göre filtrele. Kartları açarak “Nedir?”, “Ne değildir?” ve “Örnek” açıklamalarını oku.
- **Yeni öğrenme senaryoları:** Backend’de “Siparişlerim”, Database’te e-posta ile giriş, Web Güvenliği’nde güvenli oturum açma, DevOps’ta GitHub Pages yayını ve Cloud’da kampanya trafiği akışlarını açılır/kapanır adımlarla incele.
- **Kapsamlı arama:** Türkçe ve İngilizce terim adlarında, açılımlarda ve açıklamalarda ara; büyük/küçük harf ve Türkçe aksan farkları aramayı engellemez.
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

`entries` kayıtları `[terim, açılım, kategori, nedir, ne değildir, örnek]` biçimini korur. `sharedCategories`, aynı kaydı çoğaltmadan başka kategori filtrelerinde de gösterir: Backend, Reverse Proxy, Load Balancer ve Cache eski Sunucu kategorisinde kalırken Backend filtresinde de bulunur; Redis hem Database hem Backend filtresinde görünür. “Tümü” her kaydı yalnızca bir kez gösterir. Filtre düğmelerindeki sayılar kategorinin toplam benzersiz kayıt sayısını, sonuç satırı ise seçili kategori ve aramaya uyan kayıt sayısını gösterir.

Kaynak dizilerinin ilk altı alanı korunur; çalışma sırasında yedinci alana terim adından türetilen benzersiz `term-…` kimliği eklenir. Kartlar bu değeri `data-term-id` özniteliğinde taşır. Yeni terim eklerken hem adının hem türetilen kimliğinin benzersizliğini kontrol et.

İlk genişletmede 23 backend ve 28 veritabanı terimi olmak üzere 51 kayıt eklendi. Son genişletmede aşağıdaki 82 yeni kayıtla birlikte toplam **197 benzersiz terime** ulaşıldı:

| Yeni kategori | Yeni kayıt | Filtredeki toplam benzersiz terim |
| --- | ---: | ---: |
| Web Güvenliği (Web Security) | 21 | 26 |
| DevOps ve Deployment | 29 | 31 |
| Cloud ve Altyapı (Cloud & Infrastructure) | 32 | 38 |

Yeni kategorilerle paylaşılan mevcut kayıtlar:

- **Web Güvenliği:** TLS, HTTPS, CORS, Authentication, Authorization.
- **DevOps:** Environment Variables, Reverse Proxy.
- **Cloud:** CDN, Load Balancer, DNS, Cache, Redis, Backup / Restore. İstenen Backup kavramı mevcut Backup / Restore kartıyla karşılanır.

Bu kayıtlar eski kategorilerinde kalır; bağımsız kopyaları oluşturulmaz. Kategori toplamlarının toplamı, ortak kayıtlar nedeniyle “Tümü” sayısından büyük olabilir.

Değişikliklerden sonra yolculuk düğmelerini, HTTP sürümü seçimini, sözlük aramasını ve kategori filtrelerini, kartların açılıp kapanmasını ve testin tamamlanıp yeniden başlatılmasını kontrol et.

## Not

Rehber eğitim amaçlı sadeleştirilmiş örnekler içerir. Örnek IP adresleri açıklama amaçlıdır; gerçek ağlarda kullanılan protokoller ve izlenen yollar değişebilir.

## İçerik kaynakları

Yeni açıklamaların hazırlanmasında başvurulan teknik kaynaklar:

- [MDN — CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CORS)
- [PostgreSQL — Transaction](https://www.postgresql.org/docs/current/tutorial-transactions.html)
- [IETF RFC 7519 — JWT](https://datatracker.ietf.org/doc/html/rfc7519)
- [Redis — Veri saklama](https://redis.io/docs/latest/develop/get-started/data-store/) ve [kalıcılık seçenekleri](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/)
- [OWASP — Parola saklama](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)

- [OWASP — TLS](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet.html) ve [CSRF](https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html)
- [OpenID Foundation — OpenID Connect](https://openid.net/developers/how-connect-works/)
- [Docker — Container ve sanal makine farkı](https://docs.docker.com/get-started/docker-concepts/the-basics/what-is-a-container/)
- [GitHub — Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages) ve [Actions ile Pages yayını](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)
- [AWS — Region ve Availability Zone](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/global-infrastructure.html)
- [Kubernetes — Genel bakış](https://kubernetes.io/docs/concepts/overview/)

## Doğrulama

Genişletme sonrası geçici bir test ortamında jsdom ile şu kontroller yapıldı; uygulamaya çalışma zamanı bağımlılığı eklenmedi:

- Önceki 115 kaydın tüm alanlarının korunması; 82 yeni kaydın ve toplam 197 benzersiz terim kimliğinin doğrulanması.
- Görevde listelenen 90 terimin uygun kategorilerde bulunması; tüm 13 filtre seçeneğinde sayılar ve benzersiz kayıtların kontrolü.
- Türkçe/İngilizce ve aksan/büyük-küçük harf araması, arama ile kategori birlikteliği, boş sonuç ve HTML metninin güvenli gösterilmesi.
- Kartların tıklama, Enter ve boşluk tuşuyla açılıp kapanması; beş öğretici senaryonun kategoriye göre görünmesi.
- Sekmeler, dokuz ağ yolculuğu adımı, üç HTTP karşılaştırması, sekiz soruluk test ve yeniden başlatma.
- HTML ayrıştırma, CSS kuralları ve JavaScript çalıştırma kontrolleri; DOM ortamında konsol/çalıştırma hatası görülmemesi.

Filtrelerde satıra bölünme ve dar ekranlara uygun kart genişliği korunmuştur. Bu oturumda tarayıcı kontrol izni bulunmadığından gerçek tarayıcıda görsel ve mobil yerleşim doğrulaması yapılamadı.
