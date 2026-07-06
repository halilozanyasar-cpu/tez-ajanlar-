# Pin Konfigürasyonu Değişken Matrisi

> `metodoloji_agent` tarafından kullanılır. Bağımsız değişkeni (pin konfigürasyonu) sistematik, kodlanabilir gruplara böler. Sapma ve mikro-hareket bağımlı değişkenlerdir.

## Bağımsız değişken boyutları

| Boyut | Seviyeler | Gerekçe |
|-------|-----------|---------|
| Pin **sayısı** | 2 / 3 / 4 | Temel stabilite hipotezi: sayı arttıkça mikro-hareket azalır mı? |
| Açısal **dağılım** | Tek taraflı / Üçgen (3-pin) / Poligon-dengeli (4-pin) | Dağılım geometrisi rotasyonel stabiliteyi belirler |
| **Giriş yönü** | Bukkal / Palatal / Karma | Atrofik maksillada palatal kemik daha kalın → palatal pin daha iyi ankraj olabilir (anahtar hipotez) |
| Anterior-posterior **denge** | Dengeli / Öne yığılı | Posterior destek eksikliği distal sapmayı artırabilir |

## Önerilen grup kodlaması (örnek tasarım)

| Kod | Pin sayısı | Dağılım | Giriş | Açıklama |
|-----|-----------|---------|-------|----------|
| K0 | — | — | — | **Kontrol**: pinsiz / yalnız oturma (referans) |
| G1 | 2 | Tek taraflı | Bukkal | Minimal fiksasyon, bukkal |
| G2 | 2 | Karşılıklı | Bukkal+Palatal | Çapraz dengeli minimal |
| G3 | 3 | Üçgen | Karma | Klasik üçgen ankraj |
| G4 | 4 | Poligon | Bukkal | Maksimum, bukkal-baskın |
| G5 | 4 | Poligon | Karma (bukkal+palatal) | Maksimum, dengeli |

> Not: Gruplar tezin kapsamı/baskı kapasitesine göre azaltılabilir. En az kontrol + 3 deney grubu önerilir ki gruplar arası ANOVA anlamlı olsun.

## Sabit tutulacaklar (standardizasyon)

- Master maksilla modeli (tek STL)
- Guide tasarımı (pin yuvaları hariç birebir aynı)
- Pin çapı/uzunluğu/malzemesi
- Kuvvet protokolü (yön/büyüklük/nokta)
- İmplant pozisyon planı
- Ölçüm yazılımı ve operatörü

## Bağımlı değişkenler (ölçülecek)

- Koronal sapma (mm), apikal sapma (mm), açısal sapma (°), derinlik sapması (mm)
- Δsapma = kuvvet altı − kuvvet öncesi (her tür için) — **birincil**
- Guide mikro-hareketi (mm)
