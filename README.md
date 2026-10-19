# Haber Sitesi SEO Rehberi

Haber siteleri için arama motoru görünürlüğü rehberi. Google News, yapılandırılmış veri,
haber site haritası, hızlı indeksleme ve teknik kontrol listeleri.

Bu depo **eğitici bir dokümandır**. Kod, kütüphane veya hazır şablon içermez. Kaynak olarak
yalnızca kamuya açık standartlar ve resmî kurum belgeleri kullanılmıştır.

Genel yayıncılık mevzuatı (künye, mahreç, resmî ilan) ayrı bir konudur ve bu rehberin
kapsamı dışındadır.

Son güncelleme: 19 Ekim 2026 (şema başlığı uzunluğu Google'ın güncel belgesine göre düzeltildi).

---

## İçindekiler

1. [Haber SEO'su neden farklıdır](#1-haber-seosu-neden-farklıdır)
2. [Google News'e girmek](#2-google-newse-girmek)
3. [Yapılandırılmış veri: NewsArticle](#3-yapılandırılmış-veri-newsarticle)
4. [Yayıncı kimliği ve yazar sayfaları](#4-yayıncı-kimliği-ve-yazar-sayfaları)
5. [Haber site haritası](#5-haber-site-haritası)
6. [Hızlı indeksleme: IndexNow](#6-hızlı-indeksleme-indexnow)
7. [URL yapısı ve canonical](#7-url-yapısı-ve-canonical)
8. [Başlık, açıklama ve tarih alanları](#8-başlık-açıklama-ve-tarih-alanları)
9. [AMP hâlâ gerekli mi](#9-amp-hâlâ-gerekli-mi)
10. [Hız ve Core Web Vitals](#10-hız-ve-core-web-vitals)
11. [Arşiv, güncelleme ve içerik ömrü](#11-arşiv-güncelleme-ve-içerik-ömrü)
12. [Görsel ve video SEO'su](#12-görsel-ve-video-seosu)
13. [Yapay zekâ arama motorları ve alıntılanabilirlik](#13-yapay-zekâ-arama-motorları-ve-alıntılanabilirlik)
14. [Sık yapılan hatalar](#14-sık-yapılan-hatalar)
15. [Uygulama kontrol listesi](#15-uygulama-kontrol-listesi)
16. [Kaynaklar](#16-kaynaklar)

---

## 1. Haber SEO'su neden farklıdır

Klasik SEO'da bir sayfanın sıralamaya oturması haftalar alabilir. Haberde değerli olan
pencere çoğu zaman **ilk birkaç saattir**. Bu, öncelik sırasını değiştirir:

| Klasik SEO | Haber SEO'su |
|---|---|
| Aylık arama hacmi | Ani talep sıçraması |
| Uzun vadeli otorite | Hızlı keşfedilme |
| Sayfa başına derin içerik | Sürekli akış |
| Haftalık tarama yeterli | Dakikalar içinde tarama beklenir |
| Statik içerik | Gelişen, güncellenen haber |

Pratik sonucu şudur: haber sitesinde teknik altyapı, içerik kadar belirleyicidir.
Yayından sonra 20 dakika boyunca indekslenmemiş bir son dakika haberi, konu ne kadar iyi
işlenmiş olursa olsun trafiğin büyük kısmını kaçırır. Bu yüzden bir **haber yazılımı**
seçilirken site haritası üretimi, yapılandırılmış veri ve indeksleme bildirimi gibi
başlıklar "ek özellik" değil, temel gereksinim sayılmalıdır.

---

## 2. Google News'e girmek

Yaygın bir yanlış bilgi, Google News'te yer almak için başvuru yapmak gerektiğidir.
2019 sonundan itibaren Google, haber içerikli siteleri **otomatik olarak** değerlendirmeye
alır. Ayrı bir kabul başvurusu zorunlu değildir.

Publisher Center yine de işe yarar; ancak amacı farklıdır:

| Publisher Center ne yapar | Ne yapmaz |
|---|---|
| Yayın kimliğini (ad, logo, dil, ülke) tanımlar | Sıralama garantisi vermez |
| Bölümleri/kaynakları düzenler | İndekslenmeyi tek başına sağlamaz |
| Sahiplik doğrulaması sunar | Kalite sorunlarını telafi etmez |

Değerlendirmede belirleyici olan başlıklar:

- Sitenin haber niteliğinde, özgün, düzenli içerik üretmesi
- Yazarın ve yayıncının kim olduğunun açıkça görülebilmesi
- Yayın ve güncelleme tarihlerinin doğru ve tutarlı olması
- Teknik olarak taranabilir olması (robots, canonical, durum kodları)
- Aldatıcı başlık, otomatik kopya içerik ve gizlenmiş reklam bulunmaması

Bir haber sitesi bu maddeleri karşılıyorsa Google News'e girmek için ek bir tören yoktur;
karşılamıyorsa hiçbir başvuru bunu telafi etmez.

---

## 3. Yapılandırılmış veri: NewsArticle

Haber sayfalarında en yaygın kullanılan şema türü `NewsArticle`'dır. Google'ın
zorunlu-önerilen ayrımı zaman zaman değişse de, alanları eksiksiz doldurmak her zaman
lehinize çalışır.

| Alan | Ne yazılır | Not |
|---|---|---|
| `headline` | Haberin başlığı | 110 karakteri aşmaması önerilir |
| `datePublished` | İlk yayın anı | **Saat dilimi bilgisiyle**, ISO 8601 |
| `dateModified` | Son anlamlı güncelleme | Kozmetik değişiklikte güncellenmez |
| `author` | Kişi veya kurum | Adı yeterli değil, `url` de verilmeli |
| `publisher` | Yayıncı kuruluş | Ad + logo |
| `image` | Yüksek çözünürlüklü görsel | Birden çok en-boy oranı önerilir |
| `mainEntityOfPage` | Haberin kanonik adresi | Canonical ile birebir aynı olmalı |
| `articleSection` | Bölüm/kategori | Ekonomi, spor, gündem gibi |
| `inLanguage` | İçerik dili | Türkçe için `tr-TR` |

Ek olarak sayfa hiyerarşisini `BreadcrumbList` ile bildirmek, arama sonuçlarında bölüm
adının görünmesine yardımcı olur.

**Doğrulama olmadan yayına alınmaz.** Şema, sessizce bozulan türden bir alandır: şablon
değişir, bir alan boş kalır, hata aylarca fark edilmez. Her yayın öncesi otomatik doğrulama
adımı koymak, elle kontrolden çok daha güvenilirdir.

---

## 4. Yayıncı kimliği ve yazar sayfaları

Arama motorları içeriğin kim tarafından üretildiğini anlamak ister. Haber sitelerinde bu,
üç ayrı yerde tutarlı olmalıdır:

1. **Sayfadaki görünür imza** — yazar adı, tarih, güncelleme bilgisi
2. **Yapılandırılmış veri** — `author` ve `publisher` alanları
3. **Kalıcı yazar sayfası** — kısa biyografi, uzmanlık alanı, geçmiş yazılar

Kalıcı yazar sayfası çoğu sitede eksiktir. Oysa "yazar adı" bir metin dizesi olmaktan
çıkıp `url` ile adreslenebilir bir varlığa dönüştüğünde, hem arama motorları hem de
yapay zekâ tabanlı sistemler içeriği bir kaynağa bağlayabilir.

Yayıncı tarafında da benzer bir sayfa gerekir: kurumun adı, adresi, iletişim bilgisi ve
yayın ilkeleri. Bu sayfa aynı zamanda `publisher` şemasının insan tarafından okunabilir
karşılığıdır.

---

## 5. Haber site haritası

Haber site haritası (news sitemap), normal site haritasından ayrı ve çok daha dar
kapsamlıdır.

| Kural | Değer |
|---|---|
| İçerik penceresi | Yalnızca son **2 gün** içinde yayımlanan haberler |
| Azami URL sayısı | 1.000 |
| Zorunlu bilgi | Yayın adı, dil, yayın tarihi, haber başlığı |
| Güncelleme sıklığı | Yeni haber yayımlandığı anda |
| Eski haberler | Penceresi dolunca **çıkarılır** |

Sık görülen üç hata:

- **Tüm arşivi haber site haritasına koymak.** Dosya şişer, güven kaybedilir.
- **Penceresi dolan haberi çıkarmamak.** İki günden eski içerik burada durmamalıdır.
- **Site haritasını zamanlanmış görevle saatte bir üretmek.** Son dakika haberinde bir
  saatlik gecikme, haberin değerli olduğu sürenin tamamı olabilir. Üretim, yayın anına
  bağlanmalıdır.

Normal site harita(lar)ı ayrıca tutulur: kategori sayfaları, yazar sayfaları, arşiv ve
statik sayfalar oraya girer. Büyük arşivlerde site haritası dizini kullanılır.

---

## 6. Hızlı indeksleme: IndexNow

IndexNow, bir adresin yeni/güncellenmiş olduğunu arama motorlarına doğrudan bildiren açık
bir protokoldür. Taramanın keşfe dayanmasını beklemek yerine bildirimi siz yaparsınız.

| Konu | Durum |
|---|---|
| Destekleyenler | Bing, Yandex, Seznam, Naver |
| Google | Protokolü benimsemedi; Google için normal tarama ve site haritası geçerli |
| Kimlik doğrulama | Site kökünde barındırılan bir anahtar dosyası |
| Maliyet | Ücretsiz |
| Uygun kullanım | Yayın, anlamlı güncelleme ve silme anları |

Pratik notlar:

- Bildirimi **yayın anında** yapın, toplu iş olarak günde bir kez değil.
- Aynı adresi tekrar tekrar bildirmek fayda getirmez; gereksiz bildirim istenmez.
- Silinen içerik de bildirilebilir — kaldırılan adresin daha hızlı düşmesini sağlar.
- Anahtar dosyasına erişilemiyorsa bildirimler sessizce geçersiz sayılır. Kurulumdan sonra
  dosyanın gerçekten yayınlandığı doğrulanmalıdır.

Google tarafında karşılığı yoktur; oradaki hız büyük ölçüde site haritası tazeliğine,
iç bağlantıya ve sitenin genel tarama bütçesine bağlıdır.

---

## 7. URL yapısı ve canonical

Haber sitelerinde URL kararları, arşiv büyüdükçe geri dönülmesi zor kararlara dönüşür.

**Kalıcılık esastır.** Bir haberin adresi yayımlandıktan sonra değişmemelidir. Başlık
düzeltildiğinde adres sabit kalmalı, değişmesi gerekiyorsa eski adres kalıcı yönlendirme
ile korunmalıdır.

Öneriler:

- Adreste kimlik (id) ve/veya kısa açıklayıcı bir metin bulunsun; başlığın tamamı gerekmez.
- Türkçe karakterler ASCII karşılıklarına çevrilsin; adres yalnızca küçük harf, rakam ve
  tire içersin.
- Tarih içeren adres yapısı arşiv okunabilirliği sağlar ama içeriği eskimiş gösterebilir.
  Tercih sitenin yayın karakterine göre yapılmalıdır.
- Kategori değişince adres değişiyorsa, kategori adresin parçası olmamalıdır.

**Canonical**, aynı içeriğin birden çok adresten erişilebildiği her yerde gerekir:
sayfalama, filtre parametreleri, kampanya etiketleri, yazıcı görünümü, AMP kopyası.
Canonical adresi ile yapılandırılmış verideki `mainEntityOfPage` alanı birebir aynı olmalıdır.

---

## 8. Başlık, açıklama ve tarih alanları

Haber sayfasında aynı başlık üç farklı yerde kullanılır ve üçü aynı olmak zorunda değildir:

| Alan | Amaç | Uzunluk yaklaşık |
|---|---|---|
| Sayfa başlığı (`title`) | Arama sonucu | 60 karakter civarı |
| Görünür başlık (`h1`) | Okuyucu | Serbest |
| Şema `headline` | Yapılandırılmış veri | Sabit sınır yok; kısa tutulması önerilir |

Açıklama alanı sıralama sinyali değildir ama tıklanma oranını doğrudan etkiler. Haberin
ilk cümlesini kopyalamak yerine, haberin **neden önemli olduğunu** söyleyen bir cümle
daha iyi çalışır.

Başlık ve spot yazımı için ayrıntılı yazı: [Haber başlığı ve özet](docs/haber-basligi-ve-ozet.md).

Tarih alanlarında en sık görülen teknik hata **saat dilimi eksikliğidir**. Saat dilimi
belirtilmemiş bir yayın zamanı, sunucunun bulunduğu yere göre yorumlanır ve haber üç saat
sonra veya üç saat önce yayımlanmış görünebilir. Son dakika haberinde bu fark belirleyicidir.

Ayrıca:

- Görünür tarih ile şemadaki tarih **aynı** olmalıdır.
- `dateModified`, yalnızca içerik anlamlı biçimde değiştiğinde güncellenmelidir. Her
  önbellek yenilemesinde tarihi ileri almak güven kaybettirir.
- Güncellenen haberlerde neyin değiştiği kısa bir not olarak belirtilirse hem okuyucu hem
  arama motoru için şeffaflık sağlanır.

---

## 9. AMP hâlâ gerekli mi

Kısa cevap: **hayır, zorunlu değil.**

2021'deki sayfa deneyimi güncellemesiyle birlikte Google, Top Stories alanında yer almak
için AMP şartını kaldırdı. Bugün belirleyici olan, sayfanın kendisinin hızlı ve kararlı
olmasıdır.

| AMP tutmak mantıklıysa | Bırakmak mantıklıysa |
|---|---|
| Halihazırda kurulu ve sorunsuz çalışıyorsa | İki ayrı şablonu sürdürmek yük oluyorsa |
| Ana şablon ağır ve kısa vadede hafifletilemiyorsa | Ana sayfa hızları zaten iyiyse |
| Belirli dağıtım kanalları AMP bekliyorsa | Reklam ve ölçüm tarafında sürekli fark çıkıyorsa |

AMP kullanılıyorsa canonical ilişkisi doğru kurulmalı, AMP kopyası kanonik sayılmamalıdır.
AMP bırakılıyorsa eski AMP adresleri kalıcı yönlendirme ile ana sayfalara taşınmalıdır;
doğrudan silmek arşiv trafiğini boşa harcar.

---

## 10. Hız ve Core Web Vitals

Haber sayfalarında hızın düşmanı genellikle içerik değil, sayfaya sonradan eklenenlerdir:
reklam kodları, ölçüm etiketleri, sosyal gömüler, otomatik oynayan videolar.

Öncelik sırası:

1. **Görsel yükü.** Manşet görseli çoğu haber sayfasında en büyük öğedir. Modern görsel
   biçimleri, doğru boyutlandırma ve ekran altındaki görsellerde geç yükleme birlikte
   uygulanmalıdır. En üstteki görsele geç yükleme uygulanmaz — tersine etki eder.
2. **Yerleşim kaymaları.** Reklam ve gömü alanlarına baştan yer ayrılmazsa sayfa okuyucunun
   gözü önünde zıplar. Bu, ölçülebilir ve düzeltilebilir bir sorundur.
3. **Betik sırası.** Ölçüm ve reklam betikleri içerikten sonra yüklenmelidir.
4. **Önbellek katmanları.** Haber sitesinde trafik dalgalıdır; son dakika anında normalin
   onlarca katı istek gelebilir. Sunucu tarafı önbellek olmadan bu yük veritabanına iner.
5. **Yazı tipleri.** Gereğinden fazla ağırlık/varyant yüklemek ilk boyamayı geciktirir.

Ölçüm, laboratuvar aracıyla değil **gerçek kullanıcı verisiyle** yapılmalıdır. Geliştirici
makinesinde hızlı görünen sayfa, mobil bağlantıda bambaşka davranır.

---

## 11. Arşiv, güncelleme ve içerik ömrü

Haber sitelerinin en değerli ama en ihmal edilen varlığı arşividir.

- **Silmeyin, yönlendirin.** İçerik kaldırılacaksa ilgili güncel sayfaya kalıcı
  yönlendirme yapılır. Toplu silme, yıllarca birikmiş bağlantı değerini bir gecede yok eder.
- **Gerçekten kaldırılan içerik** için doğru durum kodu döndürülmeli, bu adresler site
  haritasından çıkarılmalı ve yeniden bildirilmelidir.
- **Yaşayan haberler** — seçim, deprem, uzun süren gelişmeler — yeni sayfa açmak yerine tek
  sayfada güncellenebilir. Bu durumda `dateModified` güncellenir ve güncelleme notu düşülür.
- **Eskiyen içerik** silinmek yerine gözden geçirilebilir. Hâlâ arama alan eski bir rehber
  haberi güncellemek, sıfırdan içerik üretmekten çoğu zaman daha verimlidir.
- **Etiket ve kategori sayfaları** kontrolsüz çoğalırsa birbirinin kopyası yüzlerce zayıf
  sayfa oluşur. Az sayıda, gerçekten kullanılan etiket daha iyidir.

---

## 12. Görsel ve video SEO'su

- Her habere en az bir yüksek çözünürlüklü görsel eklenmelidir; şema `image` alanı boş
  kalmamalıdır.
- Farklı en-boy oranlarında (yatay, kare, dikey) görsel sunmak, arama sonuçlarındaki farklı
  yerleşimlerde görünme şansını artırır.
- Alternatif metin (alt) görme engelli kullanıcılar için zorunlu, arama için faydalıdır.
  Anahtar kelime yığmak değil, görselde ne olduğunu yazmak gerekir.
- Telif durumu belirsiz görsel kullanılmamalıdır. Kaynak ve kullanım hakkı kayıt altında
  tutulmalıdır.
- Video varsa ayrı bir video şeması ve video site haritası düşünülmelidir; küçük resim,
  süre ve yükleme tarihi alanları doldurulur.

---

## 13. Yapay zekâ arama motorları ve alıntılanabilirlik

Arama davranışının bir kısmı, sonuç listesinden yanıt üreten sistemlere kayıyor. Bu
sistemler kaynak gösterirken bazı içerikleri diğerlerinden daha kolay alıntılıyor.

Alıntılanabilirliği artıran yapısal özellikler:

- **Kendi başına anlamlı paragraflar.** Bağlamı önceki cümleye bağlı olmayan, tek başına
  okunduğunda da doğru bilgi veren bölümler.
- **Net soru-cevap blokları.** Sorunun ardından gelen yanıtın birkaç cümle uzunluğunda ve
  tek konuya odaklı olması.
- **Sayı, tarih, birim.** Belirsiz ifade yerine ölçülebilir bilgi.
- **Açık kaynak ve yazar bilgisi.** Kime ait olduğu belli olmayan metin daha az alıntılanır.
- **Tutarlı kurum bilgisi.** Kurumun adı, adresi ve iletişim bilgisinin sitenin her yerinde
  ve yapılandırılmış veride aynı olması.

Tarama izinleri ayrı bir karardır. Arama amaçlı gezginlerle model eğitimi amaçlı gezginler
farklı ele alınabilir; yayıncı ikisi için farklı politika belirleyebilir. Önemli olan bu
kararın bilinçli verilmesi ve robot dosyasının bunu doğru yansıtmasıdır.

---

## 14. Sık yapılan hatalar

| Hata | Sonucu |
|---|---|
| Saat dilimsiz yayın tarihi | Haber yanlış saatte yayımlanmış görünür |
| Haber site haritasına tüm arşivi koymak | Dosya güvenilirliğini kaybeder |
| Site haritasını saatlik üretmek | Son dakika penceresi kaçar |
| Yazar adı var, yazar sayfası yok | Kaynak kimliği kurulamaz |
| Şemayı bir kez kurup bir daha bakmamak | Şablon değişince sessizce bozulur |
| Başlığı yayından sonra değiştirip adresi de değiştirmek | Biriken değer sıfırlanır |
| Eski haberleri toplu silmek | Arşiv trafiği kalıcı kaybedilir |
| Sayfalamada canonical'ı ilk sayfaya vermek | Derin sayfalar indekslenmez |
| Etiket sayfalarını sınırsız üretmek | Birbirinin kopyası zayıf sayfa yığını |
| Manşet görseline geç yükleme uygulamak | En büyük öğe daha da geç gelir |
| Reklam alanına yer ayırmamak | Sayfa okurken zıplar |
| IndexNow anahtar dosyasını doğrulamamak | Bildirimler sessizce boşa gider |
| `dateModified`'ı her önbellek yenilemesinde güncellemek | Tazelik sinyali güvenilmez olur |

---

## 15. Uygulama kontrol listesi

Bir haber sitesini yayına almadan önce:

- [ ] Her haber sayfasında `NewsArticle` şeması var ve doğrulayıcıdan hatasız geçiyor
- [ ] `datePublished` ve `dateModified` saat dilimi bilgisi içeriyor
- [ ] Görünür tarih ile şemadaki tarih aynı
- [ ] `author` alanı kalıcı bir yazar sayfasına bağlanıyor
- [ ] Yayıncı bilgisi (ad, logo, iletişim) sitede ve şemada tutarlı
- [ ] Haber site haritası yalnızca son 2 günü kapsıyor ve 1.000 URL'yi aşmıyor
- [ ] Site haritası yayın anında güncelleniyor, zamanlanmış göreve bağlı değil
- [ ] Normal site haritası kategori, yazar ve statik sayfaları kapsıyor
- [ ] IndexNow anahtar dosyası yayında ve erişilebilir
- [ ] Yayın/güncelleme/silme anlarında bildirim gönderiliyor
- [ ] Canonical her sayfada var ve `mainEntityOfPage` ile aynı
- [ ] Sayfalama, filtre ve kampanya parametreleri canonical ile toparlanmış
- [ ] Adresler ASCII, küçük harf ve kalıcı
- [ ] Kaldırılan içerik için doğru durum kodu veya kalıcı yönlendirme var
- [ ] Manşet görseli geç yükleme dışında tutulmuş
- [ ] Reklam ve gömü alanlarına baştan yer ayrılmış
- [ ] Ölçüm ve reklam betikleri içerikten sonra yükleniyor
- [ ] Sunucu tarafı önbellek trafik sıçramasına hazır
- [ ] Robot dosyası, gezgin politikasını bilinçli biçimde yansıtıyor
- [ ] Arama konsolu hesapları bağlı ve hata raporları izleniyor

---

## 16. Kaynaklar

Yalnızca resmî ve kamuya açık belgeler:

- Google Search Central — Haber yayıncıları belgeleri: <https://developers.google.com/search/docs/appearance/google-news>
- Google Search Central — Haber site haritası: <https://developers.google.com/search/docs/crawling-indexing/sitemaps/news-sitemap>
- Google Search Central — Makale yapılandırılmış verisi: <https://developers.google.com/search/docs/appearance/structured-data/article>
- Google Search Console: <https://search.google.com/search-console/about>
- Schema.org — NewsArticle: <https://schema.org/NewsArticle>
- IndexNow: <https://www.indexnow.org/>
- Bing Webmaster Tools: <https://www.bing.com/webmasters>
- Yandex Webmaster: <https://webmaster.yandex.com/>
- Sitemaps protokolü: <https://www.sitemaps.org/>
- web.dev — Core Web Vitals: <https://web.dev/articles/vitals>

---

## Makaleler

- [Haber başlığı ve özet: arama motoru ile okur arasında denge](docs/haber-basligi-ve-ozet.md)
- [Haber sitesinde yazar sayfası ve yazar kimliği nasıl kurulur?](docs/yazar-sayfasi-ve-yazar-kimligi.md)

---

## Katkı

Düzeltme ve ekleme önerileri için issue açabilirsiniz. Kabul edilmeyenler:

- Belirli bir ürünün tanıtımı veya karşılaştırması
- Kaynağı gösterilmeyen sayısal iddialar
- Kod, betik veya hazır şablon (bu depo yalnızca dokümandır)

## Lisans

MIT. Derleyen: [Alesta WEB](https://alestaweb.com) — 2005'ten beri haber ve e-ticaret
yazılımı geliştiriyor.

Son güncelleme: 2026-10-11
