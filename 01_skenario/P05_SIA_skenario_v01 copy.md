
<!-- Deskripsi Skenario -->

Skenario ini fiktif dan dibuat untuk keperluan praktikum. Isinya berbeda dari tugas pertemuan sebelumnya (jadwal kuliah dan pengajuan rencana studi).

Mahasiswa dan dosen sama-sama tergabung dalam Civitas Akademik, sehingga keduanya dapat membuka kalender akademik dan jadwal kuliah. Setelah masa perkuliahan selesai, dosen memasukkan nilai untuk mata kuliah yang ia ampu. Sistem menghitung nilai akhir dari komponen nilai yang dimasukkan. Mahasiswa kemudian membuka transkrip nilai untuk semester yang nilainya sudah dipublikasikan, dan dapat mengunduhnya dalam bentuk PDF bila diperlukan. Staf Akademik mengelola data mahasiswa, yaitu menambah, mengubah, dan menghapus data. Dosen PA memverifikasi rencana studi yang disusun mahasiswa.

Dua use case utama, **Input Nilai Mata Kuliah** dan **Lihat Transkrip Nilai**, masing-masing direalisasikan oleh sebuah collaboration.

<!-- 2. Asumsi dan Batasan -->

- Kode kebutuhan dimulai dari **SLA-R01** dan seluruh penomoran memakai awalan **SLA** agar berbeda dari tugas sebelumnya.
- Pengguna sudah terautentikasi dan memiliki hak akses sesuai perannya.
- Kalender akademik adalah agenda resmi institusi (awal semester, batas penyusunan rencana studi, masa ujian, dan sejenisnya). Kalender ini tidak sama dengan jadwal kuliah.
- Nilai hanya boleh dimasukkan oleh dosen pengampu mata kuliah yang bersangkutan. Nilai yang baru dimasukkan berstatus belum dipublikasikan, dan transkrip hanya menampilkan nilai yang sudah dipublikasikan.
- Data mahasiswa hanya boleh dihapus jika mahasiswa tersebut tidak memiliki data akademik aktif. Ketentuan ini fiktif untuk latihan.
- Penyusunan rencana studi tetap digambar sebagai bagian dari diagram kumulatif. Pembayaran dan perancangan basis data berada di luar cakupan tugas.

<!-- Daftar Aktor -->

| Aktor | Kedudukan | Tujuan terhadap sistem |
|---|---|---|
| Civitas Akademik | Umum (general) | Peran umum bagi pengguna akademik. Mewariskan fungsinya kepada Mahasiswa dan Dosen. |
| Mahasiswa | Khusus dari Civitas Akademik | Melihat kalender akademik dan jadwal kuliah (diwarisi), serta menyusun rencana studi, mencetak buktinya, dan melihat transkrip nilai sebagai fungsi khusus. |
| Dosen | Khusus dari Civitas Akademik | Melihat kalender akademik dan jadwal kuliah (diwarisi), serta memasukkan nilai mata kuliah sebagai     fungsi khusus. |
| Dosen PA | Aktor tersendiri | Memverifikasi rencana studi mahasiswa bimbingannya. |
| Staf Akademik | Aktor tersendiri | Mengelola jadwal kuliah dan data mahasiswa. |

<!-- Daftar Use Case -->

| ID       | Nama use case             |  Peran dalam model                               | Sumber kebutuhan |
|----------|---------------------------|--------------------------------------------------|------------------|
| SLA-UC01 | Lihat Jadwal Kuliah       | Fungsi aktor umum Civitas Akademik               | SLA-R01          |
| SLA-UC02 | Lihat Kalender Akademik   | Fungsi aktor umum Civitas Akademik               | SLA-R02          |
| SLA-UC03 | Susun Rencana Studi       | Fungsi khusus Mahasiswa                          | SLA-R03          |
| SLA-UC04 | Cek Prasyarat Mata Kuliah | Perilaku yang disertakan (include) oleh SLA-UC03 | SLA-R04          |
| SLA-UC05 | Cetak Bukti Rencana Studi | Tambahan bersyarat (extend) pada SLA-UC03        | SLA-R05          |
| SLA-UC06 | Lihat Transkrip Nilai     | Fungsi khusus Mahasiswa; direalisasikan SLA-CO02 | SLA-R06, SLA-R12 |
| SLA-UC07 | Unduh Transkrip (PDF)     | Tambahan bersyarat (extend) pada SLA-UC06        | SLA-R07          |
| SLA-UC08 | Input Nilai Mahasiswa     | Fungsi khusus Dosen; direalisasikan SLA-CO01     | SLA-R08, SLA-R12 |
| SLA-UC09 | Hitung Nilai Akhir        | Perilaku yang disertakan (include) oleh SLA-UC08 | SLA-R09          |
| SLA-UC10 | Verifikasi Rencana Studi  | Fungsi utama Dosen PA                            | SLA-R10          |
| SLA-UC11 | Kelola Data Mahasiswa     | Use case UMUM bagi SLA-UC12, SLA-UC13, SLA-UC14  | SLA-R11          |
| SLA-UC12 | Tambah Data               | Use case KHUSUS dari SLA-UC11                    | SLA-R13          |
| SLA-UC13 | Ubah Data                 | Use case KHUSUS dari SLA-UC11                    | SLA-R13          |
| SLA-UC14 | Hapus Data                | Use case KHUSUS dari SLA-UC11                    | SLA-R13          |
| SLA-UC15 | Kelola Jadwal Kuliah      | Fungsi utama Staf Akademik                       | SLA-R14          |

<!-- Keputusan Generalization Aktor -->

Mahasiswa dan Dosen adalah bentuk khusus dari Civitas Akademik.

**Alasan:** keduanya memiliki fungsi yang sama, yaitu melihat jadwal kuliah (SLA-UC01) dan kalender akademik (SLA-UC02). Asosiasi ke kedua use case itu cukup digambar satu kali, yaitu dari Civitas Akademik. Asosiasi ke fungsi yang spesifik, seperti Susun Rencana Studi atau Input Nilai, digambar langsung dari masing-masing aktor khusus.

 <!-- Keputusan Generalization Use Case -->

SLA-UC12, SLA-UC13, dan SLA-UC14 adalah bentuk khusus dari SLA-UC11 Kelola Data Mahasiswa.

- **Tambah Data:** menghasilkan catatan mahasiswa baru di dalam sistem.
- **Ubah Data:** menghasilkan data mahasiswa dengan informasi yang sudah diperbarui.
- **Hapus Data:** menghasilkan data mahasiswa yang terhapus dari sistem, dengan syarat mahasiswa tersebut tidak memiliki data akademik aktif.

<!-- Daftar Collaboration -->

| ID       | Nama collaboration    | Use case yang direalisasikan    |
|----------|-----------------------|---------------------------------|
| SLA-CO01 | Input Nilai Mahasiswa | SLA-UC08: Input Nilai Mahasiswa |
| SLA-CO02 | Lihat Transkrip Nilai | SLA-UC06: Lihat Transkrip Nilai |

<!-- Spesifikasi Use Case -->

| Elemen                | SLA-UC08: Input Nilai Mahasiswa                                                                |
|-----------------------|------------------------------------------------------------------------------------------------|
| ID dan nama           | SLA-UC08: Input Nilai Mahasiswa                                                                |
| Sumber kebutuhan      | SLA-R08 dan SLA-R12                                                                            |
| Tujuan                | Nilai mahasiswa untuk suatu mata kuliah tercatat di dalam sistem                               |
| Aktor utama           | Dosen                                                                                          |
| Pemicu                | Dosen membuka menu input nilai dan memilih mata kuliah yang masa perkuliahannya sudah berakhir |
| Prasyarat             | Dosen sudah terautentikasi dan merupakan dosen pengampu mata kuliah tersebut                   |
| Pascakondisi berhasil | Nilai mata kuliah tersimpan di dalam sistem                                                    |
| Pascakondisi gagal    | Tidak ada nilai baru yang tersimpan (sistem menolak perubahan)                                 |
| Include               | SLA-UC09: Hitung Nilai Akhir                                                                   |
| Extend                | -                                                                                              |
| Collaboration         | SLA-CO01: Input Nilai Mahasiswa                                                                |
