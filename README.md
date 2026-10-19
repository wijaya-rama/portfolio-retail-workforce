# 📊 Retail Workforce Productivity & Attrition Analysis

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-2563EB?style=for-the-badge&logo=github)](https://wijaya-rama.github.io/portfolio-retail-workforce/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Vanilla JS](https://img.shields.io/badge/Vanilla_JS-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Data](https://img.shields.io/badge/Data-Star_Schema_&_Flat_CSV-10B981?style=for-the-badge&logo=microsoftexcel&logoColor=white)](data/)

Dashboard analitik interaktif dan studi kasus People Analytics untuk mengevaluasi dinamika produktivitas, struktur biaya tenaga kerja, dan faktor pendorong *attrition* (turnover) pada industri ritel modern.

---

## 📌 Project Overview

Dalam industri ritel skala besar, pergantian karyawan (*employee turnover*) dan pembengkakan rasio biaya tenaga kerja (*labor cost percentage*) berdampak langsung terhadap profitabilitas serta kepuasan pelanggan di tingkat toko. Proyek ini menganalisis dataset 24 toko ritel dengan 2.000 karyawan aktif dan mantan karyawan sepanjang periode 2024–2025 across 3 wilayah operasional (*Midwest*, *South*, *West*).

Analisis ini dibangun dengan pendekatan **Takeaway-First Storytelling** dan arsitektur visual **Bento Grid**, memungkinkan pemangku kepentingan (HR Leaders, Retail Operations Directors, Store Managers) mengeksplorasi data secara cepat, interaktif, dan berbasis bukti (*evidence-based*).

---

## 💡 Key Business Insights

### 1. Dampak Gaya Kepemimpinan: Micromanagement vs Attrition (48.8%)
* Manajer dengan gaya kepemimpinan **Micromanagement** mencatat tingkat attrition tim mencapai **48.8%**, jauh lebih tinggi dibandingkan manajer dengan gaya **Standard** maupun **Coaching** (~12% – 14%).
* Manajer micromanage menyumbang porsi leavers sukarela terbesar. Scatter plot kepemimpinan vs turnover membuktikan korelasi kuat antara rendahnya skor kepemimpinan atasan dengan tingginya rasio turnover toko.

### 2. Inefisiensi Biaya Tenaga Kerja pada Format Toko Express
* Toko bertipe **Express** menghabiskan persentase pendapatan yang jauh lebih tinggi untuk pos tenaga kerja dibandingkan format **Regular** dan **Superstore**.
* Seluruh toko Express menempati peringkat terbawah dalam rasio pendapatan per karyawan (*revenue per employee*), mengindikasikan ketidakseimbangan antara penjadwalan shift tenaga kerja dengan volume transaksi per jam.

### 3. Kerentanan Retensi Talenta Bintang / 9-Box Grid (20.7%)
* Evaluasi matriks talenta (kinerja vs potensi) mengungkapkan bahwa **20.7% (1 dari ~5) talenta bintang (*top talent*) justru memutuskan keluar**.
* Analisis kompensasi menunjukkan *compa-ratio* karyawan keluar (0.98) hampir identik dengan karyawan bertahan (0.99). Hal ini mengonfirmasi bahwa eksodus talenta berkinerja tinggi bukan dipicu ketidakpuasan gaji semata, melainkan faktor kepemimpinan, kepastian jenjang karier, dan lingkungan kerja.

### 4. Titik Rawan Masa Kerja (Tenure < 1 Tahun)
* Tingkat turnover tertinggi terkonsentrasi pada **tahun pertama masa kerja (< 1 tahun)**, membuktikan perlunya penyempurnaan program *onboarding* serta evaluasi terstruktur pada bulan ke-3 dan ke-6.

---

## 🎯 Rekomendasi Strategis Manajemen

1. **Intervensi Kepemimpinan:** Prioritaskan pelatihan kepemimpinan (*coaching enablement*) atau rotasi manajer bertipe micromanage sebelum melakukan eskalasi anggaran remunerasi.
2. **Proteksi Tahun Pertama (New Hire Care):** Terapkan *buddy system* dan check-in berkala di bulan ke-3 dan ke-6 guna menekan turnover dini di lini depan toko.
3. **Program Retensi Khusus Talenta Kunci:** Bentuk *individual development plan* (IDP) dan *accelerated career pathing* untuk kategori *Star Talent* dan *Rising Stars*.

---

## 🛠️ Tech Stack & Arsitektur Data

* **Visualisasi & Dashboard:**
  * **HTML5 & Vanilla JavaScript (ES6+):** Ringan, zero external JS build dependency, waktu muat instan (< 100ms).
  * **Native Scalable Vector Graphics (SVG):** Visualisasi grafik batang, garis tren sparkline, dan scatter plot interaktif resolusi tinggi.
  * **Bento Grid UI & Dual Theme:** Desain responsif, clean data-ink ratio, mendukung *Dark Mode* dan switch dwi-bahasa (ID / EN).
* **Penyimpanan & Pemodelan Data (`data/`):**
  * `Retail_Workforce_Productivity_Flat_2000.csv`: Denormalized flat file berisi 2.000 baris data karyawan dengan atribut demografi, performa, flight risk, kepuasan, dan status kepegawaian.
  * `Retail_Workforce_Productivity_StarSchema.xlsx`: Relational dimensional model (Fact Table produktivitas bulanan + Dimension Tables: Toko, Karyawan, Manajer, Waktu).

---

## 📂 Struktur Repositori

```text
portfolio-retail-workforce/
├── index.html       # Standalone interactive dashboard (GitHub Pages entry point)
├── .gitignore       # Aturan pengabaian file OS & temporary files
├── README.md        # Dokumentasi portofolio & analisis eksekutif
└── data/            # Dataset sumber (Flat CSV & Star Schema Excel)
    ├── Retail_Workforce_Productivity_Flat_2000.csv
    └── Retail_Workforce_Productivity_StarSchema.xlsx
```

---

## 🚀 Petunjuk Menjalankan Dashboard

### Cara 1: Buka Langsung Secara Lokal (Paling Cepat)
Karena dashboard ini tidak membutuhkan compiler atau server backend:
1. Clone repositori ini:
   ```bash
   git clone https://github.com/wijaya-rama/portfolio-retail-workforce.git
   cd portfolio-retail-workforce
   ```
2. Cukup klik ganda (double click) file `index.html` atau buka menggunakan browser pilihan Anda (Chrome, Edge, Firefox, Safari).

### Cara 2: Menjalankan via Local Web Server
Jika ingin menjalankan via local server HTTP:
* **Menggunakan Python 3:**
  ```bash
  python -m http.server 8000
  ```
  Akses di browser: `http://localhost:8000`
* **Menggunakan VS Code:**
  Klik kanan pada `index.html` lalu pilih **Open with Live Server**.

### Cara 3: Menjalankan via GitHub Pages (Hosting Gratis)
1. Push folder repositori ini ke repository GitHub Anda.
2. Di GitHub, buka menu **Settings** > **Pages**.
3. Pada bagian **Build and deployment** > **Source**, pilih **Deploy from a branch**.
4. Pilih branch `main` (atau `master`) dengan folder `/ (root)`, lalu klik **Save**.
5. Dashboard interaktif akan live secara otomatis di URL `https://wijaya-rama.github.io/portfolio-retail-workforce/`.

---

## 👤 Author
* **Nama:** Rama Wijaya
* **LinkedIn:** [Rama Wijaya](https://www.linkedin.com/in/ramawijaya1)
* **Keahlian:** Data Analytics, People Analytics, Business Intelligence & Data Visualization
