# Laporan Singkat Pertemuan 6: Activity Diagram


|---        |---                                                                       |
| Nama      | Sofwan Robyansah Nur Zaman                                               |
| NIM       | 2406111                                                                  |
| Praktikum | Analisis dan Desain Berorientasi Objek (IFRWP5149)                       |
| Pertemuan | 6                                                                        |
| Topik     | Activity Diagram (LAB dan SIA: Input Nilai Mata Kuliah sampai Lihat KHS) |

## 1. Tujuan Pembelajaran

<!-- TODO: samakan dengan butir tujuan pembelajaran pada jobsheet P06 -->

1. Memahami unsur activity diagram: initial node, action, decision dan merge, fork dan join, activity final node, serta swimlane.
2. Menurunkan activity diagram dari tabel skenario use case yang disusun pada Pertemuan 5.
3. Menggambarkan alur bersyarat dengan decision, guard, dan merge, serta alur paralel dengan fork dan join.
4. Menempatkan setiap action pada swimlane aktor yang melakukannya.
5. Memeriksa kelengkapan dan kebenaran diagram memakai checklist penilaian.

## 2. Hasil Pengerjaan

<!-- TODO: isi dengan hasil pengerjaan praktikum terbimbing (bagian LAB), sesuai Tugas 1 dan 2 pada jobsheet -->

| Bagian | Diagram | Berkas                          | Keterangan            |
|--------|---------|---------------------------------|-----------------------|
| LAB    | ...     | `04_model_analisis/P06/LAB/...` | ...                   |

## 3. Hasil Tugas Mandiri

Tugas : menyusun satu activity diagram utuh untuk proses **Input Nilai Mata Kuliah sampai Lihat KHS** pada Sistem Informasi Akademik (SIA), diturunkan dari tabel skenario SIA-UC08 dan SIA-UC09.

### 3.1 Diagram

![Activity Diagram SIA: Input Nilai sampai Lihat KHS](../04_model_analisis/P06/SIA/P06_2406111_SIA_activity_v01.png)

### 3.2 Ringkasan Alur

1. Dosen memasukkan nilai mata kuliah.
2. Sistem menyimpan nilai, lalu memeriksa kelengkapannya (decision "Nilai sudah lengkap?").
3. Guard **[belum lengkap]**: Dosen melengkapi nilai, lalu alur bergabung kembali lewat merge.
4. Guard **[lengkap]**: Admin Akademik memeriksa dan mengesahkan nilai.
5. Sistem menyiapkan publikasi hasil studi.
6. Fork membagi alur menjadi dua proses paralel: menerbitkan KHS pada portal akademik dan mengirim pemberitahuan hasil studi kepada mahasiswa.
7. Join menyatukan kedua proses, lalu Mahasiswa melihat KHS.
8. Alur berakhir pada activity final node.

### 3.3 Pemenuhan Ketentuan Tugas

| Unsur wajib    | Pemenuhan pada diagram |
|----------------|---                                                                                                                                     |
| Proses         | Input Nilai Mata Kuliah sampai Lihat KHS                                                                                               |
| Swimlane       | Empat lane: Dosen, Admin Akademik, Sistem, Mahasiswa                                                                                   |
| Decision       | "Nilai sudah lengkap?" dengan guard [lengkap] dan [belum lengkap]; cabang [belum lengkap] kembali ke Dosen, lalu bergabung lewat merge |
| Fork dan join  | Satu pasang setelah nilai disahkan, sebelum Mahasiswa melihat KHS                                                                      |
| Awal dan akhir | Satu initial node dan satu activity final node                                                                                         |
| Keterlacakan   | Lihat tabel 3.4                                                                                                                        |

### 3.4 Keterlacakan Action ke Skenario P05

<!-- TODO: lengkapi kolom sumber dengan nomor langkah pada tabel SIA-UC08 dan SIA-UC09 milik sendiri, lalu samakan nama action dengan bunyi langkahnya -->

| Action                                              | Swimlane       | Sumber langkah        |
|-----------------------------------------------------|----------------|-----------------------|
| Memasukkan nilai mata kuliah                        | Dosen          | SIA-UC08, langkah ... |
| Menyimpan nilai                                     | Sistem         | SIA-UC08, langkah ... |
| Melengkapi nilai mata kuliah yang belum lengkap     | Dosen          | SIA-UC08, langkah ... |
| Memeriksa dan mengesahkan nilai                     | Admin Akademik | SIA-UC08, langkah ... |
| Menyiapkan publikasi hasil studi                    | Sistem         | SIA-UC09, langkah ... |
| Menerbitkan KHS pada portal akademik                | Sistem         | SIA-UC09, langkah ... |
| Mengirim pemberitahuan hasil studi kepada mahasiswa | Sistem         | SIA-UC09, langkah ... |
| Melihat KHS                                         | Mahasiswa      | SIA-UC09, langkah ... |

### 3.5 Artefak

Folder `04_model_analisis/P06/SIA`:

- `P06_2406111_SIA_activity_v01.drawio`
- `P06_2406111_SIA_activity_v01.png`

## 4. Ceklis Kelengkapan Diagram

Keterangan: ✓ terpenuhi, ✗ belum, – tidak berlaku. Kolom LAB diisi setelah diagram LAB diperiksa.

| No| Butir pemeriksaan | SIA | LAB |
|---|---|---|---|
| 1 | Tepat satu initial node dan minimal satu activity final node; tidak ada action yang terputus dari alur | ✓ | ... |
| 2 | Setiap decision punya guard pada semua alur keluaran; guard saling lepas dan bersama menutup semua kemungkinan | ✓ | ... |
| 3 | Setiap cabang decision kembali melalui merge atau bermuara ke activity final node dengan keadaan akhir yang jelas | ✓ | ... |
| 4 | Fork selalu berpasangan dengan join; proses paralel disatukan oleh join, bukan oleh merge | ✓ | ... |
| 5 | Setiap action berada pada swimlane aktor yang melakukannya; respons sistem berada pada swimlane Sistem | ✓ | ... |
| 6 | Setiap action tertelusur ke langkah tabel skenario Pertemuan 5 dan namanya sama dengan bunyi langkah sumbernya | ✗ (cocokkan nama action) | ... |
| 7 | Include digambar sebagai action wajib pada alur utama; extend digambar sebagai cabang bersyarat dengan condition yang sama | – | ... |
| 8 | Unsur proses baru (Tahap 5) diberi keterangan sebagai unsur baru, tidak diklaim berasal dari Pertemuan 3, 4, atau 5 | – | ... |
| 9 | Collaboration tidak digambar sebagai action atau sebagai swimlane | ✓ | ... |

## 5. Kendala dan Catatan

<!-- TODO: tulis kendala yang benar-benar dialami saat mengerjakan -->

-