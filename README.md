# Jarkom_Modul1_Lapres_B12

1. 05111840000057 - Maisie Chiara Salsabila
2. 05111840000062 - Geizka Wahyu Fahriza


## Daftar Isi
#### [Display Filter](#df)
  1. [Nomor 1](#1)
  2. [Nomor 2](#2)
  3. [Nomor 3](#3)
  4. [Nomor 4](#4)
  5. [Nomor 5](#5)
  6. [Nomor 6](#6)
  7. [Nomor 7](#7)
  8. [Nomor 8](#8)
  9. [Nomor 9](#9)
  10. [Nomor 10](#10)
#### [Capture Filter](#cf)
  11. [Nomor 11](#11)
  12. [Nomor 12](#12)
  13. [Nomor 13](#13)
  14. [Nomor 14](#14)
  15. [Nomor 15](#15)

<a name="df"></a>
## Display Filter 
<a name="1"></a>
### 1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
``` http.host == testing.mekanis.me``` kemudian klik kanan, pilih follow -> HTTP stream, kemudia terlihat bahwa webservernya adalah ```nginx/1.14.0 (Ubuntu)```

<a name="2"></a>
### 2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
Display Filter: ```http contains "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"```
kemudian Export Objects, pilih HTTP... lalu input pada Text Filter: ```http contains "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"```

<a name="3"></a>
### 3. Cari username dan password ketika login di "ppid.dpr.go.id"!
```http.host==ppid.dpr.go.id && http contains "login"```

<a name="4"></a>
### 4. Temukan paket dari web-web yang menggunakan basic authentication method!
```
http contains "Authorization: Basic"
http.authbasic
```

<a name="5"></a>
### 5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
```
http contains "Authorization: Basic" && http contains "aku.pengen.pw"
http.authbasic && http contains "aku.pengen.pw"
```

<a name="6"></a>
### 6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
```
ftp-data.command contains "Answer.zip"
ftp-data.command contains "zipkey.txt"
```

<a name="7"></a>
### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
```
ftp-data contains "Yes.pdf"
ftp-data.command contains "473.zip”
```

<a name="8"></a>
### 8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
```ftp contains "RETR"```

<a name="9"></a>
### 9. Cari username dan password ketika login FTP pada localhost!
```ftp.request.command==USER``` untuk mendapatkan username
```tp.request.command==PASS``` untuk mendapatkan password
Lalu didapetkan username=dhana dan password=dhana123

<a name="10"></a>
### 10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46" 
```ctrl+f``` > ```hex``` > ```25 50 44 46```> ```follow``` > ```tcp stream``` > ```raw``` > ```save as``` > ```now.pdf```

<a name="cf"></a>
## Capture Filter

<a name="11"></a>
### 11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
``` port 21 ```

<a name="12"></a>
### 12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
```src port 80```

<a name="13"></a>
### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
```dst port 443```

<a name="14"></a>
### 14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
```
ipconfig di cmd lalu ambil ipv4
src host [ip di ipv4]
saya dapat ipv4 192.168.1.8
src host 192.168.1.8
```

<a name="15"></a>
### 15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
``` dst host monta.if.its.ac.id```
