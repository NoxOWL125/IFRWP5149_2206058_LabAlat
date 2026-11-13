# STUDI KASUS
## Sistem Peminjaman Peralatan Laboratorium

### 1. Pendahuluan

Studi kasus ini menggunakan diagram kumulatif Pertemuan 4 sebagai acuan. Kebutuhan LAB-R01 sampai LAB-R11 dan spesifikasi 17 hubungan pada diagram mengacu pada Jobsheet Pertemuan 4, khususnya Tabel 4.5.

Pada pertemuan ini tidak terdapat kebutuhan baru maupun Use Case baru. Seluruh skenario yang tersedia digunakan sebagai bahan kajian untuk menelaah kesesuaian antara skenario Use Case dan diagram acuan.

### 2. Daftar Use Case

| ID | Nama Use Case |
|---|---|
| LAB-UC01 | Lihat Ketersediaan Peralatan |
| LAB-UC02 | Kelola Data Peralatan |
| LAB-UC03 | Ajukan Peminjaman |
| LAB-UC04 | Periksa Ketersediaan |
| LAB-UC05 | Cetak Bukti Pengajuan |
| LAB-UC06 | Proses Keputusan Peminjaman |
| LAB-UC07 | Lihat Laporan Peminjaman |
| LAB-UC08 | Tambah Data Peralatan |
| LAB-UC09 | Ubah Data Peralatan |
| LAB-UC10 | Hapus Data Peralatan |
| LAB-UC11 | Catat Pengembalian Peralatan |
| LAB-UC12 | Periksa Kondisi Peralatan |

---

# 3. Skenario Use Case

## 3.1 LAB-UC01 – Lihat Ketersediaan Peralatan

**Aktor:** Peminjam (Mahasiswa dan Dosen)

**Tujuan:** Peminjam dapat mengetahui peralatan yang tersedia sebelum mengajukan peminjaman.

**Deskripsi:** Peminjam membuka fungsi ketersediaan dan melihat daftar peralatan beserta status ketersediaannya.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Peminjam membuka fungsi Lihat Ketersediaan Peralatan. | 2. Sistem menampilkan daftar peralatan beserta status ketersediaannya. |
| **Skenario Alternatif** | |
| 3. Tidak ada peralatan yang tersedia pada daftar (cabang dari langkah 2). | 4. Sistem menampilkan pesan bahwa tidak ada peralatan yang tersedia. |

**Skenario Akhir:** Use Case selesai jika daftar peralatan beserta status ketersediaannya ditampilkan. Jika tidak ada peralatan yang tersedia, Use Case selesai dengan menampilkan pesan tersebut.

## 3.2 LAB-UC04 – Periksa Ketersediaan

**Aktor:** Peminjam (berjalan di dalam LAB-UC03 Ajukan Peminjaman).

**Tujuan:** Ketersediaan peralatan yang dipilih terperiksa sebelum pengajuan disimpan.

**Deskripsi:** Sistem memeriksa jumlah dan status peralatan yang dipilih peminjam serta menyampaikan hasilnya kepada alur pengajuan. Use Case ini berjalan di dalam UC03 dan tidak mempunyai interaksi langsung dengan aktor.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Alur pengajuan memanggil Periksa Ketersediaan dengan peralatan yang dipilih. | 2. Sistem memeriksa jumlah dan status peralatan tersebut. |
| 3. Sistem menyatakan peralatan tersedia. | 4. Alur pengajuan melanjutkan penyimpanan pengajuan. |
| **Skenario Alternatif** | |
| 5. Peralatan tidak tersedia atau jumlah tidak mencukupi (cabang dari langkah 2). | 6. Sistem menyampaikan hasil tidak tersedia sehingga alur pengajuan berhenti. |

**Skenario Akhir:** Use Case selesai jika hasil pemeriksaan tersampaikan kepada alur pengajuan. Hasil tersedia akan melanjutkan pengajuan, sedangkan hasil tidak tersedia akan menghentikan pengajuan.

## 3.3 LAB-UC05 – Cetak Bukti Pengajuan

**Aktor:** Mahasiswa (asosiasi khusus).

**Tujuan:** Bukti pengajuan tercetak sebagai tambahan bersyarat pada pengajuan.

**Deskripsi:** Mahasiswa yang memilih cetak pada konfirmasi pengajuan menerima bukti pengajuan dengan nomor pengajuan. Cabang ini berlaku dengan kondisi [mahasiswa memilih cetak] dan extension point Bukti Pengajuan tersedia pada LAB-UC03.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Mahasiswa memilih cetak bukti pada konfirmasi pengajuan. | 2. Sistem menampilkan bukti pengajuan dengan nomor pengajuan dan status Menunggu Keputusan. |
| 3. Mahasiswa mengonfirmasi pencetakan. | 4. Sistem mencetak bukti pengajuan. |
| **Skenario Alternatif** | |
| 5. Mahasiswa tidak memilih cetak (cabang dari langkah 1). | 6. Sistem menutup konfirmasi tanpa mencetak bukti dan pengajuan tetap tersimpan. |

**Skenario Akhir:** Use Case selesai jika bukti pengajuan tercetak. Jika mahasiswa tidak memilih cetak, pengajuan tetap selesai tanpa bukti cetak.

## 3.4 LAB-UC02 – Kelola Data Peralatan

**Aktor:** Petugas Laboratorium.

**Tujuan:** Data peralatan terkelola melalui satu fungsi pengelolaan bersama.

**Deskripsi:** Petugas membuka fungsi pengelolaan data peralatan, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khusus masing-masing.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Petugas membuka fungsi Kelola Data Peralatan. | 2. Sistem menampilkan daftar data peralatan. |
| 3. Petugas memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus. | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih. |
| 5. Petugas mengisi atau mengonfirmasi data. | 6. Sistem memeriksa kelengkapan dan keabsahan data. |
| 7. Petugas menyimpan perubahan. | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi. |
| **Skenario Alternatif** | |
| 9. Data tidak lengkap atau tidak sah (cabang dari langkah 6). | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data. |

**Skenario Akhir:** Use Case selesai jika perubahan data peralatan tersimpan. Jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan.

## 3.5 LAB-UC08 – Tambah Data Peralatan

**Aktor:** Petugas Laboratorium.

**Tujuan:** Data peralatan baru tersimpan sebagai bentuk khusus dari pengelolaan data peralatan.

**Deskripsi:** Petugas mengisi data peralatan baru dan menyimpan data tersebut. Langkah bersama mengikuti skenario LAB-UC02.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Petugas membuka fungsi Tambah Data Peralatan. | 2. Sistem menampilkan formulir data peralatan baru. |
| 3. Petugas mengisi data peralatan baru. | 4. Sistem memeriksa kelengkapan data. |
| 5. Petugas menyimpan data. | 6. Sistem menyimpan data peralatan baru dan menampilkan konfirmasi. |
| **Skenario Alternatif** | |
| 7. Data tidak lengkap (cabang dari langkah 4). | 8. Sistem menolak penyimpanan dan meminta petugas melengkapi data. |

**Skenario Akhir:** Use Case selesai jika data peralatan baru tersimpan. Jika data tidak lengkap, data tidak tersimpan.

**Keterangan:** Use Case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data baru tersimpan. Langkah bersama mengikuti skenario LAB-UC02.

## 3.6 LAB-UC09 – Ubah Data Peralatan

**Aktor:** Petugas Laboratorium.

**Tujuan:** Data peralatan berubah sebagai bentuk khusus dari pengelolaan data peralatan.

**Deskripsi:** Petugas memilih data peralatan, mengubah datanya, dan menyimpan perubahan. Langkah bersama mengikuti skenario LAB-UC02.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Petugas memilih data peralatan yang akan diubah. | 2. Sistem menampilkan data peralatan saat ini. |
| 3. Petugas mengubah data peralatan. | 4. Sistem memeriksa perubahan data. |
| 5. Petugas menyimpan perubahan. | 6. Sistem menyimpan data yang diubah dan menampilkan konfirmasi. |
| **Skenario Alternatif** | |
| 7. Data peralatan tidak ditemukan (cabang dari langkah 2). | 8. Sistem menampilkan pesan bahwa data peralatan tidak ditemukan. |

**Skenario Akhir:** Use Case selesai jika perubahan data peralatan tersimpan. Jika data tidak ditemukan, perubahan tidak tersimpan.

**Keterangan:** Use Case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data peralatan berubah. Langkah bersama mengikuti skenario LAB-UC02.

## 3.7 LAB-UC10 – Hapus Data Peralatan

**Aktor:** Petugas Laboratorium.

**Tujuan:** Data peralatan terhapus sebagai bentuk khusus dari pengelolaan data peralatan.

**Deskripsi:** Petugas memilih data peralatan, mengonfirmasi penghapusan, dan sistem menghapus data tersebut. Langkah bersama mengikuti skenario LAB-UC02.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Petugas memilih data peralatan yang akan dihapus. | 2. Sistem memeriksa bahwa peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif. |
| 3. Petugas mengonfirmasi penghapusan. | 4. Sistem menghapus data peralatan dan menampilkan konfirmasi penghapusan. |
| **Skenario Alternatif** | |
| 5. Peralatan sedang dipinjam atau memiliki pengajuan aktif (cabang dari langkah 2). | 6. Sistem menolak penghapusan dan menampilkan pesan bahwa peralatan masih terpakai. |

**Skenario Akhir:** Use Case selesai jika data peralatan terhapus. Jika peralatan sedang dipinjam atau memiliki pengajuan aktif, data tidak terhapus.

**Keterangan:** Use Case khusus dari LAB-UC02 Kelola Data Peralatan. Perilaku pembeda: data peralatan terhapus dengan syarat peralatan tidak sedang dipinjam dan tidak memiliki pengajuan aktif. Langkah bersama mengikuti skenario LAB-UC02.

## 3.8 LAB-UC06 – Proses Keputusan Peminjaman

**Aktor:** Petugas Laboratorium.

**Tujuan:** Pengajuan peminjaman mendapat keputusan setuju atau tolak.

**Deskripsi:** Petugas memeriksa pengajuan yang berstatus Menunggu Keputusan, menetapkan persetujuan atau penolakan, dan sistem menyampaikan keputusan.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Petugas membuka daftar pengajuan yang berstatus Menunggu Keputusan. | 2. Sistem menampilkan daftar pengajuan tersebut. |
| 3. Petugas memilih pengajuan dan menetapkan persetujuan. | 4. Sistem mengubah status pengajuan menjadi Disetujui dan menampilkan konfirmasi. |
| **Skenario Alternatif** | |
| 5. Petugas menetapkan penolakan (cabang dari langkah 4). | 6. Sistem mengubah status pengajuan menjadi Ditolak dan menampilkan konfirmasi penolakan. |
| 7. Pengajuan tidak ditemukan atau statusnya sudah berubah (cabang dari langkah 2). | 8. Sistem menampilkan pesan bahwa pengajuan tidak dapat diproses. |

**Skenario Akhir:** Use Case selesai jika pengajuan berstatus Disetujui atau Ditolak. Jika pengajuan tidak dapat diproses, status tidak berubah.

## 3.9 LAB-UC07 – Lihat Laporan Peminjaman

**Aktor:** Kepala Laboratorium.

**Tujuan:** Laporan peminjaman dapat dilihat oleh Kepala Laboratorium.

**Deskripsi:** Kepala Laboratorium membuka fungsi laporan dan melihat laporan peminjaman pada periode yang dipilih.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Kepala Laboratorium membuka fungsi Lihat Laporan Peminjaman. | 2. Sistem menampilkan daftar periode laporan. |
| 3. Kepala Laboratorium memilih periode. | 4. Sistem menampilkan laporan peminjaman periode tersebut. |
| **Skenario Alternatif** | |
| 5. Tidak ada data peminjaman pada periode yang dipilih (cabang dari langkah 4). | 6. Sistem menampilkan pesan bahwa tidak ada data peminjaman pada periode tersebut. |

**Skenario Akhir:** Use Case selesai jika laporan periode yang dipilih ditampilkan. Jika tidak ada data, Use Case selesai dengan menampilkan pesan tersebut.

**Keterangan:** Satu-satunya Use Case Kepala Laboratorium. Tabel ini berdiri sendiri dan tidak memuat langkah include, extend, generalization, atau realization.

## 3.10 LAB-UC11 – Catat Pengembalian Peralatan

**Aktor:** Petugas Laboratorium.

**Tujuan:** Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbarui.

**Deskripsi:** Petugas memilih peminjaman yang akan dikembalikan, mengonfirmasi alat yang kembali, dan menyimpan pencatatan.

**Prasyarat:** Peminjaman berstatus Dipinjam.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Petugas memilih peminjaman yang akan dikembalikan. | 2. Sistem menampilkan data peminjaman terpilih dan statusnya. |
| 3. Petugas mengonfirmasi alat yang kembali dan jumlahnya. | 4. Sistem menampung konfirmasi petugas. |
|  | 5. Sistem memeriksa bahwa status peminjaman harus Dipinjam. |
|  | 6. Sistem menjalankan Periksa Kondisi Peralatan (lihat skenario LAB-UC12). |
| 7. Petugas menyimpan pencatatan pengembalian. | 8. Sistem menyimpan tanggal kembali dan kondisi serta mengubah status peminjaman menjadi Selesai. |
| 9. Petugas melihat konfirmasi. | 10. Sistem menampilkan ringkasan pengembalian. |
| **Skenario Alternatif** | |
| 11. Status bukan Dipinjam (cabang dari langkah 5). | 12. Sistem menolak pencatatan dan menampilkan status peminjaman saat ini. |
| 13. Kondisi Rusak Ringan atau Rusak Berat dicatat pada langkah 6 (cabang dari langkah 6). | 14. Sistem tetap menyimpan pencatatan, menandai kondisi tersebut pada data peralatan, dan pengembalian tetap tercatat tanpa denda. |
| 15. Jumlah alat yang kembali tidak sesuai (cabang dari langkah 3). | 16. Sistem meminta petugas memeriksa kembali isian sebelum penyimpanan. |

**Skenario Akhir:** Use Case selesai jika pengembalian tercatat dengan tanggal kembali dan kondisi peralatan serta status peminjaman menjadi Selesai. Jika status bukan Dipinjam, tidak ada pengembalian baru yang tercatat dan status peminjaman tidak berubah.

**Keterangan:** Use Case ini direalisasikan oleh collaboration LAB-CO02 Catat Pengembalian Peralatan, tanpa langkah kegiatan sendiri. Keterlambatan dan denda belum dimodelkan pada pertemuan ini dan tidak menimbulkan aturan tambahan pada tabel ini.

## 3.11 LAB-UC12 – Periksa Kondisi Peralatan

**Aktor:** Petugas Laboratorium (berjalan di dalam LAB-UC11 Catat Pengembalian Peralatan).

**Tujuan:** Kondisi peralatan yang dikembalikan terperiksa dan tercatat.

**Deskripsi:** Sistem memeriksa kondisi peralatan yang dikembalikan dan mencatat nilainya sebagai bagian dari pencatatan pengembalian. Use Case ini berjalan di dalam UC11 dan tidak mempunyai interaksi langsung dengan aktor.

| Kegiatan | Respons Sistem |
|---|---|
| **Skenario Normal** | |
| 1. Alur pengembalian memanggil Periksa Kondisi Peralatan dengan peralatan yang dikembalikan. | 2. Sistem menampilkan pilihan kondisi, yaitu Baik, Rusak Ringan, atau Rusak Berat. |
| 3. Petugas memilih nilai kondisi peralatan. | 4. Sistem mencatat nilai kondisi pada data pengembalian. |
| **Skenario Alternatif** | |
| 5. Petugas belum memilih nilai kondisi (cabang dari langkah 4). | 6. Sistem meminta petugas memilih nilai kondisi sebelum pencatatan disimpan. |

**Skenario Akhir:** Use Case selesai jika nilai kondisi peralatan tercatat pada data pengembalian. Jika nilai belum dipilih, pencatatan tidak disimpan sampai nilai dipilih.

---

# 4. Catatan Hubungan Antar-Use Case

### 4.1 Kelompok Pengelolaan Data Peralatan

LAB-UC02 Kelola Data Peralatan merupakan Use Case utama yang memiliki bentuk pengelolaan khusus:

- LAB-UC08 Tambah Data Peralatan.
- LAB-UC09 Ubah Data Peralatan.
- LAB-UC10 Hapus Data Peralatan.

Ketiga Use Case tersebut mengikuti langkah bersama dari LAB-UC02 dan memiliki perilaku pembeda masing-masing.

### 4.2 Kelompok Keputusan dan Laporan

Kelompok ini terdiri atas:

- LAB-UC06 Proses Keputusan Peminjaman.
- LAB-UC07 Lihat Laporan Peminjaman.

Keduanya berdiri sendiri tanpa relasi antar-Use Case.

### 4.3 Kelompok Pengembalian Peralatan

Kelompok ini terdiri atas:

- LAB-UC11 Catat Pengembalian Peralatan.
- LAB-UC12 Periksa Kondisi Peralatan.

LAB-UC11 menyertakan LAB-UC12 sebagai langkah rujukan. Oleh karena itu, langkah pemeriksaan kondisi tidak disalin ke dalam tabel UC11.

### 4.4 Kelompok Pengajuan Peminjaman

Kelompok ini melibatkan:

- LAB-UC03 Ajukan Peminjaman.
- LAB-UC04 Periksa Ketersediaan.
- LAB-UC05 Cetak Bukti Pengajuan.

LAB-UC04 berjalan di dalam LAB-UC03 untuk memeriksa ketersediaan peralatan. Sementara itu, LAB-UC05 merupakan tambahan bersyarat ketika mahasiswa memilih untuk mencetak bukti pengajuan.

---

# 5. Catatan Kajian

Studi kasus ini digunakan untuk menelaah kesesuaian skenario Use Case terhadap diagram kumulatif Pertemuan 4. Mahasiswa diminta mengamati kedua belas Use Case beserta hubungan yang telah ditentukan pada diagram acuan.

Tidak terdapat penambahan kebutuhan maupun Use Case baru dalam studi kasus ini.

**Catatan kelengkapan sumber:** Teks sumber yang tersedia belum memuat skenario lengkap LAB-UC03 Ajukan Peminjaman. Oleh karena itu, tabel skenario UC03 perlu dilengkapi berdasarkan Jobsheet Pertemuan 4 apabila diperlukan.