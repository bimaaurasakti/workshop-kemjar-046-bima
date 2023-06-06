## Cover

<h3 align="center">
    <b>Praktikum Kemanan Jaringan</b><br>
    A8 Software and Data Integrity Failures (OWASP 10 Juice Shop)
</h3>
<br>
<p align="center">
  <img src="../../public/logo_pens.png" alt="Logo PENS" width="300">
</p>
<br>
<p align="center">
    Dosen Pembimbing:<br>
    Ferry Astika Saputra, S.T., M.Sc.
</p>
<br>
<p align="center">
    Disusun Oleh:<br>
    Bima Aurasakti Rochmatullah (3122640046)
</p>
<br>
<p align="center">
    <b>
        KELAS D4 LJ IT B <br>
        JURUSAN D4 LJ TEKNIK INFORMATIKA <br>
        DEPARTEMEN TEKNIK INFORMATIKA DAN KOMPUTER <br> 
        POLITEKNIK ELEKTRONIKA NEGERI SURABAYA <br>
        2023
    </b>
</p>
<br>


## Laporan

A08:2021 adalah pendatang baru dan berbicara tentang bahaya yang terlihat/tidak terlihat yang dibawa oleh perangkat lunak/aplikasi era modern. Sering disebut sebagai Software and Data Integrity Failures OWASP, ini berbicara tentang asumsi yang terkait dengan critical CI/CD pipeline, penanganan data, dan kegagalan integritas pembaruan perangkat lunak. Dalam bahasa awam, ketika seseorang menggunakan perangkat lunak/aplikasi/data penting tanpa mengikuti praktik verifikasi atau autentikasi terbaik, beberapa pendekatan ancaman dan A08:2021 mencakup semuanya. Tidak melalui proses otentikasi menciptakan peluang bagi peretas/aktor ancaman untuk mendapatkan akses resmi ke aplikasi/perangkat lunak yang dibatasi. Setelah itu terjadi, mereka dibiarkan menyebabkan malapetaka tanpa akhir seperti injeksi kode berbahaya, pencurian data, dan mengendalikan operasi aplikasi/perangkat lunak [[1](https://www.wallarm.com/what/a04-2021-owasp-software-and-data-integrity-failures)].

---> [Video Demo](https://drive.google.com/drive/folders/1PE0PXa1lkr7EXYPnLLwehOOLdQ2jlo73?usp=share_link) <---


### Percobaan

Pada percobaan ini akan menunjukan mengunduh kode tanpa pemeriksaan integritas.

1. Buka Aplikasi Juice Shop.

    ![Screenshot](images/1.png)

2. Tambahkan /ftp pada URL Juice Shop kita menjadi http://localhost:3000/ftp

    ![Screenshot](images/2.png)

3. Klik package.json.bak, maka akan muncul tampilan sebagai berikut

    ![Screenshot](images/3.png)

4. ubah URL pakcage.json.bak menjadi sebagai berikut localhost:3000/ftp/package.json.bak%2500.md lalu jalankan, maka kita akan mendownload file package.json tersebut seperti pada gambar berikut

    ![Screenshot](images/4.png)

5. ubah URL pakcage.json.bak menjadi sebagai berikut localhost:3000/ftp/package.json.bak%2500.md lalu jalankan, maka kita akan mendownload file package.json tersebut seperti pada gambar berikut

    ![Screenshot](images/4-1.png)
    ![Screenshot](images/4-2.png)

    Berikut adalah isi dari file package.json yang berhasil terdownload

