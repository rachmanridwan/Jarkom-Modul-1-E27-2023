# Praktikum Modul 1 Jaringan Komputer

# Anggota Kelompok E27 :
| No.  | Nama Anggota       | NRP          |
|------|--------------------|--------------|
| 1    |Rachman Ridwan           | 5025201061   |
| 2    | Akmal Nafis         | 502521   |

# Soal 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?

b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 

c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Penyelesaian Soal :
# Soal 2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

Penyelesaian Soal : Pertama kita filter protokol yang menggunakan http, kemudian mencari kode 200 dari source ip server, kemudian kita buka protokol httpnya dan mengecek header yang ada didalamnya, terlihat bahwa web server yang digunakan adalah gunicorn

![image](https://cdn.discordapp.com/attachments/945203039034306570/1154726293619875920/image.png)

# Soal 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

b. Protokol layer transport apa yang digunakan?

Penyelesaian Soal
# Soal 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

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

# Soal 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

# Soal 7
Berapa jumlah packet yang menuju IP 184.87.193.88?
- menggunakan filter `ip.dst == 184.87.193.88` , kemudian kita lihat berapa banyak packet yang tampil, yakni sebanyak 6 packet
![image](https://cdn.discordapp.com/attachments/945203039034306570/1154726660990570496/image.png)

# Soal 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
- menggunakan filter `tcp.dstport ==80 || udp.dstport == 80`dengan menggunakan filter tersebut kita bisa mengqueri packet dengan port 80 pada protokol tcp dan udp

![image](https://cdn.discordapp.com/attachments/945203039034306570/1154747359159386163/image.png)


# Soal 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

# Soal 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
