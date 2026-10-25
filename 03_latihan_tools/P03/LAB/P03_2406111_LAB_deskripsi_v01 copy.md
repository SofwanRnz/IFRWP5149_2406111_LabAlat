<!-- SIA-UC01 — Ajukan KRS -->

Bagian	                Isi
ID dan nama	            SIA-UC01 Ajukan KRS
Sumber kebutuhan	    SIA-R03, SIA-R04, SIA-R05
Tujuan	                Menghasilkan pengajuan KRS yang tersimpan
Aktor utama     	    Mahasiswa
Aktor pendukung 	    –
Pemicu	                Mahasiswa memilih fungsi pengajuan KRS
Prasyarat	            Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia
Include	                SIA-UC02 — Validasi KRS (dipanggil pada langkah 4)
Extension point  	    Bukti pengajuan tersedia, pada langkah 6
Extend	                SIA-UC03 jika [mahasiswa memilih unduh bukti]
Pascakondisi berhasil	Pengajuan tersimpan dengan nomor dan status Menunggu persetujuan dosen wali
Pascakondisi gagal	    Tidak ada pengajuan baru yang berhasil tersimpan
Aturan bisnis/asumsi	Validasi gagal berarti pengajuan tidak tersimpan; unduh bukti bukan syarat keberhasilan; KRS tersimpanbelum berarti    disetujui

<!-- Alur Utama -->
Alur utama

|Langkah| Tindakan | mahasiswa |  Respons  |                                          sistem                                          |
|-------|----------|-----------|-----------|------------------------------------------------------------------------------------------|
|   1   | Membuka  | pengajuan |    KRS    |                    Menampilkan daftar mata kuliah yang dapat dipilih                     |
|   2   | Memilih  |   mata    |  kuliah   |                                    Menampung pilihan                                     |
|   3   | Mengirim | pengajuan | Memeriksa |                            ada tidaknya mata kuliah terpilih                             |
|   4   |    —     |Menjalankan| SIA-UC02  |                                      (Validasi KRS)                                      |
|   5   |    —     |   Jika    | validasi  |berhasil, menyimpan pengajuan berstatus Menunggu persetujuan dosen wali dan memberi nomor |
|   6   | Melihat  |konfirmasi |Menampilkan|                        nomor dan status; mencapai extension point                        |
|   7   |Mengakhiri| pengajuan |  Menutup  |                                     proses pengajuan                                     |

<!-- Alur alternatif/pengecualian -->
|                                                                                  Rujukan Kondisi Tindakan dan hasil                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                        3a Tidak ada mata kuliah dipilih Sistem meminta mahasiswa memilih; kembali ke langkah 2                                                        |
|5a Validasi gagal (hasil dari SIA-UC02) Sistem menampilkan alasan kegagalan dan tidak menyimpan. Mahasiswa memperbaiki pilihan (kembali ke langkah 2) atau membatalkan. Jika batal: pascakondisi gagal |
|                                                                                                                                                                                                       |
|                                           6a [Mahasiswa memilih unduh bukti] di extension point Menjalankan SIA-UC03. Setelah selesai, lanjut ke langkah 7                                            |
|                                                            6b Mahasiswa tidak memilih unduh Lanjut ke langkah 7; pengajuan tetap tersimpan                                                            |


|   Bagian   |                                                         Isi                                                         |
|------------|---------------------------------------------------------------------------------------------------------------------|
|     ID     |                                          dan nama SIA-UC02 — Validasi KRS                                           |
|   Sumber   |                                                  kebutuhan SIA-R04                                                  |
|   Tujuan   |                               Menentukan apakah KRS layak disimpan sebagai pengajuan                                |
|   Aktor    |                                         utama Mahasiswa (melalui SIA-UC01)                                          |
|   Aktor    |                                                     pendukung –                                                     |
|   Pemicu   |                                       SIA-UC01 langkah 4 (pengajuan dikirim)                                        |
| Prasyarat  |                      Ada pilihan mata kuliah; data mata kuliah, prasyarat, dan jadwal tersedia                      |
|    Alur    |                                             utama lihat tabel di bawah                                              |
|Pascakondisi|                                   berhasil Hasil “valid” dikembalikan ke SIA-UC01                                   |
|Pascakondisi|             gagal Hasil “tidak valid” beserta alasan dikembalikan ke SIA-UC01; tidak ada data tersimpan             |
|   Aturan   |bisnis/asumsi Ketiga pemeriksaan selalu dijalankan pada setiap pengajuan; tidak ada batas SKS atau aturan pembayaran |

|Langkah|Tindakan|   Respons   |              sistem              |
|-------|--------|-------------|----------------------------------|
|   1   |   —    |  Menerima   | daftar mata kuliah dari SIA-UC01 |
|   2   |   —    |  Memeriksa  |    kelengkapan data pengajuan    |
|   3   |   —    |  Memeriksa  |    prasyarat tiap mata kuliah    |
|   4   |   —    |  Memeriksa  |benturan jadwal antar mata kuliah |
|   5   |   —    |Mengembalikan|    hasil “valid” ke SIA-UC01     |












|                                                                                                                                                                      |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                       Situasi	                Diagram	Deskripsi	        Hasil                                                        |
|  a. Validasi berhasil,   tidak unduh bukti	        UC01 include UC02; extend tidak aktif	Alur utama 1–7, langkah 6b	Konsisten. Pengajuan tersimpan, status Menunggu  |
|b. Validasi gagal	    UC02 bagian dari UC01	    Alternatif 5a; pascakondisi gagal	Konsisten. Tidak tersimpan, UC03 tidak tercapai karena extension point tidak dicapai|
|     c. Validasi berhasil,   mahasiswa unduh bukti   	UC03 extend UC01 dengan kondisi tercatat	Alternatif 6a; UC03	Konsisten. Pengajuan tersimpan, bukti terunduh     |

Dua aktor, masing-masing punya interaksi, dan Admin akademik tidak ada
 4 use case di dalam batas sistem
 Include mengarah ke Validasi KRS, dan extend mengarah ke Ajukan KRS
 Extension point ada di use case dasar
 Kondisi extend ada di diagram dan di deskripsi
 Login hanya sebagai prasyarat, bukan include
 ID dan nama sama di diagram dan deskripsi
 .drawio dan .png satu versi
 SIA-R01 dan SIA-R02 ditandai belum dimodelkan di file kebutuhan




<!-- Identifikasi aktor dan use case -->
Katalog Aktor
Mahasiswa: Mengajukan KRS dan mengunduh bukti pengajuan.  
Dosen Wali: Memproses persetujuan atau penolakan KRS.   

<!-- Katalog Use Case -->
SIA-UC03  | Ajukan KRS   | Fungsi utama mahasiswa.   
SIA-UC04  | Validasi KRS | Perilaku yang disertakan UC03.   
SIA-UC05  | Unduh bukti pengajuan KRS | Tambahan bersyarat pada UC03.   
SIA-UC06  | Proses keputusan KRS | Fungsi utama dosen wali. 

<!-- Tentukan include -->
Relasi: SIA-UC03 <<include>> SIA-UC04.   
Alasan: Validasi kelengkapan, prasyarat, dan jadwal harus selalu dilakukan sebagai bagian mutlak dari proses pengajuan KRS sebelum data disimpan

<!-- Tentukan extend -->
Relasi: SIA-UC05 <<extend>> SIA-UC03.   
Extension point: Konfirmasi penyimpanan KRS.   
Kondisi: [mahasiswa memilih unduh bukti].  
Alasan: Pengajuan KRS tetap berhasil dan tersimpan meskipun mahasiswa tidak mengunduh bukti pengajuan

<!-- Tabel Deskripsi Use Case : SIA-UC03 Ajukan KRS  -->
Elemen                |SIA-UC03 Ajukan KRS                                                               | 
Tujuan                |Menghasilkan pengajuan KRS yang tersimpan                                         |
Aktor utama           |Mahasiswa.                                                                        |
Sumber kebutuhan      |SIA-R03, SIA-R04, dan SIA-R05.                                                    |
Pemicu                |Mahasiswa memilih menu/fungsi pengajuan KRS.                                      |
Prasyarat             |Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia  |
Pasca kondisi berhasil| Pengajuan tersimpan dengan status menunggu persetujuan dosen wali.               |
Pascakondisi gagal    | Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.                   |
Include               | SIA-UC04 Validasi KRS                                                            |
Extension point       |Konfirmasi penyimpanan pengajuan (pada langkah 6).                                |
Extend                |SIA-UC05 jika [mahasiswa memilih mengunduh bukti]                                 |

<!-- Alur utama: -->
|Langkah| Tindakan mahasiswa |  Respons  |                              sistem                              | |
|-------|-----------------------------------------------------------------------------------------------------|
|-------|---------------------|-----------|------------------------------------------------------------------||
|   1   |  Membuka pengajuan |    KRS    |                  Menampilkan daftar mata kuliah                  | |
|   2   |   Memilih  mata   |  kuliah   |    dan mengirim pengajuan Menampung data pilihan mata kuliah     |  |
|   3   |Menjalankan SIA-UC04 | (Validasi |                 kelengkapan, prasyarat, jadwal)                  ||
|   4   |     Jika validasi | berhasil, |menyimpan pengajuan dengan status menunggu persetujuan dosen wali |  |
|   5   |  Melihat konfirmasi|Menampilkan|  konfirmasi keberhasilan penyimpanan; mencapai extension point   | |
|   6   | Mengakhiri pengajuan |  Menutup                          proses pengajuan                         | |
|       |                                                                                                     |

Alur alternatif (Validasi gagal):
Jika pada langkah 3 validasi gagal (karena prasyarat tidak terpenuhi atau jadwal berbenturan), sistem menampilkan peringatan kegagalan. Pengajuan belum berhasil tersimpan dan mahasiswa kembali ke langkah pemilihan mata kuliah.

<!-- Tabel Deskripsi Use Case: SIA-UC04 Validasi KRS -->
|Elemen          |                                                       SIA-UC04 Validasi KRS                                                       |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|Tujuan          |                                     Memastikan KRS memenuhi aturan akademik sebelum disimpan.                                     |
|Aktor utama     |                                         Sistem (berjalan sebagai include dari SIA-UC03).                                          |
|Sumber kebutuhan|                                                             SIA-R04.                                                              |
|Pemicu          |                                Dipanggil oleh use case SIA-UC03 saat mahasiswa mengirim pengajuan.                                |
|Prasyarat       |                                      Data mata kuliah yang diajukan sudah ditampung sistem.                                       |
|Alur utama      |Sistem memeriksa kelengkapan pengajuan, mengecek terpenuhinya prasyarat mata kuliah, dan memeriksa apakah terdapat benturan jadwal.|
|                |                                                                                                                                   |

<!-- Tabel Deskripsi Use Case: SIA-UC05 Unduh bukti pengajuan KRS -->
|Elemen          |                             SIA-UC05 Unduh bukti pengajuan KRS                              |
|----------------|---------------------------------------------------------------------------------------------|
|Tujuan          |                Memberikan fail/berkas bukti pengajuan KRS kepada mahasiswa.                 |
|Aktor utama     |                                         Mahasiswa.                                          |
|Sumber kebutuhan|                                          SIA-R05.                                           |
|Pemicu          |   Mahasiswa memilih opsi unduh pada saat konfirmasi pengajuan (mencapai extension point).   |
|Prasyarat       |              Pengajuan KRS telah berhasil divalidasi dan tersimpan di sistem.               |
|Alur utama      |Sistem menghasilkan bukti pengajuan (dokumen) dan mengirimkannya untuk diunduh oleh mahasiswa|
|                |                                                                                             |
|                |                                                                                             |

<!-- Tabel Deskripsi Use Case: SIA-UC06 Proses keputusan KRS -->
|Elemen                 | SIA-UC06 Proses keputusan KRS                                                                   |
|-------------------------------------------------------------------------------------------------------------------------|
|Tujuan                 | Menyelesaikan status KRS mahasiswa (disetujui/ditolak).                                         |
|Aktor utama            | Dosen Wali.   
|Sumber kebutuhan       | SIA-R06.   
|Pemicu                 | Dosen wali membuka daftar pengajuan KRS mahasiswa.   
|Prasyarat              | Dosen wali telah terautentikasi dan terdapat pengajuan KRS dengan status menunggu persetujuan.   
|Pascakondisi berhasil  | KRS berstatus disetujui atau ditolak, dan catatan keputusan tersimpan.   
|Alur utama             | 1. Dosen wali melihat data pengajuan KRS mahasiswa.

                        | 2. Dosen wali memilih opsi setuju atau tolak dan memasukkan catatan keputusan.
                        
                        | 3. Sistem menyimpan perubahan status KRS dan catatan dari dosen wali.   

 <!-- Uji konsistensia -->
1. Validasi berhasil dan mahasiswa tidak mengunduh bukti: Pengajuan tersimpan dengan status menunggu persetujuan dosen wali, proses selesai tanpa menjalankan tambahan unduh. (Konsisten)
2. Validasi gagal: Proses terhenti di langkah 4 alur alternatif, sistem tidak menyimpan pengajuan. (Konsisten)
3.  Validasi berhasil dan mahasiswa memilih mengunduh bukti: Pengajuan tersimpan, mencapai extension point, sistem menjalankan perilaku extend (unduh file), lalu proses selesai. (Konsisten)   

<!-- tabel model analisis -->
|       Sumber       |Hubungan | Tujuan  |
|--------------------|---------|---------|
|     Mahasiswa      |Asosiasi |LAB-UC01 |
|     Mahasiswa      |Asosiasi |LAB-UC03 |
|     Mahasiswa      |Asosiasi |LAB-UC05 |
|Petugas_laboratorium|Asosiasi |LAB-UC02 |
|Petugas_laboratorium|Asosiasi |LAB-UC06 |
|Kepala_laboratorium |Asosiasi |LAB-UC07 |
|      LAB-UC03      |«include»|LAB-UC04 |
|      LAB-UC05      |«extend» |LAB-UC03 |