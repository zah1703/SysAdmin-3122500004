<div align="center">
  <h1 style="text-align: center;font-weight: bold">Project Charter Container Based App<br>
KONSULDOK: DOCTOR APPOINTMENT  APPLICATION</h1>
  <h3 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h3>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : <br>Kelompok 1 </h3>
  <div style="align: center;">
    <table>
      <tr>
        <th>No</th>
        <th>Nama</th>
        <th>NRP</th>
      </tr>
      <tr>
        <td>1</td>
        <td>Denti Widayati</td>
        <td>3122500003</td>
      </tr>
      <tr>
        <td>2</td>
        <td>Zahrotul Hidayah</td>
        <td>3122500004</td>
      </tr>
      <tr>
        <td>3</td>
        <td>Awal Raya</td>
        <td>3122500012</td>
      </tr>
      <tr>
        <td>4</td>
        <td>Muhammad Iqbal Rahmatullah</td>
        <td>3122500014</td>
      </tr>
      <tr>
        <td>5</td>
        <td>Handaru Dwiki Yuntara</td>
        <td>3122500017</td>
      </tr>
      <tr>
        <td>6</td>
        <td>Virginia Faiqoh</td>
        <td>3122500022</td>
      </tr>
      </tr>
    </table>
  </div>

<h2 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h2>
</div>

# Daftar Isi

- [Abstrak](#abstrak)
- [Pendahuluan](#pendahuluan)
- [Ruang Lingkup](#ruang-lingkup)
- [System Architecture](#system-architecture)
- [Tahapan Pelaksaan](#tahapan-pelaksanaan)
- [Tim Dan Tugas](#tim-dan-tugas)
- [Implementasi](#implementasi)
- [Sistem Testing](#sistem-testing)
- [Kesimpulan](#kesimpulan)

<hr>

# Abstrak<br>

KonsulDok adalah aplikasi mobile berbasis Flutter yang dirancang untuk membantu penderita sakit dalam merencanakan janji temu dengan dokter. Aplikasi ini memberikan fitur pemesanan dokter dengan mudah, serta pasien dapat menghubungi dokter menggunakan fitur chat realtime pada aplikasi ini. Backend aplikasi menggunakan ExpressJS dengan bantuan ORM Prisma untuk autentikasi dan berinteraksi dengan MYSQL yang menyimpan data dan melakukan operasi CRUD. Docker Engine digunakan untuk mengembangkan, mengirimkan, dan menjalankan aplikasi dalam kontainer, memastikan portabilitas, isolasi, dan kemudahan deployment. Kemudian kami membentuk microservice pada aplikasi Docker Engine, serta melakukan containerization pada setiap service sehingga service-service tersebut dapat berjalan independen(tidak berketergantungan dengan service lainnya).<br><br>
Berikut untuk pembagian port dari tiap-tiap service yang ada :<br>
-   Api gateway → 3000:3000<br>
-   MySQL → 3306/tcp<br>
-   service_user → 4000:4000<br>
-   service_chat → 7001:7001<br>
-   service_rating → 5001:5001<br>
-   service_appointment → 8000:8000<br>
-   service_doctor → 6000:6000<br>
-   adminer → 8001:8000
<br><br>

# Pendahuluan
Dalam era digital saat ini, teknologi informasi telah merambah ke berbagai aspek kehidupan, termasuk sektor kesehatan. Salah satu hal penting dalam bidang ini adalah aplikasi Doctor Appointment. Aplikasi ini dirancang untuk memudahkan pasien dalam mengatur pertemuan dengan dokter tanpa harus melalui proses yang panjang dan rumit. Dengan hadirnya aplikasi Doctor Appointment, baik pasien maupun tenaga medis dapat mengelola waktu dan sumber daya dengan lebih efisien.<br><br>
Aplikasi Doctor Appointment tidak hanya memberikan kemudahan bagi pasien untuk membuat jadwal kunjungan, tetapi juga menawarkan berbagai fitur tambahan seperti informasi detail mengenai dokter, serta opsi konsultasi melalui fitur chat.<br><br>
Selain itu, aplikasi ini juga memberikan manfaat signifikan bagi klinik dan rumah sakit dalam mengelola jadwal dokter dan mengurangi antrean di ruang tunggu. Data dan rekam medis yang tersimpan secara digital juga memudahkan tenaga medis dalam memantau riwayat kesehatan pasien secara akurat dan cepat.<br><br>
Secara keseluruhan, aplikasi Doctor Appointment merupakan solusi yang menjawab kebutuhan akan layanan kesehatan yang lebih cepat, aman, dan efisien. Dengan terus berkembangnya teknologi dan meningkatnya kebutuhan masyarakat akan layanan kesehatan yang lebih baik, aplikasi ini memiliki potensi besar untuk terus berkembang dan memberikan kontribusi yang signifikan dalam meningkatkan kualitas pelayanan kesehatan di masa mendatang.

# Ruang Lingkup

KonsulDok adalah aplikasi mobile yang dibangun menggunakan Flutter dan memberikan pengguna akses mudah ke berbagai fitur terkait doctor appointment. Bagian backend dari aplikasi ini dikembangkan dengan menggunakan framework ExpressJS, yang mengelola segal interaksi dengan database untuk penyimpanan dan pengambilan data. Aplikasi ini memanfaatkan MySQL sebagai database, yang berfungsi untuk menyimpan dan mengakses data, serta merespons permintaan dari pengguna. Server bertindak sebagai perantara antara aplikasi mobile, backend, dan database, menerima permintaan dari pengguna, meneruskannya ke backend dan database, dan kemudian mengirimkan respons kembali kepada pengguna

# Desain Sistem

**![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdRUK4HWf4FH_e5CZJrTeETiill16ikDVRK11Ym8Kf8zAOb-6zxzohdC1OmpldgNqpyvP0HB95jSY6PLkBN9u7ma4JxheMzx8De_ULP6mwWLYOSXQHDI2UG0CtSXuwMSOz9nW0ejK1lfFHywtMr1VJbJwul?key=6Eojv_aTg9PSKZFsU8qskA)**

# Tahapan pelaksanaan

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXetaN6Pp7BQiQSaPB18IESuynteuBwmRL6qbWMpbmEZadYz8Wad_QEMRox9wY37mOaNmqIGTD2vZmE84HZ0Py-yfWxBuJ9pfwx7AaQRK5dB9TqEce3inpPDhxJ3DEVlnke5w3Qt8d8wTyhcsbfUxQPNW4aO?key=6Eojv_aTg9PSKZFsU8qskA)

1.  UI/UX
    <br> - Analisis kebutuhan fitur
    Memahami dan menganalisis kebutuhan fitur dari aplikasi. Ini melibatkan diskusi dengan kelompok dan dosen yang berkaitan, mengumpulkan persyaratan pengguna, dan mendefinisikan fitur apa saja yang akan diimplementasikan dalam aplikasi.
    <br> - Membuat komponen yang dibutuhkan
    Setelah analisis kebutuhan selesai, tim UI/UX mulai membuat komponen-komponen yang diperlukan untuk aplikasi.Aktivitas ini memastikan bahwa semua elemen desain yang dibutuhkan siap digunakan oleh tim pengembangan.
    <br> - Desain UI/UX
    UI/UX fokus pada pembuatan tampilan dan interaksi pengguna yang optimal. Ini termasuk pemilihan skema warna, tipografi, ikonografi, dan tata letak yang intuitif. Desain yang dihasilkan harus memastikan pengalaman pengguna yang baik dan mudah digunakan.
    <br>
    LINK FIGMA:
    [https://www.figma.com/design/6F058W0gxYp1WtIpcAfbuR/KonsulDok?node-id=5-23&t=z3SnLoar9uxr8hEQ-0](https://www.figma.com/design/6F058W0gxYp1WtIpcAfbuR/KonsulDok?node-id=5-23&t=z3SnLoar9uxr8hEQ-0)
    <br>

2.  Mobile Development
    <br> - Slicing design dari Figma ke Flutter
    Tim pengembangan mobile mulai menerjemahkan desain UI dari Figma ke dalam kode Flutter. Tim pengembang mulai membuat re-usable component yang nantinya digunakan untuk membentuk sebuah page.
    <br> - Konfigurasi state management
    Konfigurasi state management bertujuan untuk mengatur bagaimana data dalam aplikasi dikelola dan diubah, serta memastikan sinkronisasi data yang efisien antar komponen UI. Pada tahap ini pengembang memanfaatkan package Bloc dan Cubit.
    <br> - Integrasi datasource
    Melakukan integerasi datasource, baik remote datasource yang akan menghubungkan aplikasi dengan backend untuk mengambil dan mengirim data. Dan local data source yang akan menyimpan pada storage perangkat menggunakan package HIVE.
    <br><br>

3.  Backend development<br> 
    - Membuat REST API
    Pembuatan REST API yang akan digunakan oleh aplikasi mobile untuk berkomunikasi dengan server. REST API ini memungkinkan aplikasi untuk melakukan operasi CRUD (Create, Read, Update, Delete) dengan data yang tersimpan di backend.<br> 
    - Konfigurasi JWT
    Mengimplementasikan JWT (JSON Web Token) untuk keamanan. JWT digunakan untuk mengautentikasi pengguna dan memastikan bahwa hanya pengguna yang sah yang dapat mengakses API.<br> 
    - Konfigurasi Websocket
    Mengonfigurasi Websocket untuk mendukung komunikasi real-time. Websocket memungkinkan aplikasi untuk menerima pembaruan data secara instan tanpa perlu melakukan polling ke server secara terus-menerus.
    <br><br>

4.  Deployment<br>

    - Membuat aplikasi berbasis microservice
    Memecah aplikasi menjadi beberapa layanan kecil yang dapat diatur secara independen, meningkatkan skalabilitas dan fleksibilitas.<br>
    - Containerization Application
    Menggunakan Docker, tim memastikan bahwa setiap layanan dapat berjalan dalam lingkungan terisolasi, membuat pengelolaan dan penerapan aplikasi lebih mudah.
    <br><br>
5.  Testing
    <br> - Functional testing
    Memastikan bahwa setiap fungsi dari perangkat lunak bekerja sesuai dengan persyaratan yang telah ditetapkan.
    <br> - Intallation testinng
    Memastikan bahwa aplikasi dapat diinstal dengan benar pada berbagai lingkungan dan perangkat yang didukung.

# Tim Dan Tugas

1.  UI/UX: Awal, Zahro, Vira
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXewVwuSFCwjrg0pIJy5TZJXHTpzaHeQZmHXqGmZP9pbUDVV6gG8pfM0HbuXYPqtuLOVBsgRfXSO29FKSZKkfLOZUCmAcJTXoyooiYygMsS_U2MGQrCfeXTaGlUtLHE0Ol6TeEwuDY0LksS-mZx-ngcUlaw?key=6Eojv_aTg9PSKZFsU8qskA)
    <br>

- Riset Pengguna 
  1. Studi Pengguna: Meneliti bagaimana pasien saat ini membuat janji temu dan kesulitan apa yang mereka hadapi. 
  2. User Persona: Membuat profil persona pengguna berdasarkan data riset untuk menggambarkan target audiens secara lebih jelas.
  <br>
- UI Design
  1.  Wireframe: Membuat wireframe dari layar utama aplikasi, termasuk proses pencarian dokter, pemilihan waktu janji temu, dan konfirmasi.
  2.  Mockup: Membuat tampilan aplikasi
  3.  Prototype: Membuat prototipe interaktif yang memungkinkan pengguna menguji proses penjadwalan janji temu.
<br><br>
2.  Mobile Developer: All (Iqbal, Awal, Handaru, Zahro, Denti, Vira)
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcasg4Gz-CcFqh5uq1QCUiOepYX7otfrDg_E_LNAFv_lv7QfLtpLnirhUNYVz7veSKvEBVbEkWHVGz_G13rY9iyVNb59x-dEz7dXekbxAd6XARdVlmFDg20RpwZvTJacWVlyPputj0NZ5wluNQ81IHZP5H5?key=6Eojv_aTg9PSKZFsU8qskA)
    - Coding: Menulis kode menggunakan bahasa pemrograman dart (Slicing mockup)<br>
    - UI Implementation: Mengimplementasikan desain UI/UX yang diberikan oleh desainer, memastikan antarmuka aplikasi responsif dan intuitif<br>
    - State management : mengatur bagaimana data dalam aplikasi dikelola dan diubah, serta memastikan sinkronisasi data yang efisien antar komponen UI.<br>
    - Configuration Datasource : menghubungkan aplikasi dengan backend untuk mengambil dan mengirim data. Dan local data source yang akan menyimpan pada storage perangkat
<br><br>
3.  Backend Developer: Handaru, Iqbal
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfS4LcmMBxHtaIOQbLabi8crJT3BIwOxruB2wg664JLVgY3WWoPSGADai2fes0EwAE7jIA7BkJD9o4wNn5sP8kYKjBLPtTJ2HaC4OaNFOYS0XuN5Iqddcz6fqdaiATphwdgdViQEcsMKpoWAPaeRauf-N8C?key=6Eojv_aTg9PSKZFsU8qskA)<br>
      - Desain Skema Basis Data: Merancang skema basis data yang efisien untuk menyimpan informasi.<br>
      - Pengembangan API : Membuat REST API menggunakan express js.<br>
      - Konfigurasi JWT : mengautentikasi pengguna dan memastikan bahwa hanya pengguna yang sah yang dapat mengakses API.<br>
      - Konfigurasi websocket : Mengkonfigurasi agar aplikasi untuk menerima pembaruan data secara instan tanpa perlu melakukan polling ke server secara terus-menerus.
      <br><br>

4.  Deployment : Handaru, Iqbal
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfoiQu7LfcHpvQMkpBiIUovLZ7THWQK8EE9LpBPZE2l-lUbLU_0vk92ETK9LsV7w3oyuznaZ-AXOq3ttoitPHJ0BP0i7BPT2BSFDiBeZzEJymgYSMC2-yCWaWyWK6ZBDNR9BKbrUMK2YFd7U2gQKxyPRvA?key=6Eojv_aTg9PSKZFsU8qskA)
      - Memisahkan tiap service di server (microservice) : Memecah aplikasi menjadi beberapa layanan kecil yang dapat diatur secara independen, meningkatkan skalabilitas dan fleksibilitas.<br>
      - Konfigurasi docker image : Mengkonfigurasi dependency-dependency yang diperlukan oleh tiap service.<br>
      - Konfigurasi docker compose: Mengkonfigurasi agar semua container service dapat dijalankan dengan 1 command.<br>
<br><br>
5.  Testing : Awal, Zahro, Vira, Denti<br>
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeZDgncNt1-8mRY2xZyHeUDFdkJg5jqm56Bj_n9ALA3ivV_vKXVxrBws1bRqfzuOhWW-SP6bj_IvAiKAEJteT552pc1TBwyxlPqlTylneNbUtuCAX5K7TFi5JbF6iELFD0HmaI3QTrymT92iTAV74vzfzAB?key=6Eojv_aTg9PSKZFsU8qskA)<br>
      - Memastikan bahwa setiap fungsi dari perangkat lunak bekerja sesuai dengan persyaratan yang telah ditetapkan.<br>
      - Memastikan bahwa aplikasi dapat diinstal dengan benar pada berbagai lingkungan dan perangkat yang didukung.<br>
<br><br>

LINK BACKLOG :
[https://docs.google.com/spreadsheets/d/1tNTmUxcVCjaUMy0bOKoLLYqSv6KgNt2oU-kUH2zEUjQ/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1tNTmUxcVCjaUMy0bOKoLLYqSv6KgNt2oU-kUH2zEUjQ/edit?usp=sharing)<br>

# Implementasi
-   Tahap 1: Perencanaan & Analisis (Minggu 1-2)<br>
Tujuan & Sasaran: Mengidentifikasi dan mendokumentasikan tujuan serta sasaran implementasi KonsulDok.<br>  
Mengidentifikasi Target Pengguna:
Melakukan analisis kebutuhan, dan ekspektasi aplikasi KonsulDok.
Output: Profil target pengguna yang mendetail.<br>
Rancangan Database:Mendesain skema basis data yang efisien untuk menyimpan informasi pengguna, janji temu, rekam medis, dan data terkait lainnya.  
Output: Desain skema basis data.<br>
Pemilihan Teknologi: Memilih teknologi yang akan digunakan untuk mengembangkan aplikasi KonsulDok, mempertimbangkan skalabilitas, keamanan, dan kemudahan penggunaan.  
Output: Daftar teknologi terpilih (Flutter, ExpressJS, Prisma, MySQL, Docker).<br><br>

-   Tahap 2: Desain & Prototyping (Minggu 3-5)<br>
Desain UI/UX: Membuat wireframe dan mockup antarmuka pengguna, serta prototipe yang interaktif.
Output: Desain antarmuka pengguna yang estetis.<br>
Pengembangan Konten: Membuat konten dan fitur aplikasi KonsulDok sesuai dengan kebutuhan pengguna.
Output: Konten dan fitur yang sesuai dengan standar aplikasi janji temu dokter.<br><br>
  
-   Tahap 3: Pengembangan & Implementasi (Minggu 5-6)<br>
Pengembangan FE Mobile: Menerjemahkan desain UI dari Figma ke dalam kode Flutter, termasuk pembuatan komponen reusable dan konfigurasi state management menggunakan Bloc dan Cubit.
Output: Aplikasi mobile KonsulDok<br>
Pengembangan BE: Mengembangkan REST API menggunakan ExpressJS, mengonfigurasi JWT untuk autentikasi, dan WebSocket untuk komunikasi real-time.
Output: Rest API<br>
Containerization Docker: Memecah aplikasi menjadi beberapa layanan kecil (microservices) dan mengonfigurasi Docker untuk setiap layanan.
Output: Layanan backend yang terkontainerisasi dan mudah dikelola.<br><br>


-   Tahap 4: Testing & Deployment (Minggu 6)<br>
Testing Installation: Memastikan aplikasi dapat diinstal dengan benar di berbagai lingkungan dan perangkat yang didukung.
Output: Instalasi aplikasi yang berhasil<br>
Functional Testing: Melakukan pengujian fungsional untuk memastikan semua fitur aplikasi berfungsi dengan benar.
Output: Hasil pengujian fungsional yang baik<br><br>

# Sistem testing<br>
## Installation testing<hr>

1.  Konfigurasi docker image  
    Service appointment, doctor, user, chat, rating embutuhkan dependecy yang sama, yaitu melakukan npm install dan npm generate prisma
    ```
    FROM node:20-alpine
    WORKDIR /app
    COPY package*.json ./
    RUN npm install
    COPY prisma ./prisma
    RUN npx prisma generate
    COPY . .
    EXPOSE 8000 //sesuaikan port masing-masih
    CMD ["npm", "start"]
    ```
    <br>
    Untuk api gateway berbeda karena tidak membutuhkan ORM, jadi hanya menjalankan npm install

    ```
    FROM node:20-alpine
    WORKDIR /app
    COPY package*.json ./
    RUN npm install
    COPY . .
    EXPOSE 3000
    CMD ["npm", "start"]
    ```
<br><br>
2.  Konfigurasi docker compose

```  
services:
  mysql:
    container_name: db
    image: mysql
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: password
    networks:
      - backend

  api_gateway:
    container_name: api_gateway
    build: ./api_gateway
    ports:
      - "3000:3000"
    networks:
      - backend
    environment:
      - URL_SERVICE_USER=http://142.93.14.210:4000
      - URL_SERVICE_DOCTOR=http://142.93.14.210:6000
      - URL_SERVICE_CHAT=http://142.93.14.210:7001
      - URL_SERVICE_RATING=http://142.93.14.210:5001
      - URL_SERVICE_APPOINTMENT=http://142.93.14.210:8000

  service_user:
    container_name: service_user
    build: ./service_user
    ports:
      - "4000:4000"
    networks:
      - backend
    environment:
      - DB_NAME=meet_doctor
      - DB_HOST=db
      - DB_USERNAME=root
      - DB_PASSWORD=password
      - DATABASE_URL=mysql://root:password@db/meet_doctor

  service_chat:
    container_name: service_chat
    build: ./service_chat
    ports:
      - "7001:7001"
    networks:
      - backend
    environment:
      - DB_NAME=meet_doctor
      - DB_HOST=db
      - DB_USERNAME=root
      - DB_PASSWORD=password
      - DATABASE_URL=mysql://root:password@db/meet_doctor

  service_rating:
    container_name: service_rating
    build: ./service_rating
    ports:
      - "5001:5001"
    networks:
      - backend
    environment:
      - DB_NAME=meet_doctor
      - DB_HOST=db
      - DB_USERNAME=root
      - DB_PASSWORD=password
      - DATABASE_URL=mysql://root:password@db/meet_doctor

  service_appointment:
    container_name: service_appointment
    build: ./service_appointment
    ports:
      - "8000:8000"
    networks:
      - backend
    environment:
      - DB_NAME=meet_doctor
      - DB_HOST=db
      - DB_USERNAME=root
      - DB_PASSWORD=password
      - DATABASE_URL=mysql://root:password@db/meet_doctor

  service_doctor:
    container_name: service_doctor
    build: ./service_doctor
    ports:
      - "6000:6000"
    networks:
      - backend
    environment:
      - DB_NAME=meet_doctor
      - DB_HOST=db
      - DB_USERNAME=root
      - DB_PASSWORD=password
      - DATABASE_URL=mysql://root:password@db/meet_doctor

  adminer:
    container_name: adminer
    image: adminer
    restart: always
    ports:
      - "8081:8080"
    networks:
      - backend
    environment:
      - DB_NAME=meet_doctor
      - DB_HOST=db
      - DB_USERNAME=root
      - DB_PASSWORD=password
      - DATABASE_URL=mysql://root:password@db/meet_doctor

networks:
  backend:
    driver: bridge
```
<br><br>
3.  Migration database
-   Pada docker compose telah menginstall admine yang digunakan untuk Memanjemen database dengan interface → masuk ke sini dengan port 8081
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcQhLcvFoDgTXjLExG0asMAmLjtfQSwMYcu7lcqQ5yk99lu9aoZpx3QMdpMEJajhYQ2EvC4JUNV7fhgyasImjGJQ6NsEGjpPycO6ZNMIZV4v_hpTAvZKxRQtUAeR9_xY1ATrrFbKaVEiV2W5DOfNako-0E?key=6Eojv_aTg9PSKZFsU8qskA)<br>
-   Masuk dengan -u root -p password<br>
-   Buat database meet_doctor<br>
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcwKEmpqaTZQlnLgxSKoRXYWgW_QNAgOvSxED2TxJdzlo6SgZ2FNdXN-Sn-w2dgTJmaIygeuyHmGnSVPscGWC2v6r0nXuz3_C6vUuGxNIKPwowB705kyM5jx59FuPLAtxRzVkT22LJK0KDjtz1Rc2_rNtNH?key=6Eojv_aTg9PSKZFsU8qskA)<br>
-   Masuk ke bash dari script migration di container service user → docker exec -it service_user sh<br>
-   Jalankan npx prisma migrate dev<br>
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdmtlF0o1Zk6k7oVRMDokvDYY3wBciQxItFPUK-XCqy2nNlQGurj1-1ySgA-6lsF5eUiqaFPPcepPAvKCcgMqe1TvajVhPVrC-OYiLY2ed-dV6_pex6nhvGPvkAZ7ouZ1eaL35_bnrNkyC8ou1cy10-hR8d?key=6Eojv_aTg9PSKZFsU8qskA)<br>
Result :<br>
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXe9HeU11zGDLekCqJ6qTIVhIip1OBtF0QoIme_ypayNB7AzXU_MykNxDABK7EluvZp63pl6btp-Ja1kvdXm6JK6HgLstLHLlehiu9G6OgWRVVgGyWDDB-kwjZIgMuWKnydOaxZEEcBW0A0Z0nec4Fa5W_pf?key=6Eojv_aTg9PSKZFsU8qskA)<br><br>
4.  Up Service → docker compose up -d  
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcj7G0KQ_PixbNS-oVaigQFKOUNRAjB_XVPI1XltZgwfWbNLuDuWmsKZqt7lCApqDpSF26t_9Plij5GKVrf-0iFGSwQnczNwyNqjl7R-NiFWpt5_SRtBf-a6CC9fiBn3tAPQYYJ0R7ovvjwyQhYE9MXcWGt?key=6Eojv_aTg9PSKZFsU8qskA)<br><br>
5.  Restart service → docker compose restart  
    ![](https://lh7-us.googleusercontent.com/docsz/AD_4nXd5kbpu7jlrt6RKiCvp8f6LyRsiIltYClgml0BP1EyNoJl8Iv-K2WmnTOmbXbnNcYlbyA7fvLSkAg2APEhMMWPrP3neu8xhPK6qeyS6EGIrRWBak7mPVkPZPWfC8_xsXAcENEZejRhCVO_mVyd1UcSPQzrk?key=6Eojv_aTg9PSKZFsU8qskA)<br><br>
6. Down service → docker compose down  
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcaVRNf0DVfMLyldsCkALkTzJuDvjIrQSmpEJhmzWT4QsPHvPK8KhrP7l8h6vopWRKGx5R6jBz2RE0zzHn87DYuoaSRpIdYVBPtYtB1V12RitfSMEBVLAhcNcnJbJC8XjGLNXtg_r5RE5c5Cy0pSufdvLpe?key=6Eojv_aTg9PSKZFsU8qskA)
<br><br>

## Fuctional testing<hr>

1.  Auth service
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXe6WDulfXyGiSxwU-M39_8VPEFyCBIRfmVSWAofbwoLaIzuN28WbL-OoIzIVxkIOS_-h55SABuH4uFvVHsGhdc5z9U-UiTzqHzBzYht7_69TT7oCyYFtTUYVPAevIXUuQ0MD8dc7s_S69ssFnWkPcFw4Zj1?key=f0ajtpqy-YMg5H0LL2hqaQ)
<br><br>

2.  Doctor service
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeJQIJw1NANv7va6BdI6gYegIO_qIw_rTcH0xvkObaNPO7h_2rzee97HAidEqyTeOLOU5dJL5P32GcbyK4xvXcCZtwioIfkv91PuSA3f0kJjjk3QyTeDVKyJu0amE4H19_cNXAJz97kjdwMEEvgQLnoHD4G?key=f0ajtpqy-YMg5H0LL2hqaQ)
<br><br>

3.  Appointment Service<br>
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXefPSpTBuoqADpzoWOtm2AhJJnxr4_2CePofNNCumnVAh6B8XFzFafS2IFR0a1KP6apbKsvxRuw92U-r5HXCKzI0grJoWmyMr4ezgapFU0S8sjgDQpAArfsCHcQPUBxrDLNWeSa7ca-0jFLkvU-UPY-WJPW?key=f0ajtpqy-YMg5H0LL2hqaQ)
<br><br>

4.  Rating service<br>
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXffHxovTkeEnyOgCx1ouztl0AhPXGhKPACBvgzpBBC9p2xyOz94U4CNaayxARD3XjUxQRhR3_TJXLFP8QmaDiapXPSogemR60ZITIwaqk5_NUEOXjaZZrtJwa_MVxcuvpEDetOEvhDM6dwHQ4sznQzRU5h7?key=f0ajtpqy-YMg5H0LL2hqaQ)<br><br>

5.  Chat service<br>
![](https://lh7-us.googleusercontent.com/docsz/AD_4nXeymqgYXzwLzAbpUtOju5ax0Sda7MjzQtMRy_isrSGIA0b86K66R5k8S-YL8hF7fsxRrh3HMlqpZb0U3vGB-lFpwhVjEHRO_KlWbzWmPG4jMx-2-eIrv6OHXDLgspnocLZTkcWNi77vkwIuAOPp0-Gl8tEW?key=f0ajtpqy-YMg5H0LL2hqaQ)<br><br>

Link postman collection:<br>
[https://www.postman.com/bold-rocket-984760/workspace/konsuldok/collection/26513725-dcb759b5-68d1-413d-a7d2-2b4272070834?action=share&creator=26513725](https://www.postman.com/bold-rocket-984760/workspace/konsuldok/collection/26513725-dcb759b5-68d1-413d-a7d2-2b4272070834?action=share&creator=26513725)<br><br>

Link dokumentasi testing : <br>
[https://docs.google.com/spreadsheets/d/1NH2sAu29KwanPqM7hB3uTTyycXG-9GSt6wTgIJ2ZwXo/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1NH2sAu29KwanPqM7hB3uTTyycXG-9GSt6wTgIJ2ZwXo/edit?usp=sharing)<br><br>

# Kesimpulan<br>
KonsulDok adalah aplikasi mobile berbasis Flutter yang bertujuan membantu penderita sakit dalam merencanakan janji temu dengan dokter. Aplikasi ini menawarkan fitur pemesanan dokter dengan mudah serta memungkinkan pasien untuk menghubungi dokter melalui fitur chat real-time. Backend aplikasi menggunakan ExpressJS. Docker Engine digunakan untuk pengembangan, dan menjalankan aplikasi dalam kontainer, memastikan portabilitas, isolasi, dan kemudahan deployment.
<br><br>
Pengembangan aplikasi ini melibatkan beberapa tahapan, mulai dari perencanaan dan analisis, desain dan prototyping, pengembangan dan implementasi, hingga deployment dan testing. Tim pengembangan aplikasi menerjemahkan desain UI ke dalam kode Flutter, serta pengembang backend membuat REST API, konfigurasi JWT, dan Websocket. Docker digunakan untuk memecah aplikasi menjadi layanan-layanan kecil yang dapat diatur secara independen(microservice).
<br><br>
Dari hasil testing di atas dapat disimpulkan bahwa containerization aplikasi KonsulDok berjalan dengan baik :
-   Dimana tiap service dapat berjalan dengan baik secara independen.
-   Api_gateway yang dibuat juga dapat berjalan dengan baik untuk melakukan hit ke endpoint dari tiap service.
-   Adminer yang digunakan sebagi user interface untuk memanajemen database dapat melakukan login & create database
-   Semua fitur berjalan dengan baik dengan response yang sesuai
-   Docker compose run → 9/9 service   
-   Docker compose restart → 9/9 service
-   Docker compose down → 9/9 service
