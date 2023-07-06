# UAS_PENGCIT_E

Teori deteksi bentuk gambar menggunakan contour dalam pengolahan citra adalah salah satu pendekatan untuk mengidentifikasi dan mengklasifikasikan objek berdasarkan fitur kontur atau tepi yang ada dalam citra. Pendekatan ini didasarkan pada pemahaman bahwa kontur atau tepi objek sering kali memberikan informasi penting tentang bentuk, struktur, dan karakteristik objek tersebut.

Berikut adalah langkah-langkah umum dalam teori deteksi bentuk gambar menggunakan contour pada pengolahan citra:

Praproses Citra: Langkah pertama dalam pengolahan citra adalah melakukan praproses untuk meningkatkan kualitas citra. Ini dapat melibatkan penghilangan derau, penerapan operasi perataan, peningkatan kontras, dan normalisasi citra.
Segmentasi Citra: Setelah praproses, citra perlu disegmentasi untuk memisahkan objek dari latar belakang. Metode segmentasi yang umum digunakan meliputi metode berdasarkan ambang (thresholding), pemisahan berdasarkan warna atau tekstur, dan segmentasi berbasis wilayah.
Ekstraksi Kontur: Setelah segmentasi, langkah selanjutnya adalah mengekstraksi kontur objek dari citra. Kontur adalah tepi yang membentuk batas objek. Algoritma yang umum digunakan untuk mengekstraksi kontur adalah Algoritma Canny, Algoritma Sobel, atau Algoritma Roberts. Algoritma ini mengidentifikasi perubahan intensitas citra yang signifikan dan menghasilkan tepi objek yang halus.
Penyaringan Kontur: Setelah ekstraksi kontur, kontur yang dihasilkan mungkin mengandung noise atau tidak relevan dengan bentuk objek yang diinginkan. Oleh karena itu, langkah berikutnya adalah menerapkan penyaringan untuk menghilangkan kontur yang tidak relevan. Filter spasial seperti filter median atau filter Gaussian dapat digunakan untuk menghilangkan noise dan mempertahankan kontur yang penting.
Deskripsi Kontur: Setelah kontur difilter, langkah selanjutnya adalah mendeskripsikan kontur yang diekstraksi untuk memperoleh fitur yang berguna. Fitur kontur dapat mencakup panjang kontur, luas area tertutup oleh kontur, rasio panjang-lebar, momen, atau bentuk deskriptor seperti Fourier deskriptor atau deskriptor Fourier Transformasi Gelombang Diskrit (DFT).
Klasifikasi Objek: Setelah fitur kontur diperoleh, langkah terakhir adalah mengklasifikasikan objek berdasarkan fitur-fitur ini. Metode klasifikasi yang umum digunakan termasuk metode berbasis aturan, seperti template matching atau jaringan syaraf tiruan, dan metode berbasis pembelajaran, seperti klasifikasi SVM (Support Vector Machine) atau metode pengklasifikasi berbasis pohon keputusan.
Pendekatan deteksi bentuk gambar menggunakan contour pada pengolahan citra ini dapat digunakan dalam berbagai aplikasi, seperti pengenalan wajah, pengenalan karakter tulisan tangan, pengenalan objek pada sistem pengawasan video, dan banyak lagi.

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
