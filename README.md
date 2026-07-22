# Kılavuzluk Hizmetleri Tarife Hesaplama

Kılavuzluk, römorkaj ve palamar hizmetleri için **1 Şubat 2026 – 31 Ocak 2027** dönemi tarifesine göre
anlık ücret hesaplaması yapan, tek dosyalık (bağımlılıksız) web uygulaması.

🔗 **Canlı sürüm:** https://mkptheCapt.github.io/kilavuzluk-hizmetleri-tarife-hesaplama/

## Özellikler

- Gemi grostonu (GT) ve gemi tipine göre anlık hesaplama
- Tehlikeli madde ve resmi tatil / hafta sonu artırımları
- Römorkör adedi seçimi (0–9)
- Kılavuzluk, Römorkaj, Palamar ve Etap Seyri kalemleri + genel toplam
- Özeti panoya kopyalama, yazdırma / PDF çıktısı
- Açık ve koyu tema, ayarlanabilir yazı boyutu ve rengi
- Mobil uyumlu, tek `index.html` dosyası — kurulum veya sunucu gerektirmez

## Hesaplama kuralı

İlk 1.000 GT için taban ücret uygulanır; sonraki her 1.000 GT (veya küsuru) için ilave birim ücret eklenir:

```
Ücret = taban + ceil((GT - 1000) / 1000) × ilave      (GT > 1000 ise)
```

Artırımlar çarpımsal uygulanır:

| Koşul | Oran |
|---|---|
| Tehlikeli madde — konteyner ve yolcu/Ro-Pax/Ro-Ro/araba taşıyıcı | %20 |
| Tehlikeli madde — diğer gemiler | %30 |
| Resmi tatil / hafta sonu | %50 |

Römorkaj kalemi ayrıca seçilen römorkör adediyle çarpılır.

## Yerel çalıştırma

`index.html` dosyasını doğrudan tarayıcıda açmanız yeterlidir.

## Not

Sonuçlar bilgilendirme amaçlıdır, resmî fatura yerine geçmez. Yürürlükteki tarife ve mevzuat esastır.

---

Masaüstü (Python/Tkinter) sürümünden uyarlanmıştır — by mkp, 2026.
