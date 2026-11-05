 <!-- P04_SIA_kebutuhan_v01 — Sistem Informasi Akademik: Layanan Hasil Studi -->


<!-- Skenario -->

Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa: menambah data mahasiswa baru, mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh collaboration yang bersesuaian.

Skenario ini fiktif untuk praktikum dan diagramnya kumulatif (jadwal kuliah P02 + KRS P03 + hasil studi P04).

<!-- Kebutuhan Pertemuan 4 -->
 
| ID      | Kebutuhan                                                                                           |
|----     |-----------                                                                                          |
| SIA-R07 | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik.                    |
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya.                                             |
| SIA-R09 | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan.                      |
| SIA-R10 | Admin Akademik dapat mengelola data mahasiswa.                                                      |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa. |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS.          |

Kebutuhan SIA-R01 s.d. SIA-R02 (Pertemuan 2) dan SIA-R03 s.d. SIA-R06 (Pertemuan 3) tetap berlaku dan tidak disalin ulang; rujuk ke jobsheet/berkas P02 dan P03.

<!-- Batas dan asumsi -->

- Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01, SIA-R02 (P02) serta SIA-R03 s.d. SIA-R06 (P03) tetap berbeda identitas.
- Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
- Kalender akademik adalah agenda resmi institusi (awal semester, batas KRS, masa ujian, dan sejenisnya), bukan jadwal kuliah pada P02.
- Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai yang diinput belum terpublikasi sebelum dinyatakan resmi; KHS hanya menampilkan nilai yang sudah dipublikasikan.
- Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data akademik aktif (ketentuan fiktif untuk latihan).
- Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari P03. Pembayaran dan perancangan basis data di luar tugas ini.

<!-- Pertanyaan terbuka -->

Belum dimodelkan dan tidak dianggap selesai:

1. Rentang nilai yang sah belum ditetapkan pada tugas (skala dan batas minimum/maksimum). Deskripsi use case hanya menyebut "rentang yang sah".
2. Mekanisme dan pihak yang mempublikasikan nilai (kapan nilai berubah dari belum terpublikasi menjadi terpublikasi) belum dimodelkan.
3. Definisi "data akademik aktif" pada Hapus Data Mahasiswa belum dirinci (misalnya KRS berjalan atau nilai tersimpan).
4. Perubahan nilai setelah diinput (koreksi nilai) belum dimodelkan.

<!-- Uji konsistensi (Langkah 8) -->

<!-- Situasi A — Mahasiswa melihat kalender akademik tanpa garis asosiasi langsung -->

Tetap benar menurut diagram. Asosiasi ke SIA-UC07 Lihat Kalender Akademik digambar satu kali dari aktor umum Civitas Akademika. Mahasiswa adalah aktor khusus dari Civitas Akademika (panah generalization menuju Civitas Akademika), sehingga mewarisi seluruh asosiasi aktor umum. Menggambar ulang garis dari Mahasiswa akan menjadi asosiasi warisan yang digambar ulang dan melanggar checklist.

<!-- Situasi B — Dosen yang bukan pengampu mencoba menginput nilai -->

Menurut deskripsi SIA-UC08 Input Nilai Mata Kuliah, prasyarat tidak terpenuhi (dosen bukan pengampu). Sistem menolak penginputan dan menampilkan pesan bahwa dosen tidak berhak atas mata kuliah tersebut (alur alternatif A1). Pascakondisi gagal berlaku: tidak ada nilai yang tersimpan dan data nilai tidak berubah.

<!-- Situasi C — Admin Akademik menghapus data mahasiswa yang masih memiliki data akademik aktif -->

Menurut aturan tugas, Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data akademik aktif. Sistem menolak penghapusan dan menampilkan alasannya; data mahasiswa tetap tersimpan tanpa perubahan.

<!-- Ketertelusuran elemen baru -->

| Elemen baru | Sumber kebutuhan |
|-------------|------------------|
| Aktor Civitas Akademika (umum), Dosen; generalization aktor | SIA-R07 |
| SIA-UC07 Lihat Kalender Akademik | SIA-R07 |
| SIA-UC08 Input Nilai Mata Kuliah | SIA-R08 |
| SIA-UC09 Lihat KHS | SIA-R09 |
| SIA-UC10 Kelola Data Mahasiswa | SIA-R10 |
| SIA-UC11, SIA-UC12, SIA-UC13 + generalization use case | SIA-R10, SIA-R11 |
| SIA-CO01, SIA-CO02 + realization | SIA-R12 |

<!-- Hasil review (diisi setelah review rekan/asisten) -->

- Temuan: _(isi)_
- Perbaikan pada v02: _(isi bila ada)_