# kible-content

Sutolab Kıble uygulamasının istek üzerine indirilen içerik dosyaları
(APK boyutunu küçük tutmak için uygulamaya gömülmez; ilk kullanımda bir
kez indirilir, cihazda saklanır, sonrası tamamen çevrimdışıdır).

## Kur'an içeriği (`quran-v2`)

Uygulama önce `manifest.json`'u okur; base + seçili paketleri oradaki
URL'lerden indirir. Yeni dil/meal/okunuş eklemek = manifest'e bir girdi +
paket dosyası (uygulama güncellemesi gerekmez).

| Dosya | İçerik |
|---|---|
| `manifest.json` | Katalog: base + mealler + okunuş + hafızlar (+lisans/atıf metadatası) |
| `quran-base-v1.json.gz` | Arapça metin + sure adları (ar/en/tr) — uygulamaya da gömülü |
| `quran-tr-elmalili-v1.json.gz` | Türkçe meal — Elmalılı Hamdi Yazır |
| `quran-en-yusufali-v1.json.gz` | İngilizce meal — Abdullah Yusuf Ali |
| `quran-translit-tr-v1.json.gz` | Kuranca okunuş (Latin/Türkçe transliterasyon) |

### Kaynaklar ve lisanslar

- **Arapça metin:** [Tanzil Project](https://tanzil.net) — `quran-simple`,
  DEĞİŞTİRİLMEDEN (verbatim) kullanılmıştır (CC BY 3.0). Tanzil metin
  lisansı gereği: bu metni içeren/bu metinden türetilen tüm dosyalarda
  kaynak (Tanzil Project) açıkça belirtilmeli ve tanzil.net'e bağlantı
  verilmelidir. Güncellemeler: https://tanzil.net/updates/
- **Türkçe meal:** Elmalılı Muhammed Hamdi Yazır (v. 1942) — Türk telif
  hukukunda koruma süresi (ölüm + 70 yıl) dolmuştur, kamu malıdır.
- **İngilizce meal:** Abdullah Yusuf Ali (v. 1953) — kamu malıdır.
  Kaynak: fawazahmed0/quran-api (`eng-abdullahyusufal`).
- **Kuranca okunuş:** [QUL / Tarteel](https://qul.tarteel.ai) "Turkish
  Transliteration" (QUL kaynak id 1560; data source: Tarteel). QUL'da bu
  kaynak için üçüncü şahıs telif kaydı yoktur; QUL SSS ticari kullanıma
  izin verir. Atıf: "Okunuş: QUL / Tarteel (qul.tarteel.ai)".
- **Sure metadatası:** Tanzil.info quran-data (CC-BY).
- **Hafız sesleri (manifest `reciters`, ileriye dönük):** tilavetler ilgili
  hafızlara aittir; Al Quran Cloud (alquran.cloud) CDN üzerinden.

Dinî içerik doğrulaması yayıncının sorumluluğundadır.
