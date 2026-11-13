# JOBSHEET REVIEW PRAKTIKUM PERTEMUAN 4
**Use Case Diagram Kumulatif: Generalization dan Collaboration**

## 1. Identitas dan Metadata Praktikum

* **Nama Mahasiswa:** Sofwan Robyansah Nur Zaman
* **NIM:** 2406111
* **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149)
* **Institusi:** Institut Teknologi Garut, S1 Teknik Informatika
* **Pertemuan:** 4 (Generalization dan Collaboration)
* **Repositori GitHub:** `IFRWP5149_2406111_LabAlat`
* **Lokasi Penyimpanan Berkas:** `06_laporan/P04_2406111_laporan_singkat_v01.md`

---

## 2. Tujuan Pembelajaran

<!-- TODO: samakan dengan butir tujuan pembelajaran pada jobsheet P04 -->

Setelah mengikuti praktikum pertemuan ke-4 ini, mahasiswa mampu:

1. Menerapkan generalization pada aktor dan use case.
2. Menunjukkan realisasi use case utama dengan collaboration.
3. Menjaga diagram tetap kumulatif: hasil pertemuan sebelumnya ditambah, bukan diganti.
4. Mencatat pertanyaan terbuka dan menguji konsistensi model terhadap situasi tertentu.

---

## 3. Dasar Teori dan Prinsip Praktikum

### A. Unsur Pemodelan

1. **Generalization aktor:** aktor khusus mewarisi fungsi aktor umum; panah segitiga kosong menempel pada aktor umum.
2. **Generalization use case:** use case khusus menjabarkan use case umum; panah menuju use case umum.
3. **Collaboration:** elemen yang menunjukkan realisasi sebuah use case; tidak terhubung ke aktor.
4. **Realization:** hubungan dari collaboration menuju use case yang direalisasikan.
5. **Diagram kumulatif:** diagram pertemuan ini adalah diagram sebelumnya yang ditambah, bukan diagram baru.

### B. Pemetaan Keputusan Pemodelan

| Situasi pada skenario | Representasi pada diagram |
|---|---|
| Dua aktor berbagi fungsi yang sama | Aktor umum, dengan asosiasi fungsi bersama digambar satu kali dari aktor umum |
| Fungsi yang hanya dimiliki satu aktor | Asosiasi tetap digambar dari aktor khusus tersebut |
| Satu fungsi punya beberapa varian | Use case umum dan use case khusus (generalization use case) |
| Use case utama perlu ditunjukkan realisasinya | Collaboration dan realization ke use case |

---

## 4. Hasil Praktikum

### A. Studi Kasus Laboratorium (`LAB`)

Melanjutkan model P03.

| Aktor | Kedudukan | Tanggung jawab |
|---|---|---|
| Peminjam | Aktor umum | Melihat ketersediaan dan mengajukan peminjaman |
| Mahasiswa | Aktor khusus Peminjam | Fungsi peminjaman dan mencetak bukti pengajuan |
| Dosen | Aktor khusus Peminjam | Melihat ketersediaan dan mengajukan peminjaman |
| Petugas Laboratorium | Aktor operasional | Mengelola peralatan, memproses keputusan, mencatat pengembalian |
| Kepala Laboratorium | Aktor pelaporan | Melihat laporan peminjaman |

**Use case baru:** LAB-UC08 Tambah, LAB-UC09 Ubah, dan LAB-UC10 Hapus Data Peralatan (khusus dari LAB-UC02); LAB-UC11 Catat Pengembalian Peralatan; LAB-UC12 Periksa Kondisi Peralatan. LAB-UC01 sampai LAB-UC07 dari P03 tetap dipertahankan. Kebutuhan yang dicakup: LAB-R01 sampai LAB-R11.

| Jenis relasi | Hubungan |
|---|---|
| Generalization aktor | Mahasiswa → Peminjam; Dosen → Peminjam |
| Generalization use case | LAB-UC08, UC09, UC10 → LAB-UC02 |
| include | LAB-UC03 → LAB-UC04; LAB-UC11 → LAB-UC12 |
| extend | LAB-UC05 → LAB-UC03 (condition [mahasiswa memilih cetak]; extension point Bukti pengajuan tersedia) |
| Realization | LAB-CO01 → LAB-UC03; LAB-CO02 → LAB-UC11 |

**Pertanyaan terbuka:** batas waktu peminjaman, penentuan keterlambatan, denda atau sanksi, dan tindak lanjut peralatan rusak. Hal ini belum menjadi aturan sistem.

<!-- TODO: sisipkan diagram LAB P04 -->

### B. Studi Kasus Sistem Informasi Akademik (`SIA`)

Layanan Hasil Studi, melanjutkan jadwal kuliah P02 dan KRS P03. Civitas Akademika menjadi aktor umum; Mahasiswa dan Dosen adalah aktor khusus. Asosiasi ke SIA-UC07 digambar satu kali dari Civitas Akademika.

| ID | Nama use case | Aktor | Keterangan |
|---|---|---|---|
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | Direalisasikan SIA-CO01 |
| SIA-UC09 | Lihat KHS | Mahasiswa | Direalisasikan SIA-CO02 |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | Use case umum |
| SIA-UC11 | Tambah Data Mahasiswa | | Khusus dari UC10 |
| SIA-UC12 | Ubah Data Mahasiswa | | Khusus dari UC10 |
| SIA-UC13 | Hapus Data Mahasiswa | | Khusus dari UC10; hanya bila tidak ada data akademik aktif |

| Sumber | Hubungan | Tujuan |
|---|---|---|
| Civitas Akademika | Association | SIA-UC07 |
| Dosen | Association | SIA-UC08 |
| Mahasiswa | Association | SIA-UC09 |
| Admin Akademik | Association | SIA-UC10 |
| Mahasiswa, Dosen | Generalization | Civitas Akademika |
| SIA-UC11, UC12, UC13 | Generalization | SIA-UC10 |
| SIA-CO01, SIA-CO02 | Realization | SIA-UC08, SIA-UC09 |

**Uji konsistensi:**

* Situasi A: Mahasiswa melihat kalender akademik tanpa garis langsung tetap benar karena mewarisi asosiasi dari Civitas Akademika.
* Situasi B: dosen yang bukan pengampu ditolak sistem (alur alternatif A1); tidak ada nilai tersimpan.
* Situasi C: penghapusan data mahasiswa yang masih punya data akademik aktif ditolak; data tetap tersimpan.

**Pertanyaan terbuka:** rentang nilai yang sah, mekanisme publikasi nilai, definisi "data akademik aktif", dan koreksi nilai setelah diinput.

<!-- TODO: sisipkan diagram SIA P04 -->

### C. Struktur Direktori Repositori (`IFRWP5149_2406111_LabAlat`)

```text
IFRWP5149_2406111_LabAlat/
├── 01_skenario/
│   ├── P04_LAB_kebutuhan_v01.md
│   ├── P04_LAB_skenario_v01.md
│   ├── P04_SIA_kebutuhan_v01.md
│   └── P04_SIA_skenario_v01.md
├── 04_model_analisis/
│   └── P04/
│       ├── LAB/             <!-- TODO: isi dengan berkas diagram -->
│       └── SIA/             <!-- TODO: isi dengan berkas diagram -->
└── 06_laporan/
    └── P04_2406111_laporan_singkat_v01.md   <-- (berkas ini)
```

---

## 5. Analisis dan Verifikasi Checklist Penilaian

### A. Checklist

Keterangan: ✓ terpenuhi, ☐ belum diverifikasi pada diagram akhir, – tidak berlaku.

| No | Butir pemeriksaan | LAB | SIA |
|---|---|---|---|
| 1 | Generalization aktor memakai segitiga kosong yang menempel pada aktor umum | ☐ | ☐ |
| 2 | Asosiasi fungsi bersama digambar satu kali dari aktor umum, tidak diulang dari aktor khusus | ☐ | ☐ |
| 3 | Asosiasi fungsi khusus tetap digambar dari aktor khusus | ☐ | ☐ |
| 4 | Generalization use case mengarah dari use case khusus ke use case umum | ☐ | ☐ |
| 5 | Include dan extend dari pertemuan sebelumnya tetap benar | ☐ | ☐ |
| 6 | Collaboration tidak terhubung ke aktor; realization mengarah ke use case | ☐ | ☐ |
| 7 | Diagram kumulatif: elemen P02 dan P03 tetap ada | ☐ | ☐ |
| 8 | Seluruh kebutuhan tercakup (LAB-R01 s.d. R11; SIA-R07 s.d. R12) | ☐ | ☐ |

### B. Kendala

<!-- TODO: tulis kendala yang benar-benar dialami -->

* ...

---

## 6. Kesimpulan

Pertemuan 4 mengembangkan model dengan generalization aktor, rincian pengelolaan data, pencatatan pengembalian (LAB), dan collaboration. Fungsi dari pertemuan sebelumnya tetap digambar agar diagram bersifat kumulatif.

<!-- TODO: lengkapi setelah diagram LAB dan SIA diverifikasi -->