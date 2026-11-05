<!-- skenario -->

Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

<!-- kebutuhan tugas -->

|  ID   |                             Kebutuhan_tugas                              |
|-------|--------------------------------------------------------------------------|
|SIA-R01|                  Mahasiswa dapat melihat jadwal kuliah                   |
|SIA-R02|               Admin akademik dapat mengelola jadwal kuliah               |
|SIA-R03|                      Mahasiswa dapat mengajukan KRS                      |
|SIA-R04|             Sistem memvalidasi KRS sebagai bagian pengajuan              |
|SIA-R05|Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
|SIA-R06|        Dosen wali dapat memproses persetujuan atau penolakan KRS         |

<!-- tabel identifikasi aktor -->

|  Aktor  |                          Tujuan_terhadap_sistem                           |
|---------|---------------------------------------------------------------------------|
|Mahasiswa|   Melihat jadwal kuliah, mengajukan KRS, dan mengunduh bukti pengajuan    |
|  Admin  |                     akademik Mengelola jadwal kuliah                      |
|  Dosen  |wali Memproses persetujuan atau penolakan pengajuan KRS beserta catatannya |

<!-- tabel katalog use case -->

|   ID   |    Nama_use_case     |      Peran_dalam_model       |
|--------|----------------------|------------------------------|
|SIA-UC01| Lihat_jadwal_kuliah  |    Fungsi utama mahasiswa    |
|SIA-UC02| Kelola_jadwal_kuliah | Fungsi utama admin akademik  |
|SIA-UC03|      Ajukan_KRS      |    Fungsi utama mahasiswa    |
|SIA-UC04|     Validasi_KRS     |Perilaku yang disertakan UC03 |
|SIA-UC05|Unduh_bukti_pengajuan | Tambahan bersyarat pada UC03 |
|SIA-UC06|Proses_persetujuan_KRS|   Fungsi utama dosen wali    |

<!-- batas dan asumsi -->

• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas

<!-- Relasi Include -->
SIA-UC03 «include» SIA-UC04
Alasan : Validasi digabung menjadi satu nama label/kategori. Isinya menjelaskan secara khusus mengapa proses validasi tersebut perlu dilakukan,   yaitu untuk memeriksa kelengkapan, prasyarat, dan benturan jadwal secara otomatis serta wajib sebagai bagian dari pengajuan KRS.

<!-- Relasi Extend -->
SIA-UC05 «extend» SIA-UC03
Extension point : Titik pada alur utama di mana alur tambahan dapat dipicu Konfirmasi penyimpanan pengajuan KRS.
Kondisi : Syarat agar alur tambahan tersebut berjalan ([mahasiswa memilih mengunduh bukti]).
Alasan  : Pengajuan KRS tetap berhasil disimpan meskipun mahasiswa tidak melakukan pengunduhan bukti.

