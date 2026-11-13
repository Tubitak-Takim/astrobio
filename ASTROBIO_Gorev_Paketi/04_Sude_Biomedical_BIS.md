# ASTROBIO — Sude

**Rol:** BIS simülasyonu ve bilimsel kaynak doğrulaması  
**Teknolojiler / odak:** Python/NumPy temelleri, Cole modeli, NASA kaynakları  
**Etkinlik:** NASA Space Apps Challenge 2026, 14–15 Kasım 2026  
**Durum:** 48 saatlik prototip; sentetik veriler, tıbbi cihaz veya teşhis sistemi değil.

## 14 Kasım — 1. gün

- [ ] **01.** NASA challenge metnini okuyup sağlık izleme hedefini özetle.
- [ ] **02.** NASA RIDGE riskleri ile D/G odağını araştır.
- [ ] **03.** Mikro yerçekimindeki sıvı kayması mekanizmasını güvenilir kaynaklardan incele.
- [ ] **04.** BIA ile BIS farkını ve BIS temel prensibini öğren.
- [ ] **05.** Cole modeli R0, R∞, τ, α parametrelerinin anlamını araştır.
- [ ] **06.** BIS’in doğrudan ölçemediği hemoglobin, SpO₂, kemik yoğunluğu vb. değerleri belgele.
- [ ] **07.** Tüm-vücut BIS ile bölgesel baş-boyun sıvı değişimini değerlendirmedeki sınırlılığı açıkla.
- [ ] **08.** Kaynakların başlık, URL ve erişim tarihlerini `references.md` içine yaz.
- [ ] **09.** Sentetik normal empedans profili için örnek parametreler seç; klinik eşik iddia etme.
- [ ] **10.** Cole modeliyle frekansa bağlı karmaşık empedans fonksiyonu yaz.
- [ ] **11.** Frekans aralığında empedans genlik ve faz grafiklerini üret.
- [ ] **12.** R0 değerini zamana bağlı değiştirerek sentetik BIS sapma senaryosu oluştur.
- [ ] **13.** Gürültülü ve sensör arızalı örnek veriler üret.
- [ ] **14.** Kerim ve AI servisinin kabul ettiği aynı JSON alanlarıyla çıktı oluştur.
- [ ] **15.** Normal/sapma senaryosu örnek dosyalarını ekiple paylaş.

## 15 Kasım — 2. gün

- [ ] **01.** Farklı parametrelerle simülatörün hata vermeden çalıştığını doğrula.
- [ ] **02.** Normal, kademeli sapma, ani gürültü ve donmuş sensör veri setlerini ayır.
- [ ] **03.** Frekans aralığını, parametre birimlerini ve sentetik veri varsayımlarını belirt.
- [ ] **04.** Kerim ile BIS verisinin backend simülatörüne aktarımını test et.
- [ ] **05.** Işıkhan ile R0 eğiliminin AI motorunda görünmesini doğrula.
- [ ] **06.** Elif’in BIS grafiğindeki referans ve değişim etiketlerini kontrol et.
- [ ] **07.** Uyku, nabız ve sıvı kayması hakkında kullandığınız kaynakları kısa özetle.
- [ ] **08.** NASA kaynaklarında desteklenmeyen sayısal iddiaları kaldır veya belirsiz olarak belirt.
- [ ] **09.** Demo açıklamalarında teşhis veya doğrulanmamış fizyolojik sonuç iddiası bulunmadığını kontrol et.
- [ ] **10.** `limitations.md` için tek sayfalık sistem sınırlılıkları taslağı oluştur.
- [ ] **11.** Sentetik veri ile klinik doğrulanmış verinin farklılığını açıkça belgeye yaz.
- [ ] **12.** Tüm ekiple kaynak listesi ve olası jüri sorularını paylaş.
- [ ] **13.** Gerçek BIS donanımı kullanılmadığını sunumda belirt.
- [ ] **14.** Bilimsel son kontrolü yap ve dokümanlarla kodu commit et.

## Teslim edilecek çıktılar

- [ ] `bis_simulator.py` ve sentetik senaryo dosyaları
- [ ] `references.md` ve `limitations.md` katkısı
- [ ] Empedans genlik/faz grafikleri
- [ ] Sınırlılıkların demo metninde doğrulanması

## Ekip bağımlılıkları

- Işıkhan: Python başlangıç şablonu, AI entegrasyonu.
- Kerim: ölçüm JSON şeması ve simülatör entegrasyonu.
- Elif: BIS grafik etiketleri.
- Zehra: BIS test fixture’ları ve entegrasyon kontrolleri; sunum tüm ekibin ortak sorumluluğu.

## Önemli notlar

- Cole model: `Z(ω) = R∞ + (R0 − R∞) / (1 + (jωτ)^α)`.
- R0 değişimi, gerçek astronot sıvı hacmi ölçümü değil sentetik gösterim varsayımıdır.
- Güvenilir olmayan sayısal tıbbi eşikler üretmeyin.


## Ortak sunum katkısı

- [ ] Kendi modülü için kısa, doğrulanabilir bir demo/anlatım hazırla (yaklaşık 20–35 saniye).
- [ ] Beş kişilik ortak prova, kayıt ve teslim kontrolüne katıl.
