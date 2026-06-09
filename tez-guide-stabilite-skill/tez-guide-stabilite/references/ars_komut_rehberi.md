# ARS (academic-research-skills) — Teze Yarayan Komut & Ajan Rehberi

> Kurulu `academic-research-skills` plugin'inden tezimize uygun olanlar. `/ars-*` slash komutlarıyla çağrılır. Bizim `tez-guide-stabilite` paketimiz günlük teze-özel işi yapar; aşağıdakiler kilometre taşlarında ağır iş (hakem paneli, atıf denetimi, format) için kullanılır.

## Tier 1 — Mutlaka kullan

| Komut | Ne yapar | Tezde ne zaman |
|-------|----------|----------------|
| `/ars-reviewer` | **Simüle dergi hakem paneli** (academic-paper-reviewer): Baş Editör + Metodoloji Hakemi + Alan Hakemi + Perspektif Hakemi + Şeytanın Avukatı → birleşik karar mektubu | Tez/makale taslağı bitince, **dergiye göndermeden önce**. Özellikle Metodoloji Hakemi in-vitro tasarım + istatistik sağlamlığını sınar. |
| `/ars-citation-check` | **Atıf uyum denetimi** (citation_compliance): metin-kaynakça eşleşmesi, hedef stile (Vancouver) uymayan künyeleri işaretler | Kaynakça oluştuktan sonra ve gönderim öncesi |
| `/ars-abstract` | **İki dilli abstract** (abstract_bilingual): İngilizce + hedef dil + anahtar kelimeler | Tezin zorunlu **ABSTRACT + ÖZET**'i için birebir |
| `/ars-format-convert` | Manuscript'i **LaTeX / DOCX / PDF / Markdown**'a çevirir | Final tez/makale çıktısı; dergi DOCX/LaTeX isteyince |

## Tier 2 — Yazım sürecinde

| Komut | Ne yapar | Tezde ne zaman |
|-------|----------|----------------|
| `/ars-plan` | Sokratik, bölüm-bölüm planlama | Yazıma başlamadan iskelet/strateji |
| `/ars-outline` | Ayrıntılı outline + kanıt haritası | Her bölümün taslağından önce |
| `/ars-lit-review` | Açıklamalı bibliyografya (paper formatında) | Giriş/literatür bölümünü kurarken |
| `/ars-revision-coach` | Hakem yorumlarını ayrıştırır → revizyon yol haritası + yanıt mektubu iskeleti | Dergiden **revizyon (R&R)** gelince |
| `/ars-revision` | Revize taslak + hakeme nokta-nokta yanıtlar | R&R cevaplarını yazarken |

## Tier 3 — Duruma göre

| Komut | Ne yapar | Tezde ne zaman |
|-------|----------|----------------|
| `/ars-disclosure` | Dergiye özel **YZ kullanım beyanı** | Birçok dergi artık zorunlu tutuyor; gönderimde |
| `/ars-full` | Tam pipeline: araştır → yaz → hakem → revize → finalize | Sıfırdan uçtan uca üretim isteyince (bizim paketimizle örtüşür; genelde modülleri tek tek kullanmak daha kontrollü) |
| `/ars-mark-read`, `/ars-unmark-read`, `/ars-cache-invalidate` | Atıf doğrulama önbelleği yönetimi (okudum işareti / önbellek temizleme) | Atıf doğrulama tekrarında |

## Doğrudan /ars komutu olmayan ama güçlü iç ajanlar

Skill'ler içinde otomatik çalışan, denetim/bütünlük için değerli ajanlar:

- **methodology_reviewer** (reviewer paneli) — araştırma tasarımı geçerliliği + istatistik titizlik. In-vitro tezimiz için en kritik hakem.
- **integrity_verification** (pipeline) — tüm referans/atıf/veriyi gönderim öncesi gerçeklik açısından doğrular.
- **claim_ref_alignment_audit** (pipeline) — her atıflanan iddiayı kaynak metinle karşılaştırır → **uydurma/abartı atıf** yakalar.
- **source_verification** (deep-research) — kanıt derecelendirir, **yağmacı (predatory) dergi** tespit eder, iddiaları doğrular.
- **risk_of_bias** (deep-research) — RoB 2 / ROBINS-I; tezde klinik çalışma alıntılarsan yanlılık değerlendirmesi.
- **meta_analysis** (deep-research) — etki büyüklüğü + GRADE; ileride doğruluk çalışmalarının meta-analizini yaparsan.
- **research_architect** (deep-research) — metodolojik blueprint; tasarım kararlarında ikinci görüş.

## Bizim paketle iş bölümü

- **Günlük teze-özel iş** → bizim `tez-guide-stabilite` (sapma protokolleri, değişken matrisi, oturum belleği, PubMed 5-makale taraması, strateji/denetim).
- **Kilometre taşı / gönderim öncesi ağır denetim** → ARS (`/ars-reviewer`, `/ars-citation-check`, `/ars-abstract`, `/ars-format-convert`).
- Bizim `strateji_agent` hafif/sürekli denetim; ARS `/ars-reviewer` ise tam dergi paneli simülasyonu — ikisi tamamlayıcı.
