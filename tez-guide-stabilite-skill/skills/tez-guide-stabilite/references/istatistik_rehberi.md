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

## Ölçüm güvenilirliği (ICC) — sapma çalışmalarında ZORUNLU

Superimpozisyon/optik tarama ile yapılan sapma ölçümleri gözlemci ve yazılım kaynaklı hata taşır; in-vitro doğruluk çalışmalarında güvenilirlik raporu genelde şarttır (jüri/hakem sorar).

- **Tasarım:** aynı örneklem alt kümesinde (örn. 10-15 ölçüm) ölçümü **iki bağımsız gözlemci** ayrı ayrı, ve **aynı gözlemci ≥2 hafta arayla** tekrarlar.
- **Gözlemci-arası güvenilirlik** (inter-rater) ve **gözlemci-içi güvenilirlik** (intra-rater) için **ICC** hesapla.
  - Model: iki yönlü karışık, mutlak uyum, tek ölçüm — `ICC(3,1)` (rapor edilende model+tip belirt).
  - Yorum: <0.50 zayıf, 0.50-0.75 orta, 0.75-0.90 iyi, >0.90 mükemmel (Koo & Li 2016).
- Düşük ICC → ölçüm protokolünü sıkılaştır (referans nokta tanımı, superimpozisyon yöntemi) ve ana analizden önce çöz.
- Python: `pingouin.intraclass_corr`.

## Çoklu SONUÇ değişkeni (çokluluk — iki katman)

Bu çalışmada **dört birincil sapma sonucu** var: koronal, apikal, açısal, derinlik. İki ayrı çokluluk katmanı düzeltilmeli:

1. **Sonuçlar arası (family-wise across outcomes):** dört sonucun her birine ayrı ANOVA koşuluyorsa, aile-bazlı hata şişer. Ya (a) her sonuç ailesi için **Bonferroni/Holm** düzelt (α'yı 4'e böl veya Holm sıralı), ya da (b) sonuçlar ilişkiliyse **MANOVA** ile ortak test edip anlamlıysa tek-değişkenli takibe geç. Hangi yolu seçtiğini ve gerekçesini raporla.
2. **Grup içi post-hoc (across groups):** her ANOVA sonrası ikili karşılaştırmalarda Tukey/Bonferroni (mevcut kural).

> İki katmanı karıştırma: post-hoc düzeltmesi sonuçlar-arası düzeltmenin yerine geçmez.

## Raporlama standardı

- Her test için: test adı, istatistik değeri, df, **p**, **etki büyüklüğü** (η²/kısmi η², Cohen's d), **%95 GA**.
- Çoklu karşılaştırmada düzeltme yöntemini belirt (hem sonuçlar-arası hem post-hoc katmanı).
- Anlamlılık eşiği yanında **klinik anlamlılık** eşiğini de yorumla (örn. koronal/apikal <2 mm, açısal <5° klinik kabul aralığı — kendi referansınla doğrula).
- **Ölçüm güvenilirliği: ICC değerini (model+tip+GA) Metod ve Results'ta raporla** — güvenilirlik kanıtlanmadan sapma sonucu yorumlanmaz.

## Sık hatalar

- Tekrarlı ölçümü bağımsız sayıp normal ANOVA uygulamak (yanlış) → karışık model kullan.
- Sadece p raporlamak → etki büyüklüğü + GA ekle.
- Çoklu test düzeltmesini atlamak.
