# UTS Data Acquisition & Management — UTS_DAM_2501010151
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
| 1 | **Unduh Dataset** | Portal Data Terbuka Spasial Pariwisata & Ekonomi Kreatif NTT (OpenStreetMap) | [overpass-api.de](https://overpass-api.de) | CSV / Excel (≥ 100 baris) |
| 2 | **API** | Open-Meteo Weather API (22 Kabupaten/Kota di Provinsi NTT) | [open-meteo.com](https://open-meteo.com) | JSON → Tabel (≥ 30 baris) |
| 3 | **Web Scraping** | Tabel Statistik Daya Tarik Wisata BPS Provinsi NTT | [ntt.bps.go.id](https://bps.go.id) | HTML → Tabel |

---

## 3. Goal / Tujuan

Topik yang digunakan adalah **Pariwisata & Ekonomi Kreatif Provinsi Nusa Tenggara Timur (NTT) per Kabupaten/Kota**. Proyek ini bertujuan mengakuisisi data destinasi dan ekraf melalui dataset terbuka (≥ 100 baris), cuaca harian 22 kabupaten/kota via Open-Meteo API (≥ 30 baris), serta tabel statistik BPS yang mematuhi `robots.txt`. Data kemudian dibersihkan, divalidasi, dan digabungkan (`merge` dengan `validate="one_to_one"`) berdasarkan kunci `kabupaten_kota` untuk analisis dan visualisasi.
---

## 4. Data Raw

Folder `Data/Raw/` digunakan untuk menyimpan seluruh hasil akuisisi mentah tanpa perubahan.

| Jenis Data | Format | Keterangan |
| :--- | :--- | :--- |
| Dataset unduhan | CSV / Excel | Dataset asli dari portal terbuka NTT, minimal 100 baris |
| Data API | JSON | Respons mentah Open-Meteo (22 Kabupaten/Kota NTT) |
| Data scraping | HTML | HTML asli halaman BPS Provinsi NTT yang diizinkan |

---

## 5. Process

Folder `Data/Process/` digunakan untuk menyimpan data hasil pembacaan, normalisasi, pembersihan, penggabungan, dan visualisasi.

| Hasil Proses | Format |
| :--- | :--- |
| Dataset berkas bersih | CSV / XLSX |
| Data API ternormalisasi | CSV / JSON |
| Data scraping terstruktur | CSV / JSON |
| Hasil penggabungan (`merge`) | CSV / JSON / HTML / XLSX |
| Visualisasi hasil gabungan | PNG |

---

## 6. Dokumentasi

Folder `docs/` berisi catatan *provenance* (`provenance.csv`), *Data Ethics Checklist* 9 butir (`data_ethics_checklist.md`), bukti pemeriksaan `robots.txt` (`robots_check.json`), klasifikasi PII, estimasi *storage*, dan metadata hasil penggabungan. Berkas dokumentasi yang dihasilkan notebook akan tersimpan di folder ini.

---

## 7. Cara Menjalankan

1. Buka notebook `UTS_DAM_2501010151.ipynb` melalui Google Colab atau Jupyter.
2. Pastikan variabel `EMAIL_PRIBADI` sudah diisi dengan email pribadi/kampus yang aktif.
3. Jalankan seluruh sel notebook secara berurutan dari Sel 1 hingga Sel 7.
4. Periksa bahwa dataset mentah tersimpan di `Data/Raw/`, hasil olahan di `Data/Process/`, dan dokumentasi di `docs/`.
5. Pastikan semua sel selesai dijalankan dan hasil akuisisi benar-benar tersedia sebelum repository dibagikan.

---

## 8. Struktur Folder

```text
uts_Werner-DAM/
├── README.md
├── UTS_DAM_2501010151.ipynb
├── requirements.txt
├── Data/
│   ├── Raw/          # Data mentah sesuai instruksi UTS
│   └── Process/      # Data bersih, hasil merge, dan visualisasi
└── docs/             # Provenance, checklist, dan bukti robots.txt
```

**Dataset utama:** menggunakan data terbuka destinasi pariwisata dan ekonomi kreatif Provinsi Nusa Tenggara Timur (NTT) yang memenuhi syarat minimal 100 baris serta digabungkan berdasarkan kunci 22 kabupaten/kota di NTT.
