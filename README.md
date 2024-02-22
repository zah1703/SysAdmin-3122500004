</head>
<div align="center">
  <h1>WORKSHOP ADMINISTRASI JARINGAN</h1>
  <h2>Tugas 1 Sistem Operasi Debian</h2>
<img src="logo.png" alt="Alt teks">
<h3>Dosen Pengampu :

Dr..Ferry Astika Saputra,ST, M.Sc
Disusun Oleh:

<br>Zahrotul Hidayah 	    (3122500004)
<br>Leody Zelvon Herdiansah (3122500010)
<br>Adam Rasyid Nurmuhammad	(3122500018)</br>
 
<br>Politeknik Elektronika Negeri Surabaya
<br>Tahun Akademik 2023/2024</h3></br>

<body>
<div align="left">
  <h1></h1>
  <p>1. Langkah-langkah instalasi OS Debian
    <p>-Buat Name,Type dan Version Instalasi</p>
    <img src="1a.png" alt="Alt teks">
    <p>-Set hardware (base memory ‘RAM’, Core processors, dan virtual hardisk)</p>
    <img src="1b.png" alt="Alt teks">
    <p>-Create size of the hard disk</p>
    <img src="1b.png" alt="Alt teks">
    <p>-Pilih Virtual Hard Disk untuk mengupload ISO</p>
    <img src="1c.png" alt="Alt teks">
    <p>-Create Virtual Hardisk</p>
    <img src="1d.png" alt="Alt teks">
    <p>-Select Language</p>
    <img src="1e.png" alt="Alt teks">
    <p>-Select Country</p>
    <img src="1f.png" alt="Alt teks">
    <p>-Select keymap</p>
    <img src="1g.png" alt="Alt teks">
    <p>-Enter the Hostname</p>
    <img src="1h.png" alt="Alt teks">
    <p>-Set up users and passwords</p>
    <img src="1i.png" alt="Alt teks">
    <p>-Select username dan password</p>
    <img src="1j.png" alt="Alt teks">
    <p>-Select Timezone</p>
    <img src="1joke.png" alt="Alt teks">
    <p>-Configure the partition</p>
    <img src="1k.png" alt="Alt teks">
    <p>-Select the disk that want to partition</p>
    <img src="1L.png" alt="Alt teks">
    <p>-Create the New Partition</p>
    <p>a.  /storage 5 GB</p>
    <img src="1m.png" alt="Alt teks">
    <p>*Select Type: Primary</p>
    <img src="1n.png" alt="Alt teks">
    <p>*Select Type: Primary</p>
    <img src="1n2.png" alt="Alt teks">
    <p>*Select Location</p>
    <img src="1n3.png" alt="Alt teks">
    <p>*Done setting up the partition</p>
    <img src="1n4.png" alt="Alt teks">
    <p>*Beri nama : Storage</p>
    <img src="1n5.png" alt="Alt teks">
    <p>b. / (root) : 20 GB</p>
    <img src="2a.png" alt="Alt teks">
    <p>*Done setting up the partition</p>
    <img src="1b.png" alt="Alt teks">
    <p>c. swap : 1.5 GB</p>
    <img src="3.png" alt="Alt teks">
    <p>*Nama Partisi Disk</p>
    <img src="3a.png" alt="Alt teks">
    <p>*Select swap area</p>
    <img src="3b.png" alt="Alt teks">
    <p>*Done setting up for swap area</p>
    <img src="3c.png" alt="Alt teks">
    <p>*Data hasil partisi (20 GB, 1.5 Gb dan 5.0 GB)</p>
    <img src="3d.png" alt="Alt teks">
    <p>-Yes untuk melanjutkan proses instalasi</p>
    <img src="3ok1.png" alt="Alt teks">
    <p>-Configure the package manager (Scan extra installation media)</p>
    <img src="3ok2.png" alt="Alt teks">
    <p>-Configure the package manager and select indonesia</p>
    <img src="3ok3.png" alt="Alt teks">
    <p>2. Buat ringkasan tentang perbedaan dari Debian 12 (bookworm) dengan Debian 11 (bullseye) : versi kernel, kebutuhan sistem, penerapan systemd dan perbedaan packagenya (dalam bentuk tabel)!</p>
    <img src="2yes.png" alt="Alt teks">
    <br>3. Jelaskan fungsi dari file "/etc/groups" beserta formatnya!
    <br>Jawab:
    <br>-Isi file /etc/group : 
    <br>-Nama grup: Merupakan nama dari grup pengguna.  
    <br>-Kata sandi: Sebelumnya digunakan untuk menyimpan kata sandi grup, tetapi saat ini tidak lagi digunakan dan biasanya dibiarkan kosong (dipenuhi dengan tanda x).  
    <br>-ID grup: Merupakan nomor identifikasi unik untuk grup, dalam bentuk bilangan bulat.  
    <br>-Anggota grup: Merupakan daftar pengguna yang termasuk ke dalam grup, dipisahkan oleh koma.</br>

    Contoh 
    Wheel:x:10:root,john
    Nama grup : wheel 
    Kata sandi : x 
    ID grup: 10 
    Anggota grup: root dan john  

Artinya, grup pengguna dengan nama wheel memiliki ID 10 dan memiliki dua anggota yaitu root dan john. Grup ini sering digunakan untuk memberikan akses khusus pada pengguna tertentu seperti akses ke root atau hak akses sudo.</br>

<br>4. Jelaskan perbedaan penggunaan perintah "su" dengan "su -"!
<br>Jawab:
<br>a. su digunakan untuk berpindah dari pengguna dengan root di shell saat ini. Cara menggunakannya dengan cara ‘ su [nama pengguna]’.</br>
<img src="4a.png" alt="Alt teks">
<br>b. su – digunakan untuk berpindah dengan root di environment baru dengan menginisialisasi lingkungan shell baru.</br>
<img src="4b.png" alt="Alt teks"></br>

<br>5. Jelaskan fungsi dari "sudo" !
<br>Jawab:
<img src="5.png" alt="Alt teks"></br>
Sudo merupakan sebuah perintah dalam command-line Linux. Apabila user memiliki akses root, maka sudo akan melakukan perintah sebagai superuser. Pengguna sudo dan perintah-perintah yang dapat mereka pergunakan terdapat pada file konfigurasi, /etc/sudoers. </br>

<br>6. Jelaskan langkah-langkah penambahan user anda sebagai user sudo ! Gunakan perintah "su -" lalu setelah masuk sebagai root, jalankan perintah "visudo". Tambahkan user anda di bawah user root pada bagian " # User privilege specification"!</br>
<br>Jawab:</br>
<img src="6.png" alt="Alt teks">
 <h1></h1>
</div>