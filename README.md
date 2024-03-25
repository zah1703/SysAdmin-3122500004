# DAFTAR TUGAS WORKSHOP ADMINISTRASI JARINGAN

| TUGAS | FILE |
| ------| -----|
| TUGAS 1| (Tugas_1) , [Sistem Operasi Debian](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas1.md) |
| TUGAS 2| (Tugas_2) , [MARP](Tugas_2/assets/2_Slide_SystemAdministrasi.md)|
| TUGAS 3| (Tugas_3) , [LINUX APT COMMAND](https://github.com/zah1703/Workshop-Administrasi-Jaringan/blob/main/Tugas_3/README.md)|
| TUGAS 5| (Tugas_4) , [DNS Query & Bin9](https://github.com/zah1703/SysAdmin-3122500004/tree/main/Tugas%204#3-config-bind9)|

# Disusun Oleh

| NAMA | NRP |
| ---- | --- |
| [Zahrotul Hidayah](https://github.com/zah1703)| 3122500004 |
| [Leody Zelvon Herliansa](https://github.com/Leodyz)| 3122500010 |
| [Adam Rasyid Nurmuhammad](https://github.com/adamrasyid01)| 3122500018 |                                   

# TUGAS 4

**DAFTAR ISI**

1. [Bagaimana Internet Bekerja (pribadi)](#bagaimana-internet-bekerja)
2. [DNS Query (pribadi)](#2-dns-query)
3. [BIND9 Kelompok 8](#3-config-bind9)


<p><h2>1. Tuliskan pendapatmu tentang bagaimana Internet bekerja</h2>
    
<p>Internet adalah jaringan global yang terdiri dari jaringan komputer yang saling terhubung di seluruh dunia. Prinsip dasar dari bagaimana Internet bekerja adalah melalui pertukaran data antara komputer-komputer yang terhubung melalui protokol komunikasi standar yang disebut TCP/IP (Transmission Control Protocol/Internet Protocol).

Berikut adalah langkah-langkah umum tentang bagaimana Internet bekerja:

1. Komputer dan Perangkat Terhubung: Pengguna menggunakan perangkat seperti komputer, ponsel, atau tablet untuk terhubung ke Internet melalui penyedia layanan Internet (ISP) atau jaringan lokal seperti Wi-Fi di rumah atau kantor.

2. Protokol TCP/IP: Data dikirimkan melalui Internet menggunakan protokol TCP/IP. TCP (Transmission Control Protocol) memastikan bahwa data dikirim dengan benar dan lengkap, sedangkan IP (Internet Protocol) mengatur pengiriman data ke tujuan yang tepat.

3. Paket Data: Data yang dikirimkan melalui Internet dipecah menjadi paket-paket kecil sebelum dikirim. Setiap paket data memiliki alamat tujuan dan informasi yang cukup untuk memandu mereka ke titik tujuan yang benar.

4. Router: Setiap paket data melalui berbagai router atau simpul jaringan yang bertugas untuk meneruskan paket data ke tujuan berikutnya. Routers ini berfungsi sebagai "jembatan" antara berbagai jaringan komputer di seluruh dunia.

5. DNS (Domain Name System): Ketika Anda memasukkan nama domain seperti "www.example.com" ke browser, DNS akan menerjemahkan nama domain tersebut menjadi alamat IP yang sesuai, yang kemudian digunakan untuk menemukan server yang menyimpan situs web tersebut.

6. Server dan Klien: Di ujung yang lain, ada server yang menerima permintaan dari klien (seperti browser web) untuk data atau layanan tertentu. Server ini mengirimkan responsnya kembali ke klien, yang kemudian ditampilkan kepada pengguna.

7. Koneksi Aman (Opsional): Untuk koneksi yang memerlukan keamanan tambahan, seperti saat bertransaksi online atau mengakses informasi sensitif, HTTPS (Hypertext Transfer Protocol Secure) digunakan. Ini melibatkan enkripsi data yang dikirimkan antara klien dan server, sehingga data tidak dapat dibaca oleh pihak yang tidak sah.

Proses ini berulang setiap kali Anda mengirim atau menerima data melalui Internet. Ini adalah cara dasar bagaimana Internet bekerja, menghubungkan jutaan perangkat dan sumber daya informasi di seluruh dunia.</p>

## 2. DNS Query

***Bagaimana Cara kerja dari iterative dan recursive dari DNS Query, ada 8 step, dari PC anda! misal akses detik.com***

Berdasarkan referensi [Penjelasan DNS](https://www.hostinger.co.uk/tutorials/what-is-dns)

**Query DNS**
![Gambar Cara kerja DNS](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/how-does-dns-work-1024x590.png)

- Langkah 1 : Klien memasukkan www.detik.com ke dalam browser dan menekan Enter. Sebuah DNS query untuk alamat IP (record a) dikirim oleh resolver sistem operasi ke server DNS.

- Langkah 2 : Server DNS menerima query dan mulai mencari melalui tabelnya (cache) untuk mencari alamat IP untuk www.detik.com. Namun, entri tersebut tidak ada dalam tabelnya.

- Langkah 3 : Server DNS akan memberikan respons berupa rujukan ke server root. 

- Langkah 4 : Resolver kemudian akan melakukan query ke server root untuk alamat IP tersebut.

- Langkah 5 : Resolver melakukan query ke server DNS TLD yang diberikan oleh server root untuk mencari informasi lebih lanjut mengenai alamat IP untuk "detik.com".

- Langkah 6 : Server DNS TLD memberikan informasi mengenai server DNS otoritatif yang bertanggung jawab atas domain "detik.com".

- Langkah 7 : Resolver melakukan query ke server DNS otoritatif untuk mendapatkan alamat IP yang diinginkan.

- Langkah 8 : Server DNS otoritatif merespons dengan memberikan alamat IP untuk "detik.com" kepada resolver.


> Perbedaan utama antara iterative DNS dan recursive DNS adalah pada proses pencarian informasi DNS. Iterative DNS meminta klien untuk melakukan query lebih lanjut secara bertahap, sementara recursive DNS melakukan proses query secara menyeluruh untuk klien.

# 3. Config BIND9

1. Instalasi  BIND 9

![Instalasi](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/1.sudoaptbind9.png)

2. Cek Instalasi di  /etc/bind
![Cek](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/2.cd_etc_bind%20ls-al.png)

3. Cek Konfigurasi utama bind di named.conf
![Cek named.conf](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/4.named_conf.png)
![less named.conf](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/3.less_named.conf.png)

4. Buka named.conf.local, untuk mengset atau konfigurasi zone file. Melakukan pengubahan zone sesuai nama kelompok.
![named.conf.local](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/5.nano_named_conf_local.png)

5. Buka named.conf.option, mengisi provider dan listen-on. Listen ditambahkan sesuai kelompok masing-masing
![named.conf.options](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/5.nano_named_conf_options.png)

6. Lakukan sudo named-checkconf untuk mengeck pesan error. jika tidak ada pesan error yang keluar itu berarti konfigurasi yang dilakukan telah benar
![named-checkconf](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/6.named_checkconf.png)

7. Pergi ke arah configuration zone file dengan mengetikkan cd /var/lib/bind

8. Masuk ke zone file pertama dan mengubah data di dalamnya.
![Zone File pertama](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/7.nano_dbkelompok8local.png)

9. Masuk ke zone file kedua (.inv) untuk mengubah data seperti file sebelumnya
![Zone File Kedua](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/8.nano_dbkelompok8localinv.png)

10. Cek dengan menggunakan perintah ls -al untuk memastikan kedua file telah terbuat
![ls -al](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/9.ls-al_setelahbuat_dbkelompok8local.png)

11. Lakukan sudo named-checkzone untuk mengetahui perubahan terakhir pada zone file dan inverse file. 
![named-checkzone](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/10.namedcheckzone_kelompok8.local_db.kelompok8.local.png)

12. Jalankan sudo systemctl restart named untuk menjalankan sistem bind.
![restart,status named](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/11.sudo_systemctl_restart%2Cstatus_named.png)

13. Pergi ke file /etc/resolv.conf untuk set DNS yang telah kita atur
![etc/resolv.conf](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/new12.sudo_nano_etcresolvconf.png)

14. Jalankan perintah sudo netstat -ptlun untuk menampilkan daftar koneksi jaringan yang aktif (baik incoming maupun outgoing) serta port yang sedang digunakan
![netstat](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/13.sudo_netstat_ptlun.png)

15. Gunakan perintah dig
![dig kelompok8.local](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/14.dig_kelompok8local.png)
![dig +x ip](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/15.dig-x_192.168.136.10.png)

16. Gunakan perintah nslookup untuk mengecek instalasi berhasil atau tidak
![nslookup ns.kelompok8.local](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_4/assets/16.nslookup%20nskelompok8local.png)


















