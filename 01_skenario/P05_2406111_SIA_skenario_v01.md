<!-- P05_2406111_SIA_skenario_v01 — Skenario Use Case SIA: Layanan Hasil Studi (SIA-UC07 s.d. SIA-UC13) -->

Tugas ini melanjutkan kasus SIA Pertemuan 4. Diagram acuan adalah `P04_2406111_SIA_usecase_v01.drawio` (tidak diubah) dan kebutuhan acuannya SIA-R07 sampai SIA-R12 (Jobsheet Pertemuan 4, Tabel 4.6). Tidak ada aktor, use case, atau kebutuhan baru.

<!-- Indeks tabel skenario SIA -->

| ID       | Nama use case           | Aktor             | Catatan pemetaan                                                                      |
|----------|-------------------------|-----------------  |---------------------------------------------------------------------------------------|
| SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika | Ditulis satu kali atas nama Civitas Akademika; berlaku untuk Mahasiswa dan Dosen      |
| SIA-UC08 | Input Nilai Mata Kuliah | Dosen       | Prasyarat dosen pengampu; alternatif nilai di luar rentang ditolak; direalisasikan SIA-CO01 |
| SIA-UC09 | Lihat KHS               | Mahasiswa | Hanya nilai yang sudah dipublikasikan yang ditampilkan; direalisasikan SIA-CO02               |
| SIA-UC10 | Kelola Data Mahasiswa   | Admin Akademik | Skenario umum pengelolaan; langkah bersama dirujuk UC11, UC12, UC13                      |
| SIA-UC11 | Tambah Data Mahasiswa   | Admin Akademik | Khusus dari UC10; pembeda: data mahasiswa baru tersimpan                                 |
| SIA-UC12 | Ubah Data Mahasiswa     | Admin Akademik | Khusus dari UC10; pembeda: data mahasiswa berubah                                        |
| SIA-UC13 | Hapus Data Mahasiswa    | Admin Akademik | Khusus dari UC10; pembeda: data mahasiswa terhapus; syarat tidak ada data akademik aktif |

 <!-- Tabel S.1 Skenario Use Case SIA-UC07 Lihat Kalender Akademik -->

| Bagian        | Isi                                                                                                                           |
|---------------|-------------------------------------------------------------------------------------------------------------------------------|
| Nama use case | SIA-UC07 Lihat Kalender Akademik                                                                                              |
| Aktor         | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen)                                                                         |
| Tujuan        | Civitas Akademika dapat mengetahui agenda resmi kalender akademik                                                             |
| Deskripsi     | Civitas Akademika membuka fungsi kalender akademik, memilih periode akademik, dan melihat agenda resmi institusi pada periode tersebut. Skenario ditulis satu kali dan berlaku sama untuk Mahasiswa dan Dosen                                                                  |

| Kegiatan | Respon sistem |
|---|---|
| **Skenario Normal** | |
| 1. Civitas Akademika membuka fungsi Lihat Kalender Akademik | |
| | 2. Sistem menampilkan daftar periode akademik |
| 3. Civitas Akademika memilih periode akademik | |
| | 4. Sistem menampilkan kalender akademik periode tersebut berisi agenda resmi, yaitu awal semester, batas KRS, dan masa ujian |
| **Skenario Alternative** | |
| 5. Kalender akademik periode yang dipilih belum tersedia (cabang dari langkah 4) | |
| | 6. Sistem menampilkan pesan kalender akademik periode tersebut belum tersedia |
| **Skenario Akhir** | Use case selesai jika kalender akademik periode yang dipilih ditampilkan; jika kalender belum tersedia, use case selesai dengan pesan tersebut. |

Catatan aktor: Mahasiswa dan Dosen adalah aktor khusus dari Civitas Akademika dan mewarisi use case ini. Tidak ada perbedaan perilaku antara Mahasiswa dan Dosen, sehingga tidak ada tabel terpisah untuk keduanya. Use case ini tidak mempunyai include, extend, maupun collaboration.

<!-- Tabel S.2 Skenario Use Case SIA-UC08 Input Nilai Mata Kuliah -->

| Bagian | Isi |
|---|---|
| Nama use case | SIA-UC08 Input Nilai Mata Kuliah |
| Aktor | Dosen |
| Tujuan | Nilai mata kuliah mahasiswa tersimpan oleh dosen pengampu |
| Deskripsi | Dosen memilih mata kuliah yang diampunya, mengisi nilai mahasiswa, dan menyimpan nilai tersebut. Prasyarat: dosen adalah pengampu mata kuliah terpilih dan masa perkuliahan mata kuliah telah berakhir |

| Kegiatan | Respon sistem |
|---|---|
| **Skenario Normal** | |
| 1. Dosen membuka fungsi Input Nilai Mata Kuliah | |
| | 2. Sistem menampilkan daftar mata kuliah yang masa perkuliahannya telah berakhir |
| 3. Dosen memilih mata kuliah | |
| | 4. Sistem memeriksa bahwa dosen adalah pengampu mata kuliah tersebut dan menampilkan daftar mahasiswa peserta |
| 5. Dosen mengisi nilai untuk mahasiswa | |
| | 6. Sistem memeriksa bahwa nilai berada dalam rentang yang sah |
| 7. Dosen menyimpan nilai | |
| | 8. Sistem menyimpan nilai dengan status belum dipublikasikan dan menampilkan ringkasan nilai yang tersimpan |
| **Skenario Alternative** | |
| 9. Dosen bukan pengampu mata kuliah yang dipilih (cabang dari langkah 4) | |
| | 10. Sistem menolak penginputan dan menampilkan pesan bahwa dosen tidak berhak atas mata kuliah tersebut |
| 11. Nilai yang diisi berada di luar rentang yang sah (cabang dari langkah 6) | |
| | 12. Sistem menolak nilai tersebut dan meminta dosen memperbaiki isian nilai |
| **Skenario Akhir** | Use case selesai jika nilai tersimpan dengan status belum dipublikasikan; jika dosen bukan pengampu, tidak ada nilai yang tersimpan; jika nilai di luar rentang yang sah, nilai tidak tersimpan sampai isian diperbaiki. |

Keterangan tabel: use case ini direalisasikan oleh collaboration SIA-CO01 Input Nilai Mata Kuliah. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Rentang nilai yang sah belum ditetapkan pada tugas.

<!-- Tabel S.3 Skenario Use Case SIA-UC09 Lihat KHS -->

| Bagian | Isi |
|---|---|
| Nama use case | SIA-UC09 Lihat KHS |
| Aktor | Mahasiswa |
| Tujuan | Mahasiswa mengetahui hasil studi semester yang nilainya sudah dipublikasikan |
| Deskripsi | Mahasiswa membuka fungsi Lihat KHS, memilih semester, dan melihat KHS yang hanya memuat nilai yang sudah dipublikasikan |

| Kegiatan | Respon sistem |
|---|---|
| **Skenario Normal** | |
| 1. Mahasiswa membuka fungsi Lihat KHS | |
| | 2. Sistem menampilkan daftar semester |
| 3. Mahasiswa memilih semester | |
| | 4. Sistem menampilkan KHS semester tersebut yang hanya memuat nilai yang sudah dipublikasikan |
| **Skenario Alternative** | |
| 5. Belum ada nilai yang dipublikasikan pada semester yang dipilih (cabang dari langkah 4) | |
| | 6. Sistem tidak menampilkan KHS dan menampilkan pemberitahuan bahwa belum ada nilai yang dipublikasikan pada semester tersebut |
| **Skenario Akhir** | Use case selesai jika KHS semester terpilih ditampilkan dengan nilai yang sudah dipublikasikan; jika belum ada nilai terpublikasi, tidak ada KHS yang ditampilkan dan use case selesai dengan pemberitahuan. |

Keterangan tabel: use case ini direalisasikan oleh collaboration SIA-CO02 Lihat KHS. Collaboration tersebut tidak mempunyai langkah kegiatan pada tabel ini. Nilai yang belum dipublikasikan tidak pernah ditampilkan pada KHS.

<!-- Tabel S.4 Skenario Use Case SIA-UC10 Kelola Data Mahasiswa -->

| Bagian | Isi |
|---|---|
| Nama use case | SIA-UC10 Kelola Data Mahasiswa |
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa terkelola melalui satu fungsi pengelolaan bersama |
| Deskripsi | Admin Akademik membuka fungsi pengelolaan data mahasiswa, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing |

| Kegiatan | Respon sistem |
|---|---|
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Kelola Data Mahasiswa | |
| | 2. Sistem menampilkan daftar data mahasiswa |
| 3. Admin Akademik memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus | |
| | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih |
| 5. Admin Akademik mengisi atau mengonfirmasi data mahasiswa | |
| | 6. Sistem memeriksa kelengkapan dan keabsahan data |
| 7. Admin Akademik menyimpan perubahan | |
| | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 9. Data tidak lengkap atau tidak sah (cabang dari langkah 6) | |
| | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

Keterangan tabel: use case umum bagi SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa. Tabel ini memuat perilaku bersama; ketiga use case khusus hanya memuat perilaku pembeda dan merujuk ke tabel ini.

<!-- Tabel S.5 Skenario Use Case SIA-UC11 Tambah Data Mahasiswa -->

| Bagian | Isi |
|---|---|
| Nama use case | SIA-UC11 Tambah Data Mahasiswa |
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa baru tersimpan sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik mengisi data mahasiswa baru, yaitu NIM, nama, dan program studi, lalu menyimpan data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem |
|---|---|
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Tambah Data Mahasiswa | |
| | 2. Sistem menampilkan formulir data mahasiswa baru |
| 3. Admin Akademik mengisi NIM, nama, dan program studi mahasiswa baru | |
| | 4. Sistem memeriksa kelengkapan data |
| 5. Admin Akademik menyimpan data | |
| | 6. Sistem menyimpan data mahasiswa baru dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data tidak lengkap (cabang dari langkah 4) | |
| | 8. Sistem menolak penyimpanan dan meminta Admin Akademik melengkapi data |
| **Skenario Akhir** | Use case selesai jika data mahasiswa baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa baru tersimpan. Langkah bersama mengikuti Tabel skenario SIA-UC10.

<!-- Tabel S.6 Skenario Use Case SIA-UC12 Ubah Data Mahasiswa -->

| Bagian | Isi |
|---|---|
| Nama use case | SIA-UC12 Ubah Data Mahasiswa |
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa berubah sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik memilih data mahasiswa, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem |
|---|---|
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan diubah | |
| | 2. Sistem menampilkan data mahasiswa saat ini |
| 3. Admin Akademik mengubah data mahasiswa | |
| | 4. Sistem memeriksa perubahan data |
| 5. Admin Akademik menyimpan perubahan | |
| | 6. Sistem menyimpan data yang diubah dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data mahasiswa tidak ditemukan (cabang dari langkah 2) | |
| | 8. Sistem menampilkan pesan data mahasiswa tidak ditemukan |
| 9. Data hasil perubahan tidak lengkap atau tidak sah (cabang dari langkah 4) | |
| | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak ditemukan atau data hasil perubahan tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa berubah. Langkah bersama mengikuti Tabel skenario SIA-UC10.

<!-- Tabel S.7 Skenario Use Case SIA-UC13 Hapus Data Mahasiswa -->

| Bagian | Isi |
|---|---|
| Nama use case | SIA-UC13 Hapus Data Mahasiswa |
| Aktor | Admin Akademik |
| Tujuan | Data mahasiswa terhapus sebagai bentuk khusus dari pengelolaan data mahasiswa |
| Deskripsi | Admin Akademik memilih data mahasiswa, mengonfirmasi penghapusan, dan sistem menghapus data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem |
|---|---|
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan dihapus | |
| | 2. Sistem memeriksa bahwa mahasiswa tidak memiliki data akademik aktif |
| 3. Admin Akademik mengonfirmasi penghapusan | |
| | 4. Sistem menghapus data mahasiswa dan menampilkan konfirmasi penghapusan |
| **Skenario Alternative** | |
| 5. Mahasiswa memiliki data akademik aktif (cabang dari langkah 2) | |
| | 6. Sistem menolak penghapusan dan menampilkan pesan alasan penolakan, yaitu mahasiswa masih memiliki data akademik aktif |
| **Skenario Akhir** | Use case selesai jika data mahasiswa terhapus; jika mahasiswa memiliki data akademik aktif, data tidak terhapus dan tetap tersimpan tanpa perubahan. |

Keterangan: use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa terhapus, dengan syarat mahasiswa tidak memiliki data akademik aktif. Langkah bersama mengikuti Tabel skenario SIA-UC10.

<!-- Pemeriksaan checklist C.4 dan penelusuran relasi -->

| No. | Kode Use Case | Nama Use Case | Relasi yang ditelusur (diagram P04) | Checklist C.4 |
|---|---|---|---|---|
| 1 | SIA-UC07 | Lihat Kalender Akademik | Association Civitas Akademika ke UC07; Generalization Mahasiswa dan Dosen ke Civitas Akademika (skenario satu kali) | Terpenuhi |
| 2 | SIA-UC08 | Input Nilai Mata Kuliah | Association Dosen ke UC08; Realization SIA-CO01 ke UC08 (hanya di keterangan) | Terpenuhi |
| 3 | SIA-UC09 | Lihat KHS | Association Mahasiswa ke UC09; Realization SIA-CO02 ke UC09 (hanya di keterangan) | Terpenuhi |
| 4 | SIA-UC10 | Kelola Data Mahasiswa | Association Admin Akademik ke UC10; UC10 sebagai use case umum (generalization dari UC11, UC12, UC13) | Terpenuhi |
| 5 | SIA-UC11 | Tambah Data Mahasiswa | Generalization UC11 ke UC10 (hanya perilaku pembeda, rujuk ke tabel UC10) | Terpenuhi |
| 6 | SIA-UC12 | Ubah Data Mahasiswa | Generalization UC12 ke UC10 (hanya perilaku pembeda, rujuk ke tabel UC10) | Terpenuhi |
| 7 | SIA-UC13 | Hapus Data Mahasiswa | Generalization UC13 ke UC10 (hanya perilaku pembeda, rujuk ke tabel UC10) | Terpenuhi |

Butir yang diperiksa: field lengkap; satu aksi per langkah dengan penomoran berlanjut; kolom Kegiatan hanya aksi aktor dan kolom Respon sistem hanya tanggapan sistem; data dan status disebut eksplisit; generalization aktor dan use case diterapkan; collaboration hanya di keterangan; setiap tabel punya Skenario Alternative dan Skenario Akhir; nama, ID, dan aktor sama dengan diagram. Kebutuhan: UC07 (SIA-R07), UC08 (R08, R12), UC09 (R09, R12), UC10 (R10), UC11 sampai UC13 (R10, R11).

Logbook singkat

- Tabel skenario SIA-UC07 sampai SIA-UC13 (7 tabel) sudah ditulis dan diperiksa terhadap checklist C.4 dan diagram SIA Pertemuan 4.
- Diagram P04 tidak diubah.
- Tabel studi kasus LAB (12 tabel) ditelaah pada lembar `P05_2406111_LAB_skenario_v01.md`.
