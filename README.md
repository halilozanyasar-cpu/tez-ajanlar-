# Tez Ajanları — Atrofik Maksilla / Pin Pozisyonu & Cerrahi Guide Stabilitesi

Atrofik üst çenede kemik destekli cerrahi guide'larda **farklı pin pozisyonlarının** guide stabilitesine ve **implant pozisyon sapmasına** etkisini inceleyen in-vitro tez çalışması için kurulmuş ajan sistemi, literatür arşivi ve görsel kanıt haritası.

## Klasör yapısı

```
Ozan-Tez/
├── tez-guide-stabilite-skill/    # 9 ajanlı Claude Code/Cowork plugin'i
│   ├── .claude-plugin/plugin.json
│   └── tez-guide-stabilite/
│       ├── SKILL.md              # orkestratör (10 mod)
│       ├── agents/               # literatür, kanıt-haritalama, metodoloji,
│       │                         #   istatistik, yazım, strateji, humanizer,
│       │                         #   ars-köprü, görsel-mindmap
│       ├── references/           # teze özel protokoller
│       └── templates/            # materyal-metod + veri-toplama şablonları
├── tez-bellek/                   # her ajanın kalıcı oturum belleği
├── literatur/
│   ├── ozetler/                  # makale özetleri (PubMed)
│   ├── pdf/                      # açık erişim tam metin notları
│   └── kanit_haritasi.md         # bulgu → bölüm eşlemesi
├── tez-mindmap/
│   └── tez_mindmap.html          # etkileşimli 3D kanıt haritası (offline çalışır)
└── Tez Formatı.docx              # üniversite tez şablonu
```

## Sistem

9 ajanlı pipeline: **literatür → kanıt-haritalama → metodoloji → istatistik/analiz → yazım**, üstünde **strateji/denetim** süpervizörü, **humanizer** (akademik-mod AI-yazım temizleme, MIT), **ARS köprü** (academic-research-skills orkestrasyonu) ve **görsel 3D mind map**. Her ajanın ayrı kalıcı belleği var; literatür PubMed MCP ile taranır, açık erişim PDF linkleri kaydedilir.

## Çalışma özeti

- **Tasarım:** in-vitro fiziksel test
- **Bağımsız değişken:** pin konfigürasyonu (sayı / açısal dağılım / bukkal-palatal)
- **Bağımlı değişkenler:** koronal, apikal, açısal, derinlik sapması + guide mikro-hareketi
- **Birincil ölçüt:** kuvvet öncesi vs. kuvvet altında sapma farkı (Δsapma)
- **Dil:** İngilizce (tez + dergi), Türkçe Öz
