# UTS Data Acquisition & Management — UTS_DAM_2501010151

**Topik:** Pariwisata & Ekonomi Kreatif Provinsi Nusa Tenggara Timur (NTT) per Kabupaten/Kota  
**Alur:** (a) berkas dataset → (b) API Open-Meteo → (c) scraping situs pemerintah (BPS NTT) → gabungan (merge) → visual  
**Struktur:** `Data/Raw` (data mentah, tidak diubah) · `Data/Process` (hasil olah) · `docs` (provenance, checklist, bukti robots.txt)

---

## 1. Data Diri

| Keterangan | Identitas |
| :--- | :--- |
| **Nama** | Apolonia Werner |
| **NIM** | 2501010151 |
| **Program Studi** | Informatika — Data Science |
| **Kelas** | F |
| **Mata Kuliah** | Data Acquisition & Management |
| **Dosen** | Dr. I Gede Totok Suryawan, S.Kom., M.T. |

---

## 2. Sumber / URL

| No. | Metode Akuisisi | Sumber | URL | Bentuk Data |
| :---: | :--- | :--- | :--- | :--- |
| 1 | **Unduh Dataset** | Portal Data Terbuka Spasial Pariwisata & Ekonomi Kreatif NTT (OpenStreetMap / Overpass) | `https://overpass-api.de` | CSV / Excel (≥ 100 baris) |
| 2 | **API** | Open-Meteo Weather API (22 Kabupaten/Kota di Provinsi NTT) | `https://open-meteo.com` | JSON → Tabel (≥ 30 baris) |
| 3 | **Web Scraping** | Tabel Statistik Daya Tarik Wisata BPS Provinsi NTT | `https://bps.go.id` | HTML → Tabel |

---

## 3. Goal / Tujuan

Topik yang digunakan adalah **Pariwisata & Ekonomi Kreatif Provinsi Nusa Tenggara Timur (NTT) per Kabupaten/Kota**. Proyek ini bertujuan mengakuisisi data destinasi dan ekraf melalui dataset terbuka (≥ 100 baris), cuaca harian 22 kabupaten/kota via Open-Meteo API (≥ 30 baris), serta tabel statistik BPS yang mematuhi `robots.txt`. Data kemudian dibersihkan, divalidasi, dan digabungkan (`merge` dengan `validate="one_to_one"`) berdasarkan kunci `kabupaten_kota` untuk analisis dan visualisasi.
6
