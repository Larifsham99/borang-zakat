# Isi Borang Pengesahan Status Pengajian Pondok (PONDOK/PLJ/02 – LZNK)

Aplikasi web statik: isi maklumat → teks diletak (overlay) tepat pada borang asal →
muat turun PDF/PNG atau kongsi terus ke WhatsApp. Letterhead borang tidak diubah.

## Fail
- `index.html` – aplikasi (HTML + CSS + JS, tiada pergantungan luar)
- `template.js` – imej borang asal (PDF dirasterkan 200 dpi, dibenamkan sebagai data URL)

## Deploy di GitHub Pages
1. Cipta repo baharu, muat naik `index.html`, `template.js` dan `README.md` ke akar repo.
2. Settings → Pages → Source: "Deploy from a branch" → Branch `main` / `(root)` → Save.
3. Buka `https://<nama-akaun>.github.io/<nama-repo>/` di telefon.

HTTPS (disediakan GitHub Pages) diperlukan untuk butang **Kongsi ke WhatsApp**
(Web Share API). Pada telefon, helaian kongsi akan memaparkan WhatsApp dan fail
PDF/PNG dilampirkan terus. Pada komputer, fail dimuat turun dan perlu dilampirkan
sendiri di WhatsApp Web.

## Ciri
- Pratonton langsung; semua medan disahkan (K/P 12 digit, poskod 5 digit, telefon, e-mel).
- K/P dan poskod dimasukkan digit demi digit ke dalam petak borang.
- Nama pada Bahagian 3 & 4 serta nama pondok diambil automatik daripada medan lain.
- Muat naik tandatangan/cop (PNG/foto): "Buang latar putih" menjadikan latar lutsinar
  dan memangkas tepi; peluncur saiz tersedia.
- Maklumat pusat pengajian, penandatangan, tandatangan & cop disimpan dalam peranti
  (localStorage) untuk pelajar seterusnya; butang "Pelajar baharu" kosongkan Bahagian 1 & 3.
- Semua pemprosesan dalam pelayar; tiada data dihantar ke pelayan.
- Amaran jika tandatangan/cop belum ada atau teks terlalu panjang.

## Laras kedudukan
Koordinat medan (unit pt, A4) berada dalam objek `P` di `index.html`.
