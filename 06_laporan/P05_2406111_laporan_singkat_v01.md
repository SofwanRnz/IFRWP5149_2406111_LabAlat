# JOBSHEET REVIEW PRAKTIKUM PERTEMUAN 5
**Skenario Use Case: Dari Diagram ke Langkah Kegiatan**

## 1. Identitas dan Metadata Praktikum

* **Nama Mahasiswa:** Sofwan Robyansah Nur Zaman
* **NIM:** 2406111
* **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149)
* **Institusi:** Institut Teknologi Garut, S1 Teknik Informatika
* **Pertemuan:** 5 (Skenario Use Case)
* **Repositori GitHub:** `IFRWP5149_2406111_LabAlat`
* **Lokasi Penyimpanan Berkas:** `06_laporan/P05_2406111_laporan_singkat_v01.md`

---

## 2. Tujuan Pembelajaran

<!-- TODO: samakan dengan butir tujuan pembelajaran pada jobsheet P05 -->

Setelah mengikuti praktikum pertemuan ke-5 ini, mahasiswa mampu:

1. Menurunkan skenario use case (skenario normal, alternative, dan akhir) dari use case diagram.
2. Memisahkan kegiatan aktor dan respons sistem pada dua kolom, satu aksi per langkah.
3. Menuliskan skenario use case umum dan khusus tanpa mengulang langkah bersama.
4. Menelusuri setiap tabel skenario ke relasi pada diagram dan memeriksanya dengan checklist.

---

## 3. Dasar Teori dan Prinsip Praktikum

### A. Struktur Tabel Skenario

1. **Identitas:** nama use case, aktor, tujuan, dan deskripsi.
2. **Skenario Normal:** langkah berurutan dari awal hingga tujuan tercapai.
3. **Skenario Alternative:** cabang dari suatu langkah bila terjadi kondisi lain (misalnya data tidak lengkap).
4. **Skenario Akhir:** keadaan akhir untuk setiap kemungkinan.
5. **Dua kolom:** kolom Kegiatan hanya berisi aksi aktor, kolom Respon sistem hanya berisi tanggapan sistem.

### B. Pemetaan Relasi Diagram ke Tabel Skenario

| Relasi pada diagram | Representasi pada tabel skenario |
|---|---|
| Association | Aktor pada tabel use case yang bersangkutan |
| Generalization aktor | Skenario ditulis satu kali atas nama aktor umum |
| Generalization use case | Tabel use case umum memuat langkah bersama; tabel use case khusus hanya memuat perilaku pembeda dan merujuk ke tabel umum |
| Collaboration dan realization | Hanya disebut di keterangan, tidak punya langkah kegiatan |

<!-- TODO: tambahkan pemetaan include dan extend bila jobsheet P05 mengaturnya -->

---

## 4. Hasil Praktikum

### A. Studi Kasus Laboratorium (`LAB`)

Diagram kumulatif P04 menjadi acuan, dan tidak ada kebutuhan atau use case baru. Dua belas tabel skenario sudah disediakan, sehingga pekerjaan di bagian ini adalah **menelaah** tabel tersebut terhadap diagram acuan.

Use case yang ditelaah: LAB-UC01 sampai LAB-UC12 (Lihat Ketersediaan Peralatan, Ajukan Peminjaman, Periksa Ketersediaan, Cetak Bukti Pengajuan, Kelola Data Peralatan, Tambah, Ubah, Hapus Data Peralatan, Proses Keputusan Peminjaman, Lihat Laporan Peminjaman, Catat Pengembalian Peralatan, Periksa Kondisi Peralatan).

<!-- TODO: kolom "Relasi yang ditelusuri" pada tabel pemeriksaan LAB masih berisi "Diisi sesuai diagram". Isi dengan relasi dari diagram P04 untuk tiap use case. -->

### B. Studi Kasus Sistem Informasi Akademik (`SIA`)

Diagram acuan adalah `P04_2406111_SIA_usecase_v01.drawio` (tidak diubah) dengan kebutuhan SIA-R07 sampai SIA-R12. Tujuh tabel skenario ditulis:

| ID | Use case | Aktor | Langkah normal | Skenario alternative |
|---|---|---|---|---|
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | 4 | 1 (kalender belum tersedia) |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen | 8 | 2 (bukan pengampu; nilai di luar rentang) |
| SIA-UC09 | Lihat KHS | Mahasiswa | 4 | 1 (belum ada nilai terpublikasi) |
| SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik | 8 | 1 (data tidak lengkap atau tidak sah) |
| SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik | 6 | 1 (data tidak lengkap) |
| SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik | 6 | 2 (data tidak ditemukan; data tidak sah) |
| SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik | 4 | 1 (masih punya data akademik aktif) |

* SIA-UC07 ditulis satu kali atas nama Civitas Akademika dan berlaku untuk Mahasiswa dan Dosen.
* SIA-UC10 memuat langkah bersama; SIA-UC11, UC12, dan UC13 hanya memuat perilaku pembeda dan merujuk ke tabel UC10.
* Collaboration SIA-CO01 dan SIA-CO02 hanya disebut di keterangan.

### C. Struktur Direktori Repositori (`IFRWP5149_2406111_LabAlat`)

```text
IFRWP5149_2406111_LabAlat/
├── 01_skenario/
│   ├── P05_LAB_skenario_v01.md
│   └── P05_2406111_SIA_skenario_v01.md
├── 04_model_analisis/
│   ├── P04/                 (tetap, tidak diubah)
│   └── P05/
│       ├── LAB/             <!-- TODO: isi dengan berkas pemeriksaan -->
│       └── SIA/             <!-- TODO: isi dengan berkas pemeriksaan -->
└── 06_laporan/
    └── P05_2406111_laporan_singkat_v01.md   <-- (berkas ini)
```

---

## 5. Analisis dan Verifikasi Checklist Penilaian

### A. Checklist C.4

Keterangan: ✓ terpenuhi, ☐ belum diverifikasi, – tidak berlaku.

| No | Butir pemeriksaan | LAB | SIA |
|---|---|---|---|
| 1 | Field lengkap pada setiap tabel | ☐ | ✓ |
| 2 | Satu aksi per langkah, dengan penomoran berlanjut | ☐ | ✓ |
| 3 | Kolom Kegiatan hanya berisi aksi aktor; kolom Respon sistem hanya berisi tanggapan sistem | ☐ | ✓ |
| 4 | Data dan status disebut eksplisit | ☐ | ✓ |
| 5 | Generalization aktor dan use case diterapkan | ☐ | ✓ |
| 6 | Collaboration hanya muncul di keterangan | ☐ | ✓ |
| 7 | Setiap tabel punya Skenario Alternative dan Skenario Akhir | ☐ | ✓ |
| 8 | Nama, ID, dan aktor sama dengan diagram | ☐ | ✓ |

Kolom SIA mengikuti tabel pemeriksaan pada `P05_2406111_SIA_skenario_v01.md`, yang menyatakan ketujuh use case Terpenuhi.

### B. Catatan Berkas dan Kendala

<!-- TODO: tulis kendala yang benar-benar dialami -->

* Tabel pemeriksaan LAB pada `P05_LAB_skenario_v01.md` belum selesai: kolom "Relasi yang Ditelusuri" masih berisi penanda isian, dan baris header tabelnya rusak.
* ...

---

## 6. Kesimpulan

Pertemuan 5 menerjemahkan relasi pada diagram kumulatif P04 menjadi tabel skenario yang terstruktur. Pada studi kasus SIA, tujuh tabel (SIA-UC07 sampai SIA-UC13) ditulis dan diperiksa terhadap checklist C.4, sedangkan telaah tabel LAB masih perlu dilengkapi.

<!-- TODO: lengkapi setelah telaah LAB selesai -->