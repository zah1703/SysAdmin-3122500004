# Install phpmyadmin

## 1. Install phpmyadmin
```sudo apt -y install phpmyadmin```
Konfigurasi installasi
- Pilih web server yang digunakan, pada contoh ini menggunakan apache2
  
  ![pilih web server](./img/1.1.jpg)

- Pilih configure database for phpmyadmin dengan dbconfig-common
  
  ![configure database](./img/1.2.jpg)

- Masukkan password root phpmyadmin dan konfirmasi password root phpmyadmin
  ![password root mysql](./img/1.3.jpg)
  ![konfirmasi password root mysql](./img/1.4.jpg)


## 2. Konfigurasi phpmyadmin pada apache2
```sudo nano /etc/apache2/apache2.conf```

![apache2.conf](./img/2.1.jpg)

Tambahkan baris berikut pada file konfigurasi apache2 di bagian paling bawah
```
Include /etc/phpmyadmin/apache.conf
```
![include phpmyadmin](./img/2.2.jpg)

## 3. Restart apache2
```sudo systemctl restart apache2```

![restart apache2](./img/3.jpg)

## 4. Akses phpmyadmin
Buka browser dan akses phpmyadmin dengan alamat http://kelompok3.local/phpmyadmin

![phpmyadmin](./img/4.1.jpg)

Masukkan username dan password root mysql yang telah diatur sebelumnya
contoh:
- username: phpmyadmin
- password: 123

![login phpmyadmin](./img/4.2.jpg)

## 5. menambahkan privilege user phpmyadmin
- login ke mysql ```mysql -u root -p```
- tambahkan privilege user phpmyadmin
```
GRANT ALL PRIVILEGES ON *.* TO 'phpmyadmin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```
Hasilnya kita dapat mengatur database melalui phpmyadmin
![phpmyadmin](./img/5.jpg)