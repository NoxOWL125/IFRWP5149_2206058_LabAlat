A. UC-01 — Ajukan KRS
Unsur	            Deskripsi
ID	                UC-01
Nama	            Ajukan KRS
Aktor utama	        Mahasiswa
Sumber kebutuhan	SIA-R03

Tujuan: Mahasiswa mengajukan pilihan mata kuliah untuk KRS.
Prasyarat: Mahasiswa telah terautentikasi dan data mata kuliah tersedia.
Pemicu: Mahasiswa memilih fungsi pengajuan KRS.

Alur utama:
    1.	Mahasiswa membuka fungsi pengajuan KRS.
    2.	Sistem menampilkan daftar mata kuliah yang tersedia.
    3.	Mahasiswa memilih mata kuliah yang akan diajukan.
    4.	Mahasiswa mengirimkan pengajuan KRS.
    5.	Sistem menjalankan UC-02, yaitu Validasi KRS.
    6.	Jika validasi berhasil, sistem menyimpan pengajuan.
    7.	Sistem memberikan status menunggu persetujuan dosen wali.
    8.	Sistem menampilkan konfirmasi bahwa pengajuan berhasil disimpan.
    9.	Mahasiswa dapat memilih untuk mengunduh bukti melalui UC-03.

Alur alternatif A — Validasi gagal:
    1.	Sistem menemukan bahwa pengajuan tidak lengkap, prasyarat mata kuliah tidak terpenuhi, atau terdapat benturan jadwal.
    2.	Sistem menampilkan informasi kegagalan validasi.
    3.	Pengajuan belum berhasil tersimpan.
    4.	Mahasiswa dapat memperbaiki pilihan atau kelengkapan pengajuan dan mengajukannya kembali.

Alur alternatif B — Mahasiswa tidak mengunduh bukti:
    1.	Pengajuan berhasil disimpan.
    2.	Pada konfirmasi penyimpanan, mahasiswa tidak memilih pengunduhan bukti.
    3.	Proses pengajuan berakhir tanpa pengunduhan bukti.

Pascakondisi:
•	Jika validasi berhasil, pengajuan tersimpan dengan status menunggu persetujuan dosen wali.
•	Jika validasi gagal, pengajuan belum berhasil tersimpan.
•	Pengunduhan bukti tidak memengaruhi status keberhasilan pengajuan.

B UC-02 — Validasi KRS
Unsur	            Deskripsi
ID	                UC-02
Nama	            Validasi KRS
Aktor	            Perilaku internal sistem
Sumber kebutuhan	SIA-R04

Tujuan:	Memastikan pengajuan memenuhi pemeriksaan yang ditentukan dalam skenario.
Pemicu:	Mahasiswa mengirimkan pengajuan KRS melalui UC-01.
Prasyarat: Pengajuan KRS telah diterima untuk diperiksa dan data mata kuliah, prasyarat, serta jadwal tersedia.

Alur utama:
    1.	Sistem memeriksa kelengkapan pengajuan.
    2.	Sistem memeriksa prasyarat mata kuliah yang dipilih.
    3.	Sistem memeriksa benturan jadwal antarmata kuliah.
    4.	Jika seluruh pemeriksaan berhasil, sistem menyatakan validasi berhasil.
    5.	Sistem mengembalikan hasil validasi kepada UC-01 agar pengajuan dapat disimpan.

Alur alternatif — Validasi gagal:
    1.	Sistem menemukan satu atau lebih pemeriksaan yang tidak terpenuhi.
    2.	Sistem menyatakan validasi gagal dan memberikan informasi yang relevan.
    3.	Sistem tidak melanjutkan pengajuan ke penyimpanan yang menandakan pengajuan berhasil.

Pascakondisi:
•	Jika validasi berhasil, UC-01 dapat melanjutkan penyimpanan pengajuan.
•	Jika validasi gagal, pengajuan belum berhasil tersimpan.

C. UC-03 — Unduh Bukti Pengajuan KRS
Unsur	            Deskripsi
ID	                UC-03
Nama	            Unduh Bukti Pengajuan KRS
Aktor utama	        Mahasiswa
Sumber kebutuhan	SIA-R05

Tujuan: Mahasiswa memperoleh bukti pengajuan KRS yang berhasil disimpan.
Use Case dasar: UC-01 — Ajukan KRS
Kondisi: Pengajuan berhasil disimpan dan mahasiswa memilih mengunduh bukti.
Extension point: Konfirmasi penyimpanan

Alur utama:
    1.	Sistem menampilkan konfirmasi bahwa pengajuan KRS berhasil disimpan.
    2.	Mahasiswa memilih opsi unduh bukti pengajuan.
    3.	Sistem menyediakan bukti pengajuan KRS untuk diunduh.
    4.	Mahasiswa memperoleh bukti pengajuan.

Alur alternatif — Mahasiswa tidak memilih unduh:
    1.	Sistem menampilkan konfirmasi penyimpanan.
    2.	Mahasiswa tidak memilih opsi unduh bukti.
    3.	Use Case tambahan tidak dijalankan.
    4.	Pengajuan KRS tetap berhasil tersimpan.

Pascakondisi:
•	Jika mahasiswa memilih unduh, sistem menyediakan bukti pengajuan.
•	Jika mahasiswa tidak memilih unduh, pengajuan tetap tersimpan tanpa proses pengunduhan.

D. UC-04 — Proses Keputusan KRS
Unsur	            Deskripsi
ID	                UC-04
Nama	            Proses Keputusan KRS
Aktor utama	        Dosen Wali
Sumber kebutuhan	SIA-R06

Tujuan: Dosen wali memproses pengajuan KRS dan menetapkan keputusan.
Prasyarat: Pengajuan KRS telah tersimpan dengan status menunggu persetujuan dosen wali.
Pemicu: Dosen wali membuka pengajuan KRS untuk diproses.

Alur utama:
    1.	Dosen wali membuka pengajuan KRS yang menunggu keputusan.
    2.	Sistem menampilkan informasi pengajuan KRS.
    3.	Dosen wali memeriksa pengajuan.
    4.	Dosen wali memilih keputusan berupa persetujuan atau penolakan.
    5.	Dosen wali memberikan catatan keputusan.
    6.	Sistem menyimpan keputusan dan catatan yang diberikan.
    7.	Sistem memperbarui status pengajuan sesuai keputusan.

Alur alternatif A — Pengajuan disetujui:
    1.	Dosen wali memilih persetujuan.
    2.	Dosen wali memberikan catatan keputusan.
    3.	Sistem menyimpan keputusan dan catatan.
    4.	Status pengajuan berubah menjadi disetujui.

Alur alternatif B — Pengajuan ditolak:
    1.	Dosen wali memilih penolakan.
    2.	Dosen wali memberikan catatan keputusan.
    3.	Sistem menyimpan keputusan dan catatan.
    4.	Status pengajuan berubah menjadi ditolak.
    
Pascakondisi:
• Jika disetujui, status pengajuan menjadi disetujui.
• Jika ditolak, status pengajuan menjadi ditolak.
• Catatan keputusan tersimpan sesuai keputusan dosen wali.
