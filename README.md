# 🌿 AgrosolPump — Kalkulator ROI Irigasi Tenaga Surya

Kalkulator interaktif untuk menghitung **payback period dan ROI** investasi pompa irigasi tenaga surya, ditujukan untuk calon mitra **B2B dan B2G** (instansi/dinas pertanian).

🔗 **Live demo:** `https://[username].github.io/agros-roi-calculator`

---

## Fitur

| Fitur | Keterangan |
|---|---|
| 🌾 Preset komoditas | 6 jenis komoditas dengan parameter air & yield otomatis |
| ⛽ Sumber energi | Diesel, PLN, atau irigasi manual |
| 📊 Cashflow chart | Visualisasi kumulatif per tahun |
| 🔁 Sensitivitas | 3 skenario: pesimis / base / optimis |
| 📱 Responsive | Mobile & desktop |
| ⚡ No backend | Pure HTML/CSS/JS — tidak butuh server |

---

## Variabel Input

### 1. Komoditas & Lahan
- **Jenis komoditas** — mempengaruhi multiplier konsumsi air, default yield uplift, harga jual, dan musim tanam
- **Luas lahan** (ha)
- **Musim tanam per tahun**

### 2. Investasi
- **Harga unit + instalasi** (Rp)
- **Biaya maintenance tahunan** (Rp)
- **Horizon analisis** — 5, 7, atau 10 tahun

### 3. Biaya Irigasi Saat Ini
- **Sumber energi** — diesel (liter/bln), PLN (kWh/bln), atau manual (hari kerja)
- **Harga energi** sesuai sumber
- **Biaya tenaga kerja irigasi** (Rp/bln)

### 4. Produktivitas
- **Produktivitas saat ini** (ton/ha/panen)
- **Harga jual komoditas** (Rp/kg)
- **Estimasi peningkatan yield** (%) akibat irigasi terjadwal

---

## Logika Kalkulasi

```
Saving Energi/thn   = konsumsi × harga energi × 12
Saving TK/thn       = biaya TK × 12
Revenue Uplift/thn  = lahan × produksi × (yield% / 100) × musim × harga/kg × 1000
Net Saving/thn      = Saving Energi + Saving TK + Revenue Uplift − Maintenance

Payback Period      = Investasi Awal ÷ Net Saving/thn
ROI Kumulatif       = (Net Saving × Horizon − Investasi) ÷ Investasi × 100%
```

### Preset per Komoditas

| Komoditas | Multiplier Air | Default Yield Uplift | Musim/Thn |
|---|---|---|---|
| Padi | 1.4× | 20% | 2 |
| Sayuran | 0.8× | 15% | 3 |
| Jagung | 0.9× | 12% | 2 |
| Cabai/Tomat | 1.0× | 20% | 2 |
| Tebu | 1.8× | 15% | 1 |
| Lainnya | 1.0× | 15% | 2 |

---

## Struktur Repo

```
agros-roi-calculator/
├── index.html       # Kalkulator utama (single file)
└── README.md        # Dokumentasi ini
```

---

## Deploy

### GitHub Pages
```bash
# 1. Clone atau buat repo baru
git init
git add .
git commit -m "init: roi calculator"
git remote add origin https://github.com/[username]/agros-roi-calculator.git
git push -u origin main

# 2. Aktifkan GitHub Pages
# Settings → Pages → Source: main / root
```

### Custom Domain (opsional)
Tambahkan file `CNAME` berisi domain Anda:
```
roi.agros.id
```
Lalu arahkan DNS A record ke IP GitHub Pages.

---

## Disclaimer

Hasil kalkulasi bersifat **estimasi indikatif** untuk keperluan perencanaan awal. Angka aktual dipengaruhi kondisi iklim, kualitas lahan, dan fluktuasi harga komoditas. Untuk proposal resmi, hubungi tim PT. Agros Global Indonesia.

---

*Dibuat oleh tim data PT. Agros Global Indonesia*
