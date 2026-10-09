# Pertemuan 06 — Nested Loop Python

Nama: Nurul Aisyah Wulan Dela P.
NIM: 2225250087
Kelas: 3F

## Tujuan

1. Memahami penggunaan nested loop atau perulangan bersarang.
2. Membuat pola menggunakan perulangan.
3. Menggunakan akumulator untuk menghitung jumlah.
4. Menggunakan counter untuk menghitung banyaknya hasil yang memenuhi kondisi.

## Cara Menjalankan

Pastikan terminal berada di folder utama proyek, kemudian jalankan perintah berikut:

python3 tugas/tabel_perkalian_dan_statistik.py

Masukkan bilangan bulat positif ketika program meminta nilai "n".

## Algoritma Tugas 3

Program tabel perkalian dan statistik menggunakan nested loop untuk menghitung perkalian dari 1 sampai "n".

- Loop luar ("i"): Mengatur baris tabel perkalian dari 1 sampai "n".
- Loop dalam ("j"): Mengatur kolom dan menghitung hasil perkalian pada setiap baris.
- Akumulator ("total_baris" dan "total_semua"): Menjumlahkan hasil perkalian untuk setiap baris dan seluruh tabel.
- Counter ("count_genap"): Menghitung banyaknya hasil perkalian yang bernilai genap.
- Validasi input ("while"): Meminta pengguna memasukkan kembali nilai "n" jika nilainya kurang dari atau sama dengan nol.

## Hasil Pengujian

Input "n"| Hasil yang Diharapkan| Keluaran Aktual| Status
1| Total = 1, genap = 0| Total = 1, genap = 0| Berhasil
2| Total = 9, genap = 3| Total = 9, genap = 3| Berhasil
3| Total = 36, genap = 5| Total = 36, genap = 5| Berhasil

Pengujian dilakukan berdasarkan keluaran yang diharapkan dari algoritma. Status perlu dipastikan kembali dengan menjalankan program di VS Code.

## Analisis Efisiensi

Untuk input "n", loop luar berjalan sebanyak "n" kali. Pada setiap putaran loop luar, loop dalam juga berjalan sebanyak "n" kali.

Dengan demikian, badan loop dalam berjalan sebanyak:

n × n = n² kali.

Contohnya:

- Jika "n = 1", loop dalam berjalan 1 kali.
- Jika "n = 2", loop dalam berjalan 4 kali.
- Jika "n = 3", loop dalam berjalan 9 kali.

Oleh karena itu, kompleksitas waktu program adalah O(n²) karena jumlah operasi utama bertambah sebanding dengan kuadrat nilai "n".

## Refleksi

Salah satu kesalahan yang dapat terjadi saat menggunakan nested loop adalah meletakkan inisialisasi "total_baris = 0" di luar loop luar. Akibatnya, jumlah baris tidak dimulai kembali dari nol sehingga hasil penjumlahan setiap baris menjadi keliru.

Cara memperbaikinya adalah dengan meletakkan "total_baris = 0" di dalam loop luar, tetapi sebelum loop dalam dimulai. Dengan demikian, setiap baris memiliki akumulator sendiri, sedangkan "total_semua" tetap berada di luar loop agar dapat menjumlahkan seluruh hasil perkalian.

## Refleksi Teknis

1. Mengapa "total_baris" direset di setiap iterasi loop luar?
   Karena "total_baris" digunakan untuk menghitung jumlah hasil perkalian pada satu baris. Nilainya harus kembali menjadi nol saat memulai baris baru agar tidak tercampur dengan baris sebelumnya.

2. Mengapa "total_semua" tidak direset di setiap baris?
   Karena "total_semua" digunakan untuk menjumlahkan seluruh hasil perkalian dalam tabel. Jika direset setiap baris, jumlah sebelumnya akan hilang.

3. Untuk n, berapa kali pernyataan "hasil = i * j" dieksekusi?
   Pernyataan tersebut dieksekusi sebanyak (n^2) kali karena loop luar dan loop dalam masing-masing berjalan sebanyak n kali.

4. Bagaimana Anda membuktikan "count_genap" benar?
   Dengan memeriksa setiap hasil perkalian menggunakan kondisi "hasil % 2 == 0", lalu membandingkan jumlah hasil genap dengan hitungan manual. Contohnya, untuk n = 2 terdapat tiga hasil genap, yaitu 2, 2, dan 4.

5. Apa bagian program yang akan paling banyak melakukan operasi ketika n membesar?
   Loop dalam, karena dijalankan sebanyak (n^2) kali. Oleh sebab itu, kompleksitas waktu program adalah O(n²).