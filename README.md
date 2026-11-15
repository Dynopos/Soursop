# soursop.my — Laman Rasmi MFS Soursop Plus

Laman satu halaman (statik, tanpa pangkalan data) untuk **MFS Soursop Plus — Kapsul Durian Belanda**
(KKM MAL23076122TC) oleh Ace Soar High Enterprise, Kota Bharu, Kelantan. Gaya *Premium Bento*
(emas · perak · hijau hutan mengikut warna logo). Semua butang order menghala ke WhatsApp **014-731 5822**.

## Kandungan laman
1. **Hero** — tajuk, butang Order via WhatsApp, logo, gambar pengguna, statistik (RM220 · 60 kapsul · 4 ramuan · pos RM0)
2. **Harga promosi** — Set Lengkap 3 botol RM500 · Set Separa Lengkap 2 botol RM400 · Set Awal 1 botol RM220
   (setiap butang ORDER NOW menghantar mesej WhatsApp berisi set yang dipilih)
3. **Order dalam 3 langkah**
4. **Ramuan** — daun durian belanda, manjakani, habbatus sauda, kulit kayu manis
5. **Testimoni video** — Kak Indah, Kak Liza, Abang Mi, pengguna (4 video) + penafian
6. **Kelulusan** — KKM (pautan semakan QUEST3+), sijil SSM, ujian makmal, pos percuma
7. **Galeri** — gambar pengguna, produk, poster harga, carian QUEST3+, sijil SSM
8. **Tentang + Fakta ringkas**, **Alamat** (Google Maps/Waze), **Soalan lazim** (9 soalan), CTA, footer (TikTok, Telegram)

SEO & GEO: meta + Open Graph, JSON-LD (Organization, Product + 3 Offer, FAQPage, 4 VideoObject),
`sitemap.xml` (gambar & video), `robots.txt` (membenarkan perayap AI), `llms.txt`, `site.webmanifest`, `404.html`.

## Struktur fail
```
index.html            laman utama
css/style.css         reka bentuk (token warna di bahagian atas :root)
js/main.js            interaksi (WhatsApp, modal, lightbox, video, menu)
assets/img/           gambar WebP yang telah dioptimumkan
assets/video/         4 video testimoni (MP4 dimampatkan) + gambar poster
robots.txt sitemap.xml llms.txt site.webmanifest 404.html netlify.toml
```

## Cara menukar
- **Nombor WhatsApp**: `js/main.js` → `BOOKING_URL` (dan cari `wa.me/60147315822` dalam `index.html`).
- **Harga**: dalam `index.html` cari `RM</small><strong>` (3 kad), mesej `data-msg`, bahagian *Fakta ringkas*,
  soalan lazim harga, kemudian `llms.txt` dan blok JSON-LD (`"price"`).
- **Gambar**: letak fail WebP baharu dalam `assets/img/` dengan nama sama (atau tukar `src` dalam `index.html`).
- **Video**: ganti fail dalam `assets/video/` (MP4 H.264 + gambar `.webp` poster).
- Selepas menukar CSS/JS, naikkan versi `?v=20261115-6` dalam `index.html` supaya telefon pelawat muat fail baharu.

## Bayar online — CHIP Payment Link (tanpa pelayan)
Butang **"Bayar Online (FPX / Kad) melalui CHIP"** muncul di bawah setiap set *hanya selepas* link diisi.
1. Log masuk https://portal.chip-in.asia → **Links → Add Payment Link**. Cipta 3 link berharga tetap:
   Set Awal RM220, Set Separa Lengkap RM400, Set Lengkap RM500.
   Aktifkan medan nama, telefon dan **alamat penghantaran** jika ada pilihan itu.
2. Tetapkan halaman selepas berjaya bayar (success redirect) ke `https://soursop.my/terima-kasih.html`.
3. Tampal URL setiap link dalam `js/main.js` → `PAY_LINKS` (`set-1`, `set-2`, `set-3`), kemudian naikkan `?v=` dalam `index.html`.
   Link semasa: set-1 RM220 `…/nlWuNBUfcmijYh3qRR`, set-2 RM400 `…/HAzopQU1bSQgeH2QMj`, set-3 RM500 `…/6YyWXrbTq40Jqm59Vg`.
4. Semak bayaran di dashboard CHIP (bukan berdasarkan halaman terima kasih — pelanggan boleh buka halaman itu tanpa bayar).

## Deploy
**GitHub Pages (digunakan sekarang — fail `CNAME` = soursop.my)**: Settings → Pages → Deploy from a branch → `/ (root)`.
DNS: rekod A `@` → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153; CNAME `www` → `dynopos.github.io`.

**Netlify (alternatif)**: Add new site → Import from Git → pilih repo ini, *publish directory* `.` (tiada build).
Domain: Domain management → Add domain `soursop.my` (+ `www`). DNS di pendaftar domain:
`A @ → 75.2.60.5` dan `CNAME www → <nama-projek>.netlify.app`. HTTPS automatik.

Selepas terbit: daftar di Google Search Console + hantar `sitemap.xml`, Bing Webmaster Tools, dan letak
pautan soursop.my di TikTok, Telegram dan Google Business Profile.

## Perlu disahkan oleh pemilik
- Harga & pos percuma (ikut poster harga promosi). Poster "Happy Hour RM160" belum dimasukkan.
- Nama set di laman ditukar kepada *Set Awal / Separa Lengkap / Lengkap* (tanpa perkataan "Rawatan Penyembuhan").
- Kenyataan "Ujian makmal" — laporan makmal menyatakan ia tidak boleh digunakan untuk pengiklanan tanpa kebenaran
  bertulis makmal; dapatkan kebenaran atau buang kad tersebut.
- Iklan ubat tradisional di Malaysia memerlukan kelulusan Lembaga Iklan Ubat (KKLIU), termasuk testimoni video.
- Lokasi peta guna carian alamat — berikan pin GPS tepat jika mahu peta lebih tepat.
