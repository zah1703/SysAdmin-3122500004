# Konfigurasi Roundcube

1. Create Database
   ![roundcube](./img/R1.png)
2. Configure install and choose no
   ![roundcube](./img/R2.png)
3. Set database info
   ![roundcube](./img/R3.png)
   
4. File config.inc.php
   
   ![roundcube](./img/R4.png)

   ```add dipaling bawah```
   
   ![roundcube](./img/R5.png)

5. Uncomment file/etc/apache2/conf-enabled/rouncube.conf
   ![roundcube](./img/R6.png)
   
6. Ganti config di /etc/apache2/mods-enabled/dir.conf
    
   ![roundcube](./img/R7.png)
   
7. Restart apache2
    
   ![roundcube](./img/R8.png)
   
8. Hasil
   ![roundcube](./img/hasil.png)


# Setting Mailserver untuk jaringan di Lab C307

1. Ubah pada setting network pada virtual machine ke Bridged Adapter dan ganti adapter sesuai dengan hasil command ipconfig/all yaitu Realtek USB FE Family Controller 2
  ![mailserver](./img/L1.png)

2. Rubah juga konfigurasi di sudo nano /etc/resolv.conf tambahkan nameserver 192.168.8.10 seperti dibawah berikut:
   ![mailserver](./img/L2.png)
3. Setelah itu coba tes ping IP kelompok lain yaitu kelompok 1 dengan command ping ns.kelompok1.local jika konfigurasi network benar maka maka hasilnya akan seperti berikut:
   ![mailserver](./img/L3.png)
4. Coba juga tes nslookup ke kelompok lain dengan command nslookup kelompok1.local jika konfigurasi network benar maka akan seperti dibawah ini:
   ![mailserver](./img/L4.png)
5. Buka browser dan coba test apakah bisa mengakses webmail (roundcube) kelompok lain disini saya mencoba mengakses ke webmail kelompok 2 dengan alamat mail.kelompok2.local Jika berhasil maka akan tampil seperti berikut:
   ![mailserver](./img/L5.png)
6. Buka browser dan coba test apakah bisa mengakses webmail (roundcube) dengan alamat mail.kelompok8.local/roundcube Jika berhasil maka akan tampil seperti berikut:
   ![mailserver](./img/L6.png)
7.  Jika network static tidak bekerja dan tidak bisa tampil seperti diatas maka coba buka sudo nano /etc/network/interfaces buat auto network dengan mengcomment konfigurasi static pada seperti dibawah ini:
   ![mailserver](./img/L7.png)
8. Lalu setup manual IPv4 dengan IP addres 192.168.8.10 netmask 255.255.255.0 gateway 192.168.4.1 dan DNS 10.10.10.1

9. Hasil Akhir
   Login ke rouncube dengan user dan password yang sudah disetup. pada kasus ini saya bisa mengirim dan menerima pesan dari user lain seperti pada gambar dibawah ini:
   ![mailserver](./img/L9a.png)
   ![mailserver](./img/L9b.png)
