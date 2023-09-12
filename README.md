Tugas 1 Grafika Komputer - Lighting

Pada tugas kali ini terdapat 3 jenis lighting yang digunakan, 3 jenis lighting tersebut memiliki contoh code yang hampir sama, maka dari itu readme kali ini akan membahas 1 jenis lighting saja yakni directional lighting.

-- Directional Lighting

#index.html

<img width="305" alt="Screen Shot 2023-09-12 at 10 36 36" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/ce3ed651-f40d-4f9b-80de-46693fc2c65d">

Digunakan untuk menghubungkan ke file CSS eksternal yang disebut "style.css".

<img width="227" alt="Screen Shot 2023-09-12 at 10 49 43" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/3d061881-aa5b-455c-af5e-f8559736f76b">

Elemen HTML yang digunakan untuk membuat area gambar dengan menggambar elemen-elemen grafis secara dinamis. Elemen ini memiliki atribut "id" dengan nilai "canvas". Selanjutnya untuk div id="uiContainer" adalah elemen kotak yang memiliki atribut "id" dengan nilai "uiContainer", div id="ui"> adalah elemen kotak yang mungkin digunakan untuk menempatkan elemen-elemen antarmuka pengguna (UI) yang lebih spesifik dan div id="fRotation" adalah elemen kotak yang kemungkinan digunakan untuk menampilkan informasi atau kontrol rotasi (mungkin untuk objek 3D).

<img width="411" alt="Screen Shot 2023-09-12 at 10 53 32" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/6ce3750e-dbd0-4c0d-8bd5-659ae1e287af">

Pada code tersebut memiliki arti <script> yang mengandung kode Vertex Shader untuk mengubah posisi dan tampilan objek dalam tampilan 3D.

<img width="442" alt="Screen Shot 2023-09-12 at 10 55 43" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/7398ba91-73c1-4fdc-a35d-f9bdbc951a63">

Merupakan <script> yang mengandung kode Fragment Shader untuk mengendalikan warna dan pencahayaan dari objek dalam tampilan 3D.

<img width="660" alt="Screen Shot 2023-09-12 at 10 57 16" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/da6c1449-7806-46bd-aae8-6d227a1f7848">

Link tersebut merupakan sumber JavaScript eksternal yang digunakan dalam penyelesaian permasalahan lighting ini berisi utilitas atau fungsi yang dibutuhkan.

<img width="256" alt="Screen Shot 2023-09-12 at 10 57 21" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/3e0375ed-b8ec-464f-88e2-57457c1db449">

Elemen <script> yang menghubungkan kode JavaScript yang berfungsi untuk mengatur logika, interaktivitas, dan penggambaran objek dalam halaman web.

#script.js

<img width="360" alt="Screen Shot 2023-09-12 at 11 05 02" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/e9c795b7-9c95-4fdc-b244-d055504d5edf">

Dimulai dari cara untuk mendapatkan elemen dari halaman web dengan menggunakan metode document.querySelector() yang akan digunakan sebagai area tampilan WebGL. Selanjutnya var gl digunakan untuk mendapatkan konteks WebGL dari elemen canvas yang akan digunakan untuk berinteraksi dengan WebGL lalu dilakukan pengecekan sederhana untuk memastikan bahwa konteks WebGL berhasil diperoleh. Jika konteks WebGL tidak berhasil diperoleh, fungsi akan segera keluar.

<img width="727" alt="Screen Shot 2023-09-12 at 11 07 14" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/1cb74aa5-167c-4219-90b6-94370e5f1741">

Code ini adalah cara untuk membuat program WebGL dari dua script shader yang telah didefinisikan dalam elemen <script> dengan ID "vertex-shader-3d" dan "fragment-shader-3d". Hal ini akan digunakan untuk merender objek 3D.

<img width="501" alt="Screen Shot 2023-09-12 at 11 07 26" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/75917932-70a9-4700-ab0a-e376879d5e59">

Untuk code var cara untuk mendapatkan lokasi atribut "a_position" dari program shader. Ini digunakan untuk menghubungkan data posisi geometri ke shader sedangkan code var normalLocation cara untuk mendapatkan lokasi atribut "a_normal" yang akan digunakan untuk menghubungkan data normal geometri ke shader.

<img width="699" alt="Screen Shot 2023-09-12 at 11 10 11" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/91547b41-b464-4df5-9dec-1d147c08fb3b">

Code tersebut digunakan untuk mendapatkan lokasi uniform "u_worldViewProjection" yang akan digunakan untuk mengirim matriks transformasi ke shader.

<img width="548" alt="Screen Shot 2023-09-12 at 11 17 29" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/8cece29b-9622-4030-a2f6-8d666d49ff71">

Dalam kasus ini code tersebut merupakan cara untuk membuat buffer WebGL untuk data posisi geometri selanjutnya code dilanjutkan untuk mengikat buffer posisi yang baru dibuat sehingga data geometri dapat dimasukkan ke dalamnya. Di akhiri dengan panggilan fungsi yang akan mengisi buffer posisi dengan data geometri. Ini adalah data yang digunakan untuk menggambarkan objek 3D.

<img width="535" alt="Screen Shot 2023-09-12 at 11 17 37" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/e6f8bccc-5e03-4975-a958-216bbd69bc15">

Dalam kasus ini code tersebut merupakan cara untuk membuat buffer WebGL untuk data normal geometri selanjutnya code dilanjutkan untuk mengikat buffer normal yang baru dibuat sehingga data normal geometri dapat dimasukkan ke dalamnya. Di akhiri dengan panggilan fungsi yang akan mengisi buffer normal dengan data normal geometri.

<img width="294" alt="Screen Shot 2023-09-12 at 11 20 51" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/8e865d78-7522-46ad-9568-74aabd3dd6aa">

Kedua fungsi tersebut digunakan untuk mengonversi sudut antara derajat dan radian yang berguna saat menghitung matriks transformasi.

Selanjutnya code dilanjutnya dengan menjalankan 'drawScene(); yang merupakan fungsi untuk memulai proses menggambar adegan WebGL.

#style.css

<img width="598" alt="Screen Shot 2023-09-12 at 11 24 35" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/7b855e8f-171b-40de-b849-f3dd42cb0fd7">

Aturan untuk mengimpor file CSS eksternal dari URL yang diberikan. Dalam hal ini, itu mengimpor file "webgl-tutorials.css" dari situs web "https://webglfundamentals.org/webgl/resources/". Ini adalah cara untuk menggunakan CSS yang telah ditulis di lokasi eksternal.

<img width="99" alt="Screen Shot 2023-09-12 at 11 24 42" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/d631dd83-1547-4cc3-a887-6d49b59ff58c">

Aturan CSS yang mempengaruhi elemen <body> dari halaman HTML yang mengatur margin (jarak) dari elemen <body> menjadi 0, yang berarti tidak akan ada ruang tambahan di sekitar elemen tersebut.

<img width="141" alt="Screen Shot 2023-09-12 at 11 24 52" src="https://github.com/valenfajri18/Tugas1Grafkom/assets/114421539/fe9ad805-c015-4d4b-bb9e-c8495659495e">

Code tersebut untuk mengatur lebar elemen canvas menjadi 100% dari lebar tampilan (viewport) halaman, sehingga elemen ini akan mengisi seluruh lebar halaman, mengatur tinggi elemen canvas menjadi 100% dari tinggi tampilan halaman, sehingga elemen ini akan mengisi seluruh tinggi halaman dan mengatur elemen canvas untuk ditampilkan sebagai blok. Hal tersebut berguna untuk memastikan bahwa elemen canvas memiliki lebar penuh dan tidak memiliki tinggi tambahan yang biasanya terkait dengan elemen inline.
