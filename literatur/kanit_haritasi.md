# Kanıt Haritası — Bilgi → Bölüm Eşlemesi
> `kanit_haritalama_agent` doldurur. `yazim_agent` her bölümü yazarken buradan o bölümün kanıtlarını çeker.
> Güç: güçlü / orta / zayıf. Etiketler: INTRO-BAĞLAM, INTRO-BOŞLUK, METOD-GEREKÇE, DISC-DESTEK, DISC-ÇELİŞKİ, DISC-MEKANİZMA, DISC-KLİNİK, LIMIT, FUTURE.
> Son güncelleme: 2026-06-12 (Oturum 2 — 5 çekirdek makale eklendi: Chen 2023, Elnadoury 2025, Pessoa 2021, Verhamme 2014, Verhamme 2013. Verhamme 2014↔2013 çelişki ekseni ve atrofik-D3+pin-pozisyonu boşluğu işlendi.)

## Bölüm-bazlı kanıt tablosu

| Kaynak (yıl) [refNo] | Bulgu / alıntı | Etiket(ler) | Nasıl kullanılır | Güç |
|----------------------|----------------|-------------|------------------|-----|
| Marlière 2018 [1] | Maksillada açısal sapma en yüksek (ort. 8.4°); medüller kemik, düşük tork direnci | INTRO-BAĞLAM, DISC-MEKANİZMA | Giriş: atrofik maksilla neden zorlu; Tartışma: sapma mekanizması | güçlü |
| Marlière 2018 [1] | Kemik destekli + fiksasyonlu (pin/vida) guide en düşük sapma (Stübinger); fiksasyon açısal sapmayı azaltır (Cassetta 4.09° vs 5.62°) | INTRO-BOŞLUK, DISC-DESTEK | Giriş: fiksasyon-stabilite gerekçesi; Tartışma: hipotezi destekleyen ana kanıt | güçlü |
| Marlière 2018 [1] | Sapma taksonomisi: açısal/servikal/apikal/derinlik; in-vitro model guide stabilitesini artırır | METOD-GEREKÇE | Materyal-Metod: ölçüm parametreleri + in-vitro tasarım savunması | güçlü |
| Li-Rodríguez 2022 [2] | In-vitro **statik guide**: yatay 0.2 mm, açısal-koronal 1.1°; güvenli marj içinde | METOD-GEREKÇE, DISC-DESTEK | Materyal-Metod: in-vitro statik guide protokolü; Tartışma: beklenen doğruluk aralığı | güçlü |
| Al-Jarsha 2024 [3] *(destekleyici)* | Çıkış & açısal sapma, eksene DİK delme kuvvetiyle pozitif korele | DISC-MEKANİZMA | **Yalnız Tartışma'da** kuvvet etkisi yorumu için (ana kaynak değil; robotik/dinamik, off-modalite) | orta |
| Chen 2023 [4] *(çekirdek)* | Bilateral pin (BPF) en düşük sapma (açısal 1.88° vs pinsiz 3.65°); tek pin konumu (bukkal/palatal) etkisiz | INTRO-BOŞLUK, METOD-GEREKÇE, DISC-DESTEK | Giriş: pin konfigürasyonu gerekçesi; Metod: pin protokol matrisi örneği; Tartışma: bilateral pin faydası | güçlü |
| Elnadoury 2025 [5] *(çekirdek)* | 2 pin en az guide sapması (0.52 mm) & dikey implant sapması (0.38 mm); kuvvet tasarımdan baskın | METOD-GEREKÇE, DISC-DESTEK, DISC-MEKANİZMA | Metod: kuvvet altında guide mikro-hareketi + sanal implant tahribatsız ölçüm; Tartışma: 2 pin stabilite + kuvvet etkisi | güçlü |
| Pessoa 2021 [6] *(çekirdek)* | Maksiller reçine modelde fiksasyon pini depth & angular sapmada anlamlı (p=0.005/0.044) | METOD-GEREKÇE, DISC-DESTEK, LIMIT | Metod: maksiller model + sapma ölçüm protokolü; Tartışma: pin etkisi; Limit: basılı sleeve ~0.5 mm sapma | güçlü |
| Verhamme 2014 [7] *(çekirdek)* | Atrofik/augmente maksillada fiksasyon pini sapma + şablon rotasyon/translasyonunda ANLAMLI; sapma standarttan büyük | INTRO-BAĞLAM, DISC-DESTEK, DISC-MEKANİZMA | Giriş: atrofik maksilla zorluğu; Tartışma: pin atrofik maksillada anlamlı (stabilite mekanizması) | güçlü |
| Verhamme 2013 [8] *(çekirdek)* | Standart ödentulöz maksillada fiksasyon pini sapmada ETKİSİZ; şablon konumu kritik | DISC-ÇELİŞKİ, INTRO-BOŞLUK | Tartışma: 2014 (anlamlı) ↔ 2013 (etkisiz) çelişkisi → pin etkisi kemik/destek koşuluna bağlı; Giriş: kontrollü in-vitro gerekçesi | güçlü |

> **Çelişki ekseni (DISC-ÇELİŞKİ):** Verhamme 2014 [7] (atrofik maksilla, pin **anlamlı**) ↔ Verhamme 2013 [8] (standart ödentulöz, pin **etkisiz**). Aynı grup/metot, zıt sonuç → fiksasyon pininin etkisi **kemik kalitesi/destek tipine bağlı** olabilir. Bu, tezin "atrofik D3 + kemik destekli + pin pozisyonu" kontrollü in-vitro kurgusunun **özgün gerekçesidir**.
> **Çekirdek literatür dosyaları:** `ozetler/chen_2023.md`, `elnadoury_2025.md`, `pessoa_2021.md`, `verhamme_2014.md`, `verhamme_2013.md`. Proje kökünde: `Tez_Temel_Makaleler.md` + `Tez_Makaleler_Mindmap.html`.

## Bölüm doluluk özeti
- **INTRO:** güçlü (bağlam: Marlière + Verhamme 2014 atrofik maksilla; boşluk: Chen, Verhamme 2013 — pin etkisi tartışmalı).
- **METOD:** güçlü (sapma taksonomisi + in-vitro statik guide — Marlière, Li-Rodríguez, Pessoa; kuvvet altında stabilite + tahribatsız ölçüm — Elnadoury; pin protokol matrisi — Chen).
- **DISCUSSION:** güçlü (destek: Chen, Elnadoury, Pessoa, Verhamme 2014; çelişki: Verhamme 2014↔2013; mekanizma: Marlière, Al-Jarsha, Elnadoury kuvvet etkisi).
- **RESULTS:** boş (deney verisi sonrası).
- **LIMIT / FUTURE:** orta (Pessoa basılı sleeve sapması; çekirdek makalelerin hiçbiri atrofik-D3 kemik-destekli pin-pozisyonunu birlikte ele almadı → FUTURE/özgünlük).

## Zayıf bölümler için hedefli arama önerileri (→ literatur_agent)
- ✅ *(çözüldü)* DISC-ÇELİŞKİ: pin etkisiz bulunan çalışma → **Verhamme 2013** eklendi (Verhamme 2014 ile çelişki ekseni kuruldu).
- ✅ *(kısmen)* Statik kemik destekli guide + fiksasyon pini: Chen/Pessoa (diş destekli in-vitro) + Verhamme 2014 (mukoza destekli atrofik klinik) eklendi. **Hâlâ açık:** doğrudan **kemik destekli** statik guide + pin in-vitro çalışması (tezin tam kesişimi — muhtemelen literatür boşluğu).
- DISC-KLİNİK: klinik kabul eşiği (<2 mm / <5°) referansı (hâlâ aranmalı).
- METOD-GEREKÇE: drilling force (N) + kemik benzeri malzeme (sawbones/polyurethane) — bkz. `D3_Kemik_Model_Materyalleri.md` (Calvert 2010, Bano 2025, Ramaswamy 2009 pull-out kanıtları orada işlendi).
