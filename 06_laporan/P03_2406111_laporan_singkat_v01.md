# JOBSHEET REVIEW PRAKTIKUM PERTEMUAN 3
**Use Case Diagram: Relasi Include dan Extend**

## 1. Identitas dan Metadata Praktikum

* **Nama Mahasiswa:** Sofwan Robyansah Nur Zaman
* **NIM:** 2406111
* **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149)
* **Institusi:** Institut Teknologi Garut, S1 Teknik Informatika
* **Pertemuan:** 3 (Include dan Extend)
* **Repositori GitHub:** `IFRWP5149_2406111_LabAlat`
* **Lokasi Penyimpanan Berkas:** `06_laporan/P03_2406111_laporan_singkat_v01.md`

---

## 2. Tujuan Pembelajaran

<!-- TODO: samakan dengan butir tujuan pembelajaran pada jobsheet P03 -->

Setelah mengikuti praktikum pertemuan ke-3 ini, mahasiswa mampu:

1. Membedakan perilaku wajib (include) dari perilaku bersyarat (extend).
2. Menentukan extension point dan condition pada relasi extend.
3. Menuliskan batas sistem dan aturan agar model tidak melebar.
4. Menggambar use case diagram dengan relasi include dan extend yang benar.

---

## 3. Dasar Teori dan Prinsip Praktikum

### A. Relasi Antar-Use Case

1. **Include:** use case dasar selalu menjalankan use case yang disertakan; panah «include» dari use case dasar ke use case yang disertakan.
2. **Extend:** use case tambahan hanya berjalan bila suatu kondisi terpenuhi; panah «extend» dari use case tambahan ke use case dasar.
3. **Extension point:** titik pada use case dasar tempat perilaku tambahan dapat disisipkan.
4. **Condition:** syarat yang harus terpenuhi agar extend berjalan, ditulis dalam kurung siku.

### B. Pemetaan Skenario ke Diagram

| Unsur pada skenario | Representasi pada diagram |
|---|---|
| Langkah yang selalu terjadi sebagai bagian validasi atau proses | Include |
| Langkah opsional atas pilihan pengguna | Extend dengan condition dan extension point |
| Aturan bahwa proses tetap berhasil tanpa langkah opsional | Use case dasar tidak bergantung pada use case extend |
| Hal yang belum dianalisis | Ditulis pada batas sistem dan aturan, tidak digambar |

---

## 4. Hasil Praktikum

### A. Studi Kasus Laboratorium (`LAB`)

Mahasiswa mengajukan peminjaman peralatan dengan memilih alat, jumlah, dan rentang waktu. Sistem memeriksa ketersediaan. Jika tersedia dan data lengkap, pengajuan disimpan berstatus menunggu keputusan. Mahasiswa dapat memilih mencetak bukti pengajuan. Petugas mengelola data peralatan serta menyetujui atau menolak pengajuan, dan kepala laboratorium melihat laporan peminjaman.

**Aktor:** Mahasiswa; Petugas laboratorium; Kepala laboratorium.

| ID | Nama use case | Peran dalam model | Kebutuhan |
|---|---|---|---|
| LAB-UC01 | Lihat Ketersediaan Peralatan | Fungsi utama mahasiswa | LAB-R01 |
| LAB-UC02 | Kelola Data Peralatan | Fungsi utama petugas | LAB-R02 |
| LAB-UC03 | Ajukan Peminjaman | Fungsi utama mahasiswa | LAB-R03 |
| LAB-UC04 | Periksa Ketersediaan | Perilaku yang disertakan UC03 | LAB-R03 |
| LAB-UC05 | Cetak Bukti Pengajuan | Tambahan bersyarat pada UC03 | LAB-R04 |
| LAB-UC06 | Proses Keputusan Peminjaman | Fungsi utama petugas | LAB-R05 |
| LAB-UC07 | Lihat Laporan Peminjaman | Fungsi utama kepala laboratorium | LAB-R06 |

**Relasi:**

* include: LAB-UC03 → LAB-UC04. Pemeriksaan ketersediaan menjadi bagian validasi pengajuan.
* extend: LAB-UC05 → LAB-UC03. Condition [mahasiswa memilih cetak]; extension point Bukti pengajuan tersedia; pengajuan tetap berhasil tanpa pencetakan.

**Batas sistem dan aturan:**

* Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak terjadi di dalam perangkat lunak.
* Pengajuan yang diterima berstatus Menunggu keputusan, bukan otomatis Disetujui.
* Pengajuan dengan peralatan tidak tersedia tidak disimpan sebagai pengajuan berhasil.
* Pencetakan bukti tidak menjadi syarat keberhasilan pengajuan.
* Pengambilan, pengembalian, kondisi alat, dan denda belum dianalisis pada pertemuan ini.

<!-- TODO: sisipkan diagram LAB P03 -->

### B. Studi Kasus Sistem Informasi Akademik (`SIA`)

<!-- TODO: berkas P03_SIA_skenario belum tersedia. Isi dari skenario dan diagram P03 SIA milik sendiri. -->

Menurut katalog P04, fungsi yang berasal dari P03 adalah:

| ID | Nama use case | Aktor | Relasi |
|---|---|---|---|
| SIA-UC03 | Ajukan KRS | Mahasiswa | «include» SIA-UC04 |
| SIA-UC04 | Validasi KRS | | Perilaku yang disertakan |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | «extend» ke SIA-UC03 |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | |

Kebutuhan terkait: SIA-R03 sampai SIA-R06.

### C. Struktur Direktori Repositori (`IFRWP5149_2406111_LabAlat`)

```text
IFRWP5149_2406111_LabAlat/
├── 01_skenario/
│   └── P03_LAB_skenario_v01.md
├── 04_model_analisis/
│   └── P03/                     <!-- TODO: isi dengan berkas diagram LAB dan SIA -->
└── 06_laporan/
    └── P03_2406111_laporan_singkat_v01.md   <-- (berkas ini)
```

---

## 5. Analisis dan Verifikasi Checklist Penilaian

### A. Checklist

Keterangan: ✓ terpenuhi, ☐ belum diverifikasi pada diagram akhir, – tidak berlaku.

| No | Butir pemeriksaan | LAB | SIA |
|---|---|---|---|
| 1 | Include digambar dari use case dasar ke use case yang disertakan (UC03 → UC04) | ☐ | ☐ |
| 2 | Extend digambar dari use case tambahan ke use case dasar (UC05 → UC03) | ☐ | ☐ |
| 3 | Relasi extend memuat condition dan extension point | ☐ | ☐ |
| 4 | Use case dasar tetap berhasil tanpa use case extend | ☐ | ☐ |
| 5 | Setiap aktor hanya terhubung ke fungsi yang disebut dalam skenario | ☐ | ☐ |

### B. Catatan Berkas dan Kendala

<!-- TODO: tulis kendala yang benar-benar dialami -->

* `P03_LAB_skenario_v01.md` perlu dirapikan: komentar `!-- relasi include -->` kehilangan tanda `<`, tabel aktor bergeser (kata "laboratorium" terpisah dari Petugas), dan ada salah ketik "dianalisisn".
* ...

---

## 6. Kesimpulan

Pertemuan 3 membedakan perilaku wajib (include) dan bersyarat (extend). Pada studi kasus LAB, pemeriksaan ketersediaan disertakan pada pengajuan, sedangkan pencetakan bukti hanya berjalan bila mahasiswa memilihnya.

<!-- TODO: lengkapi setelah diagram LAB dan SIA diverifikasi -->