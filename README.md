# UAS_PENGCIT_E

Teori yang mendukung mengenai project terkait

 Projek di atas menggunakan teknik deteksi kontur untuk mendeteksi bentuk pada gambar. Berikut adalah teori yang mendukung projek tersebut:
Grayscale Conversion:
Pertama, gambar asli dikonversi ke dalam skala abu-abu (grayscale) menggunakan fungsi cv2.cvtColor() dengan mode konversi cv2.COLOR_BGR2GRAY. Konversi ini mengubah gambar menjadi citra dengan tingkat keabuan, di mana setiap piksel hanya memiliki nilai intensitas keabuan tunggal yang merepresentasikan tingkat kecerahan piksel tersebut.
Thresholding:Setelah konversi ke citra grayscale, thresholding diterapkan menggunakan fungsi cv2.threshold(). Thresholding memisahkan piksel menjadi dua kategori berdasarkan ambang batas tertentu. Piksel dengan intensitas di atas ambang batas akan diubah menjadi putih, sedangkan piksel dengan intensitas di bawah ambang batas akan diubah menjadi hitam. Dalam contoh ini, ambang batasnya adalah 127, dan piksel dengan intensitas di atas 127 akan menjadi putih (255), sedangkan piksel dengan intensitas di bawah 127 akan menjadi hitam (0).
Mendapatkan Kontur:
Setelah thresholding, fungsi cv2.findContours() digunakan untuk mendapatkan kontur dari gambar biner (hasil thresholding). Fungsi ini mengembalikan daftar kontur dan hirarki yang berhubungan dengan kontur tersebut. Parameter cv2.RETR_EXTERNAL digunakan untuk mengambil kontur eksternal, yang mengabaikan kontur dalam objek. Parameter cv2.CHAIN_APPROX_SIMPLE digunakan untuk mengompres kontur menjadi representasi yang lebih sederhana dan menghemat memori.

Menggambar Kontur pada Gambar Asli:
Kontur yang ditemukan kemudian digambar pada gambar asli menggunakan fungsi cv2.drawContours(). Dalam contoh ini, warna kontur adalah (0, 255, 0) yang mewakili warna hijau, dan ketebalan kontur adalah 2 piksel.
Menampilkan Gambar:
Terakhir, gambar asli dan gambar dengan kontur ditampilkan menggunakan Matplotlib. Fungsi plt.imshow() digunakan untuk menampilkan gambar dengan memastikan representasi warna yang tepat menggunakan cv2.cvtColor(). Subplot digunakan untuk menampilkan kedua gambar secara berdampingan dalam satu jendela. Fungsi plt.tight_layout() digunakan untuk memastikan tata letak yang rapi, dan plt.show() digunakan untuk menampilkan jendela dengan gambar.
Dengan menggunakan deteksi kontur, kita dapat mengidentifikasi dan memvisualisasikan bentuk atau objek dalam gambar berdasarkan perbedaan intensitas piksel dan hubungan spasial antara piksel-piksel tersebut.


Menjekaskan tahapan/cara menyelesaikan project dengan  rinci.

Berikut adalah tahapan cara menyelesaikan projek tersebut secara rinci:
Membaca Gambar:
Langkah pertama adalah membaca gambar menggunakan fungsi cv2.imread(). Nama file gambar yang ingin dibaca disertakan sebagai argumen.
Konversi ke Grayscale:
Gambar yang telah dibaca dikonversi ke skala abu-abu (grayscale) menggunakan fungsi cv2.cvtColor(). Citra grayscale hanya memiliki satu saluran warna yang merepresentasikan tingkat kecerahan piksel.
Thresholding:
Setelah konversi ke grayscale, langkah selanjutnya adalah menerapkan thresholding. Fungsi cv2.threshold() digunakan untuk ini. Dalam contoh ini, thresholding diterapkan dengan ambang batas 127. Piksel dengan intensitas di atas 127 akan diubah menjadi putih (255), sedangkan piksel dengan intensitas di bawah 127 akan diubah menjadi hitam (0).
Mendapatkan Kontur:
Kontur diambil dari gambar hasil thresholding menggunakan fungsi cv2.findContours(). Fungsi ini mengembalikan daftar kontur dan hirarki yang terkait dengan kontur tersebut. Parameter cv2.RETR_EXTERNAL digunakan untuk mendapatkan kontur eksternal saja, dan parameter cv2.CHAIN_APPROX_SIMPLE digunakan untuk mengompres kontur menjadi representasi yang lebih sederhana.
Menggambar Kontur pada Gambar Asli:
Setelah mendapatkan kontur, kontur tersebut digambar pada gambar asli dengan menggunakan fungsi cv2.drawContours(). Kontur digambar dengan warna hijau (0, 255, 0) dan ketebalan garis 2 piksel.
Menampilkan Gambar:
Terakhir, gambar asli dan gambar dengan kontur ditampilkan menggunakan Matplotlib. Gambar asli ditampilkan dalam subplot pertama, dan gambar dengan kontur ditampilkan dalam subplot kedua. Fungsi plt.imshow() digunakan untuk menampilkan gambar dengan memastikan representasi warna yang tepat menggunakan cv2.cvtColor(). Setelah menampilkan gambar, plt.tight_layout() digunakan untuk memastikan tata letak yang rapi, dan plt.show() digunakan untuk menampilkan jendela dengan gambar.

Dengan langkah-langkah tersebut, projek ini dapat mendeteksi kontur atau bentuk pada gambar dan memvisualisasikannya dalam gambar yang telah digambar
