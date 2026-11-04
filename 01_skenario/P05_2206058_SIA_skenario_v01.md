# LEMBAR SKENARIO USE CASE
**Tugas: Sistem Informasi Akademik (SIA) - Layanan Hasil Studi**
**Berkas:** P05_<NIM>_SIA_skenario_v01.md  
**Folder:** 01_skenario  

---

### Tabel 5.14.1 Skenario Use Case SIA-UC07 Lihat Kalender Akademik

| Field | Isi |
| :--- | :--- |
| **Nama use case** | SIA-UC07 Lihat Kalender Akademik |
| **Aktor** | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen) |
| **Tujuan** | Civitas Akademika dapat melihat jadwal dan kegiatan akademik yang berlaku |
| **Deskripsi** | Civitas Akademika membuka fungsi kalender akademik dan sistem menampilkan daftar kegiatan akademik |

| Kegiatan | Respon sistem |
| :--- | :--- |
| **Skenario Normal** | |
| 1. Civitas Akademika membuka fungsi Lihat Kalender Akademik | |
| | 2. Sistem menampilkan daftar kegiatan kalender akademik beserta tanggal dan keterangannya |
| **Skenario Alternative** | |
| 3. Data kalender akademik belum tersedia atau belum dipublikasikan *(cabang dari langkah 2)* | |
| | 4. Sistem menampilkan pesan bahwa kalender akademik belum tersedia |
| **Skenario Akhir** | Use case selesai jika daftar kegiatan kalender akademik ditampilkan; jika data belum tersedia, use case selesai dengan pesan tersebut. |

*Keterangan tabel:* Menerapkan generalization aktor. Mahasiswa dan Dosen mewarisi use case dari Civitas Akademika, sehingga skenario ditulis satu kali atas nama Civitas Akademika.

---

### Tabel 5.14.2 Skenario Use Case SIA-UC08 Input Nilai Mata Kuliah

| Field | Isi |
| :--- | :--- |
| **Nama use case** | SIA-UC08 Input Nilai Mata Kuliah |
| **Aktor** | Dosen |
| **Tujuan** | Dosen pengampu dapat menginput dan menyimpan nilai mahasiswa peserta mata kuliah |
| **Deskripsi** | Dosen membuka formulir nilai mata kuliah yang diampunya, menginput nilai mahasiswa, dan menyimpan perubahan |

| Kegiatan | Respon sistem |
| :--- | :--- |
| **Skenario Normal** | |
| 1. Dosen membuka daftar mata kuliah yang diampu | |
| | 2. Sistem memeriksa hak akses dosen sebagai pengampu mata kuliah dan menampilkan daftar mahasiswa peserta mata kuliah |
| 3. Dosen menginput nilai huruf atau angka untuk masing-masing mahasiswa | |
| 4. Dosen menyimpan penginputan nilai | |
| | 5. Sistem memeriksa keabsahan rentang nilai, menyimpan data nilai, dan menampilkan konfirmasi berhasil |
| **Skenario Alternative** | |
| 6. Dosen bukan pengampu mata kuliah tersebut *(cabang dari langkah 2)* | |
| | 7. Sistem menolak akses dan menampilkan pesan bahwa dosen bukan pengampu mata kuliah tersebut |
| 8. Nilai yang diinput di luar rentang yang sah *(cabang dari langkah 5)* | |
| | 9. Sistem menolak penyimpanan dan menampilkan pesan kesalahan rentang nilai |
| **Skenario Akhir** | Use case selesai jika data nilai mata kuliah tersimpan; jika dosen bukan pengampu atau nilai tidak sah, data nilai tidak tersimpan. |

*Keterangan tabel:* Use case ini direalisasikan oleh collaboration SIA-CO01 Input Nilai Mata Kuliah. Collaboration tersebut tidak mempunyai langkah kegiatan sendiri pada tabel ini.

---

### Tabel 5.14.3 Skenario Use Case SIA-UC09 Lihat KHS

| Field | Isi |
| :--- | :--- |
| **Nama use case** | SIA-UC09 Lihat KHS |
| **Aktor** | Mahasiswa |
| **Tujuan** | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) untuk semester terpilih |
| **Deskripsi** | Mahasiswa memilih semester dan sistem menampilkan nilai mata kuliah yang telah dipublikasikan |

| Kegiatan | Respon sistem |
| :--- | :--- |
| **Skenario Normal** | |
| 1. Mahasiswa membuka fungsi Lihat KHS dan memilih semester | |
| | 2. Sistem memeriksa status publikasi nilai dan menampilkan KHS yang memuat nilai mata kuliah yang sudah dipublikasikan |
| **Skenario Alternative** | |
| 3. Nilai pada semester terpilih belum ada yang dipublikasikan *(cabang dari langkah 2)* | |
| | 4. Sistem menampilkan pesan bahwa nilai semester terpilih belum dipublikasikan |
| **Skenario Akhir** | Use case selesai jika KHS berisi nilai yang dipublikasikan berhasil ditampilkan; jika nilai belum dipublikasikan, use case selesai dengan pesan tersebut. |

*Keterangan tabel:* Use case ini direalisasikan oleh collaboration SIA-CO02 Lihat KHS. Collaboration tersebut tidak mempunyai langkah kegiatan sendiri pada tabel ini.

---

### Tabel 5.14.4 Skenario Use Case SIA-UC10 Kelola Data Mahasiswa

| Field | Isi |
| :--- | :--- |
| **Nama use case** | SIA-UC10 Kelola Data Mahasiswa |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa terkelola melalui satu fungsi pengelolaan bersama |
| **Deskripsi** | Admin Akademik membuka fungsi pengelolaan data mahasiswa, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya |

| Kegiatan | Respon sistem |
| :--- | :--- |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Kelola Data Mahasiswa | |
| | 2. Sistem menampilkan daftar data mahasiswa |
| 3. Admin Akademik memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus | |
| | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih |
| 5. Admin Akademik mengisi atau mengonfirmasi data | |
| | 6. Sistem memeriksa kelengkapan dan keabsahan data |
| 7. Admin Akademik menyimpan perubahan | |
| | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 9. Data tidak lengkap atau tidak sah *(cabang dari langkah 6)* | |
| | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |

*Keterangan tabel:* Merupakan use case umum (generalization use case) yang memuat perilaku bersama yang dirujuk oleh SIA-UC11, SIA-UC12, dan SIA-UC13.

---

### Tabel 5.14.5 Skenario Use Case SIA-UC11 Tambah Data Mahasiswa

| Field | Isi |
| :--- | :--- |
| **Nama use case** | SIA-UC11 Tambah Data Mahasiswa |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa baru tersimpan sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik mengisi data mahasiswa baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem |
| :--- | :--- |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Tambah Data Mahasiswa | |
| | 2. Sistem menampilkan formulir data mahasiswa baru |
| 3. Admin Akademik mengisi data mahasiswa baru | |
| | 4. Sistem memeriksa kelengkapan data |
| 5. Admin Akademik menyimpan data | |
| | 6. Sistem menyimpan data mahasiswa baru dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data tidak lengkap *(cabang dari langkah 4)* | |
| | 8. Sistem menolak penyimpanan dan meminta Admin Akademik melengkapi data |
| **Skenario Akhir** | Use case selesai jika data mahasiswa baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

*Keterangan tabel:* Use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa baru tersimpan. Langkah bersama mengikuti Tabel skenario SIA-UC10.

---

### Tabel 5.14.6 Skenario Use Case SIA-UC12 Ubah Data Mahasiswa

| Field | Isi |
| :--- | :--- |
| **Nama use case** | SIA-UC12 Ubah Data Mahasiswa |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa berubah sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik memilih data mahasiswa, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem |
| :--- | :--- |
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan diubah | |
| | 2. Sistem menampilkan data mahasiswa saat ini |
| 3. Admin Akademik mengubah data mahasiswa | |
| | 4. Sistem memeriksa perubahan data |
| 5. Admin Akademik menyimpan perubahan | |
| | 6. Sistem menyimpan data yang diubah dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data mahasiswa tidak ditemukan *(cabang dari langkah 2)* | |
| | 8. Sistem menampilkan pesan data mahasiswa tidak ditemukan |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak ditemukan, perubahan tidak tersimpan. |

*Keterangan tabel:* Use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa berubah. Langkah bersama mengikuti Tabel skenario SIA-UC10.

---

### Tabel 5.14.7 Skenario Use Case SIA-UC13 Hapus Data Mahasiswa

| Field | Isi |
| :--- | :--- |
| **Nama use case** | SIA-UC13 Hapus Data Mahasiswa |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa terhapus sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik memilih data mahasiswa, mengonfirmasi penghapusan, dan sistem menghapus data tersebut. Langkah bersama mengikuti Tabel skenario SIA-UC10 |

| Kegiatan | Respon sistem |
| :--- | :--- |
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan dihapus | |
| | 2. Sistem memeriksa mahasiswa tidak memiliki data akademik aktif |
| 3. Admin Akademik mengonfirmasi penghapusan | |
| | 4. Sistem menghapus data mahasiswa dan menampilkan konfirmasi penghapusan |
| **Skenario Alternative** | |
| 5. Mahasiswa memiliki data akademik aktif *(cabang dari langkah 2)* | |
| | 6. Sistem menolak penghapusan dan menampilkan pesan data akademik mahasiswa masih aktif |
| **Skenario Akhir** | Use case selesai jika data mahasiswa terhapus; jika mahasiswa memiliki data akademik aktif, data tidak terhapus. |

*Keterangan tabel:* Use case khusus dari SIA-UC10 Kelola Data Mahasiswa. Perilaku pembeda: data mahasiswa terhapus, dengan syarat mahasiswa tidak memiliki data akademik aktif. Langkah bersama mengikuti Tabel skenario SIA-UC10.