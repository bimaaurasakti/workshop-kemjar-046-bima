## Cover

<h3 align="center">
    <b>Praktikum Kemanan Jaringan</b><br>
    Broken Access Control (OWASP 10 Juice Shop)
</h3>
<br>
<p align="center">
  <img src="../../image/logo_pens.png" alt="Size Limit CLI" width="300">
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

34 Common Weakness Enumerations (CWEs) memetakan Broken Access Control lebih banyak terjadi pada aplikasi dibandingkan kategori lainnya. Penyerang dan peretas dapat mengakses sebuah sistem ketika autentikasi dan pembatasan akses tidak diterapkan dengan baik. Dengan kata lain, Broken Access Control memungkinkan entri yang tidak sah yang dapat mengakibatkan kerentanan data dan file yang bersifat sensitif. Kontrol akses yang lemah terkait manajemen kredensial dapat dihindari dengan metode coding yang unik dan tindakan khusus seperti mematikan akun administratif dan penggunaan autentikasi multi-faktor[[1]](https://www.mandreel.com/indonesia/owasp/#:~:text=A01%3A2021%20Broken%20Access%20Control%20(Kelemahan%20Access%20Control),-34%20Common%20Weakness&text=Dengan%20kata%20lain%2C%20Broken%20Access,dan%20file%20yang%20bersifat%20sensitif.).

![Screenshot](../../image/task-2/0.png)

Gambar diatas menjelaskan bahwa user dapat mengakses pribadi pada server dengan Access Control List. Tetapi jika Access Control List tersebut tidak menghandle beberapa enpoint, maka orang lain atau hacker dapat mengakses data user tersebut pada server. 

Macam-macam Broken Access Control yang berhasil ditemukan pada Website OWASP Juice Shop:

### A. Forged Feedback   

Kita akan menambahkan feedback kepada toko dengan username sebagai pengguna lain

1. Pergi kehalaman feedback /#/contract untuk memberikan feedback dan submit feedback tersebut

    ![Screenshot](../../image/task-2/1.png)

2. Pergi ke burp suite, pada tab proxy > HTTP History, cari endpoint dengan methode POST yang digunakan untuk mengupdate data feedback

    ![Screenshot](../../image/task-2/2.png)

    Perhatikan data response pada endpoint tersebut bahwa terdapat “UserId” dengan data null, yang menandakan bahwa user yang membuat feedback adalah user anonymous.

3. Langkah selanjutnya, klik kanan pada request, lalu klik send to repeater

    ![Screenshot](../../image/task-2/3.png)

4. Selanjutnya, pergi ke tab repeater, lalu tambahkan data baru Bernama “UserId” dan berikan angka pada data “UserId” tersebut lalu klik tombol send

    ![Screenshot](../../image/task-2/4.png)

5. Muncul pesan response success dengan “UserId” orang lain tanpa login

    ![Screenshot](../../image/task-2/5.png)

### B. Forged Feedback   

Posting ulasan produk sebagai pengguna lain atau edit ulasan pengguna yang sudah ada

1.	Login as admin first using injection

    ![Screenshot](../../image/task-2/6.png)

2.	Review produk

    ![Screenshot](../../image/task-2/7.png)

3.	Buka burp suite lalu check endpoint terakhir pada HTTP History dengan method PUT dan kirim ke repeater

    ![Screenshot](../../image/task-2/8.png)

4.	Ubah request body, dengan mengubah “author” menjadi email pengguna lain yang terdaftar lalu submit

    ![Screenshot](../../image/task-2/9.png)

5.	Muncul pesan berhasil menambahkan review product menggunakan user lain

    ![Screenshot](../../image/task-2/10.png)
    <br>
    ![Screenshot](../../image/task-2/11.png)

### C. Manipulate Basket

Masukkan produk tambahan ke keranjang belanja pengguna lain

1.	Register a new user account

    ![Screenshot](../../image/task-2/12.png)

    Belum ada produk pada basket

    ![Screenshot](../../image/task-2/13.png)

2.	Login sebagai user lain selain yang kita daftar sebelumnya semisal admin

3.	Tambahkan 1 produk ke keranjang
    
    ![Screenshot](../../image/task-2/14.png)

4.	Buka burp suite dan check endpoint terakhir untuk mengupdate keranjang lalu kirim ke repeater
    
    ![Screenshot](../../image/task-2/15.png)

5.	Pada repeater ubah request body data “BasketId” menjadi double, lalu klik tombol send, maka akan muncul response berhasil menambahkan ke keranjang dengan “BasketId” 6
    
    ![Screenshot](../../image/task-2/16.png)
    <br>
    ![Screenshot](../../image/task-2/17.png)

### D. Product Tempering

1.	Login sebagai admin terlebih dahulu menggunakan injection

2.	Buka burb suite dan cari endpoint search product dan kirim ke repeater

    ![Screenshot](../../image/task-2/18.png)

3.	Endcode “OWASP SSL Advanced Forensic Tool (O-Saft)” sebagai url lalu masukan kedalam url parameter pada repeater yang baru kita kirimkan sebelumnya. Setelah itu klik tombol send

    ![Screenshot](../../image/task-2/19.png)
    <br>
    ![Screenshot](../../image/task-2/20.png)

4.	Dengan menggunakan langkah sebelumnya, kita akan mendapatkan “id” dari produk “OWASP SSL Advanced Forensic Tool (O-Saft)”. Setelah itu, kita buat repeater baru dari repeater search produk ini. Kita ubah url nya, menambahkan header Content-Type dan request body untuk mengupdate deskripsi produk yang memiliki “id” 9. Selanjutnya kita klik tombol send, maka akan muncul response berhasil dan deskripsi yang telah berubah.

    ![Screenshot](../../image/task-2/21.png)
    <br>
    ![Screenshot](../../image/task-2/22.png)
    <br>
    ![Screenshot](../../image/task-2/23.png)