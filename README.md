# Tugas-5_SISTEM-OPERASI_JOB-CONTROL

Nama    :Satrio Joronggur Mahendra

Kelas   : SK3B

NIM     :09011282328092


1. Eksekusi seluruh profile yang ada :
a. Edit file profile /etc/profile dan tampilkan pesan sebagai berikut :
echo “Profile dari /etc/profile”
![Screenshot 2024-09-21 110821](https://github.com/user-attachments/assets/e1601f64-0369-402d-a965-76bbba6734e9)
![Screenshot 2024-09-21 110746](https://github.com/user-attachments/assets/52dc2090-13a2-45a1-b817-1375683b8ed6)
![Screenshot 2024-09-21 110915](https://github.com/user-attachments/assets/5bb2f49c-ad30-41b1-8e2d-ad6cb825111e)



b. Asumsi nama anda stD02001, maka edit semua profile yang ada yaitu :

/home/stD02001/.bash_profile

/home/. stD02001/.bash_login

/home/mahasiswa/.profile

/home/mahasiswa/.bashrc


Ganti nama /home/mahasiswa dengan nama anda sendiri. Pada setiap

file tersebut, cantumkan instruksi echo, misalnya pada /home/ mahasiswa/.bash_profile :

echo “Profile dari .bash_profile”

Lakukan hal yang sama untuk file lainnya, sesuaikan tampilan dengan nama file yang bersangkutan.

ketik nano .bash_profile, setelah menggunakan command nano, ketikkan echo "Profile dari .bash_profile" kemudian tekan ctrl + x untuk menyimpan isi file, begitu juga dengan .bash_login, .profile, dan  .bashrc
![Screenshot 2024-09-21 114843](https://github.com/user-attachments/assets/760f79c7-4b63-43c4-adf1-ccfcf5414fa6)
![Screenshot 2024-09-21 114908](https://github.com/user-attachments/assets/a6b398aa-c30c-4bcc-93d7-d27070fe476f)

![Screenshot 2024-09-21 115636](https://github.com/user-attachments/assets/b37e9462-1df9-4351-8f04-79f1d8a6d1b1)
![Screenshot 2024-09-21 115657](https://github.com/user-attachments/assets/05e5a9c0-7f6a-42dc-8b7e-d2e7a39e1015)

![Screenshot 2024-09-21 120121](https://github.com/user-attachments/assets/522fc6d8-244b-48b8-8ab3-f5e88b68e54d)
![Screenshot 2024-09-21 120144](https://github.com/user-attachments/assets/11dc1463-396a-4afd-ab84-7e381f28b763)

![Screenshot 2024-09-21 120335](https://github.com/user-attachments/assets/20de8c05-f7dd-44c5-a166-8dbbb10efcdd)
![Screenshot 2024-09-21 120356](https://github.com/user-attachments/assets/852cbc49-2b46-4363-8a91-276f0d900e20)

c. Jalankan instruksi subtitute user, kemudian keluar dengan perintah exit sebagai berikut:
$ su mahasiswa
$ exit
kemudian gunakan opsi – sebagai berikut :
$ su – mahasiswa
$ exit
Jelaskan perbedaan kedua utilitas tersebut. 
![Screenshot 2024-09-21 121100](https://github.com/user-attachments/assets/12f7563f-f842-4987-bdcc-078c8d0ec6ed)

Perbedaan antara su dan su - adalah bahwa saat menggunakan su, jika kita berpindah ke akun bernama satriojr, kita tetap berada di terminal yang sama dan di direktori yang sama. Namun, saat menggunakan su -, kita benar-benar berpindah ke lingkungan pengguna baru, seolah-olah kita masuk sebagai pengguna satriojr dari awal. Ini berarti kita juga berpindah ke direktori home pengguna tersebut, dan semua pengaturan serta variabel lingkungan pengguna satriojr dimuat. Dengan kata lain, su hanya mengganti identitas pengguna tanpa mengubah lokasi, sementara su - menciptakan sesi baru dengan semua pengaturan pengguna baru.

dengan kata lain :
su satriojr hanya mengganti identitas user ke user mahasiswa tanpa mengubah lingkungan kerja atau environment yang sedang aktif. Kamu tetap menggunakan variabel environment dan direktori dari user sebelumnya.

su - satriojr mengganti identitas user ke user mahasiswa dan sekaligus memuat environment sepenuhnya, seperti variabel HOME, PATH, serta menjalankan file konfigurasi startup shell milik user mahasiswa (seperti .bash_profile). Ini memberikan pengalaman yang mirip dengan login penuh sebagai user satriojr.

Perbedaan utamanya: su tidak memuat environment user baru, sedangkan su - memuat environment dan konfigurasi startup sepenuhnya.


2. Prompt String (PS)
a. Edit file .bash_profile, ganti prompt PS1 dengan ‘>’. Instruksi export diperlukan dengan parameter nama variable tersebut, agar perubahan variable PS1 dikenal oleh semua shell

PS1=‟> „

export PS1

![Screenshot 2024-09-21 122116](https://github.com/user-attachments/assets/4bf0d231-76d8-41fe-b631-741cb33423c3)
![Screenshot 2024-09-21 122133](https://github.com/user-attachments/assets/f0842719-79c7-4733-8739-fa2b56e8b07d)

Edit file .bash_profile, ganti prompt PS1 dengan ‘>’. Instruksi export diperlukan dengan parameter nama variable tersebut, agar perubahan variable PS1 dikenal oleh semua shell

b. Eksperimen hasil PS1 : 

$ PS1=“\! > “

69 > PS1=”\d > “

Mon Sep 23 > PS1=”\t > “

10:10:20 > PS1=”Saya=\u > “

Saya=mahasiswa > PS1=”\w >”

~ > PS1=\h >”

![Screenshot 2024-09-21 123639](https://github.com/user-attachments/assets/8bb1bff0-a4e7-4fe5-87c8-8dfcc4c2bd71)
 Penjelasan :

a. PS1=“! > “ : Command ini untuk mengetahui berapa banyak history command prompt yang sudah kita gunakan dalam terminal dengan menjadikan output dari ! sebagai prompt shell sehingga prompt shellnya  menjadi 119> saja (119 adalah history command prompt yang sudah digunkakan dan > hanyalah simbol, sama seperti $, # dan lain lain)

b. 119>PS1="\d>" : ini untuk menampilkan hari, bulan dan tanggal yang kemudian hasil output nya dijadikan prompt shell

c. Sat Sep 21>PS1="\t>" : ini untuk menampilkan waktu dengan format jam, menit dan detik kemudian hasil output nya menjadi prompt shell

d. 12:33::23>PS1="Saya=\u>" : ini berfungsi untuk menampilkan username yang digunakan kemudian dijadikan sebagai prompt shell bersamaan dengan miki-purnawan= sehingga prompt shell nya adalah saya=satriojr>

e. Saya=satriojr>PS1="\w>" : ini berfungsi untuk menampilkan direktori saat ini lalu dijadikan prompt shell, karena saya berada di direktori ~ maka dari itulah prompt shell nya berubah menjadi ~>

f. ~>PS1="\h>" : ini berfungsi untuk menampilkan nama host atau nama komputer kemudian hasil output nya dijadikan teks statis di prompt shell


3. Logout

Edit file .bash_logout, tampilkan pesan dan tahan selama 5 detik, sebelum eksekusi logout

Echo “Terima kasih atas sesi yang diberikan”

Sleep 5

clear

Setelah mengedit isi file dari .bash_logout, coba lah untuk log out dengan cara exit untuk melihat apakah ada pesan echo kemudian sistem terminal akan sleep selama 10 detik, kita akan coba mengeksekusi sebuah command terminal lalu mencoba command logout yang sudah kita masukkan, di coba dgn mengeksekusi su - satrio (logout bisa digunakan saat eksekusi apapun ). Contoh output nya seperti dibawah ini
![Screenshot 2024-09-21 124758](https://github.com/user-attachments/assets/e8a1ed18-dcad-4876-9e3a-ffed141402af)
![Screenshot 2024-09-21 124905](https://github.com/user-attachments/assets/a952f749-5bbc-43cc-ba9f-847613c233e2)

4. Bash script
a. Buat 3 buah script p1.sh, p2.sh, p3.sh dengan isi masing-masing :

p1.sh

#! /bin/bash

echo “Program p1”

ls –l


p2.sh

#! /bin/bash

echo “Program p2”

who


p3.sh

#! /bin/bash

echo “Program p3”

ps x


buatlah dengan mennggunakan command nano  seperti dibawah ini

![Screenshot 2024-09-21 130725](https://github.com/user-attachments/assets/bca94ecf-49c3-4820-b957-c3f7c45143f9)
![Screenshot 2024-09-21 130706](https://github.com/user-attachments/assets/8501b00b-e392-412f-8d6e-76b5b712bb8e)

![Screenshot 2024-09-21 131132](https://github.com/user-attachments/assets/fb73c1f6-234d-4825-ae80-55bd5e1f919d)
![Screenshot 2024-09-21 131208](https://github.com/user-attachments/assets/a51a024e-51d4-47bc-8981-0fe52ccb1c82)


![Screenshot 2024-09-21 131137](https://github.com/user-attachments/assets/17b840a3-ef23-49a2-bba8-05d82f75fd8f)
![Screenshot 2024-09-21 131148](https://github.com/user-attachments/assets/e774453b-1d96-4f57-8c2f-e749a2356179)


b. Jalankan script tersebut sebagai berikut :

$ ./p1.sh ; ./p3.sh ; ./p2.sh

$ ./p1.sh &

$ ./p1.sh $ ./p2.sh & ./p3.sh &

$ ( ./p1.sh ; ./p3.sh ) & 


Ini menjalankan tiga skrip secara berurutan, yaitu p1.sh, p3.sh, dan p2.sh.
Tanda titik koma (;) digunakan untuk memisahkan perintah dan memastikan bahwa perintah berikutnya akan dijalankan setelah perintah sebelumnya selesai, tidak peduli apakah perintah sebelumnya berhasil atau gagal.


Skrip p1.sh dieksekusi terlebih dahulu. Setelah p1.sh selesai (berhasil atau gagal), p3.sh dijalankan. Setelah p3.sh selesai, p2.sh dijalankan.
Semua skrip dijalankan dalam urutan satu per satu.

![Screenshot 2024-09-21 134023](https://github.com/user-attachments/assets/96138a7c-6f73-4e98-a329-23d7064e8020)


$ ./p1.sh &


Fungsi:
Menjalankan skrip p1.sh di background. Tanda & di akhir perintah memindahkan eksekusi skrip ke background, memungkinkan user menjalankan perintah lain tanpa menunggu skrip selesai.
![Screenshot 2024-09-21 134558](https://github.com/user-attachments/assets/7cfb1af9-a7b7-468d-a8f5-ec46b9e7e6f3)

krip p1.sh dijalankan sebagai proses background, sehingga terminal langsung kembali siap menerima perintah berikutnya.
Kamu bisa menggunakan jobs untuk melihat status proses background atau fg untuk membawa proses background kembali ke foreground.


$ ./p1.sh & ./p2.sh & ./p3.sh &
Fungsi:
Perintah `./p1.sh & ./p2.sh & ./p3.sh &` menjalankan tiga skrip (`p1.sh`, `p2.sh`, dan `p3.sh`) secara **paralel** di background. Tanda `&` setelah setiap perintah menunjukkan bahwa setiap skrip dijalankan sebagai **proses background**, yang artinya terminal tidak menunggu skrip tersebut selesai dan segera siap menerima perintah baru. Semua skrip dieksekusi secara bersamaan tanpa saling menunggu satu sama lain, sehingga mempercepat eksekusi jika tidak ada ketergantungan di antara skrip-skrip tersebut. Pengguna dapat memeriksa status proses background menggunakan perintah `jobs`

![Screenshot 2024-09-21 135237](https://github.com/user-attachments/assets/76851c69-b0c2-4381-b1db-248f87e7569c)
![Screenshot 2024-09-21 135301](https://github.com/user-attachments/assets/75d4b9ab-12a6-4692-9f5a-cc77d4434ec1)

$ ( ./p1.sh ; ./p3.sh ) &

Perintah $ ( ./p1.sh ; ./p3.sh ) & menjalankan dua skrip (p1.sh dan p3.sh) secara berurutan dalam subshell, lalu mengeksekusi seluruh blok perintah ini di background.

![Screenshot 2024-09-21 135638](https://github.com/user-attachments/assets/08e5e03a-b210-4199-9799-674e70981eaf)
![Screenshot 2024-09-21 135650](https://github.com/user-attachments/assets/c095e800-570d-47ae-b69a-04bf984df896)

5. Jobs
a. Buat shell-script yang melakukan loop dengan nama pwaktu.sh,
setiap 10 detik, kemudian menyimpan tanggal dan jam pada file hasil.

#!/bin/bash

while [ true ]

do

date >> hasil

sleep 10

done


Skrip ini akan terus mencatat waktu (dari perintah date) ke dalam file bernama hasil setiap 10 detik.
Setiap kali waktu ditulis ke file, skrip berhenti selama 10 detik menggunakan sleep, lalu mengulangi prosesnya tanpa henti.


![Screenshot 2024-09-21 141410](https://github.com/user-attachments/assets/3fd3ab53-f0b2-4a16-8160-97346a799f6f)
![Screenshot 2024-09-21 141047](https://github.com/user-attachments/assets/18501ce9-fb0c-47b6-91aa-09ed58dfbc37)


b. Jalankan sebagai background; kemudian jalankan satu program (utilitas find) di background
sebagai berikut :

$ jobs

$ find / -print > files 2>/dev/null &

$ jobs


$ find / -print > files 2>/dev/null &
Perintah ini menjalankan utilitas find untuk mencari semua file dan direktori di seluruh sistem, seperti yang telah dijelaskan sebelumnya.

Output hasil pencarian dialihkan ke file files, sementara pesan kesalahan dibuang dengan mengalihkan ke /dev/null.

Tanda & di akhir menjalankan perintah ini di background, memungkinkan terminal untuk segera siap menerima perintah lain.

![Screenshot 2024-09-21 143059](https://github.com/user-attachments/assets/5f406931-7eeb-4f21-afec-2f99d5239c60)


c. Jadikan program ke 1 sebagai foreground, tekan ^Z dan kembalikan program tersebut ke
background

$ fg %1

Setelah kamu menjalankan sebuah perintah di background dan kemudian menghentikannya dengan menekan ^Z, proses tersebut akan berada dalam status "stopped".
Menggunakan jobs akan menunjukkan daftar semua pekerjaan, termasuk yang dihentikan.
Dengan menjalankan fg %1, proses tersebut akan dilanjutkan, dan outputnya akan ditampilkan di terminal. Sekarang kamu bisa melihat apa yang terjadi dengan proses itu dan memberikan input jika diperlukan.


$ bg

Cara Kerja:
Sebelum menggunakan bg, biasanya kamu akan menghentikan proses dengan menekan ^Z, yang membuat proses tersebut dalam status "stopped".
Ketika kamu menjalankan bg, sistem akan melanjutkan proses yang dihentikan tanpa mengharuskan kamu berinteraksi langsung dengannya.
Jika ada lebih dari satu pekerjaan yang dihentikan, dan kamu ingin melanjutkan pekerjaan tertentu, kamu bisa menggunakan sintaks seperti bg %1, di mana 1 adalah nomor pekerjaan yang ingin kamu jalankan di background.

![Screenshot 2024-09-21 143307](https://github.com/user-attachments/assets/805b661e-bb38-450b-a149-b89fdbf2887f)


d. Stop program background dengan utilitas kil

$ ps x

$ kill [Nomor PID]

pertana kita cari dulu nomor PID  dari file yang ungin di stopkan programnya
lalu gunakan command kill nomor pidnya untuk stopkan sebuah program


![Screenshot 2024-09-21 143729](https://github.com/user-attachments/assets/85db7df4-208d-4785-aa77-3159fdc42d13)
![Screenshot 2024-09-21 143741](https://github.com/user-attachments/assets/0ff0c992-e033-4fcb-a4e6-773af8eb0212)

![Screenshot 2024-09-21 143714](https://github.com/user-attachments/assets/eb3cd21c-b31c-4221-81d7-4559b255158a)


6. History

a. Ganti nilai HISTSIZE dari 1000 menjadi 20

$ HISTSIZE=20

$ h 

Contoh Penggunaan:
Jika kamu sering menggunakan terminal dan ingin membatasi jumlah perintah yang disimpan, mengatur HISTSIZE seperti ini bisa membantu menjaga riwayat tetap ringkas dan relevan.
Untuk mengeceknya kita bisa ketik history maka akan muncul 20 terakhir
![Screenshot 2024-09-21 144049](https://github.com/user-attachments/assets/a9a270dd-286d-412a-b19f-3c90f817b865)

b. Gunakan fasilitas history dengan mengedit instruksi baris ke 5 dari instruksi yang terakhir
dilakukan

$ !-5


Setelah mengetik $ !-5, shell akan mencari dalam riwayat perintah dan mengulangi perintah kelima dari perintah terakhir yang dieksekusi.

![Screenshot 2024-09-21 144503](https://github.com/user-attachments/assets/14756094-77c8-46ef-b26a-c63b498fc8a4)

c. Ulangi instruksi yang terakhir. Gunakan juga ^P dan ^N untuk bernavigasi pada history bufer

$ !!
digunakan untuk mengeksekusi kembali perintah terakhir. 

![Screenshot 2024-09-21 144544](https://github.com/user-attachments/assets/a87f01e8-05a6-4703-b54c-1ef863720426)

d. Ulangi instruksi pada history bufer nomor 150

$ !150

Perintah $ !150 sangat berguna untuk mengeksekusi kembali perintah tertentu dalam riwayat tanpa harus mengetiknya lagi. 


![Screenshot 2024-09-21 144722](https://github.com/user-attachments/assets/77082e29-54d1-4dff-8c37-843c030f7951)


e. Ulangi instruksi dengan prefix “ls”

$ !ls 

Perintah $ !ls sangat berguna untuk dengan cepat mengulangi perintah sebelumnya yang berkaitan dengan ls, yang sering digunakan untuk menampilkan daftar file dan direktori. 

![Screenshot 2024-09-21 152715](https://github.com/user-attachments/assets/bf74ec96-0d52-409b-8527-bc397726e864)
