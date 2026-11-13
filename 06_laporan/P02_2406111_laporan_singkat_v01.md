# JOBSHEET REVIEW PRAKTIKUM PERTEMUAN 2
**Use Case Dasar: Hubungan Aktor dan Fungsi**

## 1. Identitas dan Metadata Praktikum

* **Nama Mahasiswa:** Sofwan Robyansah Nur Zaman
* **NIM:** 2406111
* **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149)
* **Institusi:** Institut Teknologi Garut, S1 Teknik Informatika
* **Pertemuan:** 2 (Use Case Diagram Dasar)
* **Repositori GitHub:** `IFRWP5149_2406111_LabAlat`
* **Lokasi Penyimpanan Berkas:** `06_laporan/P02_2406111_laporan_singkat_v01.md`

---

## 2. Tujuan Pembelajaran

<!-- TODO: samakan dengan butir tujuan pembelajaran pada jobsheet P02 -->

Setelah mengikuti praktikum pertemuan ke-2 ini, mahasiswa mampu:

1. Mengidentifikasi aktor dan fungsi dari skenario singkat.
2. Menghubungkan setiap aktor hanya dengan fungsi yang disebut dalam skenario.
3. Menerapkan notasi dasar: aktor di luar batas sistem, fungsi berbentuk elips, dan judul sistem sesuai kasus.
4. Meninjau diagram, mencatat temuan, dan memperbaikinya secara konsisten.

---

## 3. Dasar Teori dan Prinsip Praktikum

### A. Unsur Use Case Diagram Dasar

1. **Aktor:** pihak di luar sistem yang berinteraksi dengan sistem.
2. **Use case (fungsi):** layanan yang diberikan sistem, digambar sebagai elips dan ditulis dengan pola kata kerja + objek.
3. **Batas sistem:** kotak yang membatasi fungsi milik sistem, berjudul nama sistem.
4. **Asosiasi:** garis yang menghubungkan aktor dengan fungsi yang dilakukannya.

### B. Pemetaan Skenario ke Diagram

| Unsur pada skenario | Representasi pada diagram |
|---|---|
| Pelaku yang berinteraksi dengan sistem | Aktor, di luar batas sistem |
| Fungsi yang dilakukan pelaku | Use case berbentuk elips di dalam batas sistem |
| Nama sistem pada kasus | Judul batas sistem |
| Kalimat "pelaku melakukan fungsi" | Asosiasi, hanya jika disebut dalam skenario |

Prinsip konsistensi: nama sistem harus sama pada skenario, diagram, dan metadata.

---

## 4. Hasil Praktikum

### A. Studi Kasus Laboratorium (`LAB`)

Mahasiswa melihat informasi ketersediaan peralatan, dan petugas laboratorium mengelola data peralatan. Pertemuan ini hanya menggambarkan hubungan kedua peran dengan fungsi tersebut.

| ID kebutuhan | Aktor | Nama fungsi |
|---|---|---|
| LAB-R01 | Mahasiswa | Lihat ketersediaan peralatan |
| LAB-R02 | Petugas laboratorium | Kelola data peralatan |

<!-- TODO: sisipkan diagram LAB P02 -->

### B. Studi Kasus Sistem Informasi Akademik (`SIA`)

Mahasiswa melihat jadwal kuliah melalui Sistem Informasi Akademik, dan admin akademik mengelola jadwal kuliah. Mahasiswa tidak mengelola jadwal, dan admin tidak dihubungkan dengan fungsi melihat jadwal sebagai pengguna mahasiswa.

| Aktor | Fungsi | Kode (katalog P04) |
|---|---|---|
| Mahasiswa | Lihat jadwal kuliah | SIA-UC01 |
| Admin akademik | Kelola jadwal kuliah | SIA-UC02 |

**Temuan dan perbaikan pada tinjauan diagram:**

| No | Temuan | Perbaikan yang diperlukan | Alasan |
|---|---|---|---|
| 1 | Aktor Mahasiswa diletakkan di dalam batas sistem | Pindahkan aktor ke luar batas sistem | Aktor berada di luar batas sistem |
| 2 | Fungsi "Lihat jadwal kuliah" digambar sebagai kotak biasa | Ubah fungsi menjadi elips | Notasi standar use case adalah elips |
| 3 | Aktor Mahasiswa dihubungkan dengan "Kelola jadwal kuliah" | Hubungkan Mahasiswa ke "Lihat jadwal kuliah", dan "Kelola jadwal kuliah" ke Admin akademik | Aktor hanya dihubungkan dengan fungsi yang disebut dalam skenario |
| 4 | Diagram memakai judul sistem laboratorium | Ubah judul menjadi "Sistem Informasi Akademik" | Nama sistem sama pada skenario, diagram, dan metadata |

<!-- TODO: sisipkan diagram SIA P02 -->

### C. Struktur Direktori Repositori (`IFRWP5149_2406111_LabAlat`)

```text
IFRWP5149_2406111_LabAlat/
├── 01_skenario/
│   ├── P02_LAB_skenario_v01.md
│   └── P02_SIA_skenario_v01.md
├── 03_latihan_tools/            <!-- TODO: isi dengan lokasi berkas diagram P02 -->
└── 06_laporan/
    └── P02_2406111_laporan_singkat_v01.md   <-- (berkas ini)
```

---

## 5. Analisis dan Verifikasi Checklist Penilaian

### A. Checklist

Keterangan: ✓ terpenuhi, ☐ belum diverifikasi pada diagram akhir, – tidak berlaku.

| No | Butir pemeriksaan | LAB | SIA |
|---|---|---|---|
| 1 | Aktor berada di luar batas sistem | ☐ | ☐ |
| 2 | Setiap fungsi digambar sebagai elips | ☐ | ☐ |
| 3 | Aktor hanya terhubung ke fungsi yang disebut dalam skenario | ☐ | ☐ |
| 4 | Judul sistem pada batas sistem sesuai kasus | ☐ | ☐ |

### B. Catatan Berkas dan Kendala

<!-- TODO: tulis kendala yang benar-benar dialami -->

* `P02_SIA_skenario_v01.md` memuat dua baris kebutuhan LAB (LAB-R01 dan LAB-R02) yang tersalin dari studi kasus LAB, dan tabel temuannya rusak. Perlu dirapikan.
* ...

---

## 6. Kesimpulan

Pertemuan 2 melatih penerjemahan skenario singkat menjadi use case diagram dasar: aktor di luar batas sistem, fungsi berbentuk elips, asosiasi sesuai skenario, dan nama sistem yang konsisten.

<!-- TODO: lengkapi setelah diagram diverifikasi -->