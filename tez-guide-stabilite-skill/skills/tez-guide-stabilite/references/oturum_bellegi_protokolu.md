# Oturum Belleği Protokolü (Session Memory)

> Tüm ajanlar tarafından kullanılır. Amaç: her ajan kaldığı yerden devam etsin; aynı işi (aynı literatürü taramak, aynı bölümü yeniden yazmak) tekrarlamasın. Her ajanın **ayrı** bir bellek dosyası vardır.

## Bellek dosyaları (kullanıcı klasöründe, kalıcı)

```
Ozan-Tez/tez-bellek/
├── literatur_bellek.md          # literatur_agent
├── kanit_haritalama_bellek.md   # kanit_haritalama_agent
├── metodoloji_bellek.md         # metodoloji_agent
├── istatistik_bellek.md         # istatistik_analiz_agent
├── yazim_bellek.md              # yazim_agent
├── strateji_bellek.md           # strateji_agent
├── juri_savunma_bellek.md       # juri_savunma_agent
└── gorsel_mindmap_bellek.md     # gorsel_mindmap_agent
```

> Bellek dosyaları **kullanıcı klasöründe** tutulur (skill paketinde değil), çünkü tez ilerledikçe değişen, kalıcı, kullanıcının görebileceği durumdur.
>
> **Bellek tutan ajanlar (8):** yukarıdaki sekiz ajan kalıcı bellek dosyası tutar (`juri_savunma_agent` açık/kapanan itirazları ve savunma durumunu izlediği için durumludur). **Bellek tutmayan (3):** `humanizer_agent` ve `ozgunluk_denetim_agent` durumsuz üslup/QA geçişleridir (çıktıları yazım akışına gider, kalıcı durum taşımaz); `ars_kopru_agent` orkestrasyon köprüsüdür ve denetim sonuçlarını `strateji_bellek.md`'e özetler (kendi ayrı belleği yoktur).

## İki zorunlu kural (her ajan)

1. **Oturum BAŞINDA — OKU.** İş yapmadan önce kendi `*_bellek.md` dosyanı oku. "Tamamlananlar"ı tekrar etme; "Devam eden" ve "Sıradaki" maddelerden başla. Dosya yoksa şablonuyla oluştur.
2. **Oturum SONUNDA (ve her anlamlı ilerlemede) — YAZ.** Kendi bellek dosyanı güncelle: ne yaptın, nerede kaldın, sırada ne var. Tarih damgası ekle.

## Ortak bölüm yapısı (her bellek dosyasında)

```markdown
# <Ajan> — Bellek
> Son güncelleme: <YYYY-AA-GG>  | Oturum: <n>

## Durum Özeti
<tek cümle: şu an neredeyiz>

## Tamamlananlar
- [x] ...

## Devam Edenler
- [ ] ... (nerede kalındı)

## Sıradakiler
- [ ] ...

## Kararlar & Notlar
- ...

## Oturum Günlüğü
- <tarih> — <ne yapıldı>
```

> Ajana özel ek alanlar (örn. literatürde "taranan sorgular", yazımda "aktif taslak yolu") her ajanın kendi dosyasında tanımlıdır.

## Çakışma / tutarlılık

- Bellek dosyası ile gerçek çıktılar (taslak, veri) çelişirse **gerçek çıktı esastır**; belleği ona göre düzelt.
- Bir ajan başka ajanın bellek dosyasını **okuyabilir** (bağlam için) ama **yalnız kendi dosyasını yazar**.
