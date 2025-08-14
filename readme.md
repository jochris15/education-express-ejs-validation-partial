# Validation & EJS Partial

## Validation
Konteks validasi dalam aplikasi kita yang menggunakan Express.js, EJS dan node-postgres adalah memastikan bahwa pada saat user mau menambahkan / mengupdate data, data tersebut sudah sesuai dengan kriteria yang kita inginkan. Misalnya, jika kita ingin menambahkan data game, kita perlu memastikan bahwa semua field yang diperlukan terisi dengan benar dan sesuai format yang diinginkan.

Step by step validation : 
1. Pada file `/models/index.js` buatlah static method `validation` yang akan kita gunakan untuk melakukan validasi data yang akan ditambahkan atau diupdate. Method ini akan menerima parameter data yang akan di input.
2. Di dalam method `validation`, kita akan melakukan pengecekan terhadap setiap field yang diperlukan. Jika ada field yang tidak sesuai, kita akan melempar error dengan pesan yang sesuai.
3. Gunakan method `validation` ini pada route yang menangani penambahan atau pengupdatean data. Misalnya, pada route untuk menambahkan data game, kita akan memanggil method ini sebelum menyimpan data ke database.
4. Jika validasi gagal, kita akan mengirimkan pesan error dan ditampilkan pada halama EJS.

## EJS Partial
EJS Partial adalah fitur yang memungkinkan kita untuk membuat bagian-bagian dari halaman EJS yang dapat digunakan kembali di berbagai tempat dalam aplikasi kita. Ini sangat berguna untuk menghindari duplikasi kode dan membuat kode lebih terstruktur.

Step by step EJS Partial :
1. Buatlah file EJS baru di dalam folder `views/partials` yang akan berisi bagian-bagian yang ingin kita gunakan kembali. Misalnya, kita bisa membuat file `errors.ejs` untuk menampilkan pesan error validasi. 
2. Di dalam file `errors.ejs`, kita akan menuliskan kode untuk menampilkan pesan error yang diterima dari controller. Misalnya, kita bisa menggunakan loop untuk menampilkan setiap pesan error dalam sebuah list.
3. Pada file EJS yang ingin menggunakan partial ini, kita akan menggunakan tag `<%- include('partials/errors') %>` untuk menyertakan file `errors.ejs` yang telah kita buat.