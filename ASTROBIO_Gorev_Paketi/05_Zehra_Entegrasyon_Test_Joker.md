# ASTROBIO — Zehra | Entegrasyon, QA Otomasyonu ve Joker Teknik Destek

**Ana rol:** Teknik entegrasyon, otomatik test altyapısı, hata ayıklama ve sistemin çalıştırılabilirliği  
**Destek rolü:** İhtiyacı olan modüllerde küçük geliştirmeler, teknik araştırma ve sorun çözme  
**Teknolojiler / odak:** Git, HTTP/JSON, Python veya Bash (test scriptleri), pytest, curl, GitHub Actions (zaman kalırsa)  
**Etkinlik:** NASA Space Apps Challenge 2026, 14–15 Kasım 2026  
**Kapsam:** Sentetik verilere dayalı prototip; klinik cihaz ve teşhis sistemi değil.  

## İş sınırları ve kabul kriteri

- Zehra, diğer kişilerin modüllerini yeniden yazmaz. Modüller arasındaki **veri sözleşmesini ve çalışma sürekliliğini** test eder.
- Karmaşık AI algoritması veya backend iş mantığı hata verirse ilgili sahip (Işıkhan veya Kerim) düzeltir; Zehra hatayı tekrarlanabilir hale getirir ve küçük entegrasyon düzeltmelerine yardımcı olur.
- Her test için *önkoşul, adımlar, beklenen sonuç, elde edilen sonuç* kayıt altına alınır.
- Otomatik testlerin amacı klinik kararları doğrulamak değil, belirlenen sentetik senaryoların ve hata davranışlarının tutarlı olmasını sağlamaktır.

## 14 Kasım — 1. gün | Test altyapısı ve erken entegrasyon

- [ ] **01.** Işıkhan, Elif ve Kerim'den servis adreslerini, endpoint listesini ve veri şemasını al; `docs/integration-contract.md` dosyasına yaz.
- [ ] **02.** Repository'yi yerel ortamda klonla; Git branch açma, commit ve pull request akışını doğrula.
- [ ] **03.** `tests/integration/`, `tests/fixtures/`, `scripts/` ve `docs/test-results/` klasörlerini oluştur.
- [ ] **04.** Testlerin çalışma gereksinimlerini belirle; Python sanal ortamı, `requests` ve `pytest` kurulumu için kısa komut dosyası oluştur.
- [ ] **05.** Basit `GET /health` kontrolünü önce `curl` ile manuel çalıştır, ardından script haline getir.
- [ ] **06.** Backend ve AI servisleri çalışmıyorsa anlaşılır hata veren `scripts/smoke_test.py` dosyasını hazırla.
- [ ] **07.** Işıkhan ve Kerim ile test edilecek ölçüm JSON şemasının zorunlu alanlarını ve birimlerini belirle.
- [ ] **08.** Normal, BIS sapması, çoklu sapma, eksik veri ve donmuş sensör için küçük JSON fixture dosyaları oluştur.
- [ ] **09.** Backend `GET /api/health` ve AI `GET /health` endpoint'lerini smoke test'e dahil et.
- [ ] **10.** `POST /analyze` için geçerli örnek isteğin başarıyla döndüğünü doğrulayan test yaz.
- [ ] **11.** `POST /analyze` için eksik alan, yanlış tip ve bozuk JSON durumlarında kontrollü hata beklentisini test et.
- [ ] **12.** Analiz yanıtında `astronautId`, `riskLevel`, `anomalies`, `qualityFlags`, `summary` alanlarının beklenen tipte olduğunu test et.
- [ ] **13.** Risk seviyesinin yalnızca `normal`, `monitor`, `review`, `urgent` değerlerinden biri olduğunu test et.
- [ ] **14.** Kerim'in API'sinde astronot listeleme, ölçüm ekleme ve geçmiş görüntüleme çağrılarını manuel doğrula.
- [ ] **15.** Backend → AI → Backend akışının ilk örnek veride çalışmasını Işıkhan ve Kerim ile birlikte dene; başarısızsa hatayı daralt.
- [ ] **16.** Hata kaydı şablonu oluştur: yeniden üretme adımları, giriş verisi, beklenen/gerçek çıktı, log, sorumlu kişi, önem derecesi.
- [ ] **17.** Elif'in mock dashboard'unu aç; API alanları ve UI alanları arasında uyuşmazlıkları raporla.
- [ ] **18.** En az bir entegrasyon problemini sahibiyle birlikte çözüp testin tekrar geçtiğini göster.
- [ ] **19.** `docs/test-results/day1.md` içinde geçen, başarısız ve engellenmiş testleri ayrı ayrı yaz.
- [ ] **20.** İlk gün sonunda `python scripts/smoke_test.py` komutunu ekip önünde çalıştır; eksikleri listele.

### 1. gün teslim kriteri

- [ ] Tek komutla çalıştırılan temel smoke test.
- [ ] En az beş farklı senaryo için örnek fixture.
- [ ] Temel endpoint ve analiz yanıt şeması testleri.
- [ ] Tekrarlanabilir hata kayıtları ve ilk entegrasyon raporu.

## 15 Kasım — 2. gün | Uçtan uca test, dayanıklılık ve joker destek

- [ ] **01.** Güncel ana dalı çek; bütün servislerin sürümünü ve çalıştırma sırasını not et.
- [ ] **02.** Işıkhan ve Kerim ile frontend + backend + AI servislerini aynı bilgisayarda birlikte başlat.
- [ ] **03.** `scripts/run_demo.sh` ve `scripts/stop_demo.sh` (veya eşdeğer komutlar) ile tekrar edilebilir başlatma/durdurma akışı hazırla.
- [ ] **04.** Ortam değişkenlerinin örnek `.env.example` ile açıklanmasını ve gizli bilgilerin repoya girmemesini kontrol et.
- [ ] **05.** Testten önce demo veritabanını bilinen başlangıç durumuna getiren komutu Kerim'le birlikte dene.
- [ ] **06.** Normal senaryoda veri girişinin, analiz sonucunun ve dashboard göstergesinin tutarlı olduğunu kontrol et.
- [ ] **07.** BIS R0 sapması senaryosunda Sude'nin verisi → Kerim'in API'si → Işıkhan'ın analizi → Elif'in grafiği zincirini test et.
- [ ] **08.** Çoklu anomali senaryosunda önceden kararlaştırılan simüle uyarı seviyesini doğrula.
- [ ] **09.** Tek bir anlık ölçüm sapmasında süreklilik kuralı nedeniyle beklenmedik yüksek seviye alarm oluşmadığını test et.
- [ ] **10.** Sensör donması, eksik ölçüm ve yanlış tip verinin veri kalite bayrağı veya kontrollü hata ürettiğini test et.
- [ ] **11.** AI servisini durdurarak backend'in çökmediğini; varsa hata/yeniden deneme veya fallback davranışını doğrula.
- [ ] **12.** LLM'i kullanılamaz hale getirerek istatistiksel analizin ve şablon açıklamanın çalıştığını test et.
- [ ] **13.** İletişim modunu Dünya → Ay → Mars şeklinde değiştir; API ve UI durumlarının tutarlı olduğunu kontrol et.
- [ ] **14.** Mars modunda rapor kuyruğuna ekleme, bağlantı kesintisi ve yeniden gönderim akışını test et.
- [ ] **15.** İki servisin aynı anda yeniden başlatılması, yanlış port veya boş veritabanı gibi demo risklerine yönelik kısa toparlama yönergesi yaz.
- [ ] **16.** Hata kayıtlarını P0 (demo engelleyici), P1 (önemli) ve P2 (kozmetik) olarak ayır; sahiplerini etiketle.
- [ ] **17.** Önce P0 hataları için ilgili üye ile birlikte hata ayıklama yap; gerekirse örnek istek veya küçük uyarlama kodu hazırla.
- [ ] **18.** Elif'e API hata/boş durum testlerinde, Kerim'e HTTP istek/yanıtlarında, Sude'ye fixture üretiminde, Işıkhan'a LLM fallback testinde kısa teknik destek ver.
- [ ] **19.** `pytest tests/integration -q` veya denk komutla tüm otomatik testleri çalıştır; sonuçları `docs/test-results/day2.md` dosyasına kaydet.
- [ ] **20.** Vakit uygunsa her push/pull request'te temel şema ve smoke testlerini çalıştıracak GitHub Actions iş akışı ekle; servis gerektiren testleri CI'da koşulsuz zorunlu kılma.
- [ ] **21.** Temiz klondan kurulum yönergelerini uygula; eksik paket/ortam adımlarını ilgili kişiye bildir ve düzeltmeye yardım et.
- [ ] **22.** Ortak sunum için test dayanıklılığını gösteren 20–35 saniyelik bölüm hazırla; sunum ve video işlerini tüm ekiple paylaş.
- [ ] **23.** Son testlerden sonra ana dalı sabitleyin; kritik test raporunu ve bilinen sınırlılıkları ekiple paylaş.

### 2. gün teslim kriteri

- [ ] Çalışan uçtan uca testler ve raporları.
- [ ] Tekrarlanabilir demo başlatma/durdurma yönergesi veya scripti.
- [ ] LLM kapalı, AI kapalı, sensör hatası ve iletişim kesintisi senaryolarının test sonuçları.
- [ ] Kapanmış P0 hata kayıtları ve kalan sorunların açık listesi.
- [ ] Entegrasyon ve testin ortak sunumdaki kısa teknik anlatımı.

## Joker destek havuzu (diğer görevler bittikçe)

- [ ] **Elif:** API response/type eşleşmelerini karşılaştır, CORS ve hata durumlarının tekrarlanmasına yardım et.
- [ ] **Kerim:** `curl`/HTTP örnekleri üret, SQLite test verilerinin sıfırlanmasını birlikte doğrula.
- [ ] **Sude:** BIS test fixture'larını düzenle, grafik üretim scriptlerini çalıştır, kaynak URL'lerinin erişilebilirliğini kontrol et.
- [ ] **Işıkhan:** MedGemma fallback senaryolarını koştur, sahte LLM yanıtlarıyla şema testlerine yardımcı ol.
- [ ] **Tüm ekip:** Kısa araştırma notları, README kurulum adımları, açık issue'lar, gerekli küçük refaktörler.

**Kural:** Joker destek ana test teslimlerini geciktirmemeli; P0 entegrasyon problemi varsa öncelik odur.

## Ekip bağımlılıkları

- **Işıkhan:** AI istek/yanıt şeması, servis portu, fallback davranışı ve anomali senaryoları.
- **Kerim:** Backend endpoint'leri, örnek kayıtlar, rapor kuyruğu, veritabanını sıfırlama.
- **Elif:** Dashboard'un test edilecek ekranları, hatalı durumları ve veri yenileme akışı.
- **Sude:** BIS simülasyon fixture'ları, kullanılacak varsayımlar.

## Yöntem ve sınırlar

- Testleri mümkün olduğunca küçük ve tekrar üretilebilir yap. Bir test başarısız olduğunda hangi servis/hangi veri problemli olduğu açık olmalı.
- Tüm değerler örnek sentetik veri olduğundan testler **klinik performans veya doğruluk kanıtı değildir**.
- Karmaşık sorunlarda ilgili modül sahibi çözümün sorumluluğunu korur; Zehra test/araştırma/entegrasyon desteği sağlar.
