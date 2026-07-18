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
| `quran-ur-kanzuliman-v1.json.gz` | Urduca meal — Ahmed Rıza Han (Kenzü'l-İmân) |
| `quran-fa-ghomshei-v1.json.gz` | Farsça meal — Mahdi Elahi Ghomshei |
| `quran-ru-sablukov-v1.json.gz` | Rusça meal — Гордий Саблуков (Gordy Sablukov) |
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
- **Urduca meal:** Ahmed Rıza Han / Ahmad Raza Khan Barelvi (v. 1921) —
  "Kenzü'l-İmân" (1910), kendi özgün çevirisi; Pakistan (yaşam+50) ve
  Hindistan (yaşam+60) telif sürelerinin ikisi de dolmuş, kamu malıdır.
  Kaynak: Al Quran Cloud API (`ur.kanzuliman`, düz metin, dipnotsuz);
  8 ayette kalan orijinal dipnot referans numarası (ör. "(۵۴)") veri
  temizliğiyle çıkarıldı (footnote metni zaten dahil değildi).
- **Farsça meal:** Mahdi Elahi Ghomshei / مهدی الهی قمشه‌ای (v. 1973) —
  İran telif hukukunda koruma süresi dolmuş, kamu malıdır (1970 yasası
  ömür+30 → 2003; 2010 reformu ömür+50 geriye dönük değil; en muhafazakâr
  okumada ömür+50 → 2023). İran Bern Konvansiyonu dışıdır; AB/Türkiye'de
  "kısa süre kuralı" gereği hedef pazarlarda ek koruma doğmaz. Kaynak:
  Al Quran Cloud API (`fa.ghomshei`, düz metin); 11 ayette köşeli-parantez
  içi tefsir/editör notu ([...], çoğu "(م)" işaretli) meal saflığı için
  temizlendi; Ghomshei'nin yuvarlak-parantez içi kısa açıklamaları korundu.
- **Rusça meal:** Гордий Саблуков / Gordy Sablukov (v. 1880) — meali 1878'de
  Kazan'da, HAYATTAYKEN yayımlandı (posthum değil); Rusya Federasyonu Sivil
  Kanun Madde 1281 п.1 (yaşam+70) geçerli → 1950'de kamu malı oldu. NOT:
  Krachkovsky (öl. 1951, en yaygın akademik Rusça meal) posthum 1963'te
  yayımlandığından п.3 (yayın+70) + п.5 (savaş +4 yıl) uygulanır → 2038'e
  kadar telifli, bu yüzden Sablukov tercih edildi. Kaynak: Al Quran Cloud
  API (`ru.sablukov`, düz metin, dipnotsuz/temiz — veri temizliği gerekmedi).
- **Kuranca okunuş:** [QUL / Tarteel](https://qul.tarteel.ai) "Turkish
  Transliteration" (QUL kaynak id 1560; data source: Tarteel). QUL'da bu
  kaynak için üçüncü şahıs telif kaydı yoktur; QUL SSS ticari kullanıma
  izin verir. Atıf: "Okunuş: QUL / Tarteel (qul.tarteel.ai)".
- **Sure metadatası:** Tanzil.info quran-data (CC-BY).
- **Hafız sesleri (manifest `reciters`, ileriye dönük):** tilavetler ilgili
  hafızlara aittir; Al Quran Cloud (alquran.cloud) CDN üzerinden.

Dinî içerik doğrulaması yayıncının sorumluluğundadır.
