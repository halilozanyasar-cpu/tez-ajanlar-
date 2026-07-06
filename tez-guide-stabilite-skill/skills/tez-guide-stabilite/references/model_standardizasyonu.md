# Model Üretim & Standardizasyon Protokolü

> `metodoloji_agent` tarafından kullanılır. İç geçerliliğin temeli: pin konfigürasyonu dışındaki HER ŞEY (model, malzeme, geometri) tüm gruplarda aynı olmalı.

## Master model

- Tek bir atrofik üst çene STL'si (Cawood-Howell IV-V tipi rezorpsiyon temsil eden) tüm grupların kaynağıdır.
- STL'yi CBCT segmentasyonundan veya kütüphane modelinden türet; rezorpsiyon derecesini ve gerekçesini raporla.
- Tüm guide'lar bu master modele göre tasarlanır (pin yuvaları hariç birebir aynı guide gövdesi).

## Seri baskı

- Her test için ayrı model bas (taze pin yuvası şart — önceki testin deforme ettiği delik bir sonrakini bozar).
- Aynı yazıcı, aynı reçine/lot, aynı baskı yönü ve katman kalınlığı, aynı post-cure protokolü.
- Baskı parametrelerini (cihaz, reçine, katman µm, yıkama/kür süresi) raporla.

## Kemik benzeri malzeme seçimi

| Seçenek | Artı | Eksi |
|---------|------|------|
| İki katmanlı reçine (kortikal + spongiöz) | Kemik mekaniğine en yakın, pin tutuşu gerçekçi | Üretimi zor, maliyet |
| Poliüretan blok (Sawbones tipi) | Standart, literatürde yaygın, tekrarlanabilir | Anatomi/atrofi sınırlı |
| Tek tip reçine | Ucuz, kolay | Kortikal/spongiöz ayrımı yok |

> Seçimi Tartışma'da savun; malzemenin elastik modülünü/sertliğini raporla. Mümkünse pilot testle pin tutuşunu doğrula.

## Baskı doğrulama

- Her basılan modeli tara, master STL ile boyutsal karşılaştırma (sapma haritası, RMS).
- Tolerans dışı modelleri ele. Kabul eşiğini önceden tanımla (örn. ±100 µm).

## Guide üretimi

- Tüm guide'lar aynı planlama yazılımı + aynı sleeve sistemi + aynı baskı/işleme.
- Pin yuvaları yalnızca değişken matrisine göre değişir.
- Guide oturma yüzeyi tüm gruplarda aynı (yalnız fiksasyon farklı).

## Raporlama checklist

Master STL kaynağı, rezorpsiyon tipi, yazıcı/reçine/lot, baskı parametreleri, malzeme mekanik özellikleri, doğrulama yöntemi ve tolerans, guide üretim zinciri.
