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

## Advance Sanity Check
> Yang sederhana dulu aja.
> 
> nc 10.15.42.60 44000
> 
> file: sanity.pcapng

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
> nc 10.15.42.60 46000
> file: break.pcapng

## FTP Login
> Seseorang menemukan sebuah celah dalam sebuah server. Ia mencoba untuk melakukan brute force login dan ia berhasil masuk. Lakukan pemeriksaan untuk melihat apa yang dilakukan oleh orang tersebut!
> nc 10.15.42.60 49000
> file: ftplogin.pcapng

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
> Setelah mengetahui apa yang diketahui pada challenge sebelumnya, sekarang lakukan analisis untuk mengetahui apa yang sebenarnya terjadi.
> nc 10.15.42.60 48500
> file: File sama seperti FTP Login
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
> Sebuah perusahaan IT support mendapatkan serangan oleh orang tidak dikenal. Bantulah perusahaan tersebut untuk melacak jejak yang ditinggalkan oleh attacker.
> nc 10.15.42.60 51000
> file: breach.pcapng
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
> nc 10.15.42.60 53000
> file: rahasia.pcap

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
> nc 10.15.42.60 54000
> file: ez.pcapng

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
> nc 10.15.42.60 59500
> file: riset.pcapng

   


