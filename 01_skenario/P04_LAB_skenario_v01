<!-- Deskripsi skenario -->

Skenario ini melanjutkan potongan model Pertemuan 3. Selain mahasiswa, dosen juga meminjam peralatan laboratorium untuk kegiatan praktikum dan penelitian. Mahasiswa dan dosen sama-sama dapat melihat ketersediaan peralatan dan mengajukan peminjaman. Petugas laboratorium mengelola data peralatan: menambah peralatan baru, mengubah data peralatan, dan menghapus data peralatan yang tidak lagi dipakai. Setelah peminjaman disetujui dan alat diambil, petugas mencatat pengembalian peralatan. Pada saat mencatat pengembalian, petugas memeriksa dan mencatat kondisi peralatan. Dua use case utama pada potongan model ini, Ajukan Peminjaman dan Catat Pengembalian Peralatan, ditunjukkan realisasinya oleh collaboration yang bersesuaian. Seluruh fungsi Pertemuan 3 tetap berlaku dan tetap digambar: pemeriksaan ketersediaan di dalam pengajuan, pencetakan bukti pengajuan oleh mahasiswa, proses keputusan peminjaman oleh petugas, dan laporan peminjaman untuk kepala laboratorium. Diagram Pertemuan 4 adalah diagram Pertemuan 3 yang ditambah, bukan diagram baru yang menggantikannya.

<!-- Ketentuan Sistem -->

- Sistem hanya menangani pengelolaan informasi dan pencatatan transaksi. Perpindahan fisik peralatan dilakukan di luar aplikasi.
- Pengguna diasumsikan sudah terautentikasi dan memiliki hak akses sesuai perannya.
- Pengembalian hanya dapat dicatat apabila status peminjaman adalah Dipinjam.
- Peminjaman berstatus Menunggu Keputusan atau Ditolak tidak dapat dicatat sebagai pengembalian.
- Kondisi alat saat dikembalikan harus dipilih dari kategori Baik, Rusak Ringan, atau Rusak Berat.
- Data peralatan hanya dapat dihapus jika alat tidak sedang dipinjam dan tidak mempunyai pengajuan aktif.
- Ketentuan keterlambatan dan denda belum ditentukan. Hal tersebut harus dicatat sebagai pertanyaan terbuka.
- Diagram harus mencakup seluruh kebutuhan LAB-R01  sampai LAB-R11, dengan hubungan UML yang benar dan konsisten.

<!-- Identifikasi Aktor -->

| Aktor                | Kedudukan             | Tanggung Jawab                                                       |
|---                   |---                    |---                                                                   |
| Peminjam             | Aktor umum            | Melihat ketersediaan dan mengajukan peminjaman.                      |
| Mahasiswa            | Aktor khusus Peminjam | Melakukan fungsi peminjaman dan mencetak bukti pengajuan.            |
| Dosen                | Aktor khusus Peminjam | Melihat ketersediaan dan mengajukan peminjaman.                      |
| Petugas Laboratorium | Aktor operasional     | Mengelola peralatan, memproses keputusan, dan mencatat pengembalian. |
| Kepala Laboratorium  | Aktor pelaporan       | Melihat laporan peminjaman.                                          |

<!-- Daftar Use Case -->
| Kode     | Nama Use Case                | Keterangan                                                                                    | Kebutuhan        |
|---       |---                           |---                                                                                            |---               |
| LAB-UC01 | Lihat Ketersediaan Peralatan | Fungsi umum bagi peminjam.                                                                    | LAB-R01, LAB-R07 |
| LAB-UC02 | Kelola Data Peralatan        | Fungsi utama pengelolaan inventaris.                                                          | LAB-R02, LAB-R08 |
| LAB-UC03 | Ajukan Peminjaman            | Pengajuan peminjaman yang mencakup pemeriksaan ketersediaan dan direalisasikan oleh LAB-CO01. | LAB-R03, LAB-R07 |
| LAB-UC04 | Periksa Ketersediaan         | Bagian dari proses pengajuan peminjaman.                                                      | LAB-R03          |
| LAB-UC05 | Cetak Bukti Pengajuan        | Fitur tambahan khusus mahasiswa.                                                              | LAB-R04          |
| LAB-UC06 | Proses Keputusan Peminjaman  | Petugas menentukan keputusan pengajuan.                                                       | LAB-R05          |
| LAB-UC07 | Lihat Laporan Peminjaman     | Menampilkan laporan transaksi peminjaman.                                                     | LAB-R06          |
| LAB-UC08 | Tambah Data Peralatan        | Operasi khusus penambahan data alat.                                                          | LAB-R08          |
| LAB-UC09 | Ubah Data Peralatan          | Operasi khusus perubahan data alat.                                                           | LAB-R08          |
| LAB-UC10 | Hapus Data Peralatan         | Operasi penghapusan data sesuai ketentuan.                                                    | LAB-R08          |
| LAB-UC11 | Catat Pengembalian Peralatan | Proses pengembalian yang direalisasikan oleh LAB-CO02.                                        | LAB-R09          |
| LAB-UC12 | Periksa Kondisi Peralatan    | Pemeriksaan kondisi alat saat dikembalikan.                                                   | LAB-R10          |

<!-- Generalization Aktor -->

Aktor Peminjam digunakan sebagai aktor induk karena Mahasiswa dan Dosen mempunyai fungsi yang sama dalam proses peminjaman.

Ketentuan pemodelannya adalah:

1. Mahasiswa menjadi aktor khusus dari Peminjam.
2. Dosen menjadi aktor khusus dari Peminjam.
3. Arah panah generalization menggunakan segitiga kosong yang mengarah ke Peminjam.
4. Asosiasi Peminjam dengan LAB-UC01 dan LAB-UC03 cukup digambarkan satu kali.
5. Asosiasi Mahasiswa dengan LAB-UC05 Cetak Bukti Pengajuan` tetap dipertahankan karena merupakan fungsi khusus mahasiswa.

<!-- Hubungan Antarelemen UML -->

| Jenis Relasi            | Hubungan             | Keterangan                                                                       |
|---                      |---                   |---                                                                               |
| Generalization Aktor    | Mahasiswa → Peminjam | Mahasiswa mewarisi fungsi dari aktor umum Peminjam.                              |
| Generalization Aktor    | Dosen → Peminjam     | Dosen mewarisi fungsi dari aktor umum Peminjam.                                  |
| Generalization Use Case | LAB-UC08 → LAB-UC02  | Tambah Data Peralatan merupakan fungsi khusus dari Kelola Data Peralatan.        |
| Generalization Use Case | LAB-UC09 → LAB-UC02  | Ubah Data Peralatan merupakan fungsi khusus dari Kelola Data Peralatan.          |
| Generalization Use Case | LAB-UC10 → LAB-UC02  | Hapus Data Peralatan merupakan fungsi khusus dari Kelola Data Peralatan.         |
| include                 | LAB-UC03 → LAB-UC04  | Ajukan Peminjaman selalu melibatkan pemeriksaan ketersediaan peralatan.          |
| extend                  | LAB-UC05 → LAB-UC03  | Cetak Bukti Pengajuan dijalankan apabila mahasiswa memilih untuk mencetak bukti. |
| include                 | LAB-UC11 → LAB-UC12  | Catat Pengembalian Peralatan mencakup pemeriksaan kondisi alat.                  |
| Realization             | LAB-CO01 → LAB-UC03  | Collaboration LAB-CO01 merealisasikan use case Ajukan Peminjaman.                |
| Realization             | LAB-CO02 → LAB-UC11  | Collaboration LAB-CO02 merealisasikan use case Catat Pengembalian Peralatan.     |

Pada relasi extend, gunakan kondisi [mahasiswa memilih cetak]  dan extension point Bukti pengajuan tersedia.

<!-- Perbandingan Pertemuan 3 dan Pertemuan 4 -->

| Aspek                     | Perubahan dan Penjelasan                                                                                                           |
|---                        |---                                                                                                                                 |
| Elemen yang dipertahankan | Aktor Mahasiswa, Petugas Laboratorium, Kepala Laboratorium, dan use case LAB-UC01 sampai LAB-UC07.                                 |
| Perubahan asosiasi        | Hubungan ke LAB-UC01 dan LAB-UC03 dipindahkan dari Mahasiswa ke Peminjam karena fungsi tersebut diwariskan melalui generalization. |
| Penambahan aktor          | Peminjam dan Dosen ditambahkan untuk membentuk struktur generalization.                                                            |
| Pengelolaan inventaris    | LAB-UC08, LAB-UC09, dan LAB-UC10 ditambahkan sebagai turunan dari LAB-UC02.                                                        |
| Pengembalian alat         | LAB-UC11 dan LAB-UC12 ditambahkan untuk pencatatan pengembalian serta pemeriksaan kondisi peralatan.                               |
| Collaboration             | LAB-CO01 dan LAB-CO02 ditambahkan untuk merealisasikan proses pengajuan dan pengembalian.                                          |

<!-- Pertanyaan Terbuka -->

Beberapa hal berikut masih membutuhkan klarifikasi:

- Berapa lama batas waktu peminjaman peralatan?
- Bagaimana sistem menentukan keterlambatan pengembalian?
- Apakah keterlambatan akan dikenai denda atau sanksi?
- Bagaimana tindak lanjut terhadap peralatan yang mengalami kerusakan?

Pertanyaan tersebut belum menjadi aturan sistem dan perlu dibahas pada tahap analisis kebutuhan berikutnya.

 <!-- Kesimpulan -->

Model Pertemuan 4 dikembangkan dengan menambahkan generalization aktor, rincian pengelolaan inventaris, pencatatan pengembalian, dan collaboration. Fungsi yang telah dibuat pada Pertemuan 3 tetap digunakan agar diagram bersifat kumulatif.

Penerapan relasi UML yang tepat diharapkan menghasilkan diagram yang konsisten, mudah dipahami, dan mampu mewakili kebutuhan sistem peminjaman peralatan laboratorium.
