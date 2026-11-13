# ASTROBIO — AI/ML Developer — Işıkhan

**Rol:** Anomali motoru, MedGemma entegrasyonu ve sistem mimarisi  
**Teknolojiler / odak:** Python, FastAPI, NumPy, SciPy, Pydantic, pytest, yerel LLM  
**Etkinlik:** NASA Space Apps Challenge 2026, 14–15 Kasım 2026  
**Durum:** 48 saatlik prototip; sentetik veriler, tıbbi cihaz veya teşhis sistemi değil.

## 14 Kasım — 1. gün

- [ ] **01.** Kerim, Elif ve Sude ile JSON veri sözleşmesini kesinleştir.
- [ ] **02.** Python sanal ortamı oluştur; FastAPI, uvicorn, numpy, scipy, pandas, pydantic ve pytest kur.
- [ ] **03.** `GET /health` endpoint’i olan minimal AI servisini oluştur.
- [ ] **04.** Kerim’in backend’inden gönderilecek sağlık ölçümlerini Pydantic modelleriyle doğrula.
- [ ] **05.** Geçersiz, eksik, null ve fiziksel olarak anlamsız değerler için veri kalitesi bayrakları tasarla.
- [ ] **06.** Kişisel baz çizgi için ilk N **geçerli** ölçümden medyan ve MAD hesaplayan fonksiyon yaz.
- [ ] **07.** MAD sıfır olduğunda kullanılacak güvenli alternatif hesaplama yaklaşımını belirle.
- [ ] **08.** EWMA ile kısa süreli değişimleri yumuşatan hesaplama fonksiyonu geliştir.
- [ ] **09.** Sağlam z-skoru hesapla; örnek eşikleri simüle veriyle sınayıp klinik eşik olarak sunma.
- [ ] **10.** Tek ölçümdeki sapmanın doğrudan yüksek riskli uyarıya dönüşmemesi için süreklilik kuralı ekle.
- [ ] **11.** Birlikte değişen göstergeleri değerlendiren kural tabanlı risk motoru geliştir.
- [ ] **12.** `normal`, `monitor`, `review`, `urgent` seviyelerini üreten `anomaly.py` dosyasını tamamla.
- [ ] **13.** `POST /analyze` endpoint’ini oluştur; Kerim’e örnek istek/yanıt paylaş.
- [ ] **14.** Normal, sapma, donmuş sensör ve eksik veri için pytest testleri yaz.
- [ ] **15.** MedGemma erişim/lisans ve yerel çalıştırma gereksinimlerini kontrol et; en küçük uygun sürümü dene.
- [ ] **16.** LLM çalışmazsa devreye girecek deterministik açıklama şablonlarını hazırla.

## 15 Kasım — 2. gün

- [ ] **01.** MedGemma çalışıyorsa model yükleme ve inference kodunu `llm.py` içine ayır.
- [ ] **02.** LLM’e ham uzun veri dizileri yerine doğrulanmış, yapılandırılmış anomali raporu gönder.
- [ ] **03.** Sabit prompt hazırla: teşhis koyma, kaynakta olmayan bilgi ekleme, risk seviyesini değiştirme.
- [ ] **04.** LLM’den yapılandırılmış JSON çıktısı iste ve şemasını doğrula.
- [ ] **05.** Zaman aşımı, yükleme hatası veya geçersiz yanıt durumunda şablon açıklamaya dön.
- [ ] **06.** Halüsinasyon/uydurma tıbbi iddialar için en az beş karşılaştırmalı test hazırla.
- [ ] **07.** Sude’nin BIS verisini motora bağla; R0 trendini kişisel baz çizgisiyle kıyasla.
- [ ] **08.** Gecikme modunun risk skorunu değil iletişim/sunum davranışını değiştirdiğini test et.
- [ ] **09.** Kerim ile gerçek backend üzerinden uçtan uca `POST /analyze` çağrısı yap.
- [ ] **10.** Elif için `summary`, `anomalies`, `riskLevel`, `qualityFlags` alanlarını doğrula.
- [ ] **11.** Zehra ile otomatik normal, çoklu anomali, sensör donması ve offline testlerini çalıştır.
- [ ] **12.** Model adı/sürümünü, lisansı ve çalıştırma komutlarını belgele.
- [ ] **13.** LLM olmadan tüm akışın deterministik açıklama şablonlarıyla çalışmasını doğrula.
- [ ] **14.** Paket sürümlerini sabitle; son kodu commit et ve entegre dala gönder.

## Teslim edilecek çıktılar

- [ ] `ai-service/main.py`, `baseline.py`, `anomaly.py`, `llm.py`
- [ ] En az dört test senaryosunu geçen `POST /analyze`
- [ ] LLM arızasında da çalışan açıklama mekanizması
- [ ] Model/lisans ve yerel çalıştırma notları

## Ekip bağımlılıkları

- Kerim: API sözleşmesi ve entegrasyon testi.
- Sude: BIS parametreleri ile simülasyon çıktısı.
- Elif: UI’da kullanılacak analiz yanıtı alanları.
- Zehra: otomatik regresyon/smoke testleri, LLM fallback ve entegrasyon hata ayıklama.

## Önemli notlar

- Kritik yol önce anomali motoru, sonra LLM.
- LLM klinik risk veya teşhis kararı üretmez; karar deterministik istatistiksel/kural tabanlı katmandadır.


## Ortak sunum katkısı

- [ ] Kendi modülü için kısa, doğrulanabilir bir demo/anlatım hazırla (yaklaşık 20–35 saniye).
