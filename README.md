# GIS & Industry - Retail Site Selection Analysis

Repositori ini memuat implementasi analisis data spasial berbasis Sistem Informasi Geografis (GIS) menggunakan Python. Proyek ini bertujuan untuk mengevaluasi dan merekomendasikan lokasi pembukaan gerai/cabang retail baru (*Site Selection*) berdasarkan kriteria bisnis dan analisis geospasial.

## 📌 Permasalahan & Metode Analisis

Dalam ekspansi bisnis retail, pemilihan lokasi baru memerlukan perhitungan spasial yang akurat agar tidak merugikan gerai yang sudah ada. Metode yang diterapkan dalam repositori ini mencakup:

1. **Transformasi Sistem Koordinat (CRS)**: Mengubah sistem koordinat dari WGS84 (`EPSG:4326`) ke UTM Zone 48S (`EPSG:32748`) khusus wilayah Kota Bengkulu agar perhitungan jarak dan radius dalam satuan meter akurat.
2. **Analisis Zona Kanibalisasi (*Buffering*)**: Membuat area terlarang (*buffer zone*) radius 1.000 meter (1 km) di sekitar gerai eksisting untuk mencegah tumpang tindih area pasar.
3. **Evaluasi Aturan Bisnis (*Business Rules*)**: Menyeleksi kandidat lokasi berdasarkan kriteria:
   - Lokasi berada di luar zona kanibalisasi (jarak > 1 km dari gerai eksisting).
   - Estimasi populasi di sekitar lokasi memenuhi ambang batas minimum (**>= 2.000 jiwa**).
4. **Visualisasi Peta Interaktif**: Menampilkan hasil pemetaan gerai, zona penyangga, dan status rekomendasi lokasi pada peta interaktif berbasis Leaflet/Esri.

## 📁 File Repositori
- `GIS_&_Industry_(3).ipynb` : Jupyter Notebook berisi pemrosesan data spasial, pengujian kriteria bisnis, dan pembuatan peta interaktif.

## 🛠️ Teknologi & Library
- **Python 3**
- `geopandas` & `shapely` (Pemrosesan geometri & data spasial)
- `folium` (Visualisasi peta interaktif)
- `pandas` (Manajemen data & struktur tabel)

## 📊 Hasil Evaluasi Lokasi

| ID Lokasi | Est. Populasi | Status Evaluasi | Keterangan |
| :--- | :--- | :--- | :--- |
| **Site_1** | 2.500 | DITOLAK | Terlalu dekat dengan gerai eksisting (< 1 km) |
| **Site_2** | 4.200 | **REKOMENDASI** | Memenuhi syarat jarak dan populasi |
| **Site_3** | 1.800 | DITOLAK | Populasi di bawah batas minimum (< 2.000 jiwa) |
| **Site_4** | 5.000 | **REKOMENDASI** | Memenuhi syarat jarak dan populasi |

## 🚀 Cara Menjalankan
1. Clone repositori ini:
   ```bash
   git clone [https://github.com/Aggrakurnia/GIS_-_Industry.git](https://github.com/Aggrakurnia/GIS_-_Industry.git)
