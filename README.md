# Praktikum Modul 1 Jaringan Komputer

# Anggota Kelompok E27 :
| No.  | Nama Anggota       | NRP          |
|------|--------------------|--------------|
| 1    |Rachman Ridwan           | 5025201061   |
| 2    | Akmal Nafis         | 5025211216   |

# Soal 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

Penyelesaian Soal :
Setelah membuka soal pada Wireshark, Lakukan filter dengan pencarian "FTP". Untuk mencari User yang melakukan kegiatan mengunggah, Gunakan keyword "STOR"

a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?
b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?

Dari paket yang kita dapatkan setelah filtering, Kita analisis pada tampilan layer TCP. Tampilan ini menunjukkan jawaban pada soal a dan b 
![no.1](./assets/no1part1.png)

c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Dari paket sebelumnya yaitu paket 147 kita dapat melihat paket response request, Dimana tertuju pada paket 149. Sama halnya pada paket 147, Pada tampilan TCP paket 149 terdapat sequence dan acknowlede number yang kita inginkan.
![no.1](./assets/no1part2.png)

# Soal 2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

Penyelesaian Soal : Pertama kita filter protokol yang menggunakan http, kemudian mencari kode 200 dari source ip server, kemudian kita buka protokol httpnya dan mengecek header yang ada didalamnya, terlihat bahwa web server yang digunakan adalah gunicorn

![image](https://cdn.discordapp.com/attachments/945203039034306570/1154726293619875920/image.png)

![image](https://cdn.discordapp.com/attachments/883930711290171432/1154773901772070995/image.png)
# Soal 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

Penyelesaian Soal :
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
Untuk mencari banyak paket dengan IP source atau destination dengan port pada soal dapat dilakukan filter dengan perintah berikut :
```
ip.addr == 239.255.255.250 && (tcp.port == 3702 or udp.port == 3702)
```
Filter diatas berfungsi untuk mendapatkan semua IP yang berasal dan menuju port dengan filter <code>ip.addr == 239.255.255.250</code>. Karena hanya terdapat dua macam transport layer dari port (UDP dan TCP), Maka dengan tambahan <code>tcp.port == 3702 || udp.port == 3702</code> kita akan mendapatkan apa yang diminta pada soal
![no.3](./assets/no3.png)
b. Protokol layer transport apa yang digunakan?
Pada filterisasi diatas, Protokol yang digunakan dapat terlihat pada tampilan display, Yaitu protokol UDP.

# Soal 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

Penyelesaian Soal :
Untuk mendapatkan nilai checksum dapat dilihat pada paket yang diinginkan pada bagian header UDP paket.

![no.4](./assets/no4.png)

Pada gambar, terlihat bahwa nilai checksum pada paket 130 adalah <ins>**0x18e5**<ins>

# Soal 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

- Pertama kita menganalisis paket pada file, kemudian laukan Stream kemudian follow pada paket tcp

![image](https://cdn.discordapp.com/attachments/945203039034306570/1154738624982700083/image.png)
- terdapat perintah untuk mendecode sebuah kode ke base64, setelah didecode hasilnya adalah "5implePas5word", kode tersebut digunakan untuk membuka file zip. 
![image](https://cdn.discordapp.com/attachments/945203039034306570/1154740343078666240/image.png)
![image](https://cdn.discordapp.com/attachments/945203039034306570/1154740609400197180/image.png)


kemudian kita masukkan instance dalam file untuk menjawab soal
- Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
di dalam wireshark pada pojok kanan bawah kita bisa melihat total packet yang dicapture yakni 60 packet
- Port berapakah pada server yang digunakan untuk service SMTP?
kemudian kita buka stream pada protokol SMTP, terlihat bahwa port yang digunakan yakni port 25
- Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
server yang digunakan memiliki ip publik yakni 74.53.140.153

![image](https://cdn.discordapp.com/attachments/945203039034306570/1154743021993205820/image.png)
![image](https://cdn.discordapp.com/attachments/883930711290171432/1154774305159249970/Screenshot_from_2023-09-22_20-39-38.png)

# Soal 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

Jawab
- Pertama kita menganalisis "server SOURCE ADDRESS 7812 is invalid", 7812 merupakan nomor packet, source address merupakan ip source yakni 104.18.14.101.

![image](https://cdn.discordapp.com/attachments/883930711290171432/1154770421116309616/image.png)

- Kemudian kita harus mengetahui pola a1 e5 dan u21, pola tersebut adalah posisi huruf dalam alfabet A=1 E=5 DAN U=21.
karena format ip sangat membingungkan maka semua digabung 1041814101, berhubungan dengan kode sebelumnya maka angka tersebut harus kurang dari 27, sehingga jika dipisah menjadi 
`10 4 18 14 10 1`

Disini kita tinggal mengubah angka tersebut ke huruf sehingga menjadi JDRNJA

![image](https://cdn.discordapp.com/attachments/945203039034306570/1154771942109356093/image.png)

# Soal 7
Berapa jumlah packet yang menuju IP 184.87.193.88?
- menggunakan filter `ip.dst == 184.87.193.88` , kemudian kita lihat berapa banyak packet yang tampil, yakni sebanyak 6 packet
![image](https://cdn.discordapp.com/attachments/945203039034306570/1154726660990570496/image.png)
![image](https://cdn.discordapp.com/attachments/883930711290171432/1154774305406722088/Screenshot_from_2023-09-22_20-39-55.png)

# Soal 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
- menggunakan filter `tcp.dstport ==80 || udp.dstport == 80`dengan menggunakan filter tersebut kita bisa mengqueri packet dengan port 80 pada protokol tcp dan udp

![image](https://cdn.discordapp.com/attachments/945203039034306570/1154747359159386163/image.png)

![image](https://cdn.discordapp.com/attachments/883930711290171432/1154774305700319243/Screenshot_from_2023-09-22_20-40-07.png)

# Soal 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

Penyelesaian Soal :
Lakukan query sebagai berikut :
```
ip.src == 10.51.40.1 && ip.dst != 10.39.55.34
```
Solusi pada soal no.9 adalah filter dengan memainkan comparison operator pada kedua IP. Karena yang diminta pada soal adalah "berasal dari alamat <code>10.51.40.1</code> tetapi tidak menuju alamat <code>10.39.55.34</code>, Penggunaan operatornya yaitu "==" dan "!=". Dan karena keduanya harus dipenuhi maka dengan logical operator "&&" kita akan menjawab soal ini.
![no.9](./assets/no9.png)

# Soal 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

Penyelesaian Soal :
Kita dapat melakukan filtering dengan keywords "Telnet". Pada TCP follow stream tertera informasi kredensial login dhafin beserta passwordnya. Hal ini bisa lebih cepat dengan filter keywords "Telnet contains login"
![no.10](./assets/no10.png)

