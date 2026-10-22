# Hi 👋, I'm 2406111 Sofwan Rnz

### praktikum Analisis desain beriorientasi objek

- 🌱 I'm currently learning **Pengenalan lingkungan praktikum dan kakas pemodelan UML**

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://github.com/SofwanRnz" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/github.svg" alt="SofwanRnz" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://developer.mozilla.org/en-US/docs/Web/c" target="_blank" rel="noreferrer"> <img src="https://skillicons.dev/icons?i=c" alt="c" width="40" height="40"/> </a> <a href="https://developer.mozilla.org/en-US/docs/Web/javascript" target="_blank" rel="noreferrer"> <img src="https://skillicons.dev/icons?i=js" alt="javascript" width="40" height="40"/> </a></p>

# Hi 👋, I'm Sofwan Robyansah Nur Zaman

<p align="center">
  <b>NIM:</b> 2406111 | <b>Kelas:</b> Informatika B | <b>Program Studi:</b> Teknik Informatika
</p>

---

### 📚 Praktikum Analisis & Desain Berorientasi Objek (ADBO)

Repositori ini dibuat untuk menyajikan hasil pengerjaan modul praktikum, pembuatan diagram UML, spesifikasi *use case*, serta dokumentasi revisi/evaluasi tugas Analisis dan Desain Berorientasi Objek.

---

### 🌱 Pertemuan & Progres Pembelajaran

- **Pertemuan 1:** Pengenalan Analisis & Desain Berorientasi Objek
- **Pertemuan 2:** **UNIFIED MODELLING LANGUAGE (UML)**
- **Pertemuan 3:** **USE CASE DIAGRAM DAN USE CASE DESCRIPTION**

---

### 📊 Hasil Evaluasi Diagram & Jobsheet (Pertemuan 3)

| No | Temuan | Perbaikan yang Diperlukan | Alasan |
|:--:|---|---|---|
| 1 | Arah panah relasi `«include»` terbalik dari Validasi KRS ke Ajukan KRS. | Ubah arah panah putus-putus agar mengarah dari Ajukan KRS ke Validasi KRS. | Relasi `«include»` mengharuskan *use case* dasar menunjuk ke *use case* yang disertakan. |
| 2 | Arah panah relasi `«extend»` terbalik dari Ajukan KRS ke Unduh bukti. | Ubah arah panah putus-putus agar mengarah dari Unduh bukti ke Ajukan KRS. | Relasi `«extend»` mengharuskan *use case* tambahan menunjuk ke *use case* dasar yang diperluas. |
| 3 | Aktor Mahasiswa dihubungkan langsung dengan Validasi KRS. | Hapus garis penghubung langsung antara aktor Mahasiswa dengan Validasi KRS. | Validasi berjalan otomatis oleh sistem (`«include»`), bukan diinisiasi langsung oleh aktor. |
| 4 | Proses persetujuan KRS dihubungkan dengan Admin akademik. | Ubah penghubung agar Proses persetujuan KRS hanya terhubung dengan Dosen wali. | Sesuai skenario, hanya Dosen wali yang memiliki wewenang untuk menyetujui KRS. |

---

### 📝 Catatan Konsep Spesifikasi Use Case

* **Extension Point:** Menunjukkan titik lokasi pada alur *use case* dasar tempat alur tambahan dapat dipicu (`Bukti pengajuan tersedia`).
* **Condition:** Syarat opsional agar alur ekstensi dijalankan (`[mahasiswa memilih mengunduh bukti]`).
* **Rationale (Alasan):** Menjelaskan logika bisnis bahwa proses ekstensi bersifat opsional dan tidak membatalkan alur utama pengajuan/penyimpanan KRS.

---

### 🛠️ Languages and Tools

<p align="left">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=cpp,java,python,html,css,js,git,github,vscode" />
  </a>
</p>

---

### 📫 Contact & Socials

- 📬 **Email:** `2406111@itg.ac.id`
- ⚡ **Fun Fact:** *Learning step by step, debugging mind and code.*