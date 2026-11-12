<!-- : Sistem Informasi Akademik, Activity Diagram Input Nilai sampai Lihat KHS -->

Tugas ini berbeda dari tugas Pertemuan 2 (diagram jadwal kuliah), Pertemuan 3 (pengajuan KRS), Pertemuan 4 (diagram use case Layanan Hasil Studi), dan Pertemuan 5 (penulisan skenario). Pada tugas ini Anda menggambar activity diagram dari tabel skenario SIA yang Anda susun sendiri pada Pertemuan 5. Tidak ada contoh jawaban pada jobsheet ini

# a. Tujuan dan cakupan

Tujuan tugas: menyusun satu activity diagram utuh untuk proses Input Nilai Mata Kuliah sampai Lihat KHS yang memenuhi ketentuan berikut.

| Unsur wajib   | Ketentuan                                                                                                                                          |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Proses        | Input Nilai Mata Kuliah sampai Lihat KHS, diturunkan dari tabel skenario SIA-UC08 dan SIA-UC09 yang Anda susun pada Pertemuan 5                    |
| Swimlane      | Empat swimlane, satu untuk setiap aktor utama: Dosen, Sistem, Admin Akademik, Mahasiswa                                                            |
| Decision      | Minimal satu decision kelengkapan nilai dengan guard [lengkap] dan [belum lengkap]; cabang [belum lengkap] kembali ke Dosen untuk melengkapi nilai, lalu bergabung kembali melalui merge                                                                                                                                 |
| Fork dan join | Satu pasang fork dan join setelah nilai disahkan: Menerbitkan KHS pada portal akademik dan Mengirim pemberitahuan hasil studi kepada mahasiswa berjalan paralel, lalu disatukan sebelum Mahasiswa melihat KHS                                                                                                       |
| Awal dan akhir| Tepat satu initial node dan tepat satu activity final node                                                                                         |
| Keterlacakan  | Setiap action dapat ditunjuk sumber langkahnya pada tabel skenario SIA Pertemuan 5 Anda sendiri                                                    |