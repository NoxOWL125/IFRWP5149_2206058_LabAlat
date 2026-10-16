<!-- Deskripsi -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

<!-- Tabel Kebutuhan -->
| ID      | Kebutuhan tugas                                                           |
|---------|---------------------------------------------------------------------------|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah                                     |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah                              |
| SIA-R03 | Mahasiswa dapat mengajukan KRS                                            |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan                           |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS                 |

<!-- Batasan Sistem -->
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

<!-- Identifikasi Aktor -->
| Aktor      | Tujuan Terhadap Sistem                                                                               |
| ---------- | ---------------------------------------------------------------------------------------------------- |
| Mahasiswa  | Melihat mata kuliah, melihat jadwal, mengajukan KRS, mengunduh bukti atau bukti konfirmasi pengajuan |
| Admin      | Menglola data jadwal kuliah                                                                          |
| Dosen Wali | Memproses persetujuan atau penolakan KRS                                                             |

<!-- Susunan Katalog -->
| ID      | Nama use case                         | Peran dalam model            |
| ------- | ------------------------------------- | ---------------------------- |
| SIA-R01 | Lihat jadwal kuliah                   | Fungsi utama mahasiswa       |
| SIA-R02 | Mengelola jadwal kuliah               | Fungsi utama admin           |
| SIA-R03 | Pengajuan KRS                         | Fungsi utama mahasiswa       |
| SIA-R04 | Periksa KRS                           | Perilaku yang disertakan R03 |
| SIA-R05 | Validasi KRS                          | Fungsi utama admin           |
| SIA-R06 | Cetak bukti pengajuan                 | Tambahan bersyarat R03       |
| SIA-R07 | Proses persetujuan atau penolakan KRS | Fungsi utama dosen wali      |

<!-- Relasi Include -->
SIA-R03 «include» SIA-R04
Alasan: pemeriksaan menjadi bagian validasi pengajuan.

<!-- Relasi Extend -->
SIA-R03 «extend» SIA-R05
Extension point: Bukti pengajuan tersedia.
Kondisi: [mahasiswa memilih cetak].
Alasan: pengajuan tetap berhasil tanpa pencetakan.