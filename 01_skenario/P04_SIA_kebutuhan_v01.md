ID          Kebutuhan tugas
SIA-R07     Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik.
SIA-R08     Dosen dapat menginput nilai mata kuliah yang diampunya.
SIA-R09     Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan.
SIA-R10     Admin Akademik dapat mengelola data mahasiswa.
SIA-R11     Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa.
SIA-R12     Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS.

Batas dan asumsi
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02
(Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap
mempunyai identitas berbeda.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal
semester, batas KRS, masa ujian, dan sejenisnya); jangan
menyamakannya dengan jadwal kuliah pada Pertemuan 2.
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai
yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan
tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan.
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data
akademik aktif. Ketentuan ini fiktif untuk latihan.
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari
Pertemuan 3. Pembayaran dan perancangan basis data berada di luar
tugas ini

| ID        | Nama use case             | Aktor terkait     | Sumber kebutuhan  |
|---|---|---|---|---|
| SIA-UC01  | Lihat Jadwal Kuliah       | Mahasiswa         | SIA-R01           | 
| SIA-UC02  | Kelola Jadwal Kuliah      | Admin             | SIA-R02           | 
| SIA-UC03  | Ajukan KRS                | Mahasiswa         | SIA-R03           | 
| SIA-UC04  | Validasi KRS              | Dosen Wali        | SIA-R04           | 
| SIA-UC05  | Unduh Bukti Pengajuan KRS | Mahasiswa         | SIA-R05           | 
| SIA-UC06  | Proses Keputusan KRS      | Dosen Wali        | SIA-R06           |
| SIA-UC07  | Lihat Kalender Akademik   | Civitas Akademika | SIA-R07           | 
| SIA-UC08  | Input Nilai Mata Kuliah   | Dosen Wali        | SIA-R08           | 
| SIA-UC09  | Lihat KHS                 | Mahasiswa         | SIA-R09           |
| SIA-UC10  | Kelola Data Mahasiswa     | Admin Akademik    | SIA-R10, SIA-R11  | 
| SIA-UC11  | Tambah Data Mahasiswa     | Admin Akademik    | SIA-R11           |
| SIA-UC12  | Ubah Data Mahasiswa       | Admin Akademik    | SIA-R11           | 
| SIA-UC13  | Hapus Data Mahasiswa      | Admin Akademik    | SIA-R11           |

Keputusan pemodelan:
1. Civitas Akademika merupakan aktor umum.
2. Mahasiswa dan Dosen merupakan aktor khusus.
3. Civitas Akademika mempunyai asosiasi dengan SIA-UC07 Lihat Kalender Akademik.
4. Mahasiswa dan Dosen mewarisi fungsi tersebut.
5. Tidak perlu menggambar asosiasi kalender secara langsung dari Mahasiswa dan Dosen.
Alasannya: Mahasiswa dan Dosen sama-sama termasuk Civitas Akademika sehingga memiliki hak yang sama untuk melihat kalender akademik.

Use case khusus	Perilaku pembeda
SIA-UC11 Tambah Data Mahasiswa	Admin Akademik memasukkan data mahasiswa baru ke dalam sistem.
SIA-UC12 Ubah Data Mahasiswa	Admin Akademik memperbarui informasi mahasiswa yang sudah tersimpan.
SIA-UC13 Hapus Data Mahasiswa	Admin Akademik menghapus data mahasiswa yang tidak memiliki data akademik aktif.

Ketiganya memiliki aktor Admin Akademik melalui fungsi umum Kelola Data Mahasiswa.

ID	Nama collaboration	Realisasi
SIA-CO01	Input Nilai Mata Kuliah	SIA-UC08
SIA-CO02	Lihat KHS	SIA-UC09

Ketentuan gambar:
- Elips menggunakan garis putus-putus.
- Collaboration berada di dalam batas sistem.
- Tidak ada asosiasi langsung dari aktor ke collaboration.
- Garis realization putus-putus berasal dari collaboration.
- Segitiga kosong mengarah ke use case.

Kelompok	Elemen
Aktor	Mahasiswa, Dosen, Civitas Akademika, Admin Akademik, Dosen Wali
Jadwal	UC01, UC02
KRS	UC03, UC04, UC05, UC06
Kalender	UC07
Hasil studi	UC08, UC09
Pengelolaan mahasiswa	UC10, UC11, UC12, UC13
Collaboration	CO01, CO02