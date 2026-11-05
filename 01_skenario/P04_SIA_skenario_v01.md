<!-- P04_SIA_skenario_v01 — Katalog, Generalization, Collaboration, dan Use Case Description -->

 <!-- Katalog aktor -->

| Aktor | Kedudukan | Tujuan terhadap sistem |
|-------|-----------|------------------------|
| Civitas Akademika | Umum (general), baru pada P04 | Peran umum bagi pengguna kampus. Mewariskan fungsi melihat kalender akademik kepada Mahasiswa dan Dosen. |
| Mahasiswa | Khusus dari Civitas Akademika | Melihat kalender akademik (diwarisi); ditambah fungsi miliknya sendiri, termasuk Lihat KHS dan fungsi lama P02/P03. |
| Dosen | Khusus dari Civitas Akademika, baru pada P04 | Melihat kalender akademik (diwarisi); ditambah menginput nilai mata kuliah. |
| Admin Akademik | Tetap dari pertemuan sebelumnya | Mengelola jadwal kuliah (SIA-UC02, P02) dan mengelola data mahasiswa (SIA-UC10, baru). |
| Dosen Wali | Tetap dari pertemuan sebelumnya | Memproses keputusan KRS (SIA-UC06), seperti P03 (cek P03). |
Mahasiswa, Admin Akademik, dan Dosen Wali tetap digambar seperti pada P03. Aktor baru: Civitas Akademika dan Dosen.

<!-- Katalog use case (gabungan) -->

| ID       | Nama use case                    | Aktor terkait            | Sumber kebutuhan | Tetap/Baru |
|----      |---------------                   |---------------           |------------------|------------|
| SIA-UC01 | Lihat Jadwal Kuliah              | Mahasiswa (cek P02)      | SIA-R01          | Tetap (P02) |
| SIA-UC02 | Kelola Jadwal Kuliah             | Admin Akademik (cek P02) | SIA-R02          | Tetap (P02) |
| SIA-UC03 | Ajukan KRS | Mahasiswa (cek P03) | SIA-R03                  | Tetap (P03); «include» SIA-UC04 |
| SIA-UC04 | Validasi KRS                     | —                        | SIA-R03 | Tetap (P03); perilaku yang disertakan |
| SIA-UC05 | Unduh Bukti Pengajuan KRS        | Mahasiswa (cek P03)      | SIA-R04 | Tetap (P03); «extend» ke SIA-UC03 |
| SIA-UC06 | Proses Keputusan KRS             | Dosen Wali (cek P03)     | SIA-R05/R06 | Tetap (P03) |
| SIA-UC07 | Lihat Kalender Akademik          | Civitas Akademika        | SIA-R07 | Baru |
| SIA-UC08 | Input Nilai Mata Kuliah          | Dosen                    | SIA-R08, SIA-R12 | Baru; direalisasikan SIA-CO01 |
| SIA-UC09 | Lihat KHS | Mahasiswa            | SIA-R09, SIA-R12         | Baru; direalisasikan SIA-CO02 |
| SIA-UC10 | Kelola Data Mahasiswa            | Admin Akademik           | SIA-R10 | Baru; use case UMUM bagi UC11, UC12, UC13 |
| SIA-UC11 | Tambah Data Mahasiswa            | (via UC10)               | SIA-R11 | Baru; KHUSUS dari SIA-UC10 |
| SIA-UC12 | Ubah Data Mahasiswa              | (via UC10)               | SIA-R11 | Baru; KHUSUS dari SIA-UC10 |
| SIA-UC13 | Hapus Data Mahasiswa             | (via UC10)               | SIA-R11 | Baru; KHUSUS dari SIA-UC10 |

<!-- Generalization aktor -->

- **Mahasiswa adalah bentuk khusus dari Civitas Akademika, dan Dosen adalah bentuk khusus dari Civitas Akademika.** Alasan: keduanya berbagi fungsi yang sama, yaitu melihat kalender akademik (SIA-R07), kesamaan itu berlaku seterusnya, dan nama peran umum membuat diagram lebih jelas.
- Fungsi yang diwarisi: SIA-UC07 Lihat Kalender Akademik.
- Asosiasi ke SIA-UC07 digambar **satu kali** dari Civitas Akademika. Tidak ada garis yang sama dari Mahasiswa maupun Dosen.
- Asosiasi khusus tetap digambar langsung: Dosen → SIA-UC08 Input Nilai Mata Kuliah; Mahasiswa → SIA-UC09 Lihat KHS (serta asosiasi lama P02/P03 milik Mahasiswa tidak berubah).
- Arah panah: segitiga kosong menempel pada Civitas Akademika, bukan pada Mahasiswa atau Dosen.

<!-- Generalization use case -->

Use case umum: **SIA-UC10 Kelola Data Mahasiswa**. Use case khusus:

| Use case khusus                | Perilaku pembeda                                                                                   |
|-----------------               |------------------                                                                                  |
| SIA-UC11 Tambah Data Mahasiswa | Menghasilkan data mahasiswa baru yang tersimpan.                                                   |
| SIA-UC12 Ubah Data Mahasiswa   | Menghasilkan data mahasiswa yang berubah.                                                          |
| SIA-UC13 Hapus Data Mahasiswa  | Menghasilkan data mahasiswa yang terhapus, hanya bila mahasiswa tidak memiliki data akademik aktif.|

Alasan: ketiganya sama-sama menghasilkan data mahasiswa yang terkelola. Admin Akademik cukup terhubung ke SIA-UC10 (satu asosiasi).

<!-- Collaboration dan realization -->

| ID       | Nama collaboration (sama dengan nama use case)  | Use case yang direalisasikan      |
|----      |-----------------------------------------------  |------------------------------     |
| SIA-CO01 | Input Nilai Mata Kuliah                         | SIA-UC08: Input Nilai Mata Kuliah |
| SIA-CO02 | Lihat KHS                                       | SIA-UC09: Lihat KHS                 |

Alasan: keduanya adalah use case utama pada potongan model hasil studi, sehingga realisasinya ditunjukkan eksplisit. Collaboration tidak terhubung ke aktor; arah realization dari collaboration menuju use case. Use case lain tidak diberi collaboration pada pertemuan ini.

 <!-- Use case description: SIA-UC08 Input Nilai Mata Kuliah -->

| Elemen                | SIA-UC08: Input Nilai Mata Kuliah                                                                                  |
|--------               |----------------------------------                                                                                 -|
| ID dan nama           | SIA-UC08: Input Nilai Mata Kuliah                                                                                  |
| Sumber kebutuhan      | SIA-R08 dan SIA-R12                                                                                                |
| Tujuan                | Nilai mata kuliah mahasiswa tersimpan oleh dosen pengampu                                                          |
| Aktor utama           | Dosen                                                                                                              |
| Pemicu                | Dosen memilih fungsi input nilai dan menentukan mata kuliah yang diampunya                                         | 
| Prasyarat             | Dosen telah terautentikasi; dosen adalah pengampu mata kuliah terpilih; masa perkuliahan mata kuliah telah berakhir|
| Pascakondisi berhasil | Nilai mahasiswa tersimpan untuk mata kuliah terpilih dengan status belum dipublikasikan                            |
| Pascakondisi gagal    | Tidak ada nilai baru yang tersimpan; data nilai tidak berubah                                                      |
| Generalization        | Tidak ada (tidak termasuk hierarki use case)                                                                       |
| Collaboration         | SIA-CO01: Input Nilai Mata Kuliah                                                                                  |
| Aturan bisnis/asumsi  | Hanya dosen pengampu yang boleh menginput nilai; nilai yang diinput belum dipublikasikan; rentang nilai sah                                    belum ditetapkan (lihat pertanyaan terbuka) |

<!-- Alur utama -->

| Langkah | Tindakan dosen                  | Respons sistem                                                               |
|---------|----------------                 |----------------                                                              |
| 1       | Memilih mata kuliah yang diampu | Menampilkan daftar mahasiswa peserta mata kuliah                             |
| 2       | Mengisi nilai untuk mahasiswa   | Menampung isian nilai                                                        |
| 3       | Tidak ada                       | Memeriksa bahwa dosen adalah pengampu dan nilai berada dalam rentang yang sah|
| 4       | Menyimpan nilai                 | Menyimpan nilai dengan status belum dipublikasikan                           |
| 5       | Melihat konfirmasi              | Menampilkan ringkasan nilai yang tersimpan                                   |

<!-- Alur alternatif atau pengecualian -->

- A1: Dosen bukan pengampu (pada langkah 3): sistem menolak penginputan dan menampilkan pesan bahwa dosen tidak berhak atas mata kuliah tersebut. Pascakondisi gagal berlaku.
- A2: Nilai di luar rentang yang sah (pada langkah 3): sistem menolak nilai tersebut dan meminta dosen memperbaiki isian; nilai tidak disimpan sampai berada dalam rentang yang sah. Pascakondisi gagal berlaku bila dosen membatalkan.

<!-- Use case description ringkas: SIA-UC09 Lihat KHS -->

| Elemen                | SIA-UC09: Lihat KHS                                                                                                           |
|--------               |---------------------                                                                                                          |
| ID dan nama           | SIA-UC09: Lihat KHS                                                                                                           |
| Sumber kebutuhan      | SIA-R09 dan SIA-R12                                                                                                           |
| Tujuan                | Mahasiswa mengetahui hasil studi semester yang nilainya sudah dipublikasikan                                                  |
| Aktor utama           | Mahasiswa                                                                                                                     |
| Pemicu                | Mahasiswa memilih fungsi Lihat KHS dan menentukan semester                                                                    |
| Prasyarat             | Mahasiswa telah terautentikasi                                                                                                |
| Alur ringkas          | Mahasiswa memilih semester; sistem menampilkan KHS yang **hanya memuat nilai yang sudah dipublikasikan**                      |
| Pascakondisi berhasil | KHS semester terpilih tampil dengan nilai yang sudah dipublikasikan                                                           |
| Pascakondisi gagal    | Tidak ada KHS yang ditampilkan bila belum ada nilai terpublikasi pada semester tersebut; sistem menampilkan pemberitahuan     |
| Generalization        | Tidak ada                                                                                                                     |
| Collaboration         | SIA-CO02: Lihat KHS                                                                                                           |

<!-- Tabel hubungan diagram yang harus ada (untuk dicocokkan saat menggambar) -->

Hubungan baru P04 (di luar hubungan P02/P03 yang tetap):

| Sumber                         | Hubungan         | Tujuan                           |
|--------                        |----------        |--------                          |
| Civitas Akademika              | Association      | SIA-UC07 Lihat Kalender Akademik |
| Dosen                          | Association      | SIA-UC08 Input Nilai Mata Kuliah |
| Mahasiswa                      | Association      | SIA-UC09 Lihat KHS               |
| Admin Akademik                 | Association      | SIA-UC10 Kelola Data Mahasiswa   |
| Mahasiswa                      | Generalization → | Civitas Akademika                |
| Dosen                          | Generalization → | Civitas Akademika                |
| SIA-UC11 Tambah Data Mahasiswa | Generalization → | SIA-UC10 Kelola Data Mahasiswa   |
| SIA-UC12 Ubah Data Mahasiswa   | Generalization → | SIA-UC10 Kelola Data Mahasiswa   |
| SIA-UC13 Hapus Data Mahasiswa  | Generalization → | SIA-UC10 Kelola Data Mahasiswa   |
| SIA-CO01 (collaboration)       | Realization →    | SIA-UC08                         |
| SIA-CO02 (collaboration)       | Realization →    | SIA-UC09                         |