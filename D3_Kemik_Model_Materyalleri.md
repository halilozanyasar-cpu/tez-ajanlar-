# Atrofik Üst Çenede Guide Stabilitesi Çalışması İçin D3 Kemik Modeli — Materyal Araştırması

**Konu:** Kemik destekli cerrahi guide'larda fiksasyon pin pozisyonunun guide stabilitesi ve implant sapmasına etkisi (in-vitro). Test bloğunun D3 kemik yoğunluğunu taklit etmesi gerekiyor.
**Tarih:** 12 Haziran 2026
**Not:** Tüm önemli sayısal değerler ve ürün adları kaynakla işaretlenmiştir. Literatürde tutarsızlık olan noktalar **(doğrulanmalı)** olarak belirtilmiştir.

**Tezin çekirdek literatürü:** Çalışmanın temel 5 makalesi (Chen 2023, Elnadoury 2025, Pessoa 2021, Verhamme 2014, Verhamme 2013) ayrı bir referans havuzunda toplanmıştır → `Tez_Temel_Makaleler.md` ve interaktif `Tez_Makaleler_Mindmap.html` (aynı klasör). Bu dosyadaki metodoloji/boşluk çerçevesi o havuzla tutarlıdır; özellikle Bölüm 2.3 ve Bölüm 7–8'deki atıflar bu makalelere dayanır.

---

## 1. D3 Kemik Özellikleri

**Misch sınıflaması** (kemik destekli implant cerrahisinde en yaygın referans) D3 kemiğini şöyle tanımlar:

- **Yapı:** Gözenekli (poröz) ince kreştal kortikal tabaka + altında **ince trabeküler kemik** ("porous crestal cortical + fine trabecular").
- **Yoğunluk (Hounsfield):** **350–850 HU** arası.
- **Tipik lokalizasyon:** Anterior ve **posterior maksilla** ile posterior mandibula. Anterior maksilla genellikle D3'tür (bazı vakalarda D2); posterior maksilla genellikle D4, sinüs greftleme sonrası 6 ayda D3 olabilir.

Komşu sınıflar (karşılaştırma için):

| Misch tipi | Yapı | HU aralığı | Tipik yer |
|---|---|---|---|
| D1 | Yoğun kortikal | > 1250 | Anterior mandibula |
| D2 | Kalın kortikal + kaba trabeküler | 850–1250 | Ant./post. mandibula, ant. maksilla |
| **D3** | **Poröz kortikal + ince trabeküler** | **350–850** | **Ant./post. maksilla, post. mandibula** |
| D4 | Çoğunlukla ince trabeküler, kortikal yok/çok az | 150–350 | Posterior maksilla |

> Mekanik özellikler: Misch sınıflaması kemik *kalitesini* HU ve tahta-sertliği benzetmesiyle (D1≈meşe, D4≈strafor gibi) tanımlar; her sınıf için standartlaştırılmış bir **elastik modül / MPa değeri vermez**. D3'ün mekanik karşılığı genellikle simülasyon materyalinin yoğunluğu üzerinden (aşağıdaki poliüretan değerleri) tanımlanır. Tez metninde D3'ü "yoğunluk + HU + simülasyon materyali" üçlüsüyle tanımlamak en savunulabilir yoldur. **(MPa karşılığı için poliüretan blok değerleri kullanılmalı — bkz. Bölüm 2.)**

Kaynaklar: Misch sınıflaması derlemeleri ([Pocket Dentistry — Bone density for dental implants](https://pocketdentistry.com/bone-density-for-dental-implants/); [Genieoss — Bone Type Classification](http://genieoss.com/boneclass.html)); CBCT-Hounsfield analizi ([MDPI, Oral 2024](https://www.mdpi.com/2673-1592/4/3/33)).

---

## 2. Literatürde Kullanılan Model Materyalleri

### 2.1 Rijit poliüretan köpük bloklar (Sawbones / ASTM F1839) — altın standart

İmplant in-vitro çalışmalarında trabeküler/kortikal kemiği taklit etmek için **en yaygın ve literatürde kabul gören** materyal, **ASTM F1839** standardına uygun rijit poliüretan (PU) köpük bloklardır (ticari adıyla **Sawbones / "Sawbone"**, Pacific Research Labs). Avantajı: native kemiğin heterojenliği olmadan **standart, tekrarlanabilir** bir test ortamı sunması.

- **Standart:** ASTM F1839-08 "Standard Specification for Rigid Polyurethane Foam for Use as a Standard Material for Testing Orthopaedic Devices and Instruments." Standart test bloğu boyutu 50.8 × 50.8 × 25.4 mm. Kaynak: [EndoLab — ASTM F1839](https://endolab.org/mt-polymer-analysis/astm-f1839/).
- **Mekanik karakterizasyon (anahtar referans):** Calvert ve ark. (2010), *J Mater Sci Mater Med*. ASTM F1839'a göre test edilen ticari rijit PU köpüklerde, **0.240–0.641 g/cm³** yoğunluk aralığı için **elastik modül 115–794 MPa**, **basma dayanımı 4.7–24.7 MPa**; ortalama por boyutu 125–234 µm. Bu, PU köpüğün kemik analoğu olarak mekanik geçerliliğini gösteren temel çalışmadır. *Based on articles retrieved from PubMed.* [DOI: 10.1007/s10856-010-4024-6](https://doi.org/10.1007/s10856-010-4024-6) (PMID 20162325).

**Sawbones köpük tipleri ve yoğunlukları** (kaynak: [Sawbones/MatWeb teknik veri sayfaları](https://www.matweb.com/search/GetMatlsByManufacturer.aspx?manID=191); [Sawbones biyomekanik test materyalleri kataloğu](https://pdf.medicalexpo.com/pdf/sawbones-pacific-research-labs/biomechanical-test-materials/103604-179595.html)):

- **Cellular rigid PU foam** (hücreli): 7.5–20 PCF (≈0.12–0.32 g/cm³), hücre boyutu 0.5–1.0 mm → **insan spongioz (kansellöz) kemiğine en yakın**, en sık trabeküler simülasyonu için.
- **Solid rigid PU foam** (solid): daha yüksek yoğunlukta → **kortikal tabaka** simülasyonu için.
- **Laminated bloklar:** Sawbones, solid + cellular köpüğü laminе ederek kortikal+trabeküler iki katmanlı bloklar üretir → D2/D3 gibi "kortikal kabuk + trabeküler çekirdek" yapısını taklit için ideal.

**PCF ↔ g/cm³ ↔ Misch dönüşümü** (yaklaşık):

| PCF | g/cm³ | Yaklaşık Misch karşılığı |
|---|---|---|
| 10 | 0.16 | D4 (bazı kaynaklarda D3 — **doğrulanmalı**) |
| 15 | 0.24 | **D3 (trabeküler çekirdek)** |
| 20 | 0.32 | D2 |
| 30 | 0.48 | yoğun kansellöz / ince kortikal |
| 40 | 0.64 | kortikal tabaka |

> **Önemli — literatürde tutarsızlık:** Bazı kaynaklar 10 PCF'yi doğrudan D3 (0.16 g/cm³) olarak verirken, daha yaygın dental in-vitro tasarımları **10 PCF = D4** ve **20 PCF = D2** kabul eder; bu durumda **D3'ün mantıksal karşılığı 15 PCF (0.24 g/cm³)** trabeküler köpüktür. Tez için tek bir kaynağa değil, kullandığın bloğun **ölçülen yoğunluğuna (g/cm³) ve HU değerine** dayanmak en güvenli yoldur. **(Bu eşleştirme doğrulanmalı; kullanılan blok satın alındığında veri sayfasındaki yoğunluk rapor edilmeli.)**

### 2.2 Kortikal tabaka nasıl ekleniyor?

D3 "poröz kortikal + ince trabeküler" yapı olduğu için, literatürde trabeküler köpüğün üstüne **ince bir kortikal kabuk** lamine edilir:

- Tipik dental kurgu: **15 PCF (0.24 g/cm³) trabeküler çekirdek + 1 mm kalınlığında kortikal kabuk** (kabuk genellikle 30–40 PCF). Kaynak: [Frontiers Bioeng Biotechnol 2024](https://www.frontiersin.org/journals/bioengineering-and-biotechnology/articles/10.3389/fbioe.2024.1482165/full); [PMC — Primary Stability of Implants in Polyurethane Blocks](https://pmc.ncbi.nlm.nih.gov/articles/PMC11048430/).
- Örnek tasarım: medüller kısım 15 PCF + **2 mm kortikal kısım 40 PCF** (0.64 g/cm³). **(Kortikal kalınlık ve yoğunluk çalışmadan çalışmaya değişir — doğrulanmalı.)**
- Bir başka in-vitro çalışma: 10 PCF (kortikalsiz, D4) ve 20 PCF (kortikalsiz, D2) bloklara karşı 1 mm 30 PCF kortikal kabuk eklenmiş varyasyonlar. Kaynak: [An In Vitro Analysis on Polyurethane Foam Blocks (ProQuest)](https://www.proquest.com/docview/2571095658); [PMC7216137 — Primary Stability in 10/20 pcf blocks](https://pmc.ncbi.nlm.nih.gov/articles/PMC7216137/).

> D3 için pratik kurgu: **~15 PCF trabeküler köpük + ~1 mm / 30–40 PCF kortikal kabuk** ve elde edilen bloğun HU'sunu CBCT ile 350–850 aralığında doğrulamak.

### 2.3 Guide doğruluğu çalışmalarında kullanılan modeller (metodolojik emsal)

Dikkat: Senin çalışmanın asıl konusu olan **fiksasyon pini / guide doğruluğu** in-vitro çalışmalarının çoğu D3 poliüretan **değil**, sert epoksi/reçine model kullanmıştır — bu, senin çalışmanın doldurabileceği bir boşluk (D3 yoğunluğunda gerçekçi drilling davranışı):

- **Chen ve ark. (2023), *J Oral Maxillofac Surg*** — maksiller serbest sonlu modelde fiksasyon pinleri doğruluğu artırıyor; bilateral pin en az sapma. Hasta dental modeli kullanılmış. *Based on PubMed.* [DOI: 10.1016/j.joms.2022.12.017](https://doi.org/10.1016/j.joms.2022.12.017) (PMID 36716792).
- **Elnadoury ve ark. (2025), *J Prosthodont*** — mandibular tek taraflı diş destekli guide'larda iki fiksasyon pini en iyi stabilite/en az sapma; **epoksi reçine model + yumuşak doku simülasyonu** kullanılmış. *Based on PubMed.* [DOI: 10.1111/jopr.14043](https://doi.org/10.1111/jopr.14043) (PMID 40038852).
- **Pessoa ve ark. (2021), *J Prosthodont*** — maksiller serbest sonlu; **reçine model**; fiksasyon pininin depth ve angular sapmaya etkisi anlamlı. *Based on PubMed.* [DOI: 10.1111/jopr.13371](https://doi.org/10.1111/jopr.13371) (PMID 33904640).

> Düşük kemik yoğunluğunda drilling trajektörünün yumuşak kemiğe doğru saptığı, en yüksek sapmanın **< 500 HU** durumunda görüldüğü bildirilmiştir ([PMC7502099 — Influence of bone condition on guided surgery accuracy](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7502099/)). Bu, D3 (350–850 HU) bloğu kullanmanın senin çalışman için neden önemli/anlamlı olduğunu güçlendirir.

### 2.4 Diğer model materyalleri

- **Epoksi reçine + kısa-fiber dolgulu epoksi:** Sawbones'un kortikal benzeri katmanlarda kullandığı malzeme; çok sert, daha çok kortikal/diş modeli için.
- **Hayvan kemiği (domuz/sığır kaburga, tavuk femuru):** gerçekçi ama heterojen, standardizasyonu zor; tekrarlanabilirlik düşük.
- **Reçine/jel kompozitleri:** primer stabilite ve strain çalışmalarında görülür; ancak D3 trabeküler mimarisini taklit etmez, guide drilling davranışı için PU köpük kadar valide değildir.

---

## 3. SLA/DLP Reçine ile 3D Baskı Seçeneği

> Ozan'ın yazıcısı **SLA/DLP (vat fotopolimerizasyon)** — FDM değil. Bu bölüm bu teknolojiye göre yazılmıştır.

**Kısa cevap:** SLA/DLP reçine ile *masif* (solid) blok basıp D3 trabeküler kemiği taklit etmek mekanik olarak **gerçekçi değildir**; gözenekli kafes (lattice) basarak efektif yoğunluğu D3 aralığına çekmek **teorik olarak mümkün ama** tez için validasyon yükü ve tekrarlanabilirlik riski yüksektir. Tez için **hazır Sawbones poliüretan blok** önerilir.

### 3.1 Reçine tipleriyle D3'e ne kadar yaklaşılabilir?

D3 trabeküler kemiğin efektif elastik modülü kabaca **~0.1–0.8 GPa (100–800 MPa)** rejimindedir (Calvert 2010'daki 0.24 g/cm³ köpük için ~115 MPa ile uyumlu). SLA/DLP reçinelerin *bulk* (masif) modülleri bu hedefle örtüşmez:

- **Rijit / "model" / standart dental reçineler:** Masif halde elastik modülleri tipik olarak **~1.5–2.5 GPa** ve kırılgandır — D3'ten çok daha sert, kemik gibi "yontulma/drilling" hissi vermez. Mekanik özellikler dolgu (filler) oranı, baskı yönü ve post-cure ile değişir ([PMC8874542 — filler/yön etkisi](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8874542/); [Sci Rep 2025 — ısı destekli post-cure modülü artırıyor](https://www.nature.com/articles/s41598-025-85529-7)).
- **Esnek / "tough" / "flexible" reçineler:** Modülü düşürür ama davranışı **elastomerik/sünek** hale gelir; kemik gibi gevrek-gözenekli kırılma yerine esner. Drilling ve pin tutuşu açısından D3'ü taklit etmez.
- **"Bone-like" / biyo-reçineler:** Çoğu **doku mühendisliği skafoldu** (hücre kültürü) için geliştirilmiştir, mekanik olarak dental implant drilling testi için valide edilmemiştir.

**Sonuç:** Tek bir reçineyi seçerek masif blokla D3'ü yakalamak gerçekçi değil — D3 davranışının asıl kaynağı **malzeme değil gözenekli mimaridir**.

### 3.2 Gözenekli/trabeküler iç yapı (lattice/gyroid) ile efektif yoğunluk ayarı — pratikte uygulanabilir mi?

Prensip olarak evet, sınırlı koşullarda:

- **Mekanik kanıt:** DLP ile basılan **gyroid skafoldlarda basma modülü ~0.4–0.5 MPa** elde edilip insan kansellöz kemik aralığına oturtulabilmiş; **bağıl yoğunluk ~0.2–0.65** aralığında modül lineer olarak ayarlanabiliyor ([PMC9687763 — DLP gyroid skafold, kemik doku mühendisliği](https://pmc.ncbi.nlm.nih.gov/articles/PMC9687763/); [SLA lattice mekanik optimizasyon, MDPI 2025](https://www.mdpi.com/2504-4494/9/11/354)). Yani gyroid/Voronoi hücre boyutu + duvar kalınlığı + bağıl yoğunlukla efektif modül **kalibre edilebilir**.
- **Çözünürlük:** SLA/DLP çözünürlüğü (~25–50 µm) gyroid/lattice basmaya yeterlidir; trabeküler ölçek (D3 por boyutu ~125–234 µm, Calvert 2010) basılabilir aralıktadır.

**Pratik sorunlar (tez için kritik):**

- **Kırılganlık:** Standart rijit reçineler gevrek; ince trabeküler duvarlar drilling ve pin yerleştirmede **çatlayıp kırılabilir**, gerçek trabeküler kemiğin plastik deformasyonunu vermez.
- **Temizlik (wash) sorunu:** Kapalı/iç içe lattice hücrelerinde **hapsolmuş reçine** kalır; IPA yıkaması ile tam temizlenmezse boyut ve mekanik özellikler bozulur ([gyroid post-proses: IPA + UV fırın cure](https://pmc.ncbi.nlm.nih.gov/articles/PMC9687763/)).
- **Post-cure homojensizliği:** UV kürleme kalın/gözenekli yapıda eşit nüfuz etmez → blok içinde **modül gradyanı**; tekrarlanabilirlik düşer ([yüzey defektleri SLA gyroid](https://www.researchgate.net/publication/372795832_Identification_of_Surface_Defects_on_an_SLA-Printed_Gyroid_Lattice_Structure)).
- **Anizotropi:** Baskı yönü mekanik özellikleri değiştirir; her blok aynı yönde basılmalı.
- **Kortikal kabuk:** D3'ün poröz kreştal kortikalini ayrıca modellemek (yoğun kabuk + gözenekli çekirdek tek baskıda) tasarımı daha da karmaşıklaştırır.

### 3.3 Literatürde SLA/DLP reçineyle basılmış kemik/maksilla modeli kullanan çalışma var mı?

- **Eğitim/ex-vivo amaçlı VAR:** SLA/DLP ile basılmış maksilla/mandibula modelleri implant yerleştirme ve sinüs lift **eğitimi** için kullanılmıştır (ör. [Sinus Lift and Implant Insertion on 3D-Printed Polymeric Maxillary Models — ex vivo training, PMC8538196](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8538196/); [DLP basılı maksilla/mandibula eğitim modelleri, PMC12395827](https://pmc.ncbi.nlm.nih.gov/articles/PMC12395827/)). Ancak bunlar **belirli bir Misch yoğunluğuna (D3) kalibre edilmiş ve doğruluk/sapma ölçümü için valide edilmiş** modeller değildir.
- **D3'e valide edilmiş, accuracy/guide stabilitesi ölçen baskı reçine kemik modeli: bulunamadı.** İncelenen guide doğruluğu / fiksasyon pini in-vitro çalışmaları (Chen 2023; Elnadoury 2025; Pessoa 2021) **sert epoksi/reçine model** kullanmış, fakat bunları **D3 yoğunluk analoğu olarak sunmamış** ve kemik yoğunluğunu kontrol değişkeni yapmamıştır. Yani "SLA/DLP reçineyle basılmış, mekanik olarak D3'e oturtulmuş, guide stabilitesi/implant sapması ölçen" bir çalışma literatürde **belirgin değildir** — bu senin çalışmanın özgün katkı alanı.

### 3.4 Net pratik öneri

**Tez için: hazır Sawbones (ASTM F1839) poliüretan blok kullan, kemik bloğunu basma.** Gerekçe: literatürde kabul gören, mekanik özellikleri yayınlanmış (Calvert 2010), yoğunluğu/HU'su standart ve tekrarlanabilir; danışman ve hakem önünde savunması en kolay yol. SLA/DLP yazıcını **cerrahi guide'ları** basmak için kullan.

**Eğer yine de baskı (lattice) yolu denenecekse — zorunlu validasyon protokolü:**

1. **Tasarım:** Gyroid/Voronoi iç yapı + bağıl yoğunluğu 0.2–0.65 arasında parametrik tara; üzerine ~1 mm yoğun kortikal kabuk modelle. Tüm bloklar **aynı baskı yönünde** basılmalı.
2. **Standart post-proses:** Sabit süre IPA yıkama + sabit süre/sıcaklıkta UV fırın cure (her blok için birebir aynı reçete).
3. **Mekanik validasyon (basma testi):** ASTM F1839/D1621 mantığında **uniaksiyel basma** ile elastik modül ve basma dayanımını ölç; **D3 hedefi: modül ~100–800 MPa, basma dayanımı ~4–10 MPa** (Calvert 2010 aralığı). Hedefe oturan bağıl yoğunluğu sabitle.
4. **Radyolojik validasyon (CBCT-HU):** Basılan bloğun CBCT'sini çek, **350–850 HU (D3)** aralığında olduğunu doğrula ve raporla. (Not: polimer HU'su gerçek kemikten farklı atenüasyon gösterebilir; HU'yu mutlak değil **kontrol/karşılaştırma** amaçlı kullan — **doğrulanmalı.**)
5. **Tekrarlanabilirlik:** En az 3–5 özdeş blokta modül/HU varyasyonunu (CV %) raporla; yüksek varyasyon baskı yolunu geçersiz kılar → Sawbones'a dön.

---

## 4. Tez İçin Öneri

1. **Kemik modeli:** Hazır **Sawbones / ASTM F1839 rijit poliüretan blok** kullan.
   - D3 trabeküler çekirdek: **~15 PCF (0.24 g/cm³)** hücreli (cellular) köpük.
   - Üstüne **~1 mm kortikal kabuk** (30–40 PCF solid köpük) lamine et (D3'ün poröz kreştal kortikalini temsilen). Laminе bloğu Sawbones'tan hazır da sipariş edebilirsin.
   - **(Tam PCF/kortikal kalınlık seçimi, satın alınan bloğun veri sayfasıyla doğrulanmalı.)**
2. **Doğrulama:** Satın aldıktan sonra bloğun **yoğunluğunu (g/cm³)** ve **CBCT ile HU değerini** ölç, 350–850 HU D3 aralığında olduğunu rapor et. Bu, materyal seçimini metodolojik olarak sağlamlaştırır.
3. **SLA/DLP baskı:** Cerrahi **guide'ları** kendi SLA/DLP yazıcında bas; **kemik bloğunu basma**. Masif reçine D3'ten çok sert/kırılgan; gözenekli lattice ile D3'e oturtmak mümkün ama validasyon yükü ve tekrarlanabilirlik riski yüksek (Bölüm 3.2–3.4). Baskı yolu sadece pilot/ek deney olarak ve Bölüm 3.4'teki basma testi + CBCT-HU validasyonuyla denenmeli.
4. **Metot yazımında:** Materyali "Misch D3 (350–850 HU), 15 PCF trabeküler + 1 mm kortikal PU köpük (ASTM F1839)" şeklinde, **hem yoğunluk hem HU** ile tanımla; Calvert (2010) ile mekanik geçerliliğe atıf yap.
5. **Literatür konumlandırması:** Fiksasyon pini guide çalışmalarının çoğu sert reçine model kullandığı için (Chen 2023; Elnadoury 2025; Pessoa 2021), **D3 yoğunluğunda gerçekçi blok kullanman çalışmanın özgün katkısı** olarak vurgulanabilir.

---

## 5. Sawbones Özel Model / STL ile Üretim

**Kısa cevap:** Evet — Sawbones özel (custom) anatomik model üretiyor; **müşterinin CAD/STL dosyasından** kişiye/anatomiye özel model yapabiliyor ve **yoğunluğu istenen dental dereceye (D-grade) göre ayarlayabiliyor**. Hazır maksilla/mandibula modelleri de katalogda mevcut. Kesin teknik detaylar (tam yöntem, çözünürlük, teslim süresi, fiyat) **proje bazlı olduğundan Sawbones'a doğrudan teklif için sorulmalıdır.**

**1) Özel üretim hizmeti var mı? (STL/CAD'den)**
Evet. Sawbones'un **Custom Anatomical Workshop Models** hizmeti var; müşteriyle birlikte tasarlayıp üretiyorlar ve **CAD modellerini kabul ediyorlar** — kendi mühendisleri 3D ortamda form/fit/function doğrulayıp model üretiyor. "Herhangi bir yoğunluk, kırık veya patolojiyi replike edebiliriz" diyorlar. Kaynak: [Sawbones — Custom Anatomical Workshop](https://www.sawbones.com/custom-anatomical-workshop); [Sawbones ana sayfa](https://sawbones.com/). **(STL'in CNC ile mi işlendiği yoksa 3D mi basıldığı proje/ geometriye göre değişir — birden çok üretim yöntemine erişimleri olduğunu belirtiyorlar; kesin yöntem Sawbones'a sorulmalı — doğrulanmalı.)**

**2) D3 benzeri yoğunluk + kortikal/trabeküler katman seçilebiliyor mu?**
Evet. Sawbones **maksilla/mandibulada köpük yoğunluğunu belirli dental derecelendirme spesifikasyonlarına göre değiştirebildiğini** belirtiyor; ürünleri farklı yoğunluk ve materyallerden üretiyorlar. Kortikal+trabeküler yapı standart üründe zaten mevcut: **"foam cortical shell + inner cancellous"** (rijit köpük kabuk + iç kansellöz). Bu modeller "plastik kortikal kabuklu modellerden daha kolay kesilir/drill edilir." Yani **D3 için: ince poröz kortikal kabuk + ~15 PCF trabeküler çekirdek** custom olarak istenebilir. Kaynaklar: [Sawbones dental ürün açıklamaları (custom density)](https://omssupply.com/collections/jaw-model/sawbones); [Mandible w/ foam cortical shell + cancellous + teeth #1337-3](https://www.sawbones.com/mandible-large-foam-cortical-shell-w-cancellous-w-teeth-1337-3.html). **(Tam PCF/HU eşleştirmesi ve "D3" etiketiyle sipariş edilip edilemeyeceği teklifte netleştirilmeli — doğrulanmalı.)**

**3) Hazır maksilla/mandibula modelleri (katalog örnekleri):**
- **Maxilla, Partially Edentulous (vise attachment'lı)** — #1348-11. [Ürün](https://sawbones.com/products/maxilla-partially-edentulous-with-vise-attachment.html)
- **Maxilla, Edentulous** (solid foam) — [Ürün](https://sawbones.com/products/maxilla-edentulous.html)
- **Mandible, Partially Edentulous** — [Ürün](https://sawbones.com/products/mandible-partially-edentulous.html)
- **Mandible w/ Teeth, Foam Cortical Shell + Cancellous** — #1337-3; solid foam varyant #1337-21. [Ürün](https://www.sawbones.com/mandible-large-foam-cortical-shell-w-cancellous-w-teeth-1337-3.html)
- CMF/Dental katalog: [Cranio-Maxillofacial Surgical Catalog (PDF)](https://pdf.medicalexpo.com/pdf/sawbones-pacific-research-labs/cranio-maxillofacial-surgical-catalog/103604-179597.html); [CMF Specialty Models](https://www.sawbones.com/catalog/cmf-specialty-models.html). **(Parça numaralarını ve güncel D-grade seçeneklerini güncel katalog/teklifle doğrula.)**

**4) STL gönderme süreci, yöntem ve pratik kısıtlar:**
- **Süreç:** STL/CAD dosyasını Sawbones mühendislik ekibine gönderirsin; tasarımı doğrulayıp teklif çıkarırlar. İletişim: ABD hattı **(206) 463-5551** veya site üzerinden custom talebi. Kaynak: [Custom Anatomical Workshop](https://www.sawbones.com/custom-anatomical-workshop).
- **Yöntem:** Köpük modeller için tipik olarak **CNC işleme (machining)** ve diğer üretim yöntemleri kullanılır; geometriye göre değişir — **kesin yöntem teklifte belirtilir (doğrulanmalı).**
- **Pratik kısıtlar:** Özel üretim **teslim süresi ve fiyatı proje bazlıdır** (standart kataloğa göre daha uzun/pahalı). CNC işlemede **çok ince trabeküler iç mimari** birebir çıkmayabilir (kortikal kabuk + homojen kansellöz çekirdek olarak temsil edilir). Minimum detay/çözünürlük ve gümrük/kargo (Türkiye'ye ithalat) **Sawbones'a / distribütöre sorulmalı — doğrulanmalı.**

**Tez için pratik öneri:** Atrofik üst çene anatomisi önemliyse iki seçenek mantıklı: (a) **hazır partially/edentulous maksilla modeli** (#1348-11 / edentulous maxilla) üzerinde standart D-grade; (b) **kendi CBCT/STL'inden custom maksilla** + D3 yoğunluğu siparişi. Her iki yolda da satın alınan modelin **gerçek yoğunluğu (g/cm³) ve CBCT-HU'su (350–850 = D3)** tezde rapor edilmelidir. Custom yol için **yazılı teklifte: D-grade/PCF, kortikal kalınlık, üretim yöntemi (CNC/print), teslim süresi ve fiyat** netleştirilmeli.

---

## 6. Türkiye'deki Tedarikçiler / Firmalar

> **Uyarı:** Aşağıdaki firmalar gerçek web kaynaklarına dayanır; reklam değildir. Ancak **hiçbiri "Sawbones'a denk, D3 yoğunluğuna kalibre poliüretan kemik analoğu üretiyor" diye doğrulanmamıştır.** Türkiye'deki firmaların çoğu **CT/STL'den polimer/reçine ile hastaya-özel anatomik model** basar — bunlar görüntü/anatomi olarak doğru olsa da **mekanik olarak D3'e valide değildir** (Bölüm 3'teki reçine kısıtları geçerli). Mekanik D3 gerekiyorsa en güvenli yol yine **Sawbones ithalatı** kalır. Tüm firmalarla **fiyat/teknik teklif ve malzeme yoğunluğu doğrudan teyit edilmelidir.**

**1) Sawbones'un Türkiye distribütörü:**
- Aramada **resmî, doğrulanmış bir Türkiye distribütörü bulunamadı (doğrulanamadı).** (Not: "Sawbones / D&R" sonucu medikal modelle ilgisiz bir kitap/albüm kaydıdır, distribütör değildir.) En güvenilir yol: **Sawbones'a doğrudan yazıp Türkiye/Avrupa distribütörünü sormak** ([sawbones.com](https://sawbones.com/), tel +1 206-463-5551) veya Türkiye'deki ortopedi/medikal cihaz ithalatçılarına Sawbones temini için sormak. Ithalat alternatifi: Avrupa kolu **Sawbones Europe (İsveç, Malmö)** üzerinden tedarik.

**2) Türkiye'de poliüretan köpük kemik test bloğu üreten/satan firma:**
- Aramada **Sawbones benzeri ASTM F1839 poliüretan kemik bloğu üreten yerli bir firma doğrulanamadı.** Biyomekanik test laboratuvarları (ör. test hizmeti veren EUROLAB, TechCert) mevcut ama bunlar **test hizmeti** verir, kemik analoğu **üretmez (doğrulanmalı).** Bu malzeme pratikte **ithal** ediliyor. Türk akademik derlemeler de kemik mekanik testlerinde poliüretan/Sawbones'u referans materyal olarak anar ([DergiPark — kemik mekanik test materyalleri derlemesi](https://dergipark.org.tr/tr/download/article-file/1475085)).

**3) Türkiye'de STL'den özel anatomik / dental model 3D baskı hizmeti veren firmalar:**

Medikal/anatomik 3D baskı (CT-MRI/STL → hastaya özel model, cerrahi planlama):
- **3D Medikal** (3dmedikal.com) — hastaya özel anatomik model, cerrahi kılavuz, patient-specific implant/guide tasarımı. [Site](https://3dmedikal.com/hizmetler/23-hastaya-ozel-3b-anatomik-model)
- **ARTI90 / +90 3B Dijital Fabrika** — Stratasys J750 ile çok-malzemeli ("doku kadar yumuşak, kemik kadar sert") anatomik model. [Site](https://arti90.com/medikal-anatomik-model/)
- **Trabtech (BTECH)** — CT/MRI verisinden hastaya özel 3D baskılı anatomik model, cerrahi planlama. [Site](https://www.btech.com.tr/trabtech)
- **3DDT** (3ddt.com.tr) — medikal 3D baskı ve modelleme hizmeti + yazıcı satışı. [Site](https://www.3ddt.com.tr/uygulamalar/medikal/)
- **Yazdır Gelsin** — hastaya özgü anatomik yapı / cerrahi rehber 3D baskı. [Blog/hizmet](https://yazdirgelsin.com/blog/3d-baski-ile-tip-ve-dis-hekimliginde-dijital-donusum)

Dental-odaklı (cerrahi rehber / diş modeli SLA-DLP baskı):
- **DİGİLAB 3D** — İstanbul, Şişli; cerrahi plak/guide, model, dental reçine baskı + yazıcı/reçine satışı. [Site](https://www.digilab3dstore.com/)
- **3Dream** — dental reçine/model ürünleri ve baskı desteği. [Dental sayfa](https://store.3dream.com.tr/pages/dental)
- **Dentek Diş Protez Laboratuvarı** — İzmir (Konak); dental 3D baskı/protez laboratuvarı. [Site](https://www.dentek.com.tr/3d-baski/)
- **Erlas** — dental 3D baskı/prototip hizmeti. [Site](https://erlas.com.tr/3d-prototip/dental-3d-baski)

**4) Tez için pratik yönlendirme:**
- **Mekanik olarak D3'e sadık blok** istiyorsan: yerli üreticiden çok **Sawbones (ithalat)** + Bölüm 5'teki custom maksilla yolu en savunulabilir seçenek.
- **Anatomik maksilla geometrisi** (kendi STL'inden) istiyorsan: yukarıdaki medikal 3D baskı firmaları (3D Medikal, ARTI90, Trabtech, 3DDT) üretebilir; ancak **malzeme D3 mekaniğini taklit etmez** → bu durumda yine basılan modelin **yoğunluk + CBCT-HU validasyonu** (Bölüm 3.4) yapılmalı, ya da firmaya "D3 mekaniğine yakın gözenekli/lattice baskı" yapıp yapamayacağı **özel olarak sorulmalı (doğrulanmalı).**
- En pragmatik kombinasyon: **Guide'lar** → yerli dental SLA/DLP büro veya kendi yazıcın; **D3 kemik bloğu** → ithal Sawbones. Tüm firma yetkinlikleri ve fiyatları **doğrudan teklifle teyit edilmelidir.**

---

## 7. Yerli Reçine Modellerin Akademik Kabulü

**Soru:** Türkiye'deki firmaların STL'den polimer/reçineyle bastığı anatomik modeller literatürde kabul gören modeller mi? Reviewer geçer mi?

**Kısa, dürüst yargı:** Reçine/polimer baskı modeller literatürde **belirli amaçlar için kabul görüyor (geometri, uyum, sapma)**, ama **kemik-yoğunluğuna bağlı sonuçlar için kabul görmüyor**. Senin tezinin çıktısı bu ikisinin sınırında olduğu için **materyal seçimi reviewer açısından kritik** — aşağıda ayrıştırıyorum.

### 7.1 Reçine/polimer modeller literatürde NE İÇİN kabul görüyor?

**Geometrik/pozisyonel doğruluk, guide uyumu ve sapma çalışmaları için rijit reçine model standart ve kabul gören bir tercihtir.** Bu çalışmalarda sonucu belirleyen şey **guide mekaniği ve geometri**dir, kemik yoğunluğu değil; bu yüzden sert reçine/epoksi tipodont modeller yaygın kullanılır:

- Mo ve ark. (2022), *J Dent* — guide doğruluğu test modelleri **ışıkla polimerize reçine** ile basılmış. *Based on PubMed.* [DOI: 10.1016/j.jdent.2022.104367](https://doi.org/10.1016/j.jdent.2022.104367)
- Pessoa ve ark. (2021), *J Prosthodont* — **çoğaltılmış maksiller reçine modeller** üzerinde fiksasyon pini/guide doğruluğu. [DOI: 10.1111/jopr.13371](https://doi.org/10.1111/jopr.13371)
- Elnadoury ve ark. (2025), *J Prosthodont* — **epoksi reçine model + yumuşak doku simülasyonu**; guide stabilitesi/sapma (gerçek drilling değil, **sanal implant** ile ölçüm). [DOI: 10.1111/jopr.14043](https://doi.org/10.1111/jopr.14043)
- Cheng ve ark. (2020), *Comput Biol Med* — robotik implant doğruluğu, **oral dokuları taklit eden reçine model**. [DOI: 10.1016/j.compbiomed.2020.104153](https://doi.org/10.1016/j.compbiomed.2020.104153)

> Yani: "guide oturuyor mu, kuvvet altında ne kadar kayıyor, planlanan vs. gerçek pozisyon sapması ne" sorusu için rijit reçine model **literatürde kabul edilir**. Ancak bu modeller **anatomik/geometrik geçerlilik** için kullanılır; mekanik kemik geçerliliği iddia edilmez.

### 7.2 Kemik-yoğunluğuna bağlı sonuçlar için kabul görüyor mu?

**Hayır.** Primer stabilite, insertion torque, peri-implant strain, drilling/osteotomi davranışı ve D2/D3/D4 farkı gibi **yoğunluğa bağlı** çıktılar için literatürün valide ettiği standart **ASTM F1839 rijit poliüretan köpük (Sawbones)**'tur:

- Bano & Shaukat (2025), *Cureus* — PU köpük ile epoksi reçineyi doğrudan karşılaştırmış; **PU köpük peri-implant strain tahmininde daha doğru** bulunmuş ve "geniş yoğunluk aralığı çeşitli kemik tiplerini taklit etmeyi sağladığı için biyomekanik çalışmalarda tercih edilebilir" denmiş. Ayrıca "**hiçbir tek materyal ağız içi koşullarda kemiği ideal olarak replike edemez**" uyarısı var. *Based on PubMed.* [DOI: 10.7759/cureus.79124](https://doi.org/10.7759/cureus.79124)
- Calvert ve ark. (2010) — PU köpüğün ASTM F1839'a göre mekanik karakterizasyonu (yoğunluk↔modül↔dayanım), density-bağlı çalışmaların temel referansı. [DOI: 10.1007/s10856-010-4024-6](https://doi.org/10.1007/s10856-010-4024-6)

> Standart dental SLA/DLP reçineleri masif halde ~1.5–2.5 GPa ve kırılgandır (Bölüm 3.1); D3 trabeküler kemiğin ~0.1–0.8 GPa gözenekli davranışını taklit etmez. Bu yüzden yoğunluğa bağlı çıktıda generic reçine **valide değildir.**

### 7.3 Ozan'ın tezi özelinde net yargı

Tezin birincil çıktısı: **kuvvet altında guide stabilitesi + implant sapması, D3 atrofik maksilla.** Bu, materyal seçimi açısından **iki bileşene** ayrılır:

- **Guide stabilitesi / kuvvet altında deplasman bileşeni:** Büyük ölçüde **guide tasarımı, destek ve fiksasyon pinlerine** bağlıdır; kemik yoğunluğundan görece bağımsızdır. Eğer ölçümün (Elnadoury 2025 gibi) **guide deplasmanı + sanal implant** üzerinden yapılıyorsa, rijit reçine model **savunulabilir** ve generic baskı büyük zayıflık olmaz.
- **Implant sapması / gerçek osteotomi bileşeni:** Eğer **gerçek frezleme + implant yerleştirme** yapıp sapma ölçüyorsan, drilling trajektörü kemik yoğunluğuna duyarlıdır — düşük yoğunlukta (özellikle **< 500 HU**) drilin yumuşak kemiğe sapması en yüksektir ([PMC7502099](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7502099/)). Tezin başlığı **"D3 atrofik maksilla"** olduğundan, kemik yoğunluğu **açık bir bağlam değişkenidir**; D3'e benzemeyen generic reçine kullanırsan reviewer haklı olarak "**bu sonuçlar D3'ü temsil etmiyor, dış geçerlilik zayıf**" diyebilir.

**Yargı:** Tezin D3'ü merkeze aldığı için, **generic yerli reçine baskı (D3'e valide edilmemiş) reviewer'da gerçek bir zayıflık noktasıdır** — özellikle gerçek osteotomi/sapma ölçülecekse. En güvenli ve literatürde tartışmasız yol **D3'e kalibre Sawbones poliüretan blok** kullanmaktır (gerekirse Bölüm 5'teki custom maksilla geometrisiyle). Yerli reçine baskı; ancak **(a)** ölçüm tamamen guide-deplasman/sanal-implant temelliyse **veya (b)** model aşağıdaki gibi valide edilirse kabul görür.

### 7.4 Yerli reçine baskı kullanılacaksa kabul için ne gerekir?

1. **Mekanik validasyon:** Basılan materyalin **uniaksiyel basma testi** ile elastik modül ve basma dayanımını ölç; **D3 hedefi: ~100–800 MPa modül, ~4–10 MPa dayanım** (Calvert 2010 aralığı). Gerekirse gözenekli/lattice yapıyla bu aralığa indir (Bölüm 3.2).
2. **Radyolojik validasyon:** **CBCT-HU**'yu ölç ve **350–850 HU (D3)** aralığında olduğunu raporla (polimer atenüasyonu farkı not edilmeli — **doğrulanmalı**).
3. **Materyal raporlama:** Reçine adı/üretici, baskı teknolojisi (SLA/DLP), yön, post-cure reçetesi, ölçülen yoğunluk (g/cm³), modül/dayanım ve HU değerleri **Materyal-Metot**'ta açıkça verilmeli.
4. **Kortikal+trabeküler ayrım:** D3'ün poröz kortikal kabuğu + ince trabeküler çekirdeği temsil edilmeli (tek-faz homojen reçine bunu vermez).
5. **Kısıtlılık beyanı:** "Hiçbir sentetik materyal kemiği tam replike etmez" (Cureus 2025) ifadesiyle limitation bölümünde dürüstçe belirtilmeli.

> **Pratik öneri (tekrar):** En savunulabilir kombinasyon — **guide'lar** SLA/DLP baskı (yerli büro/kendi yazıcın) + **D3 kemik bloğu** ithal **Sawbones**. Yerli reçine baskıyı kemik bloğu olarak kullanmak, ancak yukarıdaki 5 maddelik validasyon yapılırsa reviewer önünde savunulabilir.

---

## 8. Pin Pozisyonu Çalışmasında Yoğunluk Gerekli mi?

**Tasarım:** Bağımsız değişken = **fiksasyon pin pozisyonu**; bağımlı değişkenler = **guide stabilitesi (kuvvet altında mikro-hareket)** + **implant sapması**. Soru: D3'ü taklit eden bir model şart mı, sabit/basit bir materyal yeter mi?

**Kısa yargı:** Tüm gruplar aynı materyali kullandığı sürece pin pozisyonları arası **göreli fark (iç geçerlilik) korunur** — bu anlamda teorik olarak herhangi bir sabit materyal "çalışır." Ancak **pin/vida tutuculuğu kanıtlanmış biçimde yoğunluğa duyarlı** olduğundan, materyalin sertliği bağımlı değişkeni (mikro-hareket) doğrudan modüle eder; D3'ü temsil etmeyen aşırı sert bir model **etki büyüklüğünü çarpıtır ve dış geçerliliği (atrofik maksilla iddiasını) zayıflatır.** Tezin başlığı "D3 atrofik maksilla" olduğu için **minimum gereksinim: tek, klinik anlamlı bir D3 yoğunluğu, tüm gruplarda sabit.**

### 8.1 Pin tutuculuğu materyalin yoğunluğuna/sertliğine bağlı mı? (Evet — kanıt)

Bu, çalışmanın can alıcı noktası. Vida/pin **holding power (pull-out / anchorage)**'ı, içine yerleştirildiği materyalin yoğunluğu ve kayma dayanımıyla **doğrudan** artar:

- **Ramaswamy ve ark. (2009), *Injury*** — farklı yoğunlukta PU köpük bloklarda (osteoporotik/osteopenik/normal) vida pull-out ve push-out dayanımı **yoğunlukla anlamlı olarak artıyor (p<0.001)**; "vidaların tutma gücü doğrudan **kemik yoğunluğu**, diş tasarımı ve kemiğe giren diş sayısıyla ilişkilidir." *Based on PubMed.* [DOI: 10.1016/j.injury.2009.08.015](https://doi.org/10.1016/j.injury.2009.08.015)
- **Chapman ve ark. (1996), *J Biomech Eng*** — kansellöz vida pull-out'u, **içine girilen materyalin kayma dayanımı** (≈yoğunluk) ile kontrol edilir; PU köpükte yüksek korelasyon (R²=0.947). [DOI: 10.1115/1.2796022](https://doi.org/10.1115/1.2796022)
- **Varghese ve ark. (2018), *Asian Spine J*** — pedikül vida pull-out'unda **yoğunluk anlamlı faktör** (p<0.05). [DOI: 10.31616/asj.2018.12.4.611](https://doi.org/10.31616/asj.2018.12.4.611)
- **Mini-implant kortikal kalınlık/yoğunluk çalışması (2020)** — kortikal kalınlık ve yoğunluk arttıkça primer stabilite/pull-out artıyor; PU köpük ASTM tarafından bu testler için öneriliyor. *Based on PubMed.* [PMID 32005469](https://pubmed.ncbi.nlm.nih.gov/32005469/)

> **Bunun senin tasarımına anlamı:** Çok sert reçinede pinler **her pozisyonda güçlü tutar** → pozisyonlar arası fark silinebilir (**tavan/ceiling etkisi**) ve "pin pozisyonu önemli" sinyali zayıf çıkar. Yumuşak D3'te tutuculuk daha düşük olduğundan **pozisyon farkı belirginleşir** — yani efekt asıl D3'te görünür. Ayrıca senin guide'ın **kemik destekli**; hem oturma yüzeyi hem pin ankrajı kemikte olduğu için yoğunluk, diş destekli tasarımlardan **daha kritik**. *(Ceiling etkisinin gerçekten oluşup oluşmayacağı pin/guide tasarımı ve uygulanan kuvvete bağlıdır; pilot deneyle doğrulanmalı — çıkarım, kesin değil.)*

### 8.2 İç geçerlilik vs dış geçerlilik

- **İç geçerlilik (gruplar arası karşılaştırma):** Tüm pin-pozisyon grupları **aynı materyale** yerleştirildiği sürece, aralarındaki **göreli fark adildir ve iç geçerli kalır** — materyal D3 olmasa bile "A pozisyonu B'den iyi" yargısı geçerli. Bu açıdan **tek, sabit bir materyal yeterlidir.**
- **Dış geçerlilik (genellenebilirlik):** Klinik iddian **"atrofik maksilla / D3"** olduğundan, ölçülen **mutlak mikro-hareket/sapma değerleri ve hatta pozisyon sıralaması** ancak materyalin sertliği D3 aralığındaysa kliniğe genellenebilir. Aşırı sert model etki büyüklüğünü küçültüp (ceiling) **pin faydasını olduğundan az** gösterebilir. Bu yüzden temsil edici yoğunluk **bilimsel iddianın geçerliliği** için gerekir — istatistiksel adalet için değil.

### 8.3 Net yargı: hangi tasarım reviewer'da savunulabilir?

- **(b) Yoğunluğu hiç kontrol etmeyen sabit sert model:** İç geçerli ama **dış geçerlilik zayıf**; reviewer ceiling etkisi ve "D3'ü temsil etmiyor" itirazını haklı olarak yapar. **Tezin D3 çerçevesi için önerilmez.**
- **(a) Tek, klinik anlamlı D3 yoğunluğu, tüm gruplarda sabit:** **Minimum savunulabilir ve önerilen taban.** İç + dış geçerliliği D3 iddiası için karşılar; basit, temiz, uygulanabilir.
- **(c) İki-yoğunluk tasarımı (D3'ü D2 veya D4 ile karşılaştırma):** **En güçlü.** Pin pozisyonu etkisinin **yoğunlukla etkileşip etkileşmediğini** (muhtemelen yumuşak kemikte pin faydası daha büyük) test eder; bu, çalışmaya özgün katkı ve daha yüksek etki katsayısı kazandırır. İş yükü artar ama yayın gücü belirgin yükselir.

> **Reviewer gözünden sıralama: (c) > (a) ≫ (b).** Kabul edilebilir taban **(a)**; mümkünse **(c)**.

### 8.4 Pratik öneri (minimum gereksinim)

- **Minimum:** **Tek bir D3 blok** (Sawbones ~15 PCF trabeküler + ~1 mm kortikal kabuk; Bölüm 2.2), **tüm pin-pozisyon gruplarında aynı yoğunluk/lot**. Bloğun yoğunluğu (g/cm³) ve CBCT-HU'su (350–850) raporlanmalı.
- **Materyal "fark etmez" yanlış:** Pin tutuculuğu yoğunluğa duyarlı olduğundan (8.1), generic sert model ölçülen mikro-hareketi sistematik olarak değiştirir → bu bir **kısıtlılık**, görmezden gelinemez.
- **Güçlendirme:** Bütçe/zaman varsa **D3 + (D2 veya D4)** iki-yoğunluk kolu ekle; "pin pozisyonunun önemi düşük yoğunlukta artar mı?" hipotezini test et — bu, tezi sıradan bir doğruluk çalışmasından **mekanik-bağlamlı özgün bir çalışmaya** taşır.
- **Sabit tut:** Yoğunluk dışındaki her şey (guide üretim parametreleri, sleeve, dril protokolü, kuvvet yönü/büyüklüğü, operatör) tüm gruplarda standart olmalı; tek değişen pin pozisyonu (ve eklenirse yoğunluk) olmalı.

---

## 9. Maliyet Ön Araştırması

> **ÖNEMLİ:** Aşağıdaki rakamlar **tahmini / mertebe** bilgisidir; bir kısmı satıcı sayfasından doğrulandı, bir kısmı **kamuya açık listede yoktur ve kesin fiyat için resmi teklif (quote) gerekir.** Uydurma fiyat verilmemiştir; bulunamayan yerler açıkça işaretlenmiştir. Fiyatlar Haziran 2026 itibarıyla; kur, kargo, gümrük ve KDV hariç.

### 9.1 Sawbones standart poliüretan test bloğu (ASTM F1839)

- **Ürün:** Solid/cellular rigid foam bloklar, standart boyut **130 × 180 × 40 mm**; 5–50 PCF aralığında derecelerle; laminе (kortikal+trabeküler) seçenekli. Kaynak: [Sawbones — Blocks, Cylinders and Sheets](https://sawbones.com/biomechanical/blocks-cylinders-and-sheets/); [15 PCF blok ürün sayfası](https://sawbones.com/products/block-solid-foam-15-pcf-40-mm-thick.html); [laminе bloklar](https://sawbones.com/laminated-blocks/).
- **Birim fiyat:** **Kamuya açık fiyat bulunamadı** (ürün sayfalarında liste fiyatı görünmüyor). Bu biyomekanik bloklar genelde **birim başına onlarca USD mertebesinde** beklenir, ancak bu **doğrulanmamış bir mertebe tahminidir — kesin fiyat için Sawbones/distribütör teklifi gerekir.** Laminе (kortikal kabuklu) ve custom kesim bloklar standarttan pahalıdır.
- Not: D3 kurgusu için ya hazır **15 PCF + custom kortikal lamine** blok ya da ayrı 15 PCF trabeküler + ince kortikal sheet sipariş edilebilir; her ikisi de **teklif gerektirir.**

### 9.2 Sawbones custom anatomik maksilla (STL'den, D3 custom yoğunluk)

- **Fiyat: kamuya açık değil — tamamen proje bazlı teklif.** Custom anatomik modeller (özel geometri + özel yoğunluk + kortikal/trabeküler katman), standart kataloğa göre belirgin pahalıdır.
- **Mertebe (doğrulanmamış tahmin):** Tek seferlik mühendislik/kalıp + üretim nedeniyle genelde **birkaç yüz ila birkaç bin USD** bandında olması beklenir; adet arttıkça birim düşebilir. Bu sayı **kaynakla doğrulanmadı; Sawbones'tan yazılı teklif şart.** İletişim: [Custom Anatomical Workshop](https://www.sawbones.com/custom-anatomical-workshop), +1 206-463-5551.

### 9.3 Hazır Sawbones çene modelleri (doğrulanmış fiyatlar)

Satıcı **OMS Supply** (omssupply.com) üzerinden doğrulanan güncel fiyatlar ([kaynak sayfa](https://omssupply.com/collections/jaw-model/sawbones)):

| Model | Item # | Materyal | Fiyat (USD) |
|---|---|---|---|
| Maxilla with Mucosa | 1336-5 | Solid foam | **$50.00** |
| Mandible with Mucosa | — | Solid foam | **$75.00** |
| Mandible w/ Knife Ridge Deformity | 1336-4 | **Foam cortical shell** | **$45.00** |

- Arama sonuçlarında ek MSRP değerleri de görüldü (ör. Maxilla with Drill Holes ~$48.5; Partially Edentulous Maxilla #1337-29-5 ~$43; Mandible+Maxilla assembly #1345-30 ~$57.75) — bunlar **satıcı sayfasından birebir doğrulanmadı (doğrulanmalı).**
- **Uyarı:** Bu hazır modeller **solid foam / eğitim** amaçlıdır; çoğu **D3'e kalibre değildir.** D2/D3/D4 yoğunluk garantisi istiyorsan biyomekanik blok (9.1) veya custom (9.2) yolu gerekir.

### 9.4 Yerli (Türkiye) 3D baskı maliyeti

- **Per-gram TL fiyatı net bulunamadı (teklif gerekir).** Türk SLA/medikal baskı firmaları genelde **anlık teklif (model yükle → fiyat al)** sistemiyle çalışıyor: [Yazdır Gelsin fiyat hesapla](https://yazdirgelsin.com/3d-baski-fiyati-hesapla); [3Dedi teklif](https://3dedi.com/3d-baski); [Xometry Türkiye SLA](https://xometry.com.tr/tr/3d-baski-sla/); [3Durak SLA](https://www.3durak.com/pages/sla-3d-baski-hizmeti).
- **Mertebe (doğrulanmamış):** Genel SLA reçine baskıda maliyet model hacmi (gram) + reçine türü + işçilikle belirlenir; standart dental reçine baskılar **model başına düşük–orta yüz TL ila birkaç bin TL** bandında olabilir (geometri/boyuta göre). Bu **kaba mertebe**dir; **kesin fiyat için firmaya STL ile teklif** verilmeli. Uluslararası referans: dental ark modeli baskı ~**$5/model** (EPAX Dental) — yerli fiyat için bağlayıcı değil.
- **Cerrahi guide baskısı** (kendi yazıcın veya yerli büro) ayrıca düşük maliyetli — asıl maliyet kemik modelinde.

### 9.5 Çalışma için toplam tahmini bütçe (örnek senaryo)

> Varsayımlar açıkça belirtilmiştir; gerçek sayı tasarıma göre değişir.

**Senaryo A — Tek D3 yoğunluğu, non-destructive ölçüm (guide deplasmanı tarama ile, Elnadoury 2025 mantığı):**
- 3–4 pin pozisyonu × n=10 ölçüm, ama drilling yok → **model tekrar kullanılabilir** → ~**3–6 D3 blok** (yedek dahil).
- Maliyet: 9.1 bloğu mertebesi (onlarca USD/blok, doğrulanmalı) → kabaca **birkaç yüz USD** + kargo/gümrük/KDV. En ekonomik yol.

**Senaryo B — Tek D3 yoğunluğu, destructive (gerçek osteotomi + implant):**
- Her osteotomi sahası tükenir. 4 pozisyon × n=10 = **40 saha**; 130×180 mm blok ~6 saha barındırır → ~**7 blok + pilot ≈ 8–12 blok**.
- Maliyet: **birkaç yüz–~1.000+ USD** mertebesi (blok birim fiyatı doğrulanmalı) + kargo/gümrük/KDV.

**Senaryo C — İki yoğunluk (D3 + D2/D4), destructive:**
- B'nin ~2 katı blok → ~**16–24 blok**; maliyet **~1.000–2.000+ USD** mertebesi. En güçlü tasarım, en yüksek bütçe.

**Custom anatomik maksilla ile (9.2):** Eğer non-destructive ölçümle **1–3 custom model** yeniden kullanılırsa, custom mühendislik bedeli (birkaç yüz–birkaç bin USD, doğrulanmalı) toplamı belirler; destructive ve çok adet gerekiyorsa maliyet hızla artar → bu durumda hazır biyomekanik blok daha ekonomik.

> **Özet mertebe:** En ekonomik gerçekçi yol **Senaryo A/B (hazır D3 blok)** → **~birkaç yüz ila ~1.000+ USD** + ithalat kalemleri. Tüm rakamlar **resmi teklifle kesinleştirilmelidir.** Türkiye'ye ithalatta **kargo + gümrük + KDV** ciddi ek kalemdir (oran/temin süresi distribütöre sorulmalı — **doğrulanmalı**).

---

## Kaynak Listesi (özet)

**PubMed (DOI ile) — *Based on articles retrieved from PubMed*:**
- Calvert KL ve ark. (2010). Characterization of commercial rigid polyurethane foams used as bone analogs for implant testing. *J Mater Sci Mater Med*. [DOI: 10.1007/s10856-010-4024-6](https://doi.org/10.1007/s10856-010-4024-6)
- Chen X ve ark. (2023). Fixation Pins Increase the Accuracy of Implant Surgery in Free-End Models. *J Oral Maxillofac Surg*. [DOI: 10.1016/j.joms.2022.12.017](https://doi.org/10.1016/j.joms.2022.12.017)
- Elnadoury EA ve ark. (2025). Factors affecting stability of surgical guides in mandibular unilateral distal extension. *J Prosthodont*. [DOI: 10.1111/jopr.14043](https://doi.org/10.1111/jopr.14043)
- Pessoa R ve ark. (2021). Impact of Surgical Guide Fixation and Implant Location on Accuracy of sCAIS. *J Prosthodont*. [DOI: 10.1111/jopr.13371](https://doi.org/10.1111/jopr.13371)
- Amini M ve ark. (2020). Influence of processing parameters on mechanical properties of a 3D-printed trabecular bone microstructure. *J Biomed Mater Res B*. [DOI: 10.1002/jbm.b.34363](https://doi.org/10.1002/jbm.b.34363)
- Bano NZ & Shaukat A (2025). Comparison of Epoxy Resin and Rigid Polyurethane Foam as a Bone Substitute to Study Implant Biomechanics. *Cureus*. [DOI: 10.7759/cureus.79124](https://doi.org/10.7759/cureus.79124)
- Mo S ve ark. (2022). Accuracy of a 3D printed sleeveless guide system (light-polymerizing resin test models). *J Dent*. [DOI: 10.1016/j.jdent.2022.104367](https://doi.org/10.1016/j.jdent.2022.104367)
- Cheng KJ ve ark. (2020). Accuracy of dental implant surgery with robotic feedback (resin oral-tissue model). *Comput Biol Med*. [DOI: 10.1016/j.compbiomed.2020.104153](https://doi.org/10.1016/j.compbiomed.2020.104153)
- Ramaswamy R ve ark. (2009). Holding power of variable pitch screws in osteoporotic, osteopenic and normal bone (PU foam). *Injury*. [DOI: 10.1016/j.injury.2009.08.015](https://doi.org/10.1016/j.injury.2009.08.015)
- Chapman JR ve ark. (1996). Factors affecting the pullout strength of cancellous bone screws (PU foam). *J Biomech Eng*. [DOI: 10.1115/1.2796022](https://doi.org/10.1115/1.2796022)
- Varghese V ve ark. (2018). Evaluating Pedicle-Screw Instrumentation Using Decision-Tree Analysis Based on Pullout Strength. *Asian Spine J*. [DOI: 10.31616/asj.2018.12.4.611](https://doi.org/10.31616/asj.2018.12.4.611)
- Mini-implant kortikal kalınlık/yoğunluk & pull-out (2020): https://pubmed.ncbi.nlm.nih.gov/32005469/

**Web / teknik kaynaklar:**
- EndoLab — ASTM F1839 Rigid Polyurethane Foam: https://endolab.org/mt-polymer-analysis/astm-f1839/
- Sawbones / MatWeb teknik veri sayfaları: https://www.matweb.com/search/GetMatlsByManufacturer.aspx?manID=191
- Sawbones biyomekanik test materyalleri kataloğu: https://pdf.medicalexpo.com/pdf/sawbones-pacific-research-labs/biomechanical-test-materials/103604-179595.html
- Primary Stability of Implants Inserted into Polyurethane Blocks (Micro-CT): https://pmc.ncbi.nlm.nih.gov/articles/PMC11048430/
- Primary Stability in 10/20 pcf Polyurethane Foam Blocks: https://pmc.ncbi.nlm.nih.gov/articles/PMC7216137/
- Compressive/tensile properties of PU foam mimicking trabecular tissue (Frontiers 2024): https://www.frontiersin.org/journals/bioengineering-and-biotechnology/articles/10.3389/fbioe.2024.1482165/full
- Influence of bone condition on guided surgery accuracy (PMC7502099): https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7502099/
- Misch sınıflaması — Pocket Dentistry: https://pocketdentistry.com/bone-density-for-dental-implants/
- CBCT Hounsfield analizi (MDPI Oral 2024): https://www.mdpi.com/2673-1592/4/3/33
- 3D reçine mekanik özellikler (filler/yön, PMC8874542): https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8874542/
- Heat-assisted vat photopolymerization (Sci Rep 2025): https://www.nature.com/articles/s41598-025-85529-7
- DLP gyroid skafold, kansellöz kemik modülü ayarı (PMC9687763): https://pmc.ncbi.nlm.nih.gov/articles/PMC9687763/
- SLA lattice mekanik optimizasyon (MDPI JMMP 2025): https://www.mdpi.com/2504-4494/9/11/354
- SLA gyroid yüzey defektleri (ResearchGate): https://www.researchgate.net/publication/372795832_Identification_of_Surface_Defects_on_an_SLA-Printed_Gyroid_Lattice_Structure
- Sawbones — Custom Anatomical Workshop (özel model / CAD): https://www.sawbones.com/custom-anatomical-workshop
- Sawbones — Maxilla, Partially Edentulous (#1348-11): https://sawbones.com/products/maxilla-partially-edentulous-with-vise-attachment.html
- Sawbones — Mandible w/ Foam Cortical Shell + Cancellous + Teeth (#1337-3): https://www.sawbones.com/mandible-large-foam-cortical-shell-w-cancellous-w-teeth-1337-3.html
- Sawbones dental modeller (custom density notu): https://omssupply.com/collections/jaw-model/sawbones
- Sawbones — Cranio-Maxillofacial Surgical Catalog (PDF): https://pdf.medicalexpo.com/pdf/sawbones-pacific-research-labs/cranio-maxillofacial-surgical-catalog/103604-179597.html
- SLA/DLP basılı polimerik maksilla modeli — ex vivo implant/sinüs lift eğitimi (PMC8538196): https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8538196/
- DLP basılı maksilla/mandibula eğitim modelleri (PMC12395827): https://pmc.ncbi.nlm.nih.gov/articles/PMC12395827/
- SLA vs DLP cerrahi guide doğruluğu (MDPI Dent J 2025): https://www.mdpi.com/2304-6767/13/10/471

**Türkiye firmaları / tedarik (Bölüm 6):**
- DergiPark — kemik mekanik test materyalleri derlemesi: https://dergipark.org.tr/tr/download/article-file/1475085
- 3D Medikal — hastaya özel anatomik model: https://3dmedikal.com/hizmetler/23-hastaya-ozel-3b-anatomik-model
- ARTI90 — medikal anatomik model: https://arti90.com/medikal-anatomik-model/
- Trabtech (BTECH): https://www.btech.com.tr/trabtech
- 3DDT — medikal 3D baskı: https://www.3ddt.com.tr/uygulamalar/medikal/
- Yazdır Gelsin — tıp/diş 3D baskı: https://yazdirgelsin.com/blog/3d-baski-ile-tip-ve-dis-hekimliginde-dijital-donusum
- DİGİLAB 3D (İstanbul): https://www.digilab3dstore.com/
- 3Dream — dental: https://store.3dream.com.tr/pages/dental
- Dentek (İzmir): https://www.dentek.com.tr/3d-baski/
- Erlas — dental 3D baskı: https://erlas.com.tr/3d-prototip/dental-3d-baski

**Maliyet (Bölüm 9):**
- Sawbones — Blocks, Cylinders, Sheets (biyomekanik bloklar): https://sawbones.com/biomechanical/blocks-cylinders-and-sheets/
- Sawbones — 15 PCF solid foam blok ürün sayfası: https://sawbones.com/products/block-solid-foam-15-pcf-40-mm-thick.html
- Sawbones — Laminated (kortikal+trabeküler) bloklar: https://sawbones.com/laminated-blocks/
- OMS Supply — Sawbones çene modelleri fiyatları (doğrulandı): https://omssupply.com/collections/jaw-model/sawbones
- Yazdır Gelsin — 3D baskı fiyat hesapla: https://yazdirgelsin.com/3d-baski-fiyati-hesapla
- Xometry Türkiye — SLA baskı: https://xometry.com.tr/tr/3d-baski-sla/
- EPAX Dental — dental baskı hizmeti (~$5/model, uluslararası): https://epaxdental.com/products/dental-printing-service

> **Uyarı:** PCF↔Misch eşleştirmeleri ve kortikal kabuk kalınlık/yoğunluk değerleri çalışmalar arası farklılık gösterir; satın alınacak bloğun gerçek yoğunluğu ve ölçülen HU değeri tezde mutlaka rapor edilmelidir. Türkiye'deki firmaların D3-mekanik yetkinliği ve Sawbones Türkiye distribütörü **doğrulanamamıştır; doğrudan teklifle teyit edilmelidir.**
