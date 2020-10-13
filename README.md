
# Lapres Modul 1 Jarkom T02 2020

### Oleh:
- Muhammad Sulthon Nashir (05111740000171)
- namamu gas

### Display Filter
#### No. 1
Sebutkan webserver yang digunakan ketika mengakses "testing.mekanis.me"!
##### Penyelesaian
Gunakan filter :
```
http.host == testing.mekanis.me
```
Lalu follow TCP Stream

#### No. 2
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!

##### Penyelesaian
Filter dengan
```
HTTP
```
Lalu
```
Export Object >> http
```
Cari file gambar yang dimaksud, Save.

#### No. 3
Cari username dan password ketika login di "ppid.dpr.go.id"!

##### Penyelesaian
Gunakan filter :
```
http.request.method == POST
```
Lalu Follow TCP Stream

#### No. 4
Temukan paket dari web-web yang menggunakan basic authentication method!

##### Penyelesaian
Gunakan filter :
```
HTTP
```
Karena semua website HTTP masih menggunakan basic authentication

#### No. 5
Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

##### Penyelesaian
Gunakan filter packet :
```
(ip.dst == 157.245.50.224 || ip.src == 157.245.50.224) && HTTP
```

#### No. 6
Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

##### Penyelesaian
Gunakan filter
```
ftp-data
```
Pilih "Answer.zip", show and save data as "Raw", Save.

Lalu follow zipkey.txt, itu passwordnya.

#### No. 7
Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf".

##### Penyelesaian
Gunakan filter :
```
ftp-data contains "Yes.pdf"
```
Follow stream file yang masuk akal, lalu save as raw seperti biasa.

#### No. 8
Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

##### Penyelesaian
Gunakan filter :
```
ftp.request.command == RETR
```
Follow satu persatu, cek file yang menggunakan Microsoft FTP Service.

#### No. 9
Cari username dan password ketika login FTP pada localhost!

#### Penyelesaian
Gunakan filter :
```
ftp.request.command == USER || ftp.request.command == PASS
```
#### No. 10
Cari file .pdf di wireshark lalu download dan buka file tersebut!
clue: "25 50 44 46"

##### Penyelesaian
Gunakan filter :
```
http contains ".pdf"
```
Follow stream, lalu save bagian TCP Payload

### Capture Filter
