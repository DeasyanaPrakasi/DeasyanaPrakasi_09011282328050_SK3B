# Deasyana Prakasi/09011282328050/SK3B

# Pratikum 5 Job Control

## 1. Eksekusi seluruh profile yang ada : 
### a. Edit file profile /etc/profile dan tampilkan pesan sebagai berikut : 
echo “Profile dari /etc/profile” 

![1_a](https://github.com/user-attachments/assets/3fd2509e-56a1-487a-8abc-11bfa1ff7e88)

### b. Asumsi nama anda stD02001, maka edit semua profile yang ada yaitu : 
/home/stD02001/.bash_profile 


/home/. stD02001/.bash_login 

/home/mahasiswa/.profile 

/home/mahasiswa/.bashrc 

![1_b](https://github.com/user-attachments/assets/5eaedff4-5193-4840-b5ab-6fe050cd4dfe)


Ganti nama /home/mahasiswa dengan nama anda sendiri. Pada setiap file tersebut, cantumkan instruksi echo, misalnya pada /home/ mahasiswa/.bash_profile : 

echo “Profile dari .bash_profile” 

Lakukan hal yang sama untuk file lainnya, sesuaikan tampilan dengan nama file yang bersangkutan.

![1_b_bash profile](https://github.com/user-attachments/assets/08a031df-a576-44d4-aa03-50427770c5f2)

![IMG-20240924-WA0022](https://github.com/user-attachments/assets/9622d31f-f3f1-42fc-8abb-d6f2bb20784d)

![IMG-20240924-WA0021](https://github.com/user-attachments/assets/68fbc914-6b6a-4d0f-a10b-e3632e426efa)

![IMG-20240924-WA0023](https://github.com/user-attachments/assets/81fe866e-0a5b-433e-ab13-fbbea20ca78e)

### c. Jalankan instruksi subtitute user, kemudian keluar dengan perintah exit sebagai berikut: 
$ su mahasiswa 

$ exit 

kemudian gunakan opsi – sebagai berikut : 

$ su – mahasiswa 

$ exit 

![1_c](https://github.com/user-attachments/assets/6dc45ed6-c60c-4e7d-b671-41bdfe7727e4)

Jelaskan perbedaan kedua utilitas tersebut. 
#### Penjelasan
Perbedaan antara su dan su - terletak pada bagaimana mereka menangani perpindahan pengguna dan pemuatan lingkungan sistem. Jika menggunakan su, hanya terjadi perpindahan ke pengguna lain tanpa memuat file konfigurasi login seperti .bash_profile, sehingga sebagian besar pengaturan lingkungan tetap sama. Sebaliknya, dengan su -, perpindahan pengguna dilakukan sekaligus memuat lingkungan shell secara lengkap seperti saat login awal, termasuk menjalankan file konfigurasi login, sehingga memberikan sesi baru dengan lingkungan yang benar-benar bersih.

## 2. Prompt String (PS) 
### a. Edit file .bash_profile, ganti prompt PS1 dengan ‘>’. Instruksi export diperlukan dengan parameter nama variable tersebut, agar perubahan variable PS1 dikenal oleh semua shell 
PS1=">" 

export PS1 

![2_a](https://github.com/user-attachments/assets/892f97df-b116-4eb3-935c-56cece9a8d4c)


### b. Eksperimen hasil PS1 : 
$ PS1=“\! > “ 

69 > PS1=”\d > “ 

Mon Sep 23 > PS1=”\t > “ 

10:10:20 > PS1=”Saya=\u > “ 

Saya=mahasiswa > PS1=”\w >” 

~ > PS1=\h >” 

![IMG-20240924-WA0019](https://github.com/user-attachments/assets/0a23b6c5-f8ab-476b-b77d-44f0aacee435)

## 3. Logout 
Edit file .bash_logout, tampilkan pesan dan tahan selama 5 detik, sebelum eksekusi logout 

Echo “Terima kasih atas sesi yang diberikan”

Sleep 5 

clear 

![3](https://github.com/user-attachments/assets/b63d5b38-7404-4b0a-aa6c-9153461defbf)
![3_kode](https://github.com/user-attachments/assets/9792400c-4459-4cac-8ebe-fa4758c6e1bf)

## 4. Bash script 
### a. Buat 3 buah script p1.sh, p2.sh, p3.sh dengan isi masing-masing : 
p1.sh 

#! /bin/bash 

echo “Program p1” 

ls –l 

![IMG-20240924-WA0026](https://github.com/user-attachments/assets/33b1d429-cdf0-4d33-8bbc-e79fd6b721f9)

p2.sh 

#! /bin/bash 

echo “Program p2” 

who

![IMG-20240924-WA0029](https://github.com/user-attachments/assets/15d49527-fb0c-4c6a-be23-83aa6519f147)

p3.sh 

#! /bin/bash 

echo “Program p3” 

ps x

![IMG-20240924-WA0028](https://github.com/user-attachments/assets/a5dcfa48-ebbc-4e09-850e-c9f91a3ef9dd)

![4A](https://github.com/user-attachments/assets/85fca9f8-ee26-4fce-b076-dfd8621dc2a6)


### b. Jalankan script tersebut sebagai berikut : 
$ ./p1.sh ; ./p3.sh ; ./p2.sh 

![4b1](https://github.com/user-attachments/assets/40c038e0-4f1b-42de-a45c-ad50b4f80c6c)

$ ./p1.sh & 

![6b2](https://github.com/user-attachments/assets/0e8182f4-87b1-4517-bacc-772b022686ee)


$ ./p1.sh $ ./p2.sh & ./p3.sh & 

![IMG-20240924-WA0017](https://github.com/user-attachments/assets/3c1406b9-e2e2-4939-a1e2-f39ff44bb93c)

$ ( ./p1.sh ; ./p3.sh ) & 

![6b4](https://github.com/user-attachments/assets/fd2627bd-5c5e-46ca-8982-4a3c98e18230)

## 5. Jobs 
### a. Buat shell-script yang melakukan loop dengan nama pwaktu.sh, setiap 10 detik, kemudian menyimpan tanggal dan jam pada file hasil.

#!/bin/bash 

while [ true ] 

do 

date >> hasil 

sleep 10 

done 

![5a](https://github.com/user-attachments/assets/47bbc03c-34e4-4a3b-ba64-afef0e7f8085)

### b. Jalankan sebagai background; kemudian jalankan satu program (utilitas find) di background sebagai berikut : 
$ jobs 

![5b1](https://github.com/user-attachments/assets/2d4fbe46-830e-4af5-815b-dfb24be855f3)

$ find / -print > files 2>/dev/null & 

$ jobs

![5b23](https://github.com/user-attachments/assets/6a6dee19-c38a-459b-8ffa-6e46b340da06)

### c. Jadikan program ke 1 sebagai foreground, tekan ^Z dan kembalikan program tersebut ke background 

$ fg %1 

$ bg

![IMG-20240924-WA0027](https://github.com/user-attachments/assets/9917a214-e8e9-46d4-bf27-748e89ad00ab)

### d. Stop program background dengan utilitas kil 

$ ps x 

$ kill [Nomor PID]

![5d2](https://github.com/user-attachments/assets/8b58ddce-4f8d-4e2d-abef-4f5cf838b31b)

## 6. History 

### a. Ganti nilai HISTSIZE dari 1000 menjadi 20 

$ HISTSIZE=20 

![6_a](https://github.com/user-attachments/assets/d807177f-9d0a-427e-8545-5dd9f70f06c9)

$ h

![6_a_h](https://github.com/user-attachments/assets/9c823a20-cabe-40b6-8302-aadab3a5fb24)

### b. Gunakan fasilitas history dengan mengedit instruksi baris ke 5 dari instruksi yang terakhir dilakukan 

$ !-5

### c. Ulangi instruksi yang terakhir. Gunakan juga ^P dan ^N untuk bernavigasi pada history bufer 

$ !!

![6_b_c](https://github.com/user-attachments/assets/532db480-ead5-4e64-9f23-69cb81dccc1c)

### d. Ulangi instruksi pada history bufer nomor 150 

$ !150 

### e. Ulangi instruksi dengan prefix “ls” 

$ !ls

![6_d_e](https://github.com/user-attachments/assets/9ced54f2-707e-4cab-96ed-aa2204aef421)
