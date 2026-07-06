---
name: tez-guide-stabilite
description: "Atrofik üst çenede kemik destekli cerrahi guide'larda farklı pin pozisyonlarının (sayı/açı/bukkal-palatal) guide stabilitesine ve implant pozisyon sapmasına etkisini inceleyen in-vitro tez araştırma ajan ekibi. 11 ajan (literatür, kanıt-haritalama, metodoloji, istatistik-analiz, yazım, strateji-denetim, humanizer, özgünlük-denetim, ars-köprü, jüri-savunma, görsel-mindmap), 12 mod (full/literatur/harita/metodoloji/analiz/yazim/denetim/insansilastir/ozgunluk/ars/juri/mindmap). Kanıt haritalama her bulguyu uygun bölüme etiketler; görsel mind map 3D HTML şema üretir. Süpervizör strateji ajanı denetler; humanizer AI-yazım izlerini temizler; özgünlük-denetim cümle-düzeyi AI-pattern + yazar sesi QA yapar (dürüst çerçeve — dedektör kandırma DEĞİL); ARS köprü dergi hakem paneli/atıf/format için ARS plugin'ini orkestre eder; jüri-savunma savunmaya hazırlar ve jüri/hakem itirazını OTONOM düzeltme döngüsüne sokar (itiraz→ilgili ajan revize→strateji'ye bildirim, arada insan onayı yok). Tetikleyiciler: tez, guide stabilite, pin pozisyonu, implant sapması, kemik destekli cerrahi guide, in-vitro, materyal-metod yaz, sapma analizi, literatür tara, denetle, citation kontrol, referans doğrula, format kontrol, özgünlük denetimi, jüri sorusu, savunma hazırlık, hakem yanıtı, R&R."
metadata:
  version: "1.7.0"
  last_updated: "2026-07-05"
  status: active
  data_access_level: redacted
  task_type: open-ended
  study_design: in-vitro
  language: en
  abstract_languages: [en, tr]
  output_targets: [tez, yayin]
  owner: Ozan
---

# Tez — Guide Stabilite & Pin Pozisyonu Araştırma Ajan Ekibi

Atrofik üst çene (maksilla) modelinde, kemik destekli cerrahi guide'ların **fiksasyon pini sayısı, açısı ve konumunun** (1) guide stabilitesine ve (2) elde edilen implant pozisyonunun planlanan pozisyondan **sapmasına** etkisini in-vitro olarak değerlendiren 11 ajanlı bir tez pipeline'ı.

**Çalışma tipi:** In-vitro fiziksel test (3D-basılı atrofik maksilla modelleri + basılı guide'lar + universal test cihazı ile kuvvet + optik tarama/superimpozisyon ile sapma ölçümü).

## Araştırma Sorusu (Ana Hipotez)

> Atrofik üst çenede kemik destekli cerrahi guide'ların fiksasyon pin konfigürasyonu (sayı/açısal dağılım/bukkal-palatal giriş), kuvvet altında guide mikro-hareketini ve dolayısıyla implant pozisyon sapmasını (koronal, apikal, açısal, derinlik) anlamlı şekilde etkiler.

**Birincil sonuç ölçütü:** Kuvvet öncesi vs. kuvvet altında implant pozisyon sapması farkı (Δsapma).
**İkincil sonuç ölçütleri:** Guide mikro-hareketi (mm), guide-kemik temas stabilitesi, pin konfigürasyonuna göre stres dağılımı.

> **Pipeline özeti:** 11 ajan (literatür, kanıt-haritalama, metodoloji, istatistik-analiz, yazım faz-sıralı; strateji-denetim süpervizörü, humanizer, özgünlük-denetim, ARS-köprü, jüri-savunma, görsel-mindmap çapraz-fazlı). Faz sıralı ajanlar zinciri kurar; çapraz-fazlı ajanlar herhangi bir anda devreye girer.
>
> **Orkestrasyon modeli — iki kip:**
> 1. **Genel akış = insan-döngüde.** Hangi fazın/ajanın çalışacağına kullanıcı (mod seçimiyle) karar verir; `strateji_agent` süpürücü değil süpervizördür, faz ajanlarını otonom dispatch etmez, denetler ve öneri üretir.
> 2. **Jüri/hakem itiraz döngüsü = OTONOM (insan onayı beklemez).** Gerçek jüri (savunma) veya hakem (dergi R&R / `/ars-reviewer`) itirazı geldiğinde `juri_savunma_agent` itirazı ayrıştırır → doğru faz ajanına atar → o ajan **otomatik** revize eder → sonuç `strateji_agent`'a bildirilir ve doğrulatılır. Bu zincir arada kullanıcı onayı beklemez; **tek istisna** itirazın yeni veri toplama / bilimsel iddia değişikliği gerektirmesidir — o zaman kullanıcıya eskale edilir (ajan veri uyduramaz).

## Quick Start

**Minimal komut:**
```
Tezim için kemik destekli guide stabilitesi ve pin pozisyonu literatürünü tara
```
```
Pin konfigürasyonu değişken matrisini ve güç analizini kur
```
```
Sapma verilerimi analiz et ve uygun istatistik testini seç
```

**Tam pipeline akışı:**
1. **Literatür** (`literatur_agent`) — guide stabilitesi, fiksasyon pini, atrofik maksilla, statik navigasyon sapma çalışmalarını tara → Literatür Sentez Raporu + alıntı-hazır referans listesi
1.5. **Kanıt Haritalama** (`kanit_haritalama_agent`) — her literatür bulgusunu uygun bölüme etiketler (INTRO-bağlam/boşluk, METOD-gerekçe, DISCUSSION-destek/çelişki/mekanizma/klinik, LIMIT, FUTURE) → `literatur/kanit_haritasi.md`; yazım ajanına bölüm-hazır kanıt
2. **Metodoloji** (`metodoloji_agent`) — değişken matrisi, örneklem/güç analizi, kuvvet protokolü, model standardizasyonu, sapma ölçüm protokolü → Metodoloji Planı
3. **İstatistik & Analiz** (`istatistik_analiz_agent`) — sapma verilerini analiz et, test seç, Python ile görselleştir → Bulgular Tablosu + grafikler
4. **Yazım** (`yazim_agent`) — Introduction/Materials-Methods/Results/Discussion akademik **İngilizce**; çift hedef: **tez** (klasördeki Word format şablonuna uyar) + **dergi makalesi** (hedef derginin yazar kılavuzuna) → Tez ve/veya Makale taslağı
5. **Strateji & Denetim** (`strateji_agent`) — *süpervizör, çapraz-fazlı.* Tüm ajanları denetler, her ajana komşu literatür önerir, atıf (citation) / referans doğruluğu / yazım-dilbilgisi / format uyumunu kontrol eder → önceliklendirilmiş Strateji & Denetim Raporu. İstediğin an `denetim` modunda çalışır.
6. **İnsansılaştırma** (`humanizer_agent`) — *akademik mod.* Yazım çıktısındaki AI-yazım izlerini (em dash, AI kelime dağarcığı, rule-of-three, copula kaçınma, filler/hedging) temizler; nötr akademik register korunur, kişilik enjekte etmez. Kaynak: blader/humanizer (MIT). `yazim_agent`'in son geçişi.
6.5. **Özgünlük Denetimi** (`ozgunluk_denetim_agent`) — *QA, çapraz-fazlı.* `humanizer_agent`'tan **sonra** çalışır; metnin yazarın sesini taşıdığını doğrular ve kalan AI/robotik kalıpları (formülsel rule-of-three, aşırı hedging, jenerik geçiş, tekdüze cümle ritmi, içi boş dolgu, em-dash izi) **cümle düzeyinde** işaretleyip yazara revizyon önerir → önceliklendirilmiş **Özgünlük Denetim Raporu**. **Dürüst çerçeve:** hedef AI-dedektörünü kandırmak DEĞİL; özgün yazarlık + kaliteli akademik dil + şeffaf AI-kullanım beyanıdır (AI dedektörleri güvenilmezdir). Bilimi/veriyi/atfı/anlamı değiştirmez; metni yeniden yazmaz (o `humanizer_agent`'ın işi), denetler. `strateji_agent`'tan farkı: dar/derin (sadece özgünlük + AI-pattern + yazar sesi); strateji geniş/sığ süpervizördür.
7. **ARS Köprü** (`ars_kopru_agent`) — *orkestrasyon.* Kurulu `academic-research-skills` plugin'inin güçlü ajanlarını (`/ars-reviewer` dergi hakem paneli, `/ars-citation-check`, `/ars-abstract`, `/ars-format-convert`, bütünlük/integrity) doğru kilometre taşında çağırır. Harita: `references/ars_komut_rehberi.md`.
8. **Jüri & Savunma** (`juri_savunma_agent`) — *çapraz-fazlı.* İki iş: (a) savunma hazırlığı — beklenen jüri soruları, zayıf nokta envanteri, itiraz senaryoları, sunum iskeleti; (b) **jüri/hakem itiraz yönetimi** — itirazı ayrıştırıp doğru faz ajanına atar, o ajan **otomatik** revize eder, sonuç `strateji_agent`'a bildirilir. **Otonom döngü: arada insan onayı yok** (istisna: yeni veri gerektiren itiraz → kullanıcıya eskale).
9. **Görsel Mind Map** (`gorsel_mindmap_agent`) — *görselleştirme, çapraz-fazlı.* Proje durumundan **3D, etkileşimli, animasyonlu HTML mind map** üretir: TEZ → bölümler → makaleler → bulgular; hangi makaleden ne alınıp hangi bölüme gittiğini gösterir. `tez-mindmap/tez_mindmap.html`. **Her seans sonunda güncellenir.**

> **Tez format dosyası:** Üniversitenin tez şablonunu `Ozan-Tez` klasörüne adında `format` geçen bir Word dosyası olarak koy (örn. `tez format.docx`). `yazim_agent` Adım 0'da bu dosyayı bulur, yapısını (başlık hiyerarşisi, bölüm sırası, atıf stili, yazı tipi/aralık) çıkarır ve harfiyen uyar. Şablon her zaman paketteki genel iskeletten önceliklidir.

---

## Mod Seçimi (Routing)

| Mod | Ne zaman | Aktif ajan(lar) |
|-----|----------|-----------------|
| `full` | Baştan sona tüm pipeline | 11 ajan (aşağıdaki sırayla) |
| `literatur` | Sadece literatür taraması/senteri | `literatur_agent` |
| `harita` | Bulguları bölümlere etiketle (kanıt haritası) | `kanit_haritalama_agent` |
| `metodoloji` | Sadece çalışma tasarımı/protokol | `metodoloji_agent` |
| `analiz` | Veri elde, sadece istatistik/grafik | `istatistik_analiz_agent` |
| `yazim` | Bölüm yazımı/revizyon | `yazim_agent` |
| `denetim` | Mevcut işi denetle, öneri/literatür/atıf-format kontrolü | `strateji_agent` |
| `insansilastir` | Metni akademik modda AI-izlerinden temizle | `humanizer_agent` |
| `ozgunluk` | Humanizer çıktısını doğrula; cümle-düzeyi AI-pattern/yazar-sesi QA + öneri | `ozgunluk_denetim_agent` |
| `ars` | ARS ağır iş ajanlarını (hakem/atıf/abstract/format) orkestre et | `ars_kopru_agent` |
| `juri` | Savunma hazırlığı + jüri/hakem itirazı otonom düzeltme döngüsü | `juri_savunma_agent` |
| `mindmap` | 3D etkileşimli HTML tez şemasını üret/güncelle | `gorsel_mindmap_agent` |

**Belirsizse:** kullanıcıya hangi aşamada olduğunu sor (literatür mü topluyor, veri mi analiz ediyor, yazıyor mu).

### `full` mod — ajan sırası ve kalite kapıları

Faz-sıralı zincir (her ok bir handoff):

```
literatur → kanit_haritalama → metodoloji → [KAPI: strateji denetimi] →
istatistik_analiz → yazim → humanizer → ozgunluk_denetim →
[KAPI: ars_kopru /ars-reviewer] → juri_savunma (itiraz→otonom revizyon→strateji) →
gorsel_mindmap (seans sonu)
```

**Kalite kapıları (gate):** işaretli `[KAPI]` noktalarında bir sonraki faza geçmeden denetim çalışır.
- **Metodoloji sonrası** → `strateji_agent` tasarımı/örneklemi/ICC planını denetler; 🔴 bulgu varsa metodoloji revize edilir, sonra analize geçilir.
- **Yazım+humanizer+özgünlük sonrası** (ilk tam taslak) → `ars_kopru_agent` `/ars-reviewer` (dergi hakem paneli) + gerekiyorsa `/ars-citation-check` çalıştırır. **Bu noktadan sonra hakem/jüri itirazları `juri_savunma_agent`'ın OTONOM döngüsüne girer:** itiraz → ilgili faz ajanı otomatik revize eder → `strateji_agent`'a bildirilir/doğrulatılır. Kullanıcı arada onaylamaz; yalnız yeni-veri gerektiren itiraz eskale edilir.

Savunma öncesinde `juri_savunma_agent` proaktif modda beklenen soru seti, zayıf nokta envanteri ve sunum iskeleti üretir.

**Çapraz-fazlı ajanlar** zincire bağlı değildir, herhangi bir anda çağrılır: `strateji_agent` (istenen her denetimde), `gorsel_mindmap_agent` (her seans sonunda zorunlu güncelleme), `ars_kopru_agent` (uygun kilometre taşında), `juri_savunma_agent` (ilk taslak sonrası + savunma öncesi; itiraz geldiğinde otonom döngü).

**QA katmanı önceliği (çakışma önleme):** üç denetim katmanı farklı eksende çalışır, mükerrer denetim yapmaz — `ars_kopru → /ars-reviewer` bilimsel/metodolojik hakem denetimini yapar; `strateji_agent` format + atıf-eşleşme + referans + bütünlük denetimini; `ozgunluk_denetim_agent` yalnız yazar-sesi + AI-yazım kalıbını (cümle düzeyi) denetler. Bir konu birden çok katmana düşerse sahibi: bilimsel içerik→ARS, format/atıf→strateji, üslup/özgünlük→özgünlük.

## Tetikleyiciler

**Türkçe:** tez, tez konusu, guide stabilite, cerrahi guide, kemik destekli guide, fiksasyon pini, pin pozisyonu, pin sayısı, atrofik maksilla, atrofik üst çene, implant sapması, pozisyon sapması, statik navigasyon, kılavuzlu cerrahi, sonlu eleman, in-vitro, materyal ve metod, sapma analizi, koronal/apikal/açısal sapma, literatür tara, örneklem hesabı, güç analizi.

**İngilizce:** surgical guide stability, bone-supported guide, fixation pin, pin position, atrophic maxilla, implant deviation, static navigation accuracy, guided surgery, micro-movement, deviation analysis.

**Jüri/savunma & itiraz:** jüri sorusu, savunma hazırlık, savunma provası, beklenen sorular, zayıf nokta, hakem yanıtı, hakem itirazı, revizyon mektubu, R&R, reviewer response, defense prep, ICC güvenilirlik, ölçüm güvenilirliği, çokluluk düzeltme.

### Tetiklemez (başka skill kullan)

| Senaryo | Bunun yerine |
|---------|--------------|
| Digimplant ürün/sipariş/katalog işi | `digimplant-*` ajanları |
| Genel literatür taraması (teze özel değil) | `deep-research` |
| Word/PDF/Excel format çıktısı üretmek | `docx` / `pdf` / `xlsx` skill'leri |

---

## Handoff / Material Passport (Ajanlar arası veri devri)

Her ajan kendi çıktısını isimlendirilmiş bir "ürün" olarak üretir; sonraki ajan bunu girdi alır. **Kalıcılık kuralı:** her ana teslimat sohbet bağlamına ek olarak `Ozan-Tez/tez-cikti/` altında sabit bir dosyaya yazılır; böylece handoff oturumlar arası kırılmaz (bağlam kaybolsa da sonraki ajan diskten okur). Sohbet bağlamı yalnız hız içindir, kaynak-doğru değildir.

- `literatur_agent` → **Literatür Sentez Raporu** + **Referans Listesi** → `tez-cikti/literatur_sentez.md`
- `kanit_haritalama_agent` → **Kanıt Haritası** → `literatur/kanit_haritasi.md`
- `metodoloji_agent` → **Metodoloji Planı** (değişken matrisi + örneklem + protokoller) → `tez-cikti/metodoloji_plani.md`
- `istatistik_analiz_agent` → **Bulgular Tablosu** + **Grafikler** + **İstatistik Özeti** → `tez-cikti/bulgular.md` + `tez-cikti/grafikler/` + `analiz.py`
- `yazim_agent` → **Tez Bölüm Taslağı** ve/veya **Dergi Makale Taslağı** → `tez-cikti/taslak_*.md`
- `humanizer_agent` → **İnsansılaştırılmış final metin** (üslup temizlenmiş; içerik sabit)
- `ozgunluk_denetim_agent` → **Özgünlük Denetim Raporu** (cümle-düzeyi işaretler; metni değiştirmez)
- `strateji_agent` → **Strateji & Denetim Raporu** (süpervizör; diğerlerinin yerine geçmez, denetler ve öneri verir)
- `ars_kopru_agent` → **ARS Orkestrasyon çıktısı** (hakem paneli / atıf / format sonuçları, ilgili ajana handoff)
- `gorsel_mindmap_agent` → **3D HTML mind map** → `tez-mindmap/tez_mindmap.html` (seans sonu güncellenir)

Bir ajan kendi fazının dışına taşmaz (örn. metodoloji ajanı sonuç uydurmaz, literatür ajanı tez bölümü yazmaz). Aşağı akıştaki iş gerektiğinde kontrolü kullanıcıya öneriyle iade eder.

## Oturum Belleği (Session Memory — zorunlu)

Her ajanın **ayrı** ve **kalıcı** bir bellek dosyası vardır; böylece sonraki oturumda kaldığı yerden devam eder, aynı işi tekrarlamaz:

```
Ozan-Tez/tez-bellek/
├── literatur_bellek.md      # taranan sorgular + dahil edilen kaynaklar (tekrar tarama yok)
├── metodoloji_bellek.md     # kesinleşen tasarım kararları + açık sorular
├── istatistik_bellek.md     # çalıştırılan testler + grafikler + bekleyenler
├── yazim_bellek.md          # bölüm durumu + aktif taslak + format profili
├── strateji_bellek.md       # açık/kapanan denetim bulguları + öneriler
├── kanit_haritalama_bellek.md  # haritalanan kaynaklar + bölüm doluluk
├── juri_savunma_bellek.md      # açık/kapanan itirazlar + zayıf nokta envanteri + savunma durumu
└── gorsel_mindmap_bellek.md    # son render + düğüm sayıları (seans sonu güncellenir)
```

**Görsel şema:** `Ozan-Tez/tez-mindmap/tez_mindmap.html` — 3D etkileşimli mind map; `gorsel_mindmap_agent` her seans sonunda günceller.

**Literatür arşivi** (literatür ajanı doldurur): `Ozan-Tez/literatur/ozetler/` (her kaynağın özeti) + `Ozan-Tez/literatur/pdf/` (yalnız açık erişim tam metin). İndeks `literatur_bellek.md`'dedir.

**İki zorunlu kural (her ajan):**
1. **Oturum başında kendi `*_bellek.md` dosyasını OKU** — "Tamamlananlar"ı tekrar etme, "Sıradakiler"den başla.
2. **Oturum sonunda (ve her anlamlı ilerlemede) güncelle** — ne yapıldı, nerede kalındı, sırada ne var (tarihli).

Bir ajan başka ajanın bellek dosyasını okuyabilir ama yalnız kendi dosyasını yazar. Detay: `references/oturum_bellegi_protokolu.md`.

## Referanslar ve Şablonlar

- `references/sapma_olcum_protokolu.md` — koronal/apikal/açısal/derinlik sapma ölçümü, superimpozisyon iş akışı
- `references/kuvvet_uygulama_protokolu.md` — kuvvet yönü/büyüklüğü/uygulama noktası standardizasyonu
- `references/model_standardizasyonu.md` — 3D baskı, kemik benzeri malzeme, baskı doğrulama
- `references/degisken_matrisi.md` — pin konfigürasyon grupları ve isimlendirme
- `references/istatistik_rehberi.md` — test seçim ağacı, güç analizi, varsayım kontrolleri
- `references/oturum_bellegi_protokolu.md` — oturum belleği (session memory) kuralları
- `references/ars_komut_rehberi.md` — ARS /ars-* komut & ajan rehberi (teze uygunlar)
- `references/humanizer_kaynak.md` + `humanizer_LICENSE.txt` — AI-yazım izi kalıpları (blader/humanizer, MIT)
- `templates/materyal_metod_template.md` — Materyal ve Metod bölümü iskeleti
- `templates/veri_toplama_template.md` — sapma verisi kayıt tablosu (CSV başlıkları)
