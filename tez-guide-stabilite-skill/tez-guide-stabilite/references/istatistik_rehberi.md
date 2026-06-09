# İstatistik Rehberi — Test Seçimi & Güç Analizi

> `metodoloji_agent` (güç analizi) ve `istatistik_analiz_agent` (test seçimi/uygulama) tarafından kullanılır.

## Güç analizi (örneklem hesabı — tasarım aşaması)

- Yazılım: G*Power (veya R `pwr`).
- Girdi: etki büyüklüğü (literatürden veya pilot), α=0.05, güç=0.80 (tercihen 0.90).
- Tasarıma uygun test ailesi:
  - Gruplar arası karşılaştırma → tek yönlü ANOVA (etki büyüklüğü f).
  - Grup × kuvvet etkileşimi → tekrarlı ölçümlü/karışık ANOVA.
- Çıktı: grup başı n. Toplam = grup sayısı × n × (gerekirse) kuvvet senaryosu sayısı.
- Beklenen kaybı (başarısız baskı/ölçüm) ekle (%10-15).

## Varsayım kontrolleri (analiz aşaması)

1. **Normallik:** Shapiro-Wilk (grup başına). Görsel: Q-Q plot.
2. **Varyans homojenliği:** Levene testi.
3. **Bağımsızlık:** tasarımdan (her model bağımsız; tekrarlı ölçüm uygun modelle ele alınır).
4. **Aykırı değer:** kutu grafiği / standardize rezidü.

## Test seçim ağacı

```
Sapma türü (sürekli) karşılaştırılıyor
│
├─ Aynı modelde kuvvet öncesi vs. sonrası (eşleştirilmiş) + gruplar arası
│   └─ Karışık (mixed) ANOVA: faktörler = pin grubu (gruplar arası) × kuvvet (grup içi)
│       ├─ Etkileşim anlamlı → basit etkileri incele (her kuvvet düzeyinde gruplar arası)
│       └─ Varsayım bozuk → dönüşüm dene; olmazsa non-parametrik (aşağı)
│
├─ Sadece gruplar arası (tek ölçüm, örn. mutlak Δsapma)
│   ├─ Varsayım OK → Tek yönlü ANOVA → post-hoc Tukey
│   └─ Varsayım bozuk → Kruskal-Wallis → post-hoc Dunn (Bonferroni)
│
├─ Sadece iki grup
│   ├─ Varsayım OK → bağımsız t-testi (gruplar arası) / eşleştirilmiş t (önce-sonra)
│   └─ Bozuk → Mann-Whitney / Wilcoxon işaretli sıra
│
└─ İlişki (mikro-hareket ↔ sapma)
    └─ Pearson (normal) / Spearman (değilse) + gerekirse regresyon
```

## Raporlama standardı

- Her test için: test adı, istatistik değeri, df, **p**, **etki büyüklüğü** (η²/kısmi η², Cohen's d), **%95 GA**.
- Çoklu karşılaştırmada düzeltme yöntemini belirt.
- Anlamlılık eşiği yanında **klinik anlamlılık** eşiğini de yorumla (örn. koronal/apikal <2 mm, açısal <5° klinik kabul aralığı — kendi referansınla doğrula).
- Ölçüm güvenilirliği: ICC (operatörler/tekrarlar arası).

## Sık hatalar

- Tekrarlı ölçümü bağımsız sayıp normal ANOVA uygulamak (yanlış) → karışık model kullan.
- Sadece p raporlamak → etki büyüklüğü + GA ekle.
- Çoklu test düzeltmesini atlamak.
