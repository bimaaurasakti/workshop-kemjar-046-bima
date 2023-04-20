## Cover

<h3 align="center">
    <b>Praktikum Kemanan Jaringan</b><br>
    A5 Security Misconfiguration (OWASP 10 Juice Shop)
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

Security Misconfiguration keamanan adalah kelemahan yang paling sering terjadi di antara kelemahan lain di daftar ini. Biasanya kesalahan terjadi jika Anda hanya menggunakan default konfigurasi tanpa melihat kebutuhan website [[1](https://www.dewaweb.com/blog/owasp-standar-keamanan-web-app-dunia/)].

Berikut ini macam-macam Security Misconfiguration yang berhasil ditemukan pada Website OWASP Juice Shop beserta video demonya:

---> [Video Demo](https://drive.google.com/drive/folders/1PE0PXa1lkr7EXYPnLLwehOOLdQ2jlo73?usp=share_link) <---


### A. Error Handling

memunculkan error, tetapi error yang ditampilkan tidak secara bagus dan konsisten.

1. Nyalakan Burp Suite terlebih dahulu

    ![Screenshot](images/1.png)

2. Selanjutnya buka browser dan pergi ke halaman utama website OWASP Juice Shop

    ![Screenshot](images/2.png)

3. Buka kembali Burp Suite maka akan muncul request baru yaitu /rest/product/search

    ![Screenshot](images/3.png)

4. Masukkan payload /rest/product/search tadi ke repeater lalu ubah enpointnya menjadi text random lalu klik tombol send

    ![Screenshot](images/4.png)

    maka yang terjadi adalah response error 500 atau internal server error yang disini terlihat terdapat error message yang begitu panjangnya dan tidak tertata


### B. Deprecated Interface

Menggunakan antarmuka B2B usang yang tidak dimatikan dengan benar.

1. Pada halaman utama, klik tombol menu di pojok kiri atas untuk memunculkan sidebar. Setelah itu klik complaint

    ![Screenshot](images/5.png)

2. Setelah sudah masuk ke halaman complaint, isikan form yang ada, dan masukkan file dengan format xml

    ![Screenshot](images/6.png)

3. Setelah itu akan muncul challange Deprecated Interface berhasil di selesaikan seperti ini

    ![Screenshot](images/7.png)

4. Jika kita lihat di proxy history pada burp suite, akan muncul error panjang seperti ini

    ![Screenshot](images/8.png)

