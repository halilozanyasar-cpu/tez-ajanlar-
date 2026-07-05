# Tez — Guide Stabilite & Pin Pozisyonu (in-vitro)

Atrofik üst çenede kemik destekli cerrahi guide'larda **farklı pin pozisyonlarının** guide stabilitesine ve **implant pozisyon sapmasına** etkisini inceleyen in-vitro tez için, `academic-research-skills` mimarisinde tasarlanmış 11 ajanlı bir Claude Code plugin'i.

## Mimari

```
tez-guide-stabilite-skill/
├── .claude-plugin/
│   └── plugin.json                  # Plugin manifesti
├── README.md
└── tez-guide-stabilite/
    ├── SKILL.md                     # Orkestratör: modlar, routing, handoff, full-mod sırası + kapılar
    ├── agents/                      # 11 ajan
    │   ├── literatur_agent.md            # Faz 1 — literatür tarama & sentez
    │   ├── kanit_haritalama_agent.md     # Faz 1.5 — bulgu → bölüm etiketleme (köprü)
    │   ├── metodoloji_agent.md           # Faz 2 — tasarım, örneklem, ICC + çokluluk protokolü
    │   ├── istatistik_analiz_agent.md    # Faz 3 — analiz, ICC güvenilirlik, test seçimi, grafik
    │   ├── yazim_agent.md                # Faz 4 — akademik bölüm yazımı (tez + dergi + TR özet)
    │   ├── humanizer_agent.md            # Faz 4.5 — akademik-mod AI-yazım izi temizleme (MIT)
    │   ├── ozgunluk_denetim_agent.md     # Faz 4.7 — humanizer sonrası cümle-düzeyi özgünlük QA
    │   ├── strateji_agent.md             # Çapraz-fazlı — süpervizör denetim (format/atıf/bütünlük)
    │   ├── ars_kopru_agent.md            # Çapraz-fazlı — academic-research-skills orkestrasyonu
    │   ├── juri_savunma_agent.md         # Çapraz-fazlı — savunma hazırlık + jüri/hakem itirazı OTONOM döngü
    │   └── gorsel_mindmap_agent.md       # Çapraz-fazlı — 3D HTML mind map (seans sonu güncellenir)
    ├── references/                   # Teze özel protokoller
    │   ├── sapma_olcum_protokolu.md
    │   ├── kuvvet_uygulama_protokolu.md
    │   ├── model_standardizasyonu.md
    │   ├── degisken_matrisi.md
    │   ├── istatistik_rehberi.md
    │   ├── oturum_bellegi_protokolu.md
    │   ├── ars_komut_rehberi.md
    │   ├── humanizer_kaynak.md
    │   └── humanizer_LICENSE.txt
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
