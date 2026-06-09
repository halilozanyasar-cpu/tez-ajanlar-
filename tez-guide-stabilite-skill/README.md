# Tez — Guide Stabilite & Pin Pozisyonu (in-vitro)

Atrofik üst çenede kemik destekli cerrahi guide'larda **farklı pin pozisyonlarının** guide stabilitesine ve **implant pozisyon sapmasına** etkisini inceleyen in-vitro tez için, `academic-research-skills` mimarisinde tasarlanmış 4 ajanlı bir Claude Code plugin'i.

## Mimari

```
tez-guide-stabilite-skill/
├── .claude-plugin/
│   └── plugin.json                  # Plugin manifesti
├── README.md
└── tez-guide-stabilite/
    ├── SKILL.md                     # Orkestratör: modlar, routing, handoff
    ├── agents/
    │   ├── literatur_agent.md        # Faz 1 — literatür tarama & sentez
    │   ├── metodoloji_agent.md       # Faz 2 — tasarım, örneklem, protokoller
    │   ├── istatistik_analiz_agent.md# Faz 3 — analiz, test seçimi, grafik
    │   └── yazim_agent.md            # Faz 4 — akademik bölüm yazımı
    ├── references/                   # Teze özel protokoller
    │   ├── sapma_olcum_protokolu.md
    │   ├── kuvvet_uygulama_protokolu.md
    │   ├── model_standardizasyonu.md
    │   ├── degisken_matrisi.md
    │   └── istatistik_rehberi.md
    └── templates/
        ├── materyal_metod_template.md
        └── veri_toplama_template.md
```

## Kurulum

Bu paket bir Claude Code / Cowork plugin'idir. Kurmak için:

1. **Cowork (önerilen):** Ayarlar → Capabilities → Skills/Plugins → bu klasörü ekle.
2. **Claude Code:** Bir plugin marketplace'ine ekleyip `/plugin install tez-guide-stabilite` ile kur, ya da `tez-guide-stabilite/` klasörünü kullanıcı skill dizinine kopyala.

> Not: Bu plugin oturum içinde otomatik kaydedilemez; yukarıdaki adımlarla bir kez kurman gerekir. Kurulduktan sonra ajanlar tez bağlamında otomatik tetiklenir.

## Kullanım

```
Tezim için guide stabilitesi ve fiksasyon pini literatürünü tara
Pin konfigürasyonu değişken matrisini ve güç analizini kur
Sapma verilerimi analiz et (CSV ekte)
Materyal ve Metod bölümünü yaz
```

## Çalışma özeti

- **Tasarım:** in-vitro fiziksel test
- **Birincil ölçüt:** kuvvet öncesi vs. kuvvet altında implant sapması farkı
- **Bağımsız değişken:** pin konfigürasyonu (sayı / açısal dağılım / bukkal-palatal)
- **Bağımlı değişkenler:** koronal, apikal, açısal, derinlik sapması + guide mikro-hareketi
