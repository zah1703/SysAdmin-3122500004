# TUGAS 6

# Disusun Oleh

| NAMA | NRP |
| ---- | --- |
| [Zahrotul Hidayah]| 3122500018 | 

**DAFTAR ISI**

1. [Web Server](#web-server)
2. [Web Browser Architecture](#web-browser-architecture)
3. [Web Server menggunakan Docker](#web-server-menggunakan-docker)
4. [Apache2 + Dns Resolver + Docker Uptime Kuma Package](#4-apache2--dns-resolver--docker-uptime-kuma-package)


# 1. Web Server
![Gambar Web Server](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/Web%20Server.drawio.png)

Web server adalah aplikasi perangkat lunak atau perangkat keras yang menyimpan, memproses, dan melayani konten web kepada pengguna melalui internet. Web server memainkan peran penting dalam model klien-server dari World Wide Web, di mana klien (biasanya browser web) meminta halaman web dan sumber daya, dan server merespons permintaan ini dengan mengirimkan konten yang diminta.

Proses yang terjadi di server web

1. Permintaan dan Respon HTTP
2. Penanganan Permintaan
3. Pemrosesan Server-Side
4. Penyimpanan Konten
5. Keamanan
6. Logging dan Pelaporan

# 2. Web Browser Architecture

![Gambar Web Browser](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/Web%20Browser.drawio.png))

The user interface: Antarmuka pengguna browser dirancang agar memungkinkan personalisasi, karena setiap individu memiliki minat yang berbeda. Personalisasi ini dicapai dengan menyediakan fitur dasar seperti grup, koleksi, bookmark, dan tema. Setiap browser dapat memiliki antarmuka pengguna dan fitur yang berbeda.

Browser Engine: Bertanggung jawab untuk mengoordinasikan konten web yang diambil dari server dan interaksi pengguna. Ini mencatat tombol mana yang diklik, URL mana yang diminta untuk diurai, dan bagaimana konten web akan diproses dan ditampilkan di browser.

Rendering Engine: Menginterpretasikan dan merender konten web. Rendering engine bekerja sama untuk memberikan hasil yang lebih baik kepada pengguna.

Networking Layer: Menangani bagian komunikasi. Ketika pengguna memasukkan atau mengklik URL, Networking Layer memulai permintaan HTTP ke server web untuk memuat halaman web yang diminta. Ini juga mengelola pengambilan sumber daya dari file HTML, gambar, stylesheet, dan lainnya.

JavaScript Engine: Komponen inti dari arsitektur browser, dengan kemampuan untuk memanipulasi konten web dan menghadirkan perilaku dinamis di halaman web.

Data Storage: Sebagian besar browser digunakan untuk menyimpan berbagai jenis data, yang meliputi tidak hanya preferensi pengguna, riwayat penelusuran, kata sandi, tetapi juga pembaruan data reguler (alamat, nama, dan kontak).

UI backend: Menyediakan perilaku dinamis dan interaktif pada halaman web dan meningkatkan fungsionalitas dan kinerja keseluruhan browser.

# 3. Web Server menggunakan docker

Langkah-langkah

1. Pemasang Docker di Debian vmBox
Hapus paket-paket terkait Docker bawaan !

![for apt ](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/1.%20for%20docker.png))

2. Lakukan Update/Upgrade Repository dan tambahkan Docker's official GPG key:

![apt-get update](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/2.%20apt%20get%20update.png)

![curl](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/3.install%20certificates%20curl.png)

![keyrings](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/4.keyrings.png)

![fsSL](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/5.%20curl%20fsSL.png)

![chmod a+r](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/6.chmod%20a%2Br.png)

![echo panjang](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/7.echo%20puanjangg.png)

3. Install DOCKER OFFICIAL PACKAGE

![Docker Package](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/8.%20install%20docker%20packages.png)

4. Apabila Docker Sudah Terpasang, Coba jalankan Hello World

![Hello World](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/9.docker%20run%20hello%20world.png)

## 3.1 Membuat Docker Image

1. Buat File dengan Konfigurasi Berikut Buat file bernama Dockerfile

![mynginx directory](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/10.%20membuat%20directory%20mynginx.png)

    > from nginx:alpine

    > COPY index.html /usr/share/nginx/html
    EXPOSE 80
   
    >CMD ["nginx", "-g", "daemon off;"]

![isi Dockerfile](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/11.isi%20didalam%20Dockerfile.png)

![Tulis Echo ](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/12.tulis%20echo%20Hello%20C307.png)

2. Build Ke dalam Docker IMAGES

    > sudo docker build -t contoh .

![Build](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/13.%20build%20ke%20dalam%20Docker%20IMAGES.png)

3. Jalankan DOCKER IMAGES

    >  sudo docker run -d -p 8080:80 contoh

![Port 8080](https://github.com/zah1703/SysAdmin-3122500004/blob/main/Tugas%206/assets/14.%20docker%20run%20port%208080.png)

4. Berhasil!, akses port 8080

![Run di browser](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/15.berhasil%20port%208080.png)


# 4. Apache2 + Dns Resolver + Docker Uptime Kuma Package

Langkah-langkah:

1. Git Clone Uptime Kuma dahulu

    > git clone https://github.com/louislam/uptime-kuma.git

    > cd uptime-kuma

2. Lalu Jalankan dengan cara berikut

    >  sudo docker compose up

3. Cek running container dan pastikan berjalan

![Running uptime kuma](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/16.%20sudo%20docker%20ps-a.png)

4. Cek pada browser dengan port yaitu 3001

![Running pada port 3001](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/17.%20running%20uptime%20kuma.png)

TASK

Lalu Bagaimana jika menggunakan url monitoring.kelompok8.local ?

1. Konfigurasi file /var/lib/bind/db.kelompok8.local

    Tambahkan monitoring pada CNAME ns dan jangan lupa ubah version file + date, kemudian lakukan restart

    sudo sytemctl restart named

![konfigurasi file db.kelompok8.local](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/18.%20tambahkan%20monitoring%20di%20db.kelompok8.local.png)

2. Untuk melakukan pointing ke domain localhost kita, kita gunakan ReverseProxy pada Apache2 Kita ( a2enmod )


Install Beberapa Package Berikut dengan menjalankan perintah berikut:

> sudo a2enmod

Masukkan Package berikut "proxy proxy_ajp proxy_http rewrite deflate headers proxy_balancer proxy_connect proxy_html"

![proxy-proxy](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/19.%20package%20yang%20proxy2.png)

3. Lakukan Konfigurasi pada Apache2 Kita

> /etc/apache2/sites-enabled/000-default.conf

![sudo](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/20.%20setting%20enabled.png)

Tambahkan baris berikut untuk monitoring subdomain

![Baris monitoring](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/21.%20tambah%20baris%20monitoring.png)


Berhasil tes monitoring.kelompok8.local
![Running di web](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_6/assets/22.test%20di%20web.png)
