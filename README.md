# Jarkom_Modul1_Lapres_B12

1. 05111840000057 - Maisie Chiara Salsabila
2. 05111840000062 - Geizka Wahyu Fahriza


## Daftar Isi
#### Display Filter
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
#### Capture Filter
  11. [Nomor 11](#11)
  12. [Nomor 12](#12)
  13. [Nomor 13](#13)
  14. [Nomor 14](#14)
  15. [Nomor 15](#15)

## Display Filter 
<a name="1"></a>
### 1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
filter menggunakan ``` http.host == testing.mekanis.me``` kemudian klik kanan, pilih ```follow -> HTTP stream```, kemudia terlihat bahwa webservernya adalah ```nginx/1.14.0 (Ubuntu)```
![testestes](/modul1/1.png)

<a name="2"></a>
### 2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
- Display Filter: ```http contains "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"``` untuk menyimpan gambar
- kemudian ```Export Objects```, pilih ```HTTP...``` 
- lalu pada Text Filter input: ```http contains "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"```
- kemudian save file pada direktori yang diinginkan
![testestes](/modul1/2.png)

<a name="3"></a>
### 3. Cari username dan password ketika login di "ppid.dpr.go.id"!
filter menggunakan ```http.host==ppid.dpr.go.id && http contains "login"```, kemudian pada perintah ```POST``` terdapat informasi berupa:
- username: 10pemuda
- password: guncangdunia
![testestes](/modul1/3.png)

<a name="4"></a>
### 4. Temukan paket dari web-web yang menggunakan basic authentication method!
Dengan menggunakan filter:
```
http contains "Authorization: Basic"
http.authbasic
```
![testestes](/modul1/4.png)

<a name="5"></a>
### 5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
```
http contains "Authorization: Basic" && http contains "aku.pengen.pw"
http.authbasic && http contains "aku.pengen.pw"
```
Lalu ```GET > Credential``` dan didapatkan:
- username: kakakgamtenk
- password: hartatahtabermuda
![testestes](/modul1/5.png)

<a name="6"></a>
### 6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

- ```ftp-data.command contains "Answer.zip"``` untuk mencari dan mendownload file .zip
- kemudian ```klik kanan > Follow > TCP Stream > Save as Raw Bernama Answer.zip```
- ```ftp-data.command contains "zipkey.txt"``` untuk mencari file text yang ada pada file zip tersebut
- kemudian ```klik kanan > Follow > TCP Stream > Save as Raw Bernama zipkey.txt```
![testestes](/modul1/6.png)

<a name="7"></a>
### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
- ```ftp-data contains "Yes.pdf"``` untuk mencari file "Yes.pdf" lalu didapat file zip yang berisi file "Yes.pdf" yaitu "473.zip"
- ```ftp-data.command contains "473.zip”``` untuk mencari file "473.zip"
- kemudian ```klik kanan > Follow > TCP Stream > Save as Raw Bernama 473.zip```
Buka 473.zip dan buka .pdf nya
![testestes](/modul1/7.png)

<a name="8"></a>
### 8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
```ftp contains "RETR"```
![testestes](/modul1/8.png)

<a name="9"></a>
### 9. Cari username dan password ketika login FTP pada localhost!
```ftp.request.command==USER``` untuk mendapatkan username
```tp.request.command==PASS``` untuk mendapatkan password
Lalu didapetkan username=dhana dan password=dhana123
![testestes](/modul1/9.png)

<a name="10"></a>
### 10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46" 
```ctrl+f > hex > 25 50 44 46 > follow > tcp stream > raw > save as > now.pdf```
![testestes](/modul1/10.png)


## Capture Filter

<a name="11"></a>
### 11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
menggunakan ``` port 21 ``` biasa. Tampilan ketika filter baru saja dijalankan tanpa ada aktivitas dalam filezilla:
![testestes](/modul1/11-1.png)
Ketika ada suatu aktivitas (misal: mengoneksikan filezilla)
![testestes](/modul1/11-2.png)

<a name="12"></a>
### 12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
```src port 80```
![testestes](/modul1/12.png)

<a name="13"></a>
### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
```dst port 443```
![testestes](/modul1/13.png)

<a name="14"></a>
### 14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
```
ipconfig di cmd lalu ambil ipv4
src host [ip di ipv4]
saya dapat ipv4 192.168.1.8
src host 192.168.1.8
```
![testestes](/modul1/14.png)

<a name="15"></a>
### 15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
``` dst host monta.if.its.ac.id```
![testestes](/modul1/15.png)
