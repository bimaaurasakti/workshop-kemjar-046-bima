## Cover

<h3 align="center">
    <b>Praktikum Kemanan Jaringan</b><br>
    A3 Injection (OWASP 10 Juice Shop)
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

SQL Injection (SQLi) merupakan jenis serangan injeksi yang memungkinkan untuk mengeksekusi statement SQL yang berbahaya. Statement yang digunakan ini dapat mengontrol server database di belakang aplikasi web.

Hacker dapat melakukan otentikasi dan otorisasi halaman web atau aplikasi web dan mengambil konten dari seluruh database SQL. Mereka juga dapat menggunakan SQL Injection untuk menambah, mengubah, dan menghapus catatan dalam database.

Serangan SQL Injection ini dapat menarget semua website yang memanfaatkan SQL database, seperti MySQL, PostgreSQL, SQL Server, dan lainnya [[1](https://dqlab.id/kenali-sql-injection-dan-pencegahannya-sebelum-terlambat)].

Berikut ini macam-macam Injection yang berhasil ditemukan pada Website OWASP Juice Shop beserta video demonya:

---> [Video Demo](https://drive.google.com/drive/folders/1PE0PXa1lkr7EXYPnLLwehOOLdQ2jlo73?usp=share_link) <---


### A. Bender Login

Bender login adalah login menggunakan akun email bender@juice-sh.op menggunakan injection

1. Masuk kehalaman login dengan melakukan klik account pada bagian navbar lalu klik login

    ![Screenshot](images/1.png)

2. Selanjutnya pada halaman login ini masukkan email bender@juice-sh.op dan dengan password diisi dengan inputan acak. Untuk melakukan injection tambahkan ' -- yang dimana maksud dari inputan tersebut adalah digunakan untuk menonaktifkan argumen query sql setelahnya atau melakukan comment jadi kita dapat menonaktifkan kondisi pengecekan passwordnya

    ![Screenshot](images/2.png)

3. Submit login form, maka kita akan berhasil masuk sebagai user bender

    ![Screenshot](images/3.png)
    ![Screenshot](images/4.png)


### B. Jim Login

Sama seperti Bender login, Jim Login adalah login menggunakan akun email jim@juice-sh.op menggunakan injection

1. Pada web OWASP Juice Shop, pergi kehalaman customer feedback yang berada pada sidebar menu web

    ![Screenshot](images/1.png)

2. Selanjutnya pada halaman login ini masukkan email jim@juice-sh.op dan dengan password diisi dengan inputan acak. Untuk melakukan injection tambahkan ' OR '1'='1 yang dimana maksud dari inputan tersebut adalah digunakan untuk menambahkan kondisi jika 1=1 maka kondisi return pasti sama dengan true, maka login akan berhasil dilakukan

    ![Screenshot](images/5.png)

3. Submit login form, maka kita akan berhasil masuk sebagai user jim
    ![Screenshot](images/6.png)

