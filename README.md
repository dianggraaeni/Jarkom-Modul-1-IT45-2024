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
   * Malicious Code

## Advance Sanity Check
> Yang sederhana dulu aja.
> nc 10.15.42.60 44000
> file: sanity.pcapng

![image](https://github.com/user-attachments/assets/40b98317-668c-49e9-bbc8-87e7b033bc34)
![image](https://github.com/user-attachments/assets/bbcc7e1e-1296-47e8-a170-7147b01ab646)
![image](https://github.com/user-attachments/assets/174b9a88-3bae-4e74-8444-6d65d8c42714)
![image](https://github.com/user-attachments/assets/c15b474d-d1b6-4691-8841-901ddea66910)
![image](https://github.com/user-attachments/assets/ea581344-341d-4362-83f8-b9df2f2e4603)

## Illegal Breakthrough
> Seorang full-stack developer bernama kevin sedang membuat sebuah web yang memiliki login page. Tetapi karena ia hanya digaji rendah, ia lupa untuk mengamankan web yang ia buat. Bantulah kevin untuk tracing dari jejak yang ditinggalkan oleh attacker.
> nc 10.15.42.60 46000
> file: break.pcapng

## FTP Login
> Seseorang menemukan sebuah celah dalam sebuah server. Ia mencoba untuk melakukan brute force login dan ia berhasil masuk. Lakukan pemeriksaan untuk melihat apa yang dilakukan oleh orang tersebut!
> nc 10.15.42.60 49000
> file: ftplogin.pcapng

## Surprise
> Setelah mengetahui apa yang diketahui pada challenge sebelumnya, sekarang lakukan analisis untuk mengetahui apa yang sebenarnya terjadi.
> nc 10.15.42.60 48500
> file: File sama seperti FTP Login

## Corporate Breach
> Sebuah perusahaan IT support mendapatkan serangan oleh orang tidak dikenal. Bantulah perusahaan tersebut untuk melacak jejak yang ditinggalkan oleh attacker.
> nc 10.15.42.60 51000
> file: breach.pcapng

## Pegawai Negeri Sebelah
> Kamu seorang data analisis diminta untuk memastikan ulang data-data dari beberapa pegawai.
> nc 10.15.42.60 53000
> file: rahasia.pcap

## EZ
> Aku sedang mencoba bikin chat service tapi kayanya pesannya bisa di sniffing deh? coba temukan pesannya.
> nc 10.15.42.60 54000
> file: ez.pcapng

## Rizzset
> Aku sedang bereksperimen dengan suatu tools, kamu juga bisa menggunakannya untuk menjawab soal ini.
> nc 10.15.42.60 59500
> file: riset.pcapng

## Malicious Code
> Ternyata sang attacker dengan sengaja meninggalkan sesuatu untuk dibaca oleh kamu. Lihat pesan apa yang ditinggalkan attacker.
File sama seperti Corporate Breach.
> nc 10.15.42.60 52000
> file: breach.pcapng

![Screenshot 2024-09-18 234023](https://github.com/user-attachments/assets/7ae2e5eb-10a7-4230-93b0-1afeab6c73df)

  - Pertama kita melakukan "http contains 'GET'" untuk menemukan berapa kali attacker melakukan HTTP request "GET" dan melihat berapa paket HTTP yang terdisplay
    ![image](https://github.com/user-attachments/assets/e646fa00-bf25-452a-acb7-cea5650bbf34)
  - Lalu untuk pertanyaan kedua kita lihat HTTP request yang sudah ter display filter tadi dan cari packet yang terakhir. Di situ kita dapat menemukan endpoint "index.php"
    ![Screenshot 2024-09-19 001432](https://github.com/user-attachments/assets/f5c6cfda-3b58-42e4-adf8-304d7222c3ec)
  - Lalu kita display filter "HTTP contains 'POST'" untuk melihat POST berupa login dari attacker
    ![image](https://github.com/user-attachments/assets/b6cfc585-8b4e-4399-b478-268713803886)
  - Setelah di analisis 5 POST paling bawah memiliki messege dari attacker namun tidak ada pertanyaan... Di packet yang terakhir terdapat ASCII yang jika di lakukan decode menjadi seperti berikut
    ![Screenshot 2024-09-18 233141](https://github.com/user-attachments/assets/5cddda6e-d3cd-4bae-b49b-aa55188e954f)
  - Jawabannya adalah merah karena VSCODE salah satu ASLAB yang MERAH sangat mencolok

