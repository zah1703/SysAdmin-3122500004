# Konfigurasi NTP Server

## 1. Install NTP (Network Time Protocol)
install NTP dengan perintah
```bash apt-get install ntp -y```

![ntp](./img/1.jpg)
## 2. Konfigurasi NTP ke timezone local (Asia/Jakarta)
```bash sudo timedatectl set-timezone Asia/Jakarta```

![ntp](./img/2.jpg)
## 3. Konfigurasi RTC (Real Time Clock) ke timezone local (Asia/Jakarta) dan mengaktifkan RTC
- ```sudo timedatectl set-local-rtc false```
- ```bash sudo timedatectl set-local-rtc true```

![ntp](./img/3.jpg)
## 4. Konfigurasi NTP ke server terdekat
```sudo nano /etc/systemd/timesyncd.conf```
ubah bagian ```NTP=``` menjadi ```NTP=0.id.pool.ntp.org```

![ntp](./img/4.jpg)
![ntp](./img/5.jpg)
## 5. Restart NTP
- ```bash sudo systemctl restart systemd-timesyncd```
- ```bash sudo systemctl status systemd-timesyncd```

![ntp](./img/6.jpg)
## 6. Lakukan pengecekan waktu
```bash timedatectl```

![ntp](./img/7.jpg)
