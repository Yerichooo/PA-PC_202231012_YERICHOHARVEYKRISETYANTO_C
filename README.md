# PA-PC_202231012_YERICHOHARVEYKRISETYANTO_C

import cv2
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
import skimage
-----Penjelasan:-----
> import cv2
Modul OpenCV untuk Python yang digunakan untuk pemrosesan gambar dan video. Dengan mengimpor modul ini, Anda dapat menggunakan fungsi-fungsi yang disediakan oleh OpenCV untuk berbagai tugas pengolahan citra.
> import numpy as np
 Modul NumPy yang digunakan untuk operasi matematika tingkat tinggi dan manipulasi array.
> import matplotlib.pyplot as plt
Modul Matplotlib untuk Python yang digunakan untuk membuat visualisasi data, seperti grafik dan plot. pyplot adalah submodul dari Matplotlib yang menyediakan antarmuka seperti MATLAB untuk membuat grafik.
> %matplotlib inline
Magic command di Jupyter Notebook yang digunakan untuk memastikan bahwa grafik yang dibuat oleh Matplotlib akan ditampilkan langsung di dalam notebook.
> import skimage
library open-source yang didasarkan pada NumPy, dan menyediakan berbagai fungsi untuk analisis citra yang lebih lanjut dan spesifik dibandingkan OpenCV
---------------------
img = cv2.imread('Yericho Gans.jpg')
-----Penjelasan:-----
> img
Variabel ini akan menyimpan data gambar yang dihasilkan dari pembacaan file gambar.
> cv2.imread('Yericho Gans.jpg')
Fungsi cv2.imread dari OpenCV digunakan untuk membaca file gambar yang namanya adalah 'Yericho Gans.jpg'. Fungsi ini membaca gambar dan mengembalikannya sebagai array NumPy.
---------------------
cv2.imshow("Yericho", img)
cv2.waitKey(0)
cv2.destroyAllWindows()
-----Penjelasan:-----
> cv2.imshow("Yericho", img)
Menampilkan gambar yang tersimpan dalam variabel img di sebuah jendela bernama "Yericho".
> cv2.waitKey(0)
Menunggu sampai ada tombol yang ditekan. Angka 0 berarti program akan menunggu tanpa batas waktu.
> cv2.destroyAllWindows()
Menutup semua jendela yang dibuka oleh OpenCV.
---------------------
cv2.imshow("Yericho 2", edges)
cv2.waitKey(0)
cv2.destroyAllWindows()
-----Penjelasan:-----
> cv2.imshow("Yericho 2", edges)
Menampilkan gambar yang tersimpan dalam variabel edges di sebuah jendela bernama "Yericho 2". edges biasanya berisi hasil dari proses edge detection (deteksi tepi) seperti Canny edge detection.
> cv2.waitKey(0)
Menunggu sampai ada tombol yang ditekan. Angka 0 berarti program akan menunggu tanpa batas waktu.
> cv2.destroyAllWindows()
Menutup semua jendela yang dibuka oleh OpenCV.
---------------------
fig, axs = plt.subplots(1,2, figsize =(20,10))
ax = axs.ravel()

ax[0].imshow(img_rgb)
ax[0].set_title("Original")

ax[1].imshow(edges, cmap = "gray")
ax[1].set_title("Canny Edge")
-----Penjelasan:-----
> fig, axs = plt.subplots(1, 2, figsize=(20, 10))
Membuat sebuah figure dengan dua subplot yang diatur secara horizontal (1 baris dan 2 kolom).
> ax = axs.ravel()
Mengubah array 2D axs menjadi array 1D.
> ax[0].imshow(img_rgb)
Menampilkan gambar img_rgb pada subplot pertama (ax[0]). img_rgb adalah variabel yang berisi gambar dalam format RGB.
> ax[0].set_title("Original")
Memberi judul "Original".
> ax[1].imshow(edges, cmap="gray")
Menampilkan gambar edges pada subplot kedua (ax[1]) dengan colormap grayscale.
> ax[1].set_title("Canny Edge")
Memberi judul "Canny Edge".
---------------------
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
-----Penjelasan:-----
> img_rgb
Variabel yang akan menyimpan gambar yang telah dikonversi dari format BGR ke RGB.
> cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
Fungsi cvtColor dari OpenCV digunakan untuk mengkonversi ruang warna gambar.
---------------------
edges = cv2.Canny(img, 100, 150)
-----Penjelasan:-----
> edges: Variabel yang akan menyimpan hasil dari deteksi tepi menggunakan algoritma Canny.
> cv2.Canny(img, 100, 150): Fungsi Canny dari OpenCV digunakan untuk melakukan edge detection pada gambar img.
---------------------
contours, _ = cv2.findContours(edges, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
-----Penjelasan:-----
> Mendeteksi kontur dalam gambar edges dan menyimpannya dalam variabel contours. Kontur yang ditemukan hanya yang terluar dan disederhanakan untuk menghemat memori.
---------------------
ig, axs = plt.subplots(1, 3, figsize=(20, 10))
axs[0].imshow(img_rgb)
axs[0].set_title("Original Image")

axs[1].imshow(edges, cmap='gray')
axs[1].set_title("Canny Edge")

axs[2].imshow(img_contours)
axs[2].set_title("Contours Detection")

plt.show()
-----Penjelasan:-----
> fig, axs = plt.subplots(1, 3, figsize=(20, 10))
Membuat sebuah figure dengan tiga subplot yang disusun secara horizontal (1 baris dan 3 kolom).
> axs[0].imshow(img_rgb) Menampilkan gambar asli (img_rgb) pada subplot pertama (axs[0]).
axs[0].set_title("Original Image") Memberi judul "Original Image" pada subplot pertama (axs[0]).
> axs[2].imshow(img_contours) Menampilkan gambar yang telah ditambahkan kontur (img_contours) pada subplot ketiga (axs[2]).
> axs[2].set_title("Contours Detection") Memberi judul "Contours Detection" pada subplot ketiga (axs[2]).
> plt.show()
Menampilkan keseluruhan figure dengan subplot-subplotnya.

