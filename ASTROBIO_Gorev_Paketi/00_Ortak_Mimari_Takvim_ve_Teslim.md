# ASTROBIO — Ortak Mimari, Takvim ve Teslim Kontrolü

**Etkinlik:** NASA Space Apps Challenge 2026 (14–15 Kasım)  
**Temel kural:** Prototip simüle verilerle çalışır; tıbbi cihaz değildir, teşhis veya klinik karar vermez.

## Rol dağılımı

| Kişi | Ana rol | İkincil rol |
|---|---|---|
| Işıkhan | AI/ML ve anomali tespiti | Mimari, Zehra’ya entegrasyon desteği |
| Elif | React frontend ve UX | Demo ekranları |
| Kerim | ASP.NET Core backend | Simülatör, gecikme yöneticisi |
| Sude | BIS ve bilimsel araştırma | Senaryoların doğrulanması |
| Zehra | Entegrasyon mühendisi, otomasyon testleri ve hata ayıklama | Joker teknik destek, araştırma ve CI |

## Teknoloji yığını

- Frontend: React + TypeScript + Vite + Recharts
- Backend: C# + ASP.NET Core Minimal API + SQLite + HttpClient
- AI: Python + FastAPI + NumPy + SciPy + pytest; MedGemma (yalnızca uygun lisans/çalıştırma koşullarıyla)
- BIS: NumPy ile Cole modeli, sentetik ölçüm
- Repo: GitHub, feature branches, issues, pull requests

## Örnek ölçüm sözleşmesi

```json
{
  "astronautId": "ASTRO-001",
  "timestamp": "2026-11-14T10:00:00Z",
  "heartRate": 78,
  "spo2": 98,
  "bodyTemperature": 36.7,
  "sleepHours": 7.2,
  "bis": {"r0": 520, "rInfinity": 310, "tau": 0.00001, "alpha": 0.8},
  "radiationDose": 0.0,
  "cabinCo2": 650,
  "signalQuality": "good",
  "simulated": true
}
```

**Not:** Bunlar yalnızca örnek sentetik değerlerdir. Her alanın birimi ve anlamı API sözleşmesinde ayrıca belirtilmelidir.

## AI yanıt sözleşmesi

```json
{
  "astronautId": "ASTRO-001",
  "riskLevel": "monitor",
  "anomalies": [{
    "metric": "bis.r0",
    "type": "persistent_deviation",
    "severity": "moderate",
    "explanation": "R0 kişisel baz çizgisinden sapıyor."
  }],
  "qualityFlags": [],
  "summary": "BIS ölçümlerinde devam eden değişim var.",
  "modelUsed": "statistical",
  "llmAvailable": false
}
```

Risk değerleri: `normal`, `monitor`, `review`, `urgent`. LLM risk seviyesini tek başına belirlemez.

## Geliştirme kilometre taşları

| Başlangıçtan itibaren | Gerekli çıktı |
|---|---|
| Saat 0–1 | Şema, endpoint'ler, roller ve klasörler sabit |
| Saat 1–4 | API ve frontend iskeletleri hazır |
| Saat 4–8 | Anomali motoru, BIS örneği, simülatör |
| Saat 8–12 | Backend → AI → Backend çalışıyor |
| Saat 12–18 | Dashboard gerçek API’den veri alıyor |
| Saat 18–24 | İlk uçtan uca demo |
| Saat 24–32 | LLM, iletişim modu, rapor kuyruğu |
| Saat 32–38 | Zehra’nın otomatik entegrasyon/smoke testleri, sistem hata düzeltmeleri |
| Saat 38–42 | Tüm ekip ortak demo kaydı, belgeler, kaynak kontrolü |
| Saat 42–46 | Teslim ve doğrulama |
| Saat 46–48 | Son teknik düzeltmeler (gerekirse) |

## Öncelik sırası

- **P0:** Veri simülasyonu, kişisel baz çizgi, anomali tespiti, dashboard, BIS trendi, gecikme modu.
- **P1:** Veri kalitesi, sakla-ve-ilet kuyruğu, MedGemma entegrasyonu.
- **P2:** Gelişmiş LLM metinleri, çok astronotlu destek, kapsamlı R/I/E panelleri, fiziksel BIS donanımı.

## Son teslim kontrol listesi

- [ ] Frontend, backend, AI temiz kurulumdan başlıyor.
- [ ] Demo verileri tek komutla yüklenebiliyor/oluşturulabiliyor.
- [ ] Normal senaryo çalışıyor.
- [ ] BIS sapması ve anomali uyarısı gösteriliyor.
- [ ] Çoklu sağlık göstergesi sapması açıklanabiliyor.
- [ ] Sensör donması veri kalitesi sorunu olarak işaretleniyor.
- [ ] Dünya/Ay/Mars modları çalışıyor.
- [ ] Rapor kuyruğu en azından simülasyon düzeyinde gösteriliyor.
- [ ] LLM servis olmadan temel analiz ve açıklama çalışıyor.
- [ ] Tüm verilerin sentetik olduğu açıkça yazıyor.
- [ ] Teşhis iddiası veya doğrulanmamış tedavi yönergesi bulunmuyor.
- [ ] Bilimsel kaynaklar ve model lisansı belgelenmiş.
- [ ] README, mimari şema ve demo videosu hazır.
- [ ] GitHub bağlantısı ve yarışma teslimi doğrulanmış.

## Modül bağımlılıkları

- **Işıkhan + Kerim:** `/analyze` istek/yanıt şemasını ilk dört saat içinde sabitleyin.
- **Kerim + Elif:** API endpoint listesini ilk saatlerde paylaşın; frontend başlangıçta mock kullanabilir.
- **Sude + Işıkhan + Kerim:** BIS örnek JSON’u ilk gün erken paylaşılmalı.
- **Zehra + herkes:** Smoke test, API sözleşme testi ve uçtan uca senaryolar her önemli merge sonrasında çalıştırılmalı. Zehra gerekli noktalarda diğer geliştiricilere destek verebilir.
- **Sunum + herkes:** İçerik, demo, kayıt ve yarışma teslimi beş kişiye dağıtılır.

## Kaynak belgeler

- Kullanıcının sağladığı **ASTROBIO_Proje_Dokumani.pdf**; özellikle s. 2–5 (RIDGE, mimari, BIS, 48 saatlik plan, sınırlılıklar).
- Güncel resmî Space Apps Challenge sayfası ve tıbbi model lisans koşulları yarışma öncesi ayrıca doğrulanmalıdır.

## Ortak sunum ve teslim sorumluluğu

| Kişi | Sunum katkısı |
|---|---|
| Işıkhan | AI mimarisi, kişisel baz çizgi, MedGemma'nın sınırları, canlı model açıklaması |
| Elif | Dashboard akışı, grafikleri ve kullanıcı deneyimi demosu |
| Kerim | Backend, veri simülatörü, haberleşme gecikmesi ve rapor kuyruğu |
| Sude | BIS prensibi, sentetik ölçüm ve bilimsel sınırlılıklar |
| Zehra | Otomatik test gösterimi, entegrasyon dayanıklılığı ve hata senaryosu |

- [ ] Her üye kendi bölümünün 20–35 saniyelik anlatımını ve bir ekran görüntüsünü hazırlar.
- [ ] Proje özeti ve sunum akışı beş üye tarafından ortak gözden geçirilir.
- [ ] Kayıt, kurgu, son kontrol ve yarışma formu, ekip müsaitliğine göre bölüştürülür.
- [ ] Geliştirme tamamlandıktan sonra beş üye ortak demo provası yapar.

## Zehra'nın test sözleşmesi (ilk gün kararlaştırılacak)

- `tests/integration/` altında API ve AI servisleri arasında doğrulanan testler bulunur.
- `scripts/smoke_test.py` veya eşdeğer bir script, çalışır servislerin `/health` endpoint'lerini ve temel akışı kontrol eder.
- `scripts/run_demo.sh` ve `scripts/stop_demo.sh` demo ortamını başlatır/durdurur; araç seçimi ekiple kararlaştırılır.
- `tests/fixtures/` normal, BIS sapması, çoklu anomali, eksik veri ve sensör donması örneklerini içerir.
- Sözleşme/entegrasyon testlerinde klinik doğruluk iddiası değil, *önceden tanımlanmış simülasyon beklentileri* sınanır.
