# Konfigurasi NTP Server

## 1. Install NTP (Network Time Protocol)
install NTP dengan perintah
```apt install systemd-timesyncd```

![ntp](./img/1ok.png)
## 2. Konfigurasi NTP ke timezone local (Asia/Jakarta)
```sudo timedatectl set-timezone Asia/Jakarta```

![ntp](./img/2ok.png)
## 3. Konfigurasi RTC (Real Time Clock) ke timezone local (Asia/Jakarta) dan mengaktifkan RTC
- ```sudo timedatectl set-local-rtc false```
- ```bash sudo timedatectl set-ntp true```

![ntp](./img/3ok.png)
![ntp](./img/4ok.png)
## 4. Konfigurasi NTP ke server terdekat
```sudo nano /etc/systemd/timesyncd.conf```
ubah bagian ```NTP=``` menjadi ```NTP=0.id.pool.ntp.org```

![ntp](./img/5ok.png)

## 5. Restart NTP
- ```sudo systemctl restart systemd-timesyncd```
- ```sudo systemctl status systemd-timesyncd```

![ntp](./img/6ok.png)
## 6. Lakukan pengecekan waktu
```timedatectl```

![ntp](./img/7ok.png)
