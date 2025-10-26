### Log Eksperimen: 2025-10-26

1. **Tujuan singkat**: Melakukan analisis bibliometrik, menghasilkan laporan, dan membuat interpretasi awal dari data yang sudah disaring pada 2025-10-25.
2. **Data & sumber**: Data Scopus hasil *filtering* akhir (`2025-10-25_data_mentah-5.csv`).
3. **Alat & versi**: Biblioshiny (berbasis Bibliometrix R package).
4. **Protokol ringkas**:
    1. Data mentah Scopus diimpor ke Biblioshiny.
    2. Menghasilkan laporan umum (MainInfo, AnnualSciProd, AnnualCitPerYear) dan mengekspornya.
    3. Menghasilkan analisis dasar (Laporan Bibliometrik, Plot Tiga Bidang).
5. **Keputusan pembersihan**: Tidak ada pembersihan tambahan; data sudah bersih (clean data) dan siap dianalisis.
6. **Hasil cepat**:
    1. **Data Analisis:** Dihasilkan Laporan Biblioshiny Data Mentah (`2025-10-26_Laporan-Biblioshiny-Data-Mentah.xlsx`). Parameter versi: `Report`.
    2. **Interpretasi Umum:** Dibuat Interpretasi Bibliometrik SCOPUS (`2025-10-26_Interpretasi-Bibliometrik-SCOPUS.txt`). Parameter versi: Analisis dilakukan pada koleksi dari database SCOPUS.
    3. **Interpretasi Jaringan:** Dibuat Interpretasi Three-Field Plot (`2025-10-26_Interpretasi-Three-Field-Plot.txt`). Parameter versi: Target 'AU', kanan 'KW\_Merged', kiri 'CR'.
7. **Catatan lanjutan**: Hasil interpretasi awal menunjukkan fokus riset yang kuat pada *blockchain* dan *Islamic banking*. Lanjutkan dengan analisis klaster (clustering) dan visualisasi mendalam.

---

### Log Eksperimen: 2025-10-25

1. **Tujuan singkat**: Akuisisi data awal dari Scopus (filtering bertahap).
2. **Data & sumber**: Web interface Scopus. Kueri spesifik disimpan di metadata.
3. **Alat & versi**: Scopus (Web, Fungsi Ekspor CSV).
4. **Protokol ringkas**:
    1. Masuk ke Scopus dan memilih pencarian 'Document'.
    2. Memasukkan kueri pencarian dasar (lihat `data_mentah-0.meta.json`).
    3. Kueri disaring (filtered) secara bertahap (mis. Tipe Dokumen, Bahasa, dll.) dan diekspor pada tiap tahap.
4. Menyimpan file sebagai `2025-10-25_data_mentah-{number}.csv` dan membuat file `.meta.json` untuk mencatat kueri spesifik.
5. **Keputusan pembersihan**: Tidak ada pembersihan, ini adalah data mentah (raw data).
6. **Hasil cepat**: *Kueri Dasar (KD): ("Blockchain" OR "Smart Contract") AND ("Islamic Finance" OR "Sharia Compliance" OR "Islamic Banking") AND ("Akad" OR "Contract" OR "Transparency" OR "Murabahah" OR "Mudharabah")*
    1. `2025-10-25_data_mentah-0.csv` : Total dokumen ditemukan: 1041. Rentang tahun: 2017-2026. *Kueri: (KD)*
    2. `2025-10-25_data_mentah-1.csv` : Total dokumen ditemukan: 574. Rentang tahun: 2017-2026. *Kueri: (KD) AND ( LIMIT-TO ( DOCTYPE,"ar" ) )*
    3. `2025-10-25_data_mentah-2.csv` : Total dokumen ditemukan: 567. Rentang tahun: 2017-2026. *Kueri: (KD) AND ( LIMIT-TO ( DOCTYPE,"ar" ) ) AND ( LIMIT-TO ( LANGUAGE,"English" ) )*
    4. `2025-10-25_data_mentah-3.csv` : Total dokumen ditemukan: 508. Rentang tahun: 2017-2026. *Kueri: (KD) AND ( LIMIT-TO ( DOCTYPE,"ar" ) ) AND ( LIMIT-TO ( LANGUAGE,"English" ) ) AND ( LIMIT-TO ( PUBSTAGE,"final" ) )*
    5. `2025-10-25_data_mentah-4.csv` : Total dokumen ditemukan: 501. Rentang tahun: 2017-2026. *Kueri: (Metadata tidak tersedia)*
    6. `2025-10-25_data_mentah-5.csv` : Total dokumen ditemukan: 209. Rentang tahun: 2019-2026. *Kueri: (KD) AND ( LIMIT-TO ( DOCTYPE,"ar" ) ) AND ( LIMIT-TO ( LANGUAGE,"English" ) ) AND ( LIMIT-TO ( PUBSTAGE,"final" ) ) AND ( LIMIT-TO ( SRCTYPE,"j" ) ) AND ( LIMIT-TO ( OA,"all" ) )*
7. **Catatan lanjutan**: Segera lakukan pembersihan awal (langkah selanjutnya).

---