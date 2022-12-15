Langkah Kerja

Open QGIS and locate the downloaded files in the Browser panel. Expand individual zip files to show the .hgt files. Hold the Ctrl key and select all individual files. Once selected, drag them to the canvas.

Anda akan melihat 11 layer individual dimuat di panel Layers dan ditampilkan di kanvas. Kami akan menggabungkan ubin individual ini menjadi satu mozaik. Pergi ke Processing ‣ Toolbox.

Cari dan temukan GDAL Raster miscellaneous Merge tool. Klik dua kali untuk meluncurkannya.

Dalam dialog Merge, klik tombol … di sebelah Input layer. Klik Select All untuk memilih semua lapisan individu.

Seperti disebutkan dalam detail lapisan dataset, tipe data input adalah bilangan bulat bertanda 16-bit. Untuk menjaga integritas data, kita harus menyimpan tipe data yang sama untuk layer gabungan. Pilih Int16 sebagai tipe data Keluaran. Juga format data keluaran default adalah GeoTiff. File GeoTiff bisa menjadi sangat besar jika tidak dikompresi. Pilih Kompresi Tinggi sebagai Profil. Klik Run.

Setelah pemrosesan selesai, OUTPUT layer baru akan ditambahkan ke panel Layers. Jika lapisan tidak berada di bagian atas tumpukan, pilih dan seret ke bagian atas panel Layers.

Anda akan melihat bahwa lapisan OUTPUT berisi data elevasi gabungan dari ubin masukan individual. Visualisasi default hanya menampilkan nilai piksel dalam kisaran 0-255. Namun data kami berisi piksel dengan nilai -14 hingga 2371, menghasilkan rendering kontras yang rendah. Mari kita ubah menjadi visualisasi yang lebih baik. Klik tombol Open the layer Styling panel di panel Layers.

Di panel Layer Styling, klik Render type dropdown dan pilih Hillshade renderer. Opsi rendering ini sangat cocok untuk data elevasi.

Operasi umum lainnya saat bekerja dengan raster adalah dengan memotong raster ke area yang Anda minati. Untuk tutorial ini, kami akan mengklip layer gabungan ke batas negara untuk Sri Lanka. Temukan file ne_10m_admin_0_countries.zip yang diunduh dan perluas. Seret file ne_10m_admin_0_countries.shp ke kanvas.

Pilih layer ne_10m_admin_0_countries yang baru ditambahkan di panel Layers. Klik tombol Select Features by area atau single click pada Attributes Toolbar. Setelah dipilih, klik poligon Sri Lanka untuk memilihnya.

Tetap pilih apa adanya dan buka Processing ‣ Toolbox. Cari dan temukan GDAL ‣ Ekstraksi raster ‣ Klip raster dengan alat lapisan topeng. Klik dua kali untuk meluncurkannya.

Dalam dialog Clip Raster by Mask Layer, atur OUTPUT sebagai Input Layer. Pilih ne_10m_admin_0_countries sebagai layer Mask, dan centang kotak Selected features only. Masukkan 0,0000 sebagai Menetapkan nilai nodata yang ditentukan ke pita keluaran. Seperti sebelumnya, pilih Kompresi tinggi sebagai Profil. Klik Run.

OUTPUT layer baru akan ditambahkan ke panel Layers. Pada titik ini, mungkin sulit untuk melihat hasilnya karena kita memiliki terlalu banyak lapisan yang tumpang tindih. Klik tombol Kelola Tema Peta di panel Lapisan dan pilih Sembunyikan Semua Lapisan.

Nyalakan hanya layer OUTPUT terbaru dan gayakan dengan renderer Hilshade seperti yang dilakukan sebelumnya.

Lapisan elevasi keluaran gabungan dan subset untuk Sri Lanka sudah siap.
