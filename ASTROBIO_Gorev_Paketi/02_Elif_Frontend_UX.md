# ASTROBIO — Elif

**Rol:** Frontend ve kullanıcı deneyimi  
**Teknolojiler / odak:** React, TypeScript, Vite, Recharts, CSS  
**Etkinlik:** NASA Space Apps Challenge 2026, 14–15 Kasım 2026  
**Durum:** 48 saatlik prototip; sentetik veriler, tıbbi cihaz veya teşhis sistemi değil.

## 14 Kasım — 1. gün

- [ ] **01.** React + TypeScript + Vite projesini oluştur.
- [ ] **02.** Mobil ve masaüstünde çalışacak dashboard yerleşimini tasarla.
- [ ] **03.** Koyu uzay temalı, okunabilir renk ve tipografi sistemi belirle.
- [ ] **04.** Astronot seçimi, görev adı ve bağlantı durumunu gösteren başlığı oluştur.
- [ ] **05.** Nabız, SpO₂, sıcaklık ve uyku kartlarını hazırla.
- [ ] **06.** Her kartta birim, güncelleme zamanı ve veri kalitesini göster.
- [ ] **07.** Recharts ile geçmiş ölçümlerin zaman grafiğini oluştur.
- [ ] **08.** BIS için R0 ve baz çizgi eğilimini gösteren grafik hazırla.
- [ ] **09.** Normal/İzle/İncele/Acil için tutarlı görsel uyarı tasarımı oluştur.
- [ ] **10.** Anomali nedenlerini gösterecek açıklama panelini geliştir.
- [ ] **11.** Dünya/Ay/Mars iletişim modu seçicisi tasarla.
- [ ] **12.** Simülasyonu başlat/durdur ve senaryo değiştir kontrollerini ekle.
- [ ] **13.** Gerçek API hazır değilken örnek JSON/mocks oluştur.
- [ ] **14.** API çağrılarını ortak servis katmanında topla.
- [ ] **15.** Yükleniyor, veri yok, bağlantı hatası ve bozuk sensör durumlarını tasarla.
- [ ] **16.** İlk dashboard’u çalıştır; Zehra ile UI durum ve API sözleşme testlerini gerçekleştir.

## 15 Kasım — 2. gün

- [ ] **01.** Mock veriyi Kerim’in canlı API’siyle değiştir.
- [ ] **02.** Periyodik yenileme (polling) ile ölçümleri güncelle.
- [ ] **03.** API risk seviyelerini uygun kartlarda ve bildirimlerde göster.
- [ ] **04.** AI açıklamalarını panele bağla; varsa model adını göster.
- [ ] **05.** Veri kalite bayraklarını sensör sorunu olarak göster.
- [ ] **06.** BIS grafiğinde referans çizgisi ve güncel eğilimi ayır.
- [ ] **07.** İletişim modu seçiminde ilgili API’ye istek gönder.
- [ ] **08.** Gecikme, iletişim durumu ve bekleyen rapor sayısını göster.
- [ ] **09.** Mars modunda raporun kuyruğa alındığını görünür kıl.
- [ ] **10.** Normal, BIS sapması, çoklu anomali ve sensör arızası senaryolarını arayüzde dene.
- [ ] **11.** Tüm ekranlarda “Sentetik veriler — prototip, tıbbi cihaz değildir” ibaresi ekle.
- [ ] **12.** Renk dışında metin ve ikonla da risk seviyesi belirt.
- [ ] **13.** Küçük ekranları ve en az iki tarayıcıda temel görünümü kontrol et.
- [ ] **14.** Grafik yenileme, boş ekran ve taşma hatalarını düzelt.
- [ ] **15.** Ortak ekip sunumu için temiz ve tekrarlanabilir demo akışı hazırla.
- [ ] **16.** Son kodu commit et; build ve çalıştırma komutlarını belgeleyip ekiple paylaş.

## Teslim edilecek çıktılar

- [ ] Çalışan `frontend/` uygulaması
- [ ] Vital göstergeler, BIS grafiği ve açıklama paneli
- [ ] Gecikme modu ve rapor kuyruğu arayüzü
- [ ] Mock ve gerçek API entegrasyonu

## Ekip bağımlılıkları

- Kerim: endpoint listesi, örnek yanıtlar, CORS.
- Işıkhan: AI JSON alanları ve risk seviyeleri.
- Zehra: otomatik smoke/entegrasyon testleri ve hata senaryoları.

## Önemli notlar

- Backend’i bekleme: ilk gün mock veriyle arayüzü bitir.
- Riskler yalnızca renkle kodlanmamalı; yazılı etiket de bulunmalı.


## Ortak sunum katkısı

- [ ] Kendi modülü için kısa, doğrulanabilir bir demo/anlatım hazırla (yaklaşık 20–35 saniye).
