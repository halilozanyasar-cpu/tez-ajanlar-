# Sapma Ölçüm & Superimpozisyon Protokolü

> `metodoloji_agent` ve `istatistik_analiz_agent` tarafından kullanılır. İmplant pozisyon sapmasının nasıl tanımlanıp ölçüldüğünü standartlaştırır. Statik navigasyon literatüründe oturmuş 4 sapma ölçütü esas alınır.

## Ölçülen sapma türleri (literatür standardı)

| Ölçüt | Tanım | Birim |
|-------|-------|-------|
| **Koronal (giriş) sapma** | Planlanan ve elde edilen implantın platform/giriş noktası arası 3B mesafe | mm |
| **Apikal sapma** | İmplant apeksleri arası 3B mesafe | mm |
| **Açısal sapma** | İki implant eksen ekseni arası açı | derece (°) |
| **Derinlik sapması** | Eksen boyunca dikey (apiko-koronal) fark | mm |

## İş akışı

**Referans (planlanan) pozisyon.**
1. Atrofik maksilla modelinin CBCT/tarama verisi → implant planlama yazılımı (örn. coDiagnostiX, Blue Sky Plan vb.).
2. İmplant pozisyonu planla; guide bu plana göre tasarlanır.
3. Planlanan implant pozisyonu = "gerçek referans" (ground truth).

**Kuvvet ÖNCESİ ölçüm (ideal oturma).**
4. Guide modele tam otursun, pinlerle fiksle.
5. İmplant (veya implant analoğu/pin) guide üzerinden yerleştir.
6. Modeli tara (lab tarayıcı / masaüstü optik tarayıcı / post-op CBCT).
7. Elde edilen pozisyonu planla superimpoze et → kuvvet öncesi sapma değerleri.

**Kuvvet ALTINDA/SONRASI ölçüm (gerçekçi).**
8. `kuvvet_uygulama_protokolu.md`'ye göre kuvvet uygula.
9. Kuvvet altında (veya hemen sonra) implant yerleştirme/ölçüm taraması.
10. Tekrar superimpoze et → kuvvet altı sapma değerleri.

**Birincil çıktı.**
11. **Δsapma = kuvvet altı sapma − kuvvet öncesi sapma** (her tür için ayrı). Bu, pin konfigürasyonunun "kuvvet altında pozisyonu ne kadar koruduğunu" gösterir.

## Superimpozisyon ilkeleri

- Best-fit / referans nokta tabanlı hizalama; yöntem tüm gruplarda aynı.
- Hizalama hatasını raporla (RMS).
- Mümkünse kör ölçüm (operatör grup kodunu görmesin).
- Her ölçümü en az 2 kez (veya 2 operatör) → ölçüm güvenilirliği (ICC).

## Raporlama

Her model için: grup kodu, koronal/apikal/açısal/derinlik sapma (kuvvet öncesi), aynısı (kuvvet altı), Δ değerleri, mikro-hareket, hizalama RMS. Şema: `templates/veri_toplama_template.md`.
