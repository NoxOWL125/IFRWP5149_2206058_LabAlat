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
| Dosen Wali | Memproses persetujuan atau penolakan KRS                                                             |

Kenapa admin tidak di masukan sebagai aktor?
Alasan: Admin tetap tercantum dalam kebutuhan untuk mengelola jdawal kuliah. Tetapi hal ini juga tidak berarti Admin ini dihapus dari keseluruhan Sistem. Kebutuhan tetap di pertahankan dan dapat di modelkan dalam diagram pengelolaan jadwal kuliah yang terpisah. Itu mungkin yang baru saya pikiran, untuk kedepannya mungkin akan ada beberapa perubahan lagi.

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

ID Use Case	    Nama Use Case	            Aktor Terkait	            Sumber Kebutuhan
UC-01	        Ajukan KRS	                Mahasiswa	                SIA-R03
UC-02	        Validasi KRS	            Perilaku internal sistem	SIA-R04
UC-03	        Unduh Bukti Pengajuan KRS	Mahasiswa	                SIA-R05
UC-04	        Proses Keputusan KRS	    Dosen Wali	                SIA-R06

Catatan: ID Use Case (UC-01 sampai UC-04) berbeda dari ID kebutuhan (SIA-R03 sampai SIA-R06). Validasi KRS merupakan perilaku internal sistem yang dijalankan sebagai bagian dari pengajuan, bukan aktivitas Admin akademik.

<!-- Relasi Include -->
Unsur	                Keterangan
Use Case sumber	        UC-01 — Ajukan KRS
Use Case tujuan	        UC-02 — Validasi KRS
Relasi	                <<include>>
Sumber kebutuhan	    SIA-R03 dan SIA-R04

• Use Case Ajukan KRS menggunakan relasi <<include>> ke Use Case Validasi KRS karena validasi merupakan bagian wajib dari setiap proses pengajuan KRS.
• Sistem memeriksa kelengkapan pengajuan, prasyarat mata kuliah, dan benturan jadwal. Jika salah satu pemeriksaan gagal, pengajuan belum berhasil tersimpan. Jika seluruh pemeriksaan berhasil, pengajuan dapat disimpan dengan status menunggu persetujuan dosen wali.
• Arah panah relasi <<include>> adalah dari Use Case yang menyertakan perilaku menuju Use Case yang disertakan.
Notasi:
UC-01 Ajukan KRS => UC-02 Validasi KRS : <<include>>

<!-- Relasi Extend -->
Unsur	Keterangan
Use Case dasar	    UC-01 — Ajukan KRS
Use Case tambahan	UC-03 — Unduh Bukti Pengajuan KRS
Relasi	            <<extend>>
Kondisi	            Pengajuan berhasil disimpan dan mahasiswa memilih mengunduh bukti.
Extension point	    Konfirmasi penyimpanan
Sumber kebutuhan	SIA-R03 dan SIA-R05

• Use Case Unduh Bukti Pengajuan KRS menggunakan relasi <<extend>> terhadap Use Case Ajukan KRS karena pengunduhan bukti bersifat opsional. Mahasiswa dapat memilih untuk mengunduh bukti setelah sistem berhasil menyimpan pengajuan.
• Jika mahasiswa tidak memilih pengunduhan, pengajuan tetap dianggap berhasil selama validasi telah berhasil dan data pengajuan sudah tersimpan. Dengan demikian, pengunduhan bukti tidak menentukan keberhasilan proses pengajuan KRS.
• Arah panah relasi <<extend>> adalah dari Use Case tambahan menuju Use Case dasar.
Notasi:
UC-03 Unduh Bukti Pengajuan KRS => UC-01 Ajukan KRS : <<extend>>
Extension point: Konfirmasi penyimpanan

