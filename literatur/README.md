# Literatür Arşivi

`literatur_agent` bulduğu kaynakları buraya indirir ve özetler.

```
Ozan-Tez/literatur/
├── README.md
├── pdf/            # açık erişim (open-access) tam metin PDF'ler
└── ozetler/        # her kaynak için ayrı özet MD'si (paywall olsa da özet burada)
```

## Kurallar

- **PDF indirme yalnız açık erişim** kaynaklar için yapılır (open-access / yazarın paylaştığı / PMC). Paywall'lu makalelerin PDF'i indirilmez; bunun yerine `ozetler/` altında künye + DOI/link + abstract + özet tutulur. Telif/erişim kısıtlarına saygı gösterilir.
- Her kaynağın bir **özet dosyası** olur: `ozetler/<anahtar>.md` (anahtar = ilkyazar_yıl, örn. `tahmaseb_2018.md`).
- `tez-bellek/literatur_bellek.md` bu arşivin indeksidir (hangi kaynak var, tezle ilgisi, durum). İkisi tutarlı tutulur.

## Özet dosyası şablonu

Her `ozetler/<anahtar>.md` şu yapıdadır:

```markdown
# <İlk yazar yıl> — <Kısa başlık>
- **Künye:** <tam APA/Vancouver künye>
- **DOI/Link:** <doi veya url>
- **Erişim:** açık erişim / paywall (PDF: var/yok)
- **Çalışma tipi:** <in-vitro / RCT / derleme / FEA …>
- **Örneklem/Materyal:** <n, model, malzeme>
- **Yöntem (özet):** <2-3 cümle>
- **Ana bulgular:** <madde madde, sayısal>
- **Tezle ilgisi:** <neden önemli; hangi bölümde kullanılır — Giriş/Metod/Tartışma>
- **Alıntılanabilir cümleler:** <sayfa/atıf ile kullanılabilecek 1-2 nokta>
- **Kanıt düzeyi:** <I-VII>
- **Notlar/çekinceler:** <kısıt, yanlılık>
```
