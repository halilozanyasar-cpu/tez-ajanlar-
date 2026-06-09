# Veri Toplama Şablonu — Sapma Kayıt Tablosu

> `istatistik_analiz_agent` bu şemayı bekler. Her satır = bir model/ölçüm. CSV başlıkları aşağıdadır; doğrudan Excel/CSV olarak kullan.

## CSV başlıkları

```csv
model_id,grup_kodu,pin_sayisi,dagilim,giris_yonu,kuvvet_senaryo,operator,tekrar,koronal_once_mm,apikal_once_mm,acisal_once_derece,derinlik_once_mm,koronal_sonra_mm,apikal_sonra_mm,acisal_sonra_derece,derinlik_sonra_mm,mikrohareket_mm,hizalama_rms_mm,not
```

## Alan açıklamaları

| Alan | Tip | Açıklama |
|------|-----|----------|
| model_id | metin | Benzersiz model kimliği (örn. M001) |
| grup_kodu | metin | K0/G1/G2… (değişken matrisi) |
| pin_sayisi | tam sayı | 0/2/3/4 |
| dagilim | metin | tek_tarafli/ucgen/poligon/karsilikli |
| giris_yonu | metin | bukkal/palatal/karma |
| kuvvet_senaryo | metin | eksenel/lateral (tek senaryoysa sabit) |
| operator | metin | Ölçen kişi (ICC için) |
| tekrar | tam sayı | Ölçüm tekrar no (1/2…) |
| koronal_once_mm | ondalık | Kuvvet öncesi koronal sapma |
| apikal_once_mm | ondalık | Kuvvet öncesi apikal sapma |
| acisal_once_derece | ondalık | Kuvvet öncesi açısal sapma |
| derinlik_once_mm | ondalık | Kuvvet öncesi derinlik sapması |
| koronal_sonra_mm | ondalık | Kuvvet altı/sonrası koronal sapma |
| apikal_sonra_mm | ondalık | Kuvvet altı/sonrası apikal sapma |
| acisal_sonra_derece | ondalık | Kuvvet altı/sonrası açısal sapma |
| derinlik_sonra_mm | ondalık | Kuvvet altı/sonrası derinlik sapması |
| mikrohareket_mm | ondalık | Kuvvet altında guide yer değiştirmesi |
| hizalama_rms_mm | ondalık | Superimpozisyon hata payı |
| not | metin | Serbest not (anomali vb.) |

> Δsapma alanları analiz sırasında türetilir: `koronal_delta = koronal_sonra − koronal_once` (her tür için). Ham veriye Δ eklemeye gerek yok; script hesaplar.

## Örnek satır

```csv
M001,G5,4,poligon,karma,eksenel,Op1,1,0.42,0.61,1.8,0.30,0.55,0.78,2.3,0.41,0.12,0.05,
```
