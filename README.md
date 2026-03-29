# 🎯 Dart Scorer Pro

Aplikasi pencatat skor dart berbasis web yang bisa diinstall sebagai PWA. Mendukung hingga 8 pemain, mode Double Out, multi-leg, dan dilengkapi checkout table otomatis.

---

## Cara Install (PWA)

### Android (Chrome)
1. Buka `index.html` di Chrome
2. Tap ikon **⋮** (menu) → **"Add to Home Screen"**
3. Tap **Install** — app akan muncul di home screen

### iPhone / iPad (Safari)
1. Buka di Safari
2. Tap ikon **Share** (kotak dengan panah ke atas)
3. Pilih **"Add to Home Screen"** → **Add**

### Desktop (Chrome / Edge)
1. Buka di browser
2. Klik ikon install di address bar (pojok kanan)
3. Klik **Install**

> Setelah install, app bisa dipakai **offline** tanpa koneksi internet.

---

## Cara Pakai

### 1. Setup Permainan
- Pilih **Skor Awal**: 301, 501, atau 701
- Pilih **Legs**: berapa leg yang dimainkan (Best of 1/3/5/7)
- Aktifkan **Double Out** jika ingin aturan checkout wajib double
- Tambah pemain (maks. 8 orang), lalu tekan **MULAI PERMAINAN**

### 2. Input Skor
- Masukkan skor tiap dart di kolom **D1, D2, D3** (nilai 0–60 per dart)
- Tekan **INPUT SKOR** atau Enter untuk submit
- Gunakan tombol **quick score** (26, 41, 45, 60, dll.) untuk input cepat
- Tombol **Miss (0)** untuk giliran tanpa skor, **180!** untuk skor maksimal

### 3. Checkout
- Saat skor pemain ≤ 170, sistem otomatis menampilkan **saran checkout**
- Contoh: skor 170 → `T20 T20 Bull`

### 4. Undo
- Tekan **↩ Undo** untuk membatalkan input terakhir

### 5. Tombol Lain
| Tombol | Fungsi |
|--------|--------|
| ⟳ Ulang | Mulai ulang dengan pemain yang sama |
| ✕ Reset | Kembali ke halaman setup |
| ☀️ / 🌙 | Toggle tema terang / gelap |

---

## Aturan Permainan Dart (501 / 301)

### Tujuan
Kurangi skor dari nilai awal (501 atau 301) menjadi **tepat 0**. Pemain yang pertama mencapai 0 menang leg tersebut.

### Cara Menghitung Skor
| Area | Nilai |
|------|-------|
| Single (S) | Nilai nominal (1–20) |
| Double (D) | 2× nilai nominal |
| Triple (T) | 3× nilai nominal |
| Bull (25) | 25 poin |
| Bullseye / Double Bull | 50 poin |
| Miss | 0 poin |

Nilai maksimal per giliran (3 dart): **180** (T20 + T20 + T20)

### Bust
Giliran dianggap **BUST** (hangus) jika:
- Total skor melebihi sisa poin (hasil negatif)
- Sisa poin menjadi **1** (tidak ada checkout yang valid)
- *(Mode Double Out)* Sisa poin menjadi **0** tapi dart terakhir bukan double

Saat bust, skor pemain tidak berubah dan giliran berpindah ke pemain berikutnya.

### Double Out (Opsional)
Jika mode **Double Out** aktif:
- Dart terakhir yang mencetak skor 0 **harus** mendarat di area **Double** atau **Bullseye (50)**
- Jika tidak, giliran dianggap bust
- Contoh checkout: sisa 32 → harus kena **D16**

### Multi-Leg
- Pemain yang memenangkan sejumlah leg yang ditentukan (misal Best of 3 = menang 2 leg) menjadi pemenang keseluruhan
- Setiap leg baru, semua skor direset ke nilai awal

---

## Notasi Checkout

| Kode | Artinya |
|------|---------|
| `T20` | Triple 20 (60 poin) |
| `D20` | Double 20 (40 poin) |
| `S20` | Single 20 (20 poin) |
| `Bull` | Bullseye (50 poin) |

Contoh: skor **170** → `T20 T20 Bull` = 60 + 60 + 50

---

## Teknologi

- React 18 (via CDN, no build step)
- Vanilla CSS dengan CSS Variables (dark/light mode)
- PWA: Web App Manifest + Service Worker (offline support)
