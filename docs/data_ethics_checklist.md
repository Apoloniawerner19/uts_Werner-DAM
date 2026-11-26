# Jawaban Soal 2: Lisensi, Identifikasi PII, & Data Ethics Checklist (9 Butir)

## 1. Lisensi & Ketentuan Sumber
* **Dataset Terbuka (OpenStreetMap / Overpass API):** Lisensi **Open Database License (ODbL)** — bebas diunduh, diolah, dan digunakan kembali dengan mencantumkan atribusi sumber.
* **API Cuaca (Open-Meteo API):** Lisensi **Creative Commons Attribution 4.0 (CC BY 4.0)**.
* **Web Scraping (BPS Provinsi NTT):** **Data Terbuka Pemerintah (Open Government Data)** yang mengizinkan akses otomatis melalui `robots.txt` (`User-agent: *`, `Disallow:` kosong).

## 2. Identifikasi PII & Quasi-Identifier
* **PII (Personally Identifiable Information):** **Tidak ditemukan.** Seluruh data hanya memuat informasi tempat wisata/ekraf publik, statistik wilayah, dan cuaca tanpa identitas pribadi individu (NIK, nama perorangan, nomor telepon, atau alamat rumah).
* **Quasi-Identifier:** Kolom `kabupaten_kota` dan `tanggal` merupakan agregat wilayah administratif sehingga tidak dapat mengidentifikasi individu tertentu.

## 3. Data Ethics Checklist (9 Butir)
1. **[x] Kepatuhan Hukum & Lisensi:** Menggunakan sumber data terbuka resmi yang mengizinkan penggunaan akademis (Bukti: `docs/provenance.csv`).
2. **[x] Kepatuhan `robots.txt` & Larangan Platform:** Telah memeriksa `https://bps.go.id` dengan status `True` dan tidak melakukan scraping pada platform terlarang (Bukti: `docs/robots_check.json`).
3. **[x] Transparansi Identitas (`User-Agent`):** Menyertakan identitas proyek dan email pada setiap header HTTP request.
4. **[x] Pembatasan Kecepatan (*Rate Limiting*) & Timeout:** Setiap request menerapkan `timeout` dan jeda `time.sleep()`.
5. **[x] Perlindungan Privasi (Non-PII):** Memastikan tidak ada informasi identitas pribadi yang dikumpulkan.
6. **[x] Integritas Data Mentah:** Seluruh berkas mentah disimpan utuh tanpa modifikasi di folder `Data/Raw/`.
7. **[x] Pencatatan Asal-Usul (*Provenance*):** Mencatat URL asli, waktu akses, lisensi, dan hash MD5 seluruh berkas mentah (Bukti: `docs/provenance.csv`).
8. **[x] Keamanan Kredensial:** Tidak menuliskan kredensial rahasia secara terbuka di dalam notebook.
9. **[x] Validasi Integrasi Data:** Menggunakan parameter `validate="one_to_one"` saat menggabungkan data untuk mencegah duplikasi baris (Bukti: `Data/Process/metadata_gabungan.json`).
