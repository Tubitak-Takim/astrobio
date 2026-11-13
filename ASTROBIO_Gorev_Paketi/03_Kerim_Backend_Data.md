# ASTROBIO — Kerim

**Rol:** Backend, veritabanı, sensör simülasyonu ve gecikme yöneticisi  
**Teknolojiler / odak:** C#, ASP.NET Core Minimal API, SQLite, HttpClient  
**Etkinlik:** NASA Space Apps Challenge 2026, 14–15 Kasım 2026  
**Durum:** 48 saatlik prototip; sentetik veriler, tıbbi cihaz veya teşhis sistemi değil.

## 14 Kasım — 1. gün

- [ ] **01.** Desteklenen .NET SDK ile ASP.NET Core Web API projesini oluştur.
- [ ] **02.** Elif ve AI için ortak JSON DTO modellerini tanımla.
- [ ] **03.** Swagger/OpenAPI ile endpoint test arayüzünü hazırla.
- [ ] **04.** Frontend geliştirme adresi için CORS ayarlarını yapılandır.
- [ ] **05.** SQLite veritabanını oluştur ve bağlantısını kontrol et.
- [ ] **06.** Astronaut, HealthReading, AnalysisResult ve CommunicationReport tablolarını oluştur.
- [ ] **07.** İlk migration/DB şeması ve örnek astronot kaydını hazırla.
- [ ] **08.** `GET /api/health` endpoint’ini oluştur.
- [ ] **09.** `GET /api/astronauts` endpoint’ini oluştur.
- [ ] **10.** `GET /api/astronauts/{id}/readings` endpoint’ini oluştur.
- [ ] **11.** `GET /api/astronauts/{id}/latest` endpoint’ini oluştur.
- [ ] **12.** `POST /api/readings` ile ölçüm ekleme ve giriş doğrulama sağla.
- [ ] **13.** Normal, BIS sapması, uyku azalması ve nabız artışı için deterministik simülatör yaz.
- [ ] **14.** Simülatöre sabit random seed ve hızlandırılmış zaman parametresi ekle.
- [ ] **15.** Sensör donması, eksik ölçüm ve gürültü enjekte etme seçenekleri ekle.
- [ ] **16.** `POST /api/simulation/start` ve `/stop` endpoint’lerini oluştur.
- [ ] **17.** Python AI servisine istek gönderecek HttpClient sınıfı yaz.
- [ ] **18.** Örnek AI cevabını kaydet ve Elif’in kullanacağı API üzerinden sun.

## 15 Kasım — 2. gün

- [ ] **01.** Simülatörün ölçümlerini otomatik veritabanına kaydet.
- [ ] **02.** Her yeni geçerli ölçümü AI servisinin `/analyze` endpoint’ine gönder.
- [ ] **03.** AI sonuçlarını ilgili astronot ve ölçümle ilişkilendirip sakla.
- [ ] **04.** `GET /api/astronauts/{id}/analysis/latest` endpoint’ini oluştur.
- [ ] **05.** `GET /api/astronauts/{id}/analysis/history` endpoint’ini oluştur.
- [ ] **06.** `GET /api/communication/status` endpoint’ini oluştur.
- [ ] **07.** `POST /api/communication/mode` endpoint’iyle Dünya/Ay/Mars modları arasında geçiş sağla.
- [ ] **08.** Modlara ilişkin **simüle** tek yönlü gecikme bilgisini yönet.
- [ ] **09.** Yerel anomali analizini Dünya’ya rapor gönderme işleminden ayır.
- [ ] **10.** Sakla-ve-ilet için kalıcı rapor kuyruğu ve gönderildi/gönderilmedi durumları oluştur.
- [ ] **11.** İletişim kesintisi ve yeniden bağlantı senaryolarını simüle et.
- [ ] **12.** AI servisi kapalıyken backend’in çökmemesini ve hatanın kayıt altına alınmasını sağla.
- [ ] **13.** Timeout ve anlamlı HTTP hata yanıtları ekle.
- [ ] **14.** Elif ile frontend → backend uçtan uca akışı test et.
- [ ] **15.** Sude’nin BIS verisini simülatöre entegre et.
- [ ] **16.** Demo için veritabanı sıfırlama/örnek veri yükleme komutu hazırla.
- [ ] **17.** Endpoint’leri örnek HTTP istekleriyle belgele.
- [ ] **18.** Zehra ile otomatikleştirilmiş normal, hata ve bağlantı kesintisi testlerini gerçekleştir.

## Teslim edilecek çıktılar

- [ ] Çalışan ASP.NET Core API ve SQLite veritabanı
- [ ] Deterministik simülatör, senaryo endpoint’leri
- [ ] AI servisi istemcisi, analiz geçmişi
- [ ] Gecikme modu ve sakla-ve-ilet kuyruğu

## Ekip bağımlılıkları

- Işıkhan: `POST /analyze` sözleşmesi, hatalar ve örnek yanıt.
- Elif: API ihtiyaçları ve veri yenileme.
- Sude: BIS JSON örnekleri.
- Zehra: otomatik API/entegrasyon testleri, başlatma scriptleri ve hata ayıklama.

## Önemli notlar

- Python öğrenme baskısı yok: C# API, Python AI ile HTTP/JSON üzerinden haberleşir.
- İlk etapta WebSocket yerine polling kullanmak yeterli.


## Ortak sunum katkısı

- [ ] Kendi modülü için kısa, doğrulanabilir bir demo/anlatım hazırla (yaklaşık 20–35 saniye).
- [ ] Beş kişilik ortak prova, kayıt ve teslim kontrolüne katıl.
