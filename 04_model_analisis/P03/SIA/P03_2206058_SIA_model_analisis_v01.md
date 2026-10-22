• Mahasiswa berasosiasi dengan UC-01 untuk mengajukan KRS.
• UC-01 menyertakan UC-02 menggunakan <<include>> karena validasi wajib dilakukan.
• UC-03 memperluas UC-01 menggunakan <<extend>> karena pengunduhan bukti bersifat opsional.
• Extension point pada UC-01 adalah Konfirmasi penyimpanan.
• Dosen Wali berasosiasi dengan UC-04 untuk memproses keputusan KRS.
• Admin akademik tidak muncul pada diagram ini karena pengelolaan jadwal bukan bagian dari interaksi KRS dalam skenario yang diberikan.


Situasi	                                Hasil yang Diharapkan	                                    Konsisten?
A. Validasi berhasil dan 
mahasiswa tidak mengunduh bukti.	    Pengajuan tersimpan dengan status 
                                        menunggu persetujuan dosen wali. UC-03 tidak dijalankan.	    Ya
B. Validasi gagal.	                    Pengajuan belum berhasil tersimpan 
                                        dan sistem menampilkan informasi kegagalan validasi.	        Ya
C. Validasi berhasil 
dan mahasiswa memilih mengunduh bukti.	Pengajuan tersimpan dengan status menunggu 
                                        persetujuan dosen wali dan sistem menyediakan bukti pengajuan.	Ya
                                        
Analisis Hasil Uji
Situasi A: Relasi <<include>> memastikan validasi tetap dijalankan. Karena pengunduhan bukti bersifat opsional, mahasiswa dapat mengakhiri proses tanpa mengunduh bukti.
Situasi B: Ketika validasi gagal, pengajuan belum berhasil tersimpan. Dengan demikian, sistem tidak boleh memberikan hasil seolah-olah pengajuan telah berhasil diajukan.
Situasi C: Setelah validasi berhasil dan pengajuan tersimpan, mahasiswa dapat memilih pengunduhan bukti melalui relasi <<extend>>. Pengunduhan tidak mengubah status pengajuan menjadi disetujui.
Berdasarkan ketiga pengujian tersebut, diagram dan deskripsi Use Case sudah konsisten dengan skenario dan batas yang ditetapkan.
