# Kanıt Haritası — Bilgi → Bölüm Eşlemesi
> `kanit_haritalama_agent` doldurur. `yazim_agent` her bölümü yazarken buradan o bölümün kanıtlarını çeker.
> Güç: güçlü / orta / zayıf. Etiketler: INTRO-BAĞLAM, INTRO-BOŞLUK, METOD-GEREKÇE, DISC-DESTEK, DISC-ÇELİŞKİ, DISC-MEKANİZMA, DISC-KLİNİK, LIMIT, FUTURE.
> Son güncelleme: 2026-06-09 (Oturum 1 revize — 2 ana statik kaynak + 1 destekleyici; Chen & Ruiz-Romero çıkarıldı, Al-Jarsha yalnız Tartışma)

## Bölüm-bazlı kanıt tablosu

| Kaynak (yıl) [refNo] | Bulgu / alıntı | Etiket(ler) | Nasıl kullanılır | Güç |
|----------------------|----------------|-------------|------------------|-----|
| Marlière 2018 [1] | Maksillada açısal sapma en yüksek (ort. 8.4°); medüller kemik, düşük tork direnci | INTRO-BAĞLAM, DISC-MEKANİZMA | Giriş: atrofik maksilla neden zorlu; Tartışma: sapma mekanizması | güçlü |
| Marlière 2018 [1] | Kemik destekli + fiksasyonlu (pin/vida) guide en düşük sapma (Stübinger); fiksasyon açısal sapmayı azaltır (Cassetta 4.09° vs 5.62°) | INTRO-BOŞLUK, DISC-DESTEK | Giriş: fiksasyon-stabilite gerekçesi; Tartışma: hipotezi destekleyen ana kanıt | güçlü |
| Marlière 2018 [1] | Sapma taksonomisi: açısal/servikal/apikal/derinlik; in-vitro model guide stabilitesini artırır | METOD-GEREKÇE | Materyal-Metod: ölçüm parametreleri + in-vitro tasarım savunması | güçlü |
| Li-Rodríguez 2022 [2] | In-vitro **statik guide**: yatay 0.2 mm, açısal-koronal 1.1°; güvenli marj içinde | METOD-GEREKÇE, DISC-DESTEK | Materyal-Metod: in-vitro statik guide protokolü; Tartışma: beklenen doğruluk aralığı | güçlü |
| Al-Jarsha 2024 [3] *(destekleyici)* | Çıkış & açısal sapma, eksene DİK delme kuvvetiyle pozitif korele | DISC-MEKANİZMA | **Yalnız Tartışma'da** kuvvet etkisi yorumu için (ana kaynak değil; robotik/dinamik, off-modalite) | orta |

## Bölüm doluluk özeti
- **INTRO:** orta-güçlü (bağlam + boşluk — Marlière). Daha fazla doğrudan statik-guide kaynağı iyi olur.
- **METOD:** güçlü (sapma taksonomisi + in-vitro statik guide — Marlière, Li-Rodríguez)
- **DISCUSSION:** orta (destek: Marlière, Li-Rodríguez; mekanizma: Marlière + Al-Jarsha kuvvet etkisi)
- **RESULTS:** boş (deney verisi sonrası)
- **LIMIT / FUTURE:** zayıf

## Zayıf bölümler için hedefli arama önerileri (→ literatur_agent)
- **Öncelik:** statik **kemik destekli guide + fiksasyon pini** doğrudan çalışmaları (Giriş'i güçlendirmek için).
- DISC-ÇELİŞKİ: pin sayısının sapmaya etkisiz bulunduğu çalışma var mı?
- DISC-KLİNİK: klinik kabul eşiği (<2 mm / <5°) referansı.
- METOD-GEREKÇE: drilling force (N) + kemik benzeri malzeme (sawbones/polyurethane).
