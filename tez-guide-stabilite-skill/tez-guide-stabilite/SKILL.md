---
name: tez-guide-stabilite
description: "Atrofik üst çenede kemik destekli cerrahi guide'larda farklı pin pozisyonlarının (sayı/açı/bukkal-palatal) guide stabilitesine ve implant pozisyon sapmasına etkisini inceleyen in-vitro tez araştırma ajan ekibi. 9 ajan (literatür, kanıt-haritalama, metodoloji, istatistik-analiz, yazım, strateji-denetim, humanizer, ars-köprü, görsel-mindmap), 10 mod (full/literatur/harita/metodoloji/analiz/yazim/denetim/insansilastir/ars/mindmap). Kanıt haritalama her bulguyu uygun bölüme etiketler; görsel mind map 3D HTML şema üretir (seans sonu güncellenir). Süpervizör strateji ajanı tüm ajanları denetler; humanizer AI-yazım izlerini temizler (akademik mod); ARS köprü dergi hakem paneli/atıf/format için kurulu ARS plugin'ini orkestre eder. Tetikleyiciler: tez, guide stabilite, pin pozisyonu, implant sapması, kemik destekli cerrahi guide, in-vitro, materyal-metod yaz, sapma analizi, literatür tara, denetle, citation kontrol, referans doğrula, format kontrol."
metadata:
  version: "1.0.0"
  last_updated: "2026-06-09"
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

Atrofik üst çene (maksilla) modelinde, kemik destekli cerrahi guide'ların **fiksasyon pini sayısı, açısı ve konumunun** (1) guide stabilitesine ve (2) elde edilen implant pozisyonunun planlanan pozisyondan **sapmasına** etkisini in-vitro olarak değerlendiren 4 ajanlı bir tez pipeline'ı.

**Çalışma tipi:** In-vitro fiziksel test (3D-basılı atrofik maksilla modelleri + basılı guide'lar + universal test cihazı ile kuvvet + optik tarama/superimpozisyon ile sapma ölçümü).

## Araştırma Sorusu (Ana Hipotez)

> Atrofik üst çenede kemik destekli cerrahi guide'ların fiksasyon pin konfigürasyonu (sayı/açısal dağılım/bukkal-palatal giriş), kuvvet altında guide mikro-hareketini ve dolayısıyla implant pozisyon sapmasını (koronal, apikal, açısal, derinlik) anlamlı şekilde etkiler.

**Birincil sonuç ölçütü:** Kuvvet öncesi vs. kuvvet altında implant pozisyon sapması farkı (Δsapma).
**İkincil sonuç ölçütleri:** Guide mikro-hareketi (mm), guide-kemik temas stabilitesi, pin konfigürasyonuna göre stres dağılımı.

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
7. **ARS Köprü** (`ars_kopru_agent`) — *orkestrasyon.* Kurulu `academic-research-skills` plugin'inin güçlü ajanlarını (`/ars-reviewer` dergi hakem paneli, `/ars-citation-check`, `/ars-abstract`, `/ars-format-convert`, bütünlük/integrity) doğru kilometre taşında çağırır. Harita: `references/ars_komut_rehberi.md`.
8. **Görsel Mind Map** (`gorsel_mindmap_agent`) — *görselleştirme, çapraz-fazlı.* Proje durumundan **3D, etkileşimli, animasyonlu HTML mind map** üretir: TEZ → bölümler → makaleler → bulgular; hangi makaleden ne alınıp hangi bölüme gittiğini gösterir. `tez-mindmap/tez_mindmap.html`. **Her seans sonunda güncellenir.**

> **Tez format dosyası:** Üniversitenin tez şablonunu `Ozan-Tez` klasörüne adında `format` geçen bir Word dosyası olarak koy (örn. `tez format.docx`). `yazim_agent` Adım 0'da bu dosyayı bulur, yapısını (başlık hiyerarşisi, bölüm sırası, atıf stili, yazı tipi/aralık) çıkarır ve harfiyen uyar. Şablon her zaman paketteki genel iskeletten önceliklidir.

---

## Mod Seçimi (Routing)

| Mod | Ne zaman | Aktif ajan(lar) |
|-----|----------|-----------------|
| `full` | Baştan sona tüm pipeline | 4 ajan sırayla |
| `literatur` | Sadece literatür taraması/senteri | `literatur_agent` |
| `harita` | Bulguları bölümlere etiketle (kanıt haritası) | `kanit_haritalama_agent` |
| `metodoloji` | Sadece çalışma tasarımı/protokol | `metodoloji_agent` |
| `analiz` | Veri elde, sadece istatistik/grafik | `istatistik_analiz_agent` |
| `yazim` | Bölüm yazımı/revizyon | `yazim_agent` |
| `denetim` | Mevcut işi denetle, öneri/literatür/atıf-format kontrolü | `strateji_agent` |
| `insansilastir` | Metni akademik modda AI-izlerinden temizle | `humanizer_agent` |
| `ars` | ARS ağır iş ajanlarını (hakem/atıf/abstract/format) orkestre et | `ars_kopru_agent` |
| `mindmap` | 3D etkileşimli HTML tez şemasını üret/güncelle | `gorsel_mindmap_agent` |

**Belirsizse:** kullanıcıya hangi aşamada olduğunu sor (literatür mü topluyor, veri mi analiz ediyor, yazıyor mu).

## Tetikleyiciler

**Türkçe:** tez, tez konusu, guide stabilite, cerrahi guide, kemik destekli guide, fiksasyon pini, pin pozisyonu, pin sayısı, atrofik maksilla, atrofik üst çene, implant sapması, pozisyon sapması, statik navigasyon, kılavuzlu cerrahi, sonlu eleman, in-vitro, materyal ve metod, sapma analizi, koronal/apikal/açısal sapma, literatür tara, örneklem hesabı, güç analizi.

**İngilizce:** surgical guide stability, bone-supported guide, fixation pin, pin position, atrophic maxilla, implant deviation, static navigation accuracy, guided surgery, micro-movement, deviation analysis.

### Tetiklemez (başka skill kullan)

| Senaryo | Bunun yerine |
|---------|--------------|
| Digimplant ürün/sipariş/katalog işi | `digimplant-*` ajanları |
| Genel literatür taraması (teze özel değil) | `deep-research` |
| Word/PDF/Excel format çıktısı üretmek | `docx` / `pdf` / `xlsx` skill'leri |

---

## Handoff / Material Passport (Ajanlar arası veri devri)

Her ajan kendi çıktısını isimlendirilmiş bir "ürün" olarak üretir; sonraki ajan bunu girdi alır. Bir sonraki ajan bu ürünleri konuşma bağlamında arar ve otomatik içe aktarır:

- `literatur_agent` → **Literatür Sentez Raporu** + **Referans Listesi (kaynak künyeleri)**
- `metodoloji_agent` → **Metodoloji Planı** (değişken matrisi + örneklem + protokoller)
- `istatistik_analiz_agent` → **Bulgular Tablosu** + **Grafikler** + **İstatistik Özeti**
- `yazim_agent` → **Tez Bölüm Taslağı** ve/veya **Dergi Makale Taslağı**
- `strateji_agent` → **Strateji & Denetim Raporu** (süpervizör; diğerlerinin yerine geçmez, denetler ve öneri verir)

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
