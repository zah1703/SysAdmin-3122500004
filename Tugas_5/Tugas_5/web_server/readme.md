# Konfigurasi Web Server (apache2) dan PHP fpm

## 1. Install apache2 dan php-fpm
```sudo apt-get install apache2 -y```

![apache2](./img/8ok.png)

## 2. Konfigurasi apache2
Lakukan konfigurasi security apache2
- ```sudo nano /etc/apache2/conf-enabled/security.conf```
  
   Ubah bagian ```ServerTokens``` menjadi ```Prod```

    ![ServerTokens](./img/9ok.png)
  
Lakukan konfigurasi directory apache2 
- ```sudo nano /etc/apache2/mods-enabled/dir.conf```
  
    Ubah bagian ```DirectoryIndex``` menjadi ```index.html index.htm```

  ![Directory](./img/10ok.png)

  Tambahkan virtual host yang sudah disiapkan berdasarkan Canonical Name (CNAME) yang sudah dibuat (kelompok8.local)

- ```sudo nano /etc/apache2/apache2.conf```
 
  Tambahkan ServerName www.kelompok8.local

  ![VirtualHost](./img/11ok.png)

  Ubah Kontak email admin menjadi email webmaster@kelompok8.local
- ```sudo nano /etc/apache2/sites-available/000-default.conf```
  
  Ubah bagian ```webmaster@localhost``` menjadi ```webmaster@kelompok8.local```

  ![Admin](./img/12ok.png)


## 3. Restart apache2 dan cek status apache2
```sudo systemctl restart apache2```
```sudo systemctl status apache2```

![Restart](./img/13ok.png)


## 4. Lakukan Pengujian di browser
Buka browser dan ketikkan alamat www.kelompok3.local

![Browser](./img/14ok.png)

## 5. Install PHP dan extensi mbstring serta lakukan pengujian
- fungsi mbstring digunakan untuk memanipulasi string atau text non  ASCII
```sudo apt -y install php8.2 php8.2-mbstring php-pear```
```php -v```

  ![PHP](./img/15ok.png)
  ![PHP](./img/16ok.png)

- buat file php_info.php di /var/www/html
```sudo nano /var/www/html/php_info.php```
  ![PHP](./img/17ok.png)

- isi file php_info.php dengan kode berikut
```<?php phpinfo(); ?>```
  ![PHP](./img/18ok.png)

- Buka browser dan ketikkan alamat www.kelompok8.local/php_info.php

  ![PHPInfo](./img/19ok.png)

## 6. Install dan konfigurasi PHP-FPM
php fpm adalah FastCGI Process Manager untuk PHP berfungsi sebagai server untuk PHP
```sudo apt -y install php-fpm```

![PHP-FPM](./img/20ok.png)

## 7. Konfigurasi PHP-FPM di apache2
- ```nano /etc/apache2/sites-available/default-ssl.conf```
    ini berfungsi untuk mengarahkan apache2 ke php-fpm
    tambahkan di dalam tag ```<VirtualHost *:443></VirtualHost>```
    
    ```
    <FilesMatch \.php$>
        SetHandler "proxy:unix:/var/run/php/php8.2-fpm.sock|fcgi://localhost/"
    </FilesMatch>
    ```
    ![PHP-FPM](./img/21ok.png)

- ```a2enmod proxy_fcgi setenvif```
  Ini berfungsi untuk mengaktifkan modul proxy_fcgi dan setenvif

  ![PHP-FPM](./img/22ok.png)

- ```a2enconf php8.2-fpm```
  Ini berfungsi untuk mengaktifkan konfigurasi php8.2-fpm

  ![PHP-FPM](./img/23a.png)

- ```systemctl restart php8.2-fpm apache2```
  Ini berfungsi untuk merestart php8.2-fpm dan apache2

  ![PHP-FPM](./img/23ok.png)







