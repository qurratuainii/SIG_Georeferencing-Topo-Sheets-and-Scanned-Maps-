# SIG_Georeferencing-Topo-Sheets-and-Scanned-Maps-

*Tutorial Georeferencing Topo Sheets and Scanned Maps 

1. Download terlebih dahulu 1870_southern_india.jpg setelah itu buka QGIS dan klik Layer lalu pilih Georeferencer untuk membuka tool (*Gambar 1*)

2. Geoferencer dibagi menjadi 2 bagian. Bagian atas merupakan tempat gambar yang ditampilkan dan bagian bawah tempat tabel yang menunjukkan GCP akan muncul (*Gambar 2*)

3. Sekarang kita akan membuka gambar JPG. Buka File lalu pilih Open Raster. Cari gambar yang telah diunduh dan klik open (*Gambar 3*)

4. Setelah itu kita akan melihat gambar pada bagian atas. Kita dapat menggunakan kontrol zoom/geser di toolbar untuk mempelajari peta lebih lanjut (*Gambar 4*)

5. Sekarang kita perlu meneta[kan koordinat ke beberapa titik pada peta. Jika diperhatikan lebih dekat, kita akan melihat kisi koordinat dengan tanda. Yang arah kekiri merupakan garis grid bujur dan ke bawah garis grid lintang.

6. Sebelum menambahkan Ground Control Points (GCP), kita perlu mendefinisikan pengaturan transformasi. Klik settings pada jendela georeferencing untuk membuka Transformation settings dialog (*Gambar 5*)

7. Pada pengaturan Transformation, pilih jenis transformasi sebagai Polynomial 2. Lihat dokumentasi QGIS untuk mempelajari tentang berbagai jenis transformasi dan penggunaannya. Kemudian pilih Resampling Method Nearest neighbour. Klik tombol Select CRS di sebelah target SRS (*Gambar 6*) 

8. Jika kita melakukan georefencing peta yang dipindai seperti ini, kita dapat memperoleh informasi CRS dari peta tersebut. Melihat gambar peta koordinat berada di Lintang/Bujur. Tidak ada informasi datum yang diberikan, jadi kita harus mengasumsikan yang tepat. Karena ini adalah peta india dan petanya cukup tua, kita dapat bertaruh bahwa data Everest 1830 akan memberikan hasil yang baik. Cari everest dan pilih CRS dengan definition of the Everest datum (EPSG:4042), lalu klik OK (*Gambar 7*)

9. Beri nama raster keluaran dengan 1870_southern_india_modified,tif, Pilih LZW sebagai compression. Centang Save GCP points untuk menyimpan poin sebagai file terpisah untuk tujuan selanjutnya. Pastikan opsi QGIS saat selesai di centang, lalu klik OK (*Gambar 8*)

10. Sekarang kita dapat mulai menambahkanGround Control Points (GCP), lalu klik tombol Add point (*Gambar 9*)

11. Sekarang tempatkan cross-hair di persimpangan garis grid dan klik kiri, ini akan berfungsi sebagai ground-truth dalam kasus kita. Saat garis kisi diberi label, kita dapat menentukan koordinat X dan Y dari titik-titik dengan menggunakannya. Pada pop-up masukkan koordinat. Ingat bahwa X=bujur dan Y=lintang, lalu klik OK (*Gambar 10*)

12. Kita akan melihat tabel GCP sekarang memiliki baris dengan detail GCP pertama (*Gambar 11*)

13. Demikian pula, tambahkan lebih banyak GCP yang mencakup seluruh gambar. Semakin banyak poin yang dimiliki, semakin akurat gambar terdaftar ke koordinat target. Transformasi Polynomial 2 membutuhkan setidaknya 6 GCP. Setelah menambahkan jumlah minimum poin yang diperlukan untuk transformasi, kita akan melihat bahwa GCP sekarang memiliki nilai kesalahan dX dY dan residual yang tidak nol. Jika GCP tertentu memiliki nilai kesalahan yang sangat tinggi, itu berarti kesalahan manusia dalam memasukkan nilai koordinat. Jadi, kita dapat menghapus GCP tersebut dan merekamnya kembali. Kita dapat mengedit nilai koordinat di tabel GCP dengan mengklik sel di salah satu tujuan (*Gambar 12*)

14. Setelah kita puas dengan GCP, klik tombol Start Georeferencing. Ini akan memulai proses melengkungkan gambar menggunakan GCP dan membuat raster target (*Gambar 13*)

15. Setelah proses selesai, kita akan melihat lapisan georeferenced dimuat pada QGIS. Georeferensi sekarang selesai. Kita akan melihat Project CRS di kanan bawah diatur ke EPSG:4042 seperti yang dijelaskan dalam pengaturan Transformation (8Gambar 14*)

16. Drag dan drop OpenStreetMap sebagai base map dari dropdown XYZ Tiles di bagian bawah panel Browser untuk memverifikasi lapisan georeferensi. Untuk mengatur transparansi, klik ikon Open Layer styling panel dan pilih tab Transparency. Atur transparansi menjadi 40%. Sekarang gambar yang digeoreferensu harus di-overlay dengan garis peta dasar (*Gambar 15*)

17. Jika georeferensi perlu lebih disempurnakan,  kita bisa mulai dari titik GCP yang dikumpulkan. Telusuri lokasi file 1870_southern_india_modified.tif. Kita dapat menemukan file tambahan 1870_southern_india_modified.tif.points. File ini akan berisi informasi poin GCP

18. Buka georeferencing pada QGIS, klik file load GCP Points, dan pilih 1870_southern_india_modified.tif.points. Ini akan memuat GCP yang dibuat sebelumnya. Kemudian muat 1870_southern_india_modified.tif untuk menyempurnakan pekerjaan kita 
