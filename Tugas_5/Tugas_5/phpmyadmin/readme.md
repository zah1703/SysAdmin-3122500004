# Install phpmyadmin

## 1. Install phpmyadmin
```sudo apt -y install phpmyadmin```
Konfigurasi installasi
- Pilih web server yang digunakan, pada contoh ini menggunakan apache2
  
  ![pilih web server](./img/37ok.png)

- Pilih configure database for phpmyadmin dengan dbconfig-common
  
  ![configure database](./img/38ok.png)

- Masukkan password root phpmyadmin dan konfirmasi password root phpmyadmin
  ![password root mysql](./img/39ok.png)
 

## 2. Konfigurasi phpmyadmin pada apache2
```sudo nano /etc/apache2/apache2.conf```

![apache2.conf](./img/40ok.png)

Tambahkan baris berikut pada file konfigurasi apache2 di bagian paling bawah
```
Include /etc/phpmyadmin/apache.conf
```
![include phpmyadmin](./img/41ok.png)

## 3. Restart apache2
```sudo systemctl restart apache2```

![restart apache2](./img/42ok.png)
