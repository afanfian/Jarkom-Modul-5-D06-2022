# Laporan Resmi Praktikum Modul 5 Jarkom Kelompok D06
Dokumen laporan resmi praktikum modul 5 Jarkom Kelompok D06 Jaringan Komputer D Tahun 2022/2023

### Anggota Kelompok:
Nama Lengkap                | NRP
--------------------------- | -------------
Fian Awamiry Maulana        | 5025201035 
Rere Arga Dewanata          | 5025201078 
Muhamad Ridho Pratama       | 5025201186  

  - [Soal A](#soal-A)
    - [Jawab](#jawab-A)
  - [Soal B](#soal-B)
    - [Jawab](#jawab-B)
  - [Soal C](#soal-C)
    - [Jawab](#jawab-C)
  - [Soal D](#soal-D)
    - [Jawab](#jawab-C)
  - [Soal 1](#soal-1)
    - [Jawab](#jawab-1)
  - [Soal 2](#soal-2)
    - [Jawab](#jawab-2)
  - [Soal 3](#soal-3)
    - [Jawab](#jawab-3)
  - [Soal 4](#soal-4)
    - [Jawab](#jawab-4)
  - [Soal 5](#soal-5)
    - [Jawab](#jawab-5)
  - [Soal 6](#soal-6)
    - [Jawab](#jawab-6)
    
## Soal A  
Tugas pertama kalian yaitu membuat topologi jaringan sesuai dengan rancangan yang diberikan Loid dibawah ini:  
Keterangan :	Eden adalah DNS Server
WISE adalah DHCP Server
		Garden dan SSS adalah Web Server
		Jumlah Host pada Forger adalah 62 host
		Jumlah Host pada Desmond adalah 700 host
		Jumlah Host pada Blackbell adalah 255 host
		Jumlah Host pada Briar adalah 200 host
### Jawab  

## Soal B  
Untuk menjaga perdamaian dunia, Loid ingin meminta kalian untuk membuat topologi tersebut menggunakan teknik CIDR atau VLSM setelah melakukan subnetting.  
### Jawab  
Disini kami menggunakan teknik VLSM yaitu dengan Pembagian Subnetting, Gambar Tree dan Pembagian Host ID sebagai berikut:  
  * Pembagian subnetting menggunakan VLSM (Variable Length Subnet Masking):  
  ![Pembagian Subnet](https://user-images.githubusercontent.com/82325182/206819220-5ed9b840-7ddd-41c6-b7f1-a13899d6920c.png)
  * Pembuatan Tree dari pembagian subnetting diatas:  
  ![Pembagian Subnet-VLSM_Tree drawio](https://user-images.githubusercontent.com/82325182/206819251-7c503dc5-3175-4b9c-88d0-002de666c687.png)
  * Pembagian Host ID:  
  ![Pembagian Host ID](https://user-images.githubusercontent.com/82325182/206819261-bf2dbccf-34b6-48e2-8174-7f87b86e5c28.png)
## Soal C  
Anya, putri pertama Loid, juga berpesan kepada anda agar melakukan Routing agar setiap perangkat pada jaringan tersebut dapat terhubung.  
### Jawab  

## Soal D  
Tugas berikutnya adalah memberikan ip pada subnet Forger, Desmond, Blackbell, dan Briar secara dinamis menggunakan bantuan DHCP server. Kemudian kalian ingat bahwa kalian harus setting DHCP Relay pada router yang menghubungkannya.  
### Jawab  

## Soal 1  
Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Strix menggunakan iptables, tetapi Loid tidak ingin menggunakan MASQUERADE.  
### Jawab  

## Soal 2  
Kalian diminta untuk melakukan drop semua TCP dan UDP dari luar Topologi kalian pada server yang merupakan DHCP Server demi menjaga keamanan.  
### Jawab  

## Soal 3  
Loid meminta kalian untuk membatasi DHCP dan DNS Server hanya boleh menerima maksimal 2 koneksi ICMP secara bersamaan menggunakan iptables, selebihnya didrop.  
### Jawab  

## Soal 4  
Akses menuju Web Server hanya diperbolehkan disaat jam kerja yaitu Senin sampai Jumat pada pukul 07.00 - 16.00.  
### Jawab  

## Soal 5  
Karena kita memiliki 2 Web Server, Loid ingin Ostania diatur sehingga setiap request dari client yang mengakses Garden dengan port 80 akan didistribusikan secara bergantian pada SSS dan Garden secara berurutan dan request dari client yang mengakses SSS dengan port 443 akan didistribusikan secara bergantian pada Garden dan SSS secara berurutan.  
### Jawab  

## Soal 6  
Karena Loid ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level.  
### Jawab  
