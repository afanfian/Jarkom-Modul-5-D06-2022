# Laporan Resmi Praktikum Modul 5 Jarkom Kelompok D06
Dokumen laporan resmi praktikum modul 5 Jarkom Kelompok D06 Jaringan Komputer D Tahun 2022/2023

### Anggota Kelompok:
Nama Lengkap                | NRP
--------------------------- | -------------
Fian Awamiry Maulana        | 5025201035 
Rere Arga Dewanata          | 5025201078 
Muhamad Ridho Pratama       | 5025201186  

- [Laporan Resmi Praktikum Modul 5 Jarkom Kelompok D06](#laporan-resmi-praktikum-modul-5-jarkom-kelompok-d06)
    - [Anggota Kelompok:](#anggota-kelompok)
  - [Soal A](#soal-a)
    - [Jawab](#jawab)
  - [Soal B](#soal-b)
    - [Jawab](#jawab-1)
  - [Soal C](#soal-c)
    - [Jawab](#jawab-2)
  - [Soal D](#soal-d)
    - [Jawab](#jawab-3)
      - [Di server WISE (DHCP Server)](#di-server-wise-dhcp-server)
      - [Di Router untuk DHCP Relay](#di-router-untuk-dhcp-relay)
  - [Soal 1](#soal-1)
    - [Jawab](#jawab-4)
  - [Soal 2](#soal-2)
    - [Jawab](#jawab-5)
  - [Soal 3](#soal-3)
    - [Jawab](#jawab-6)
  - [Soal 4](#soal-4)
    - [Jawab](#jawab-7)
  - [Soal 5](#soal-5)
    - [Jawab](#jawab-8)
  - [Soal 6](#soal-6)
    - [Jawab](#jawab-9)
    
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
Topologi jaringan yang telah kami buat sebagai berikut:  
![image](https://user-images.githubusercontent.com/82325182/206819811-7f8af1fa-38b0-46b4-8d3c-e17e6dd81344.png)  
Alamat IP pada pembagian subnetting pada nomer 2, yaitu sebagai berikut:  
 * **A1** 
   * Eden  
     auto eth0  
	 iface eth0 inet static  
         address 10.18.7.130  
         netmask 255.255.255.248  
         gateway 10.18.7.129  

   * WISE  
     auto eth0  
	 iface eth0 inet static  
         address 10.18.7.131  
         netmask 255.255.255.248  
         gateway 10.18.7.129  
   * Router Westalis mengarah ke A1 (Kiri)  
      auto eth3  
	 iface eth3 inet static  
         address 10.18.7.129  
         netmask 255.255.255.248  
  * **A2**
    * Router Westalis mengarah ke A2 (Atas)  
      auto eth0  
	 iface eth0 inet static  
         address 10.18.7.146  
         netmask 255.255.255.252  
         gateway 10.18.7.145  
    * Router Strix mengarah ke A2 (Bawah)  
      auto eth2  
	 iface eth2 inet static  
         address 10.18.7.145  
         netmask 255.255.255.252  
  * **A3**  
    * Router Strix mengarah ke A3 (Kanan)
      auto eth1  
	iface eth1 inet static  
        address 10.18.7.149  
        netmask 255.255.255.252  
    * Router Ostania mengarah ke A3 (Kiri)  
      auto eth0  
	iface eth0 inet static  
        address 10.18.7.150  
        netmask 255.255.255.252  
        gateway 10.18.7.149  
  * **A4**  
    * Router Ostania mengarah ke A4 (Atas)  
      auto eth1
	iface eth1 inet static
        address 10.18.4.1
        netmask 255.255.254.0

    * Blackbell 255 Host  
      auto eth0  
      iface eth0 inet dhcp  
  * **A5**  
    * Router Ostania mengarah ke A5 (Kanan)  
      auto eth2  
	 iface eth2 inet static  
         address 10.18.7.137  
         netmask 255.255.255.248  
    * Garden  
      auto eth0  
	 iface eth0 inet static  
         address 10.18.7.138  
         netmask 255.255.255.248  
         gateway 10.18.7.137  
    * SSS  
      auto eth0  
	 iface eth0 inet static  
         address 10.18.7.139  
         netmask 255.255.255.248  
         gateway 10.18.7.137  
  * **A6**  
    * Router Westalis mengarah ke A6 (Bawah)  
      auto eth2  
	 iface eth2 inet static  
         address 10.18.7.1  
         netmask 255.255.255.128  
    * Forger 62 Host  
      auto eth0  
 	  iface eth0 inet dhcp  
  * **A7**  
    * Router Westalis mengarah ke A7 (Kanan)  
      auto eth1  
 	 iface eth1 inet static  
         address 10.18.0.1  
         netmask 255.255.252.0  
    * Desmond 700 Host  
      auto eth0  
	  iface eth0 inet dhcp  
  * **A8**  
    * Router Ostania mengarah ke A8 (Bawah)  
      auto eth3
	 iface eth3 inet static
         address 10.18.6.1
         netmask 255.255.255.0
    * Briar 200 Host  
      auto eth0  
	  iface eth0 inet dhcp  
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
Ketikkan command ```route -n``` Routing pada 3 router, yaitu Router Strix, Ostania & Westalis, sebagai berikut:  
  * **Router Strix**  
    Destination     Gateway         Genmask         Flags Metric Ref    Use Iface  
    0.0.0.0         192.168.122.1   0.0.0.0         UG    208    0        0 eth0  
    10.18.0.0       10.18.7.146     255.255.252.0   UG    0      0        0 eth2  
    10.18.4.0       10.18.7.150     255.255.254.0   UG    0      0        0 eth1  
    10.18.6.0       10.18.7.150     255.255.255.0   UG    0      0        0 eth1  
    10.18.7.0       10.18.7.146     255.255.255.128 UG    0      0        0 eth2  
    10.18.7.128     10.18.7.146     255.255.255.248 UG    0      0        0 eth2  
    10.18.7.136     10.18.7.150     255.255.255.248 UG    0      0        0 eth1  
    10.18.7.144     0.0.0.0         255.255.255.252 U     0      0        0 eth2  
    10.18.7.148     0.0.0.0         255.255.255.252 U     0      0        0 eth1  
    192.168.122.0   0.0.0.0         255.255.255.0   U     0      0        0 eth0  
  * **Router Ostania**  
    Destination     Gateway         Genmask         Flags Metric Ref    Use Iface  
    0.0.0.0         10.18.7.149     0.0.0.0         UG    0      0        0 eth0  
    10.18.4.0       0.0.0.0         255.255.254.0   U     0      0        0 eth1  
    10.18.6.0       0.0.0.0         255.255.255.0   U     0      0        0 eth3  
    10.18.7.136     0.0.0.0         255.255.255.248 U     0      0        0 eth2  
    10.18.7.148     0.0.0.0         255.255.255.252 U     0      0        0 eth0   
  * **Router Westalis**  
    Destination     Gateway         Genmask         Flags Metric Ref    Use Iface  
    0.0.0.0         10.18.7.145     0.0.0.0         UG    0      0        0 eth0  
    10.18.0.0       0.0.0.0         255.255.252.0   U     0      0        0 eth1  
    10.18.7.0       0.0.0.0         255.255.255.128 U     0      0        0 eth2  
    10.18.7.128     0.0.0.0         255.255.255.248 U     0      0        0 eth3  
    10.18.7.144     0.0.0.0         255.255.255.252 U     0      0        0 eth0  
## Soal D  
Tugas berikutnya adalah memberikan ip pada subnet Forger, Desmond, Blackbell, dan Briar secara dinamis menggunakan bantuan DHCP server. Kemudian kalian ingat bahwa kalian harus setting DHCP Relay pada router yang menghubungkannya.
### Jawab

#### Di server WISE (DHCP Server)

  1. Install isc-dhcp-server dengan `apt install isc-dhcp-server`
  2. Ubah file `/etc/default/isc-dhcp-server` dan isi variabel `INTERFACES` dengan "`eth0`"
      ```
      # On what interfaces should the DHCP server (dhcpd) serve DHCP requests?
      #       Separate multiple interfaces with spaces, e.g. "eth0 eth1".
      INTERFACES="eth0"
      ```
  3. Edit file `/etc/dhcp/dhcpd.conf` dan tambahkan line berikut:
      ```
      # Ke A6 (Forger)
      subnet 10.18.7.0 netmask 255.255.255.128 {
          range 10.18.7.2 10.18.7.63;
          option routers 10.18.7.1;
          option broadcast-address 10.18.7.127;
          option domain-name-servers 10.18.7.130; # IP Eden
          default-lease-time 600;
          max-lease-time 7200;
      }

      # Ke A7 (Desmond)
      subnet 10.18.0.0 netmask 255.255.252.0 {
          range 10.18.0.2 10.18.3.191;
          option routers 10.18.0.1;
          option broadcast-address 10.18.3.254;
          option domain-name-servers 10.18.7.130; # IP Eden
          default-lease-time 600;
          max-lease-time 7200;
      }

      # Ke A4 (Blackbell)
      subnet 10.18.4.0 netmask 255.255.254.0 {
          range 10.18.4.2 10.18.5.0;
          option routers 10.18.4.1;
          option broadcast-address 10.18.5.255;
          option domain-name-servers 10.18.7.130;
          default-lease-time 600;
          max-lease-time 7200;
      }

      # Ke A8 (Briar)
      subnet 10.18.6.0 netmask 255.255.255.0 {
          range 10.18.6.2 10.18.6.201;
          option routers 10.18.6.1;
          option broadcast-address 10.18.6.255;
          option domain-name-servers 10.18.7.130;
          default-lease-time 600;
          max-lease-time 7200;
      }

      # Ke A1 (Sendiri)
      subnet 10.18.7.128 netmask 255.255.255.248 {
      }
      ```
  4. Restart isc-dhcp-server dengan `service isc-dhcp-server restart`

#### Di Router untuk DHCP Relay

  1. Di Strix, Ostania, dan Westalis, install isc-dhcp-relay dengan `apt install isc-dhcp-relay`
  2. Ubah file `/etc/default/isc-dhcp-relay` dengan ketentuan masing-masing router sebagai berikut:
       - Strix
          ```
          # What servers should the DHCP relay forward requests to?
          SERVERS="10.18.7.131"

          # On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
          INTERFACES="eth1 eth2"
          ```
       - Ostania
          ```
          # What servers should the DHCP relay forward requests to?
          SERVERS="10.18.7.131"

          # On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
          INTERFACES="eth0 eth1 eth3"
          ```
       - Westalis
          ```
          # What servers should the DHCP relay forward requests to?
          SERVERS="10.18.7.131"

          # On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
          INTERFACES="eth0 eth1 eth2 eth3"
          ```
  3. Restart isc-dhcp-relay di setiap router dengan `service isc-dhcp-relay restart`

Berikut adalah tampilan IP di tiap subnet yang membutuhkan IP dinamis:
- Forger<br>
  ![soal_D_forger](https://user-images.githubusercontent.com/55425460/206826568-02686f5e-ba01-49bc-a99c-dca5cd661576.png)
- Desmond<br>
  ![soal_D_desmond](https://user-images.githubusercontent.com/55425460/206826573-6d14eb52-a400-47d3-a8c7-01bcef9355ec.png)
- Blackbell<br>
  ![soal_D_blackbell](https://user-images.githubusercontent.com/55425460/206826575-b6b6aca4-0551-4504-8b41-da7cff5a26c9.png)
- Briar<br>
  ![soal_D_briar](https://user-images.githubusercontent.com/55425460/206826578-06ec9ea4-8eaa-4076-bfda-40aef53583ca.png)


## Soal 1  
Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Strix menggunakan iptables, tetapi Loid tidak ingin menggunakan MASQUERADE.  

### Jawab

1. Di router Strix, hapus rule iptables yang masih menggunakan MASQUERADE
2. Kita perlu dapatkan IP address dari NAT terlebih dahulu, karena setiap node-nya di-restart, IP yang didapatkan berubah-ubah. Dapat dilakukan dengan command berikut:
    ```
    ipgateway=$(ip -4 addr show eth0 | grep inet | awk '{ print substr( $2, 1, length($2)-3 ) }')
    ```
3. Masukkan IP yang didapat tadi ke rule iptables:
    ```
    iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ipgateway
    ```

## Soal 2  
Kalian diminta untuk melakukan drop semua TCP dan UDP dari luar Topologi kalian pada server yang merupakan DHCP Server demi menjaga keamanan.

### Jawab  

1. Di router Strix, tambahkan aturan iptables sebagai berikut:
    ```
    iptables -A FORWARD -p udp -d 10.18.7.131 -i eth0 -j DROP
    iptables -A FORWARD -p tcp -d 10.18.7.131 -i eth0 -j DROP
    ```
2. Tes koneksi ke luar di server WISE<br>
    ![soal_no2_no2](https://user-images.githubusercontent.com/55425460/206826587-7e1e011a-0ae5-4fe8-ad1b-71f340f41eb6.png)

## Soal 3  
Loid meminta kalian untuk membatasi DHCP dan DNS Server hanya boleh menerima maksimal 2 koneksi ICMP secara bersamaan menggunakan iptables, selebihnya didrop.  
### Jawab

1. Di server Eden dan WISE, tambahkan aturan iptables sebagai berikut
    ```
    iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT 
    iptables -A INPUT -p icmp -m connlimit --connlimit-above 2 --connlimit-mask 0 -j DROP
    ```

Berikut adalah tampilan saat melakukan `ping` ke Eden dari 3 client yang berbeda:
- Koneksi pertama (dari Desmond)<br>
  ![soal_no3_desmond](https://user-images.githubusercontent.com/55425460/206826595-d4706d9e-893e-4e58-a274-8642152400e4.png)
- Koneksi kedua (dari Forger)<br>
  ![soal_no3_forger](https://user-images.githubusercontent.com/55425460/206826599-613266c2-e6c1-495e-8736-d716548bb0ce.png)
- Koneksi ketiga (dari Blackbell)<br>
  ![soal_no3_blackbell](https://user-images.githubusercontent.com/55425460/206826601-498f8dc6-8601-404f-ba5e-b5236f45ef45.png)

## Soal 4  
Akses menuju Web Server hanya diperbolehkan disaat jam kerja yaitu Senin sampai Jumat pada pukul 07.00 - 16.00.  
### Jawab  

## Soal 5  
Karena kita memiliki 2 Web Server, Loid ingin Ostania diatur sehingga setiap request dari client yang mengakses Garden dengan port 80 akan didistribusikan secara bergantian pada SSS dan Garden secara berurutan dan request dari client yang mengakses SSS dengan port 443 akan didistribusikan secara bergantian pada Garden dan SSS secara berurutan.  
### Jawab  

## Soal 6  
Karena Loid ingin tau paket apa saja yang di-drop, maka di setiap node server dan router ditambahkan logging paket yang di-drop dengan standard syslog level.  
### Jawab  
