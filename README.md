# Jarkom-Modul-1-IT45-2024

|           Nama               |     NRP    |
|            --                |     --     |
| Dian Anggraeni Putri         | 5027231016 |
| ⁠Abhirama Triadyatma Hermawan | 5027231061 |

## Content
   * Advance Sanity Check
   * Illegal Breakthrough
   * FTP Login
   * Surprise
   * Corporate Breach
   * Pegawai Negeri Sebelah
   * EZ
   * Rizzset
   * Packets Barrage
   * Malicious Code
   (+)
   * Gajah Terbang (Server Recon)
   * Gajah Terbang (Attacker Recon)
   * Stegography

## Advance Sanity Check
> Yang sederhana dulu aja.
> 
> nc 10.15.42.60 44000
> 
> file: sanity.pcapng

Dalam menyelesaikan challenge ini kami menggunakan filter "TCP stream" di Wireshark untuk melihat data komunikasi yang terjadi di satu aliran jaringan. Kami mulai dengan menyaring stream dari nomor 0, kemudian menemukan informasi penting pada stream ke-3. Selanjutnya, karena di terminal ditanyakan "apa username pengirim" maka kami mencoba untuk memasukkan username pengirim yaitu "JaneD03" ke dalam terminal dan ternyata berhasil, lalu menaikkan stream ke nomor 4, di mana clue "clue3.txt" muncul dimana menjawab pertanyaan dan memenuhi persyaratan format filename.txt. Petunjuk selanjutnya meminta kami untuk mengikuti petunjuk untuk mendapatkan pesan rahasia, yang dimana saat kami scroll isi konten di stream 4 itu ada tulisan yang mengarahkan kami untuk memeriksa aturan soal shift. Kami pun memeriksa ppt aturan praktikum di bagian soal shift dan akhirnya menemukan pesan rahasia. Pesan tersebut kami decode dan akhirnya kami berhasil menemukan flag!

![image](https://github.com/user-attachments/assets/40b98317-668c-49e9-bbc8-87e7b033bc34)
![image](https://github.com/user-attachments/assets/bbcc7e1e-1296-47e8-a170-7147b01ab646)
![image](https://github.com/user-attachments/assets/174b9a88-3bae-4e74-8444-6d65d8c42714)
![image](https://github.com/user-attachments/assets/c15b474d-d1b6-4691-8841-901ddea66910)
![image](https://github.com/user-attachments/assets/ea581344-341d-4362-83f8-b9df2f2e4603)
![image](https://github.com/user-attachments/assets/eede7b39-c0e2-471d-a9a6-039c94cece5d)
```
$ nc 10.15.42.60 44000

===== Advanced Sanity Check =====
Note: You can exit anytime by typing 'exit'

Apa username pengirim?
Format: username
> JaneD03
Apa nama file yang dikirim?
Format: filename.extension
> Clue3.txt
Ikuti petunjuk untuk mendapatkan pesan rahasia
Format: string
> penword
Benar! Ini flag-mu: JarkomIT{8uK4n_S4n1ty_b1a5A_PZsva59iSBLGsLwPMcz5nvnQbSu576bmxnNYiYxCiUqBudYOAOmDDIKK}
```

## Illegal Breakthrough
> Seorang full-stack developer bernama kevin sedang membuat sebuah web yang memiliki login page. Tetapi karena ia hanya digaji rendah, ia lupa untuk mengamankan web yang ia buat. Bantulah kevin untuk tracing dari jejak yang ditinggalkan oleh attacker.
> 
> nc 10.15.42.60 46000
> 
> file: break.pcapng

Dalam challenge ini, kami menotice bahwa banyak paket yang mengarah ke stream 1917. Dengan mengikuti stream ini, kami pada akhirnya bisa melihat seluruh aktivitas penyerang, termasuk IP, port, endpoint, serta tools yang digunakan. Dan ternyata isi konten stream 1917 adalah jawaban yang benar sehingga kami mendapatkan flag!

![image](https://github.com/user-attachments/assets/72d1798f-5bf4-45a3-ac86-e96e6b9c3771)
![image](https://github.com/user-attachments/assets/a9ed58c0-ed63-4307-a09b-2cca5c5495fc)

```
$ nc 10.15.42.60 46000

===== Illegal Breakthrough =====
Note: You can exit anytime by typing 'exit'

Apa IP address dari korban?
Format: xxx.xxx.xxx.xxx
> 172.21.88.207
Apa port yang digunakan sebagai webserver?
Format: xxxx: ex. 443
> 1917
Dimana endpoint yang terdapat login?
Format: /endpoint/path.php
> /ww1.php
Tools apa yang digunakan oleh attacker?
Format: toolsname-version ex. hydra-v9.0-dev
> ffuf-v2.1.0-dev
Apa kredensial yang berhasil digunakan oleh attacker untuk login?
Format: username:password
> Redbaron:fly1ng4c3
Benar! Ini flag-mu: JarkomIT{d34th_fr0m_th3_sky_ZLi11nOcndhzMkdIDTSFoDd82H1LDXeQabpP1pHallN0QJDYtM0WWW1}
```

## FTP Login
> Seseorang menemukan sebuah celah dalam sebuah server. Ia mencoba untuk melakukan brute force login dan ia berhasil masuk. Lakukan pemeriksaan untuk melihat apa yang dilakukan oleh orang tersebut!
> 
> nc 10.15.42.60 49000
> 
> file: ftplogin.pcapng

Mirip dengan challenge "Advance Sanity Check", kami juga harus mencari username dan password dalam challenge ini. Prosesnya sama yaitu dimulai dengan melihat apa yang terjadi di terminal dan kemudian menggunakan filter TCP stream. Setelah memulai dari stream 0, pada akhirnya kami menemukan login yang berhasil pada stream ke-4. Dari situ, kami mengetahui bahwa username yang digunakan untuk FTP login adalah "sn34ky" dan passwordnya adalah "sup3rsn1ff3r".

![image](https://github.com/user-attachments/assets/926ba162-f4d4-45d3-8ff3-8f0cbfa8be83)
![image](https://github.com/user-attachments/assets/0573b959-75e6-4d6f-91bc-f245a03e053f)
```
$ nc 10.15.42.60 49000

===== FTP Login =====
Note: You can exit anytime by typing 'exit'

Apa username yang berhasil digunakan untuk FTP login?
Format: username
> sn34ky                
Apa password yang berhasil digunakan untuk FTP login?
Format: string
> sup3rsn1ff3r
Benar! Ini flag-mu: JarkomIT{n0t_s0_s3cur3_ftp_3ZvMs3ZibbtrySJYxKgvG72wyL0ig3hhssiawM0R2OlrquvDwBDLG1N}
```

## Surprise
> Setelah mengetahui apa yang diketahui pada challenge sebelumnya, sekarang lakukan analisis untuk mengetahui apa yang sebenarnya terjadi
> 
> nc 10.15.42.60 48500
> 
> file: File sama seperti FTP Login

Challenge ini dimulai dengan pertanyaan mengenai service apa saja yang digunakan. Prosesnya sama seperti challenge sebelumnya, di mana kami mengikuti TCP stream dari nomor 0. Setelah beberapa kali mencoba, di stream ke-4 ditemukan informasi login berhasil dengan versi yang benar. Setelah itu, ditemukan file bernama "gotcha.cpp". Setelah menjalankan program tersebut, pesan rahasia ditemukan dan kami mendapatkan flag!

![image](https://github.com/user-attachments/assets/68fbcede-1cc9-4097-b567-cbff3e253e5f)
![image](https://github.com/user-attachments/assets/926ba162-f4d4-45d3-8ff3-8f0cbfa8be83)
![image](https://github.com/user-attachments/assets/86b54813-b9f7-4dbc-8e0d-a963cc2a6e18)
![image](https://github.com/user-attachments/assets/a764359a-ec01-4dd0-990e-afcb5825887f)
![image](https://github.com/user-attachments/assets/2bae3f82-8f21-4586-9332-3c0fb66686be)
![image](https://github.com/user-attachments/assets/b8e7f702-c633-49d5-9df5-018e4b8f3a51)
```
$ nc 10.15.42.60 48500

===== Surprise =====
Note: You can exit anytime by typing 'exit'

Apa service yang digunakan pada FTP server?
Format: service ver 
ex. proFTPd 1.1.0
> vsFTPd 3.0.3
Apa nama file yang dikirim oleh attacker?
Format: filename.extension
> g0tcha.cpp
Apa pesan rahasia yang ditinggalkan oleh attacker?
Format: string ex. h4lo wor1d
> g0tchu n0w l1ttl3 m0us3
Benar! Ini flag-mu: JarkomIT{l1ttl3_m0us3_1n_th3_h0us3_lUhvSdRHEPjx2SGkhL3AT4DiNG0xdtHFNq9LVBDvec7aLxCwkA9qTCHU}
```

## Corporate Breach
> Sebuah perusahaan IT support mendapatkan serangan oleh orang tidak dikenal. Bantulah perusahaan tersebut untuk melacak jejak yang ditinggalkan oleh attacker
> 
> nc 10.15.42.60 51000
> 
> file: breach.pcapng

Dalam challenge ini, pertama, kami disuruh mencari siapa nama attackernya. Sama seperti sebelum-sebelumnya kami memakai filter tcp stream dan berakhir menemukan pesan dengan nama Nakhimov, akhirnya kami berasumsi bahwa Nakhimovlah attackernya dan ternyata benar. Lalu kami mengikuti stream tersebut hingga akhirnya di stream 207 ditemukan informasi login yang benar. Kami memperoleh email dan password tersebut karena terlihat mencurigakan, berbeda dari konten lainnya karena tidak ada HTML di bawahnya, sehingga kami yakin itu adalah informasi yang benar, dan ternyata dugaan kami benar, sehingga kami mendapatkan flag!

![image](https://github.com/user-attachments/assets/d3b70d89-3460-4e65-9884-995d1b8e4d56)
![image](https://github.com/user-attachments/assets/14813eea-ce08-4525-927b-a4a3039d1716)
![image](https://github.com/user-attachments/assets/09c34fa9-21f9-4458-9408-8a4a2a1f4148)
```
$ nc 10.15.42.60 51000

===== Corporate Breach =====
Note: You can exit anytime by typing 'exit'

Siapa nama attacker?
Format: string
> Nakhimov
Apa email yang digunakan untuk login?
Format: email@gmail.com
> jarkomsupport@gmail.com
Apa password yang digunakan untuk login?
Format: string
> j4rk0mg4c0rbg
Benar! Ini flag-mu: JarkomIT{supp0rt_k0k_l3m4h_bg_caT1X51I2UoFwpZcw5fVTAUm8G6zDwNEsM4UwCMMTMrx4EXaNPEpG6}
```

## Pegawai Negeri Sebelah
> Kamu seorang data analisis diminta untuk memastikan ulang data-data dari beberapa pegawai.
> 
> nc 10.15.42.60 53000
> 
> file: rahasia.pcap

Untuk challenge ini, kami harus menemukan beberapa informasi seperti pemilik password "nNnM%coQuF" dan jabatan orang tertentu. Dengan mengikuti TCP stream, kami berhasil menemukan data-datanya. Lalu dengan memakai fitur find di bagian bawah akhirnya kami menemukan bahwa password tersebut dimiliki oleh "Vero Tampubolon". Selain itu, ditemukan bahwa jabatan Taufan Kuswandari adalah "Analis Kebijakan", dan urutan pertama di daftar adalah "Cici Mustofa", sementara password terakhir yang ditemukan adalah "RyxaJPv^yF". Semua jawabannya benar dan akhirnya kami mendapatkan flag!

![image](https://github.com/user-attachments/assets/0d1a9b1c-fa37-4ce2-be07-f0f69c7dafa7)
![image](https://github.com/user-attachments/assets/2ccec5bd-b089-4fc4-923e-d68f14dab6f5)
![image](https://github.com/user-attachments/assets/ce896b1c-6009-49a3-86db-c2348ee33216)
![image](https://github.com/user-attachments/assets/09c7f492-1adc-4d45-836a-f1d1ae4943f7)
![image](https://github.com/user-attachments/assets/5221c9ae-d255-408e-befa-edb30fa6ee44)
```
$ nc 10.15.42.60 53000

=====  Pegawai Negeri Sebelah =====
Note: You can exit anytime by typing 'exit'

Siapa yang memiliki password nNnM%coQuF?
Format: String
> Vero Tampubolon
Apa jabatan dari Taufan Kuswandari?
Format: String
> Analis Kebijakan
Siapa yang paling awal di list?
Format: String
> Cici Mustofa
Apa password paling akhir dari list?
Format: String
> RyxaJPv^yF
Benar! Ini flag-mu: JarkomIT{Tum8eN_p45SnYa_Ku4t_B1aS4Nya_d4EjysuhNbOdCX7LoT4Z9gnSaL337FHGQYe5n3ieKFehKMpDry7cM4h}
```

## EZ
> Aku sedang mencoba bikin chat service tapi kayanya pesannya bisa di sniffing deh? coba temukan pesannya.
> 
> nc 10.15.42.60 54000
> 
> file: ez.pcapng

Challenge ini melibatkan searching jawaban darii file log. Kami memulai dengan mencari stream 0, lalu kami coba untuk follow stream random, dan ternyata kami menemukan isi kontennya sesuai dengan format yang diminta. Dan ternyata jawabannya lalu kami juga menemukan port yang digunakan untuk layanan tersebut adalah 1234. Dari situlah kami akhirnya mendapatkan flag!

![image](https://github.com/user-attachments/assets/ec747c8e-189b-4b98-a0ca-d1b96c8f3877)
![image](https://github.com/user-attachments/assets/e98a2cb3-ee83-41b4-9981-611c7d3b1b39)
![image](https://github.com/user-attachments/assets/d0dd35d0-f4d7-4db8-a9e5-20f6bea508d6)
```
─$ nc 10.15.42.60 54000

===== EZ =====
Note: You can exit anytime by typing 'exit'

Temukan jawaban dari log tersebut
Format: string ex. kata kata
> jawabannya jawaban
Port berapa yang digunakan service tersebut
Format: xxxx: ex. 443
> 1234
Benar! Ini flag-mu: JarkomIT{BiAr_aman_Pake_sSh_6kgAozQUg7KBsvScORpWgISPs3zepqu7yIJd9bjAg6alxXZeTwbeEZ}
```

## Rizzset
> Aku sedang bereksperimen dengan suatu tools, kamu juga bisa menggunakannya untuk menjawab soal ini.
> 
> nc 10.15.42.60 59500
> 
> file: riset.pcapng
> 
> Pertama saya melakukan filter untuk mencari protocol "dns"

![image](https://github.com/user-attachments/assets/3f10db8c-fda4-4c46-a7e3-f62a48826449)

> Lalu dari filter tersebut kita juga bisa melihat IP dari domain tersebut yaitu "103.94.189.5" 

> Lalu kita lakukan "python3 jarm.py www.its.ac.id"

![image](https://github.com/user-attachments/assets/d8c90235-61a7-4f8e-b180-78001c1e2900)

![Screenshot 2024-09-18 225645](https://github.com/user-attachments/assets/f20aa130-3be6-4c4e-b314-3ef1826d83b5)

## Malicious Code
> Setelah membantu kevin untuk tracing attacker, sekarang bantu lagi kevin untuk mencari apa yang dilakukan oleh attacker.
> 
> File sama seperti Illegal Breakthrough.
> 
> nc 10.15.42.60 47000
> 
> file: break.pcapng

![image](https://github.com/user-attachments/assets/a416302b-2022-4772-8e75-c0c555266a64)

> Pertama kita cari "http contains 'POST'" untuk melihat IP dari attacker

![Screenshot 2024-09-19 014632](https://github.com/user-attachments/assets/b9c2aa69-c64e-49ac-88a4-b761dfb0b19d)

> Lalu "http contains 'download'" untuk mencari file yang di download

![image](https://github.com/user-attachments/assets/72436e62-b4bc-4b1f-9670-215d95089280)

> Disitu kita juga bisa menumukan messege yang di selipakan attacker "Der Rote Kampfflieger"

## Malicious Code
> Ternyata sang attacker dengan sengaja meninggalkan sesuatu untuk dibaca oleh kamu. Lihat pesan apa yang ditinggalkan attacker.
File sama seperti Corporate Breach.
> 
> nc 10.15.42.60 52![Screenshot 2024-09-19 014632](https://github.com/user-attachments/assets/9afba505-90a8-4f2a-b670-ab058eaff43b)
> 
000
> file: breach.pcapng

![Screenshot 2024-09-18 234023](https://github.com/user-attachments/assets/7ae2e5eb-10a7-4230-93b0-1afeab6c73df)
Pertama kita melakukan "http contains 'GET'" untuk menemukan berapa kali attacker melakukan HTTP request "GET" dan melihat berapa paket HTTP yang terdisplay
    ![image](https://github.com/user-attachments/assets/e646fa00-bf25-452a-acb7-cea5650bbf34)
    Lalu untuk pertanyaan kedua kita lihat HTTP request yang sudah ter display filter tadi dan cari packet yang terakhir. Di situ kita dapat menemukan endpoint "index.php"
    ![Screenshot 2024-09-19 001432](https://github.com/user-attachments/assets/f5c6cfda-3b58-42e4-adf8-304d7222c3ec)
    Lalu kita display filter "HTTP contains 'POST'" untuk melihat POST berupa login dari attacker
    ![image](https://github.com/user-attachments/assets/b6cfc585-8b4e-4399-b478-268713803886)
    Setelah di analisis 5 POST paling bawah memiliki messege dari attacker namun tidak ada pertanyaan... Di packet yang terakhir terdapat ASCII yang jika di lakukan decode menjadi seperti berikut
    ![Screenshot 2024-09-18 233141](https://github.com/user-attachments/assets/5cddda6e-d3cd-4bae-b49b-aa55188e954f)
    Jawabannya adalah merah karena VSCODE salah satu ASLAB yang MERAH sangat mencolok

# Bagian Revisi
## Gajah Terbang (Server Recon)
> Yang sederhana dulu aja.
>
> nc 10.15.42.60 61000
> 
> Pada perusahaan PT. +1000 Aura telah terjadi insiden yang besar, dimana seorang hengker berhasil masuk ke sistem database perusahaan tersebut, dan melakukan manipulasi sistem database mereka. Anda sebagai profesional Cyber Security Analyst ditugaskan untuk melakukan investigasi melalui log network yang berhasil tercapture!

![image](https://github.com/user-attachments/assets/616bd21e-2fec-41ca-abb5-e1d683784842)
![image](https://github.com/user-attachments/assets/8b907892-3254-4c75-8421-0b319d6287db)
![image](https://github.com/user-attachments/assets/81aae13b-3972-4af2-9c9d-1f92f7b1a21d)

```
$ nc 10.15.42.60 61000

===== Gajah Terbang (Server Recon) =====
Note: You can exit anytime by typing 'exit'

Apa DBMS yang digunakan pada server tersebut?
Format: string ex. MonggoDB
> PostgreSQL
Di port berapa DBMS server tersebut berjalan?
Format: xxxx ex. 443
> 6969    
OS apa yang digunakan untuk server tersebut?
Format: string ex. linux
> Debian
Apa credentials username DBMS valid yang digunakan?
Format: string
> s1gm4
Apa nama database yang digunakan?
Format: string
> sigmaskibidigyatrizzzz
Ada berapa banyak users dalam database tersebut?
Format: number
> 4
Apa email yang digunakan oleh admin?
Format: email@gmail.com
> jojohermawan@gmail.com
Apa password yang digunakan oleh admin?
Format: string
> admin1234
Benar! Ini flag-mu: JarkomIT{Gy4tT_M5g_4U_EtfGOMNeXuVKYB7KXeLlaF9pP5k1WZWvWqmjaRMXNTUZszkPFp9IJBiD1}
```

## Gajah Terbang (Attacker Recon)
> Yang sederhana dulu aja.
>
> nc 10.15.42.60 62000
> 
> Setelah berhasil menginvestigasi server yang berjalan, kamu diharuskan untuk mencari identitas dan mencari jejak apa saja yang telah dilakukan oleh penyerang! Kamu jago, pasti bisa let’s go temukan tersangkanya!!!
File sama seperti Gajah Terbang.

## Stegeography
> Seekor stegosaurus berusaha menyimpan pesan di dalam beberapa gambar apakah kamu bisa memperoleh dan menyusunnya?
>
> nc 10.15.42.60 58000
>
> 14.zip

