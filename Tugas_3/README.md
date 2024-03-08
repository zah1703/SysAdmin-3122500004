# TUGAS 3

# Disusun Oleh

| NAMA | NRP |
| ---- | --- |
| [Zahrotul Hidayah](https://github.com/zah1703)| 3122500004 |
| [Leody Zelvon Herliansa](https://github.com/Leodyz)| 3122500012 |
| [Adam Rasyid Nurmuhammad](https://github.com/adamrasyid01)| 3122500018 | 

**DAFTAR ISI**

1. [Linux Apt Command](#linux-apt-command)
2. [Mengatur Subnet di Mikrotik](#mengatur-subnet-pada-mikrotik)
3. [Topologi kelompok 8](#toplogi-jaringan)


## LINUX APT COMMAND

### UNTUK USER

| Command           | Description     |
|-----------        |-----------|
|apt show foo       |Menampilkan informasi paket foo      |
|apt search foo     | Mencari paket bernama/berkaitan foo         |
|apt-cache policy foo| Menampilkan versi tersedia paket foo       |


### Command apt untuk Administrator

> **Gunakan** sudo untuk menjalankan perintah berikut (root)

| Command           | Description     |
|-----------        |-----------|
|apt update      |Update repository metadata (list versi dll)     |
|apt install foo   | Memasang paket foo dan yang terkait        |
|apt upgrade| Menghapus versi lama paket      |
|apt full-upgrade| Mengupdate/hapus paket yang beneran terbaru     |
|apt remove foo| Menghapus paket foo, tidak confignya    |

## Cara menggunakan APT command
> Mengubah Repository Apt (pastikan gunakan sudo)

![Update Dependencies](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/apt_sourceslist.png)

> Setelah melakukan update dan upgrade untuk depedency, kita bisa install aplikasi menggunakan Aplikasi Software Bawaan

![Software Terinstall](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/software_terinstall.png)

### Melihat Storage yang terpakai di linux menggukan Terminal

![Free Storage](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/3_disk_free.png)

### Membuat daftar Directory, diurutkan dari yang terbesar yang terkecil

> Melihat isi direktori dengan perintah du dan sort (satuan megabyte):

![Sorting Directory](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/4_du_sort.png)

### Perintah ncdu (NCurses Disk Usage)

    Fungsi perintah ncdu untuk memberikan tampilan interaktif dari penggunaan disk pada suatu direktori atau file di sistem file.

Install terlebih dahulu ncdu dengan menggunakan perintah

> apt update && apt install ncdu

![Install Package ncdu](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/5_install_ncdu.png)

Akses ncdu dengan command $ ncdu
![Tampilan ncdu](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/6_UI_ncdu.png)

### Perintah baobab
Digunakan untuk menganalisa ruang pada disk dengan tampilan grafis 
Ketikkan perintah $ baobab
![Tampilan baobab](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/7_tampilan_baobab.png)

### Membersihkan Package

**Apt/aptitude/dpkg**

Manajer paket debian biasa. Ketika  menginstal sebuah paket, sumber arsip/debnya disimpan di sistem (di folder/var/cache/apt/) untuk mengaktifkan kemungkinan instalasi ulang tanpa koneksi internet 

Untuk membersihkan "apt cache" gunakan perintah apt clean.

Setelah cache dari paket yang diinstal dibersihkan, Kita juga dapat menghapus paket yang tidak berguna dari sistem, serta file konfigurasi. Namun Ingatlah untuk memeriksa dengan cermat daftar paket yang direncanakan untuk dihapus, sebelum menerima operasi:

![Apt remove](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/8_apt_remove.png)

Jika sistem telah diupgrade ke versi terbaru, ada kemungkinan beberapa paket tidak lagi tersedia di repositori baru (paket tersebut sudah usang). Untuk membuat daftar dan menghapus paket-paket ini, gunakan apt dan periksa dengan cermat daftar paket yang direncanakan untuk dihapus:
![Apt remove obsolete](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/9_apt_remove_obsolete.png)

Terakhir, untuk membuat daftar dan membersihkan file konfigurasi yang tetap ada meskipun aplikasi telah dihapus, gunakan perintah berikut :
![Dpkg list](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/10_dpkg_awk_rc.png)

**deborphan**

Mencantumkan paket-paket yang diadopsi pada sistem : paket-paket yang tidak bergantung pada paket lain.

Ingatlah untuk memeriksa dengan cermat daftar paket yang direncanakan untuk dihapus, sebelum menjalankan operasi.
![Install deborphan](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/11_install_deborphan.png)

![Autoremove deborphan](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/12_autoremove_deborphan.png)

### Mengosongkan trash-bin

Tiga trash-bin (wastebasket) yang berbeda harus dipertimbangkan:

**trash-bin user**

Anda dapat mengosongkannya dengan system file manager atau dengan perintah :
![rm -Rf](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/13_rm_Rf.png)

**trash-bin admin**

Untuk mengosongkannya dengan cara yang benar, gunakan terminal dalam mode administrator:
![rm -Rf cache](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/14_rm_rf_cache.png)

**trash-bin eksternal**

biasanya diberi nama '/media/(loginname)/your_disk/.Trash_1000'.
img
![rm -Rf thumbnails](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/15_rm_rf_thumbnails.png)

# Menginstall Package EXTERNAL Extensi .deb

### DEBI Application

Kita dapat menginstall package External (.deb) menggunakan aplikasi Gdebi yang dapat diinstall dengan cara berikut.
![apt update apt gdebi](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/16_apt_install_apt_gdebi.png)

Sekarang kita coba melakukan installasi untuk paket dari aplikasi VSCODE



# Mengatur Subnet pada Mikrotik
**1. Login mikrotik di winbox**


**2. Buka terminal pada komputer lab dan masukkan perintah ip addr.**

**3. Pasang kabel WLAN pada laptop anda.**
**4. Pasang dan jalankan Winbox pada laptop anda.**
**5. Connect pada physical address (MAC) yang ada di layar winbox. Dengan cara mengklik MAC address kemudian klik connect. Jika terdapat pesan error, pergi ke tools, pilih legacy mode, lakukan connect kembali.**
**6. Nantinya akan muncul pesan configuration, pilih remove configuration.**

**7. Pertama-tama untuk mengecek level mikrotik, cari 'System' di sidebar dan pilih License. Mikrotik yang digunakan memiliki level 5.**
![Login Mikrotik](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/1_login_mikrotik.png)

**8. Untuk menambahkan alamat IP, pergi ke sidebar 'IP' dan pilih 'Address List'. Klik tanda plus berwarna biru di sebelah kiri atas. Masukkan alamat IP 192.168.88.2/24, network 192.168.88.0, dan interface di ether1.**
![Sidebar](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/2_ceklevel_mikrotik.png)
![Ip Address](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/3.1_sidebar_ip.png)
![Address list](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/3.2_address_list.png) 
![Bridge](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/3.3_bridge.png) 
![DHCP Server](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/3.4_dhcp_server.png) 

**9. Buka terminal baru dan jalankan perintah 'ping 192.168.88.254'. Pastikan berhasil melakukan ping ke IP tersebut.**
![Ping 192.168.88.254](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/4._ping_192.168.88.254.png) 

**10. Pindah ke tab ports tambahkan ports,setting interface di ether2 dan Bridge di bridge1. Lakukan hal yang sama pada ether3, ether4, dan ether5.setelah ditambahkan, set ether2 sebagai Address baru. Masukkan address 192.168.8.1/24 dan network 192.168.8.0, klik apply.**
![Tab Ports](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/5.1_tab_ports.png) 
![Address 192.168.8.1](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/5.2_address_192.168.8.1.png) 

**11. Setting gateway dari sidebar 'IP', kemudian pilih route dan klik tanda plus untuk add route. Masukkan 0.0.0.0 untuk destination address dan 192.168.88.254 untuk gateway. kemudian Klik apply untuk menerapkan/menambahkan.**
![General destination address](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/6_general_dstaddres.png) 


**12. Setting DHCP dari sidebar 'IP', pilih DHCP server. Pada DHCP Setup pilih bridge1 di DHCP Server Interface, ubah Set Addresses menjadi 192.168.8.200-192.168.8.254. Jika sudah, hasil pengubahan disimpan.**

![DHCP setting IP](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/7_dhcp_settingIP.png) 

**13. Buka IP pilih DNS. Tambahkan DNS dengan alamat PENS yaitu 202.9.85.4**
![DHCP setting address](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/8_dhcp_settingaddress.png) 

**14.Terakhir setting firewall dari sidebar 'IP'. Pilih NAT dan klik tanda plus. Masukkan source addressnya 192.168.8.0/24 dan destination addressnya 0.0.0.0. Klik apply untuk menyimpan (Jangan lupa action modenya ke ‘masquerade’)..**
![DHCP setting address](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/9_firewall_NAT.png) 
![Action masquerade](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/10_action_masquerade.png) 

**15. Setelah itu kita Coba lakukan ipconfig dan ping. di CMD**
![Ip Config](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/11.1_ipconfig.png) 
![Ping](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/11.2_ping.png) 

# TOPLOGI JARINGAN 
![Topologi Kelompok 8](https://github.com/adamrasyid01/SysAdmin-3122500018/blob/main/Tugas_3/assets/mikrotik/Topologi%20Kelompok%208.jpg) 








