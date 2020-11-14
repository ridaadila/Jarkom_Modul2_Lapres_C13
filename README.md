# Jarkom_Modul2_Lapres_C13

# LAPRES MODUL 2 JARKOM

### KELOMPOK C13:
#### 1) Rida Adila 051111840000002
#### 2) Bayu Surya B. 05111840000114

###### Mohon maaf bila dalam lapres kami masih banyak kekurangan penjelasan, karena baru sadar kalau deadlinenya jam 00.00 15 November 2020

********

##### SOAL 1 : Membuat sebuah website utama dengan alamat http://semeruc13.pw

- Membuat file topologi.sh terlebih dahulu, syntaxnya adalah sbb :
![1 1](https://user-images.githubusercontent.com/71973415/99148992-cb838280-26bd-11eb-8f15-eba83f63bf22.PNG)

- Terdapat 6 UML. Client (Gresik, Sidoarjo), Server (Malang, Probolinggo, Mojokerto), Router (Surabaya).

- Setelah UML terbentuk dengan menjalankan bash topologi.sh , maka Setting IP pada setiap UML dengan mengetikkan nano /etc/network/interfaces Lalu setting IPnya sebagai berikut :


![1 2](https://user-images.githubusercontent.com/71973415/99149351-0e465a00-26c0-11eb-9ea0-ebb60038745b.PNG)
![1 3](https://user-images.githubusercontent.com/71973415/99149353-130b0e00-26c0-11eb-933e-6df02da518ed.PNG)
![1 4](https://user-images.githubusercontent.com/71973415/99149356-14d4d180-26c0-11eb-9a2f-f0dd8c2ff156.PNG)
![1 5](https://user-images.githubusercontent.com/71973415/99149357-17372b80-26c0-11eb-8ce4-77173e2f1624.PNG)
![1 6](https://user-images.githubusercontent.com/71973415/99149359-19998580-26c0-11eb-96c8-c8ec9a913ae9.PNG)
![1 7](https://user-images.githubusercontent.com/71973415/99149361-1b634900-26c0-11eb-8515-53d1131f2c84.PNG)

- Restart network dengan mengetikkan service networking restart

- Topologi yang dibuat sudah bisa berjalan secara lokal, tetapi kita belum bisa mengakses jaringan keluar. Ketikkan iptables –t nat –A POSTROUTING –o eth0 –j MASQUERADE –s 192.168.0.0/16 pada router SURABAYA.

- tes di semua UML dengan melakukan ping ke jaringan luar. Sebagai contoh coba ping google.com untuk mengecek apakah setting yang dilakukan sudah benar atau belum.

- Buat File proxy.sh , kemudian isikan sbb (sesuai dgn uname dan pass vpn masing-masing) :
export http_proxy=”http://[username-vpn]:[password]@proxy.its.ac.id:8080”
export https_proxy=”http://[username-vpn]:[password]@proxy.its.ac.id:8080”
export ftp_proxy=”http://[username-vpn]:[password]@proxy.its.ac.id:8080”

-Kemudian jalankan source proxy.sh pada setiap UML agar terhubung ke internet

- Hasil nomor 1 ketika diketikkan pada client gresik, mengarah ke IP probolinggo :

![1 8](https://user-images.githubusercontent.com/71973415/99150581-3639bb80-26c8-11eb-883f-8cd7aa2a04c2.PNG)

********

##### SOAL 2 : Membuat alias dengan alamat http://www.semeruc13.pw

- Hasil nomor 2 ketika diketikkan pada client gresik, mengarah ke IP probolinggo :

![2 1](https://user-images.githubusercontent.com/71973415/99150652-97618f00-26c8-11eb-9a91-c27298473afd.PNG)

*******

##### SOAL 3 : subdomain http://penanjakan.semeruc13.pw yang diatur DNS-nya pada MALANG dan mengarah ke IP Server PROBOLINGGO

- Hasil nomor 3 :

![3 1](https://user-images.githubusercontent.com/71973415/99150692-e0194800-26c8-11eb-8e36-31b14839ddc4.PNG)

**********

##### SOAL 6 : subdomain dengan alamat http://gunung.semeruc13.pw yang didelegasikan pada server MOJOKERTO dan mengarah ke IP Server PROBOLINGGO .

- Hasil nomor 6 :

![6 1](https://user-images.githubusercontent.com/71973415/99150823-c2001780-26c9-11eb-8138-1f3e66e4ce3e.PNG)
********
##### SOAL 7 : subdomain dengan nama http://naik.gunung.semeruc13.pw , domain ini diarahkan ke IP Server PROBOLINGGO

- Hasil nomor 7 :
![7 1](https://user-images.githubusercontent.com/71973415/99150877-055a8600-26ca-11eb-8fda-19fedad90e7e.PNG)

******

##### SOAL 8 : Domain http://semeruc13.pw memiliki DocumentRoot pada /var/www/semeruc13.pw

- Settingan nomor 8 :

![8 1](https://user-images.githubusercontent.com/71973415/99150978-97628e80-26ca-11eb-868b-f31403774fe5.PNG)

- Hasil di browser :

![8 2](https://user-images.githubusercontent.com/71973415/99151001-b5c88a00-26ca-11eb-9a67-bc227b28939c.PNG)


*********

##### SOAL 9 : Awalnya web dapat diakses menggunakan alamat http://semeruc13.pw/index.php/home . Karena dirasa alamat urlnya kurang bagus, maka diaktifkan mod rewrite agar urlnya menjadi http://semeruc13.pw/home

- Membuat file .htaccess pada /var/www/semeruc13.pw

![9 1](https://user-images.githubusercontent.com/71973415/99151075-3e472a80-26cb-11eb-8129-7f6caeac2c3b.PNG)

- Hasil di browser :

![9 2](https://user-images.githubusercontent.com/71973415/99151086-56b74500-26cb-11eb-91e4-e301fae186f3.PNG)

******

##### SOAL 10 :Web http://penanjakan.semeruc13.pw akan digunakan untuk menyimpan assets file yang memiliki DocumentRoot pada /var/www/ penanjakan.semeruyyy.pw dan memiliki struktur folder sebagai berikut: 
/var/www/ penanjakan.semeruyyy.pw
/public/javascripts
/public/css
/public/images
/errors

- Settingan : 

![10 1](https://user-images.githubusercontent.com/71973415/99151147-c4fc0780-26cb-11eb-88c1-c627e4821105.PNG)

- Hasil : 
![10 2](https://user-images.githubusercontent.com/71973415/99151186-df35e580-26cb-11eb-9386-196f64eb1306.PNG)

*******

##### SOAL 11 : Pada folder /public dibolehkan directory listing namun untuk folder yang berada di dalamnya tidak dibolehkan

- Settingan : 

![11 2](https://user-images.githubusercontent.com/71973415/99151230-31770680-26cc-11eb-8b33-65031393f741.PNG)

- Hasil : 

![11 1](https://user-images.githubusercontent.com/71973415/99151207-160bfb80-26cc-11eb-91e3-655cdde591bf.PNG)

*****
##### SOAL 12 : Untuk mengatasi HTTP Error code 404, disediakan file 404.html pada folder /errors untuk mengganti error default 404 dari Apache

- Settingan : 

![12 1](https://user-images.githubusercontent.com/71973415/99151284-8fa3e980-26cc-11eb-99a2-2032f8e82c4b.PNG)

- Hasil : 

![12 2](https://user-images.githubusercontent.com/71973415/99151295-afd3a880-26cc-11eb-8d07-4440dbb61611.PNG)

*******

##### SOAL 13 : Untuk mengakses file assets javascript awalnya harus menggunakan url http://penanjakan.semeruc13.pw/public/javascripts . Karena terlalu panjang maka dibuatkan konfigurasi virtual host agar ketika mengakses file assets menjadi http://penanjakan.semeruc13.pw/js .

- Settingan :

![13 1](https://user-images.githubusercontent.com/71973415/99151335-fd501580-26cc-11eb-8004-a4c91e655b1d.PNG)

Hasil (Forbidden karena tidak boleh directory listing) :

![13 2](https://user-images.githubusercontent.com/71973415/99151345-1bb61100-26cd-11eb-87e0-2fd24ff9912e.PNG)

*******
##### SOAL 14 : web http://naik.gunung.semeruc13.pw sudah bisa diakses hanya dengan menggunakan port 8888. DocumentRoot web berada pada /var/www/naik.gunung.semeruc13.pw .

- Settingan :

![14 1](https://user-images.githubusercontent.com/71973415/99151404-8a936a00-26cd-11eb-8f63-2fdd40bad431.PNG)

![14 2](https://user-images.githubusercontent.com/71973415/99151441-bca4cc00-26cd-11eb-9dbc-847aaa84ab14.PNG)

********

##### SOAL 15 : Dikarenakan web http:// naik.gunung.semeruc13.pw bersifat private, dibuatkan autentikasi username dan password

- Settingan :

![15 1](https://user-images.githubusercontent.com/71973415/99151487-1e653600-26ce-11eb-9301-b6d08b67f479.PNG)

- Hasil :


![15 2](https://user-images.githubusercontent.com/71973415/99151509-46ed3000-26ce-11eb-9754-0ec49bcb38ee.PNG)

![15 3](https://user-images.githubusercontent.com/71973415/99151513-58363c80-26ce-11eb-9a2b-ba77ad238ced.PNG)

********
##### SOAL 16 : Setiap mengunjungi IP Probolinggo akan dialihkan otomatis ke http://semeruc13.pw

- Settingan :

![16 1](https://user-images.githubusercontent.com/71973415/99151551-b531f280-26ce-11eb-895d-d7c5edf1d7b3.PNG)

- Hasil :

![16 2](https://user-images.githubusercontent.com/71973415/99151574-df83b000-26ce-11eb-84f3-477b53f597e6.PNG)
