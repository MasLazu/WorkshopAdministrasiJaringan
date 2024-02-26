# TUGAS 1

## Instal Debian dengan Virtual Box

1. **Persiapan** Unduh ISO Debian: Kunjungi situs web resmi Debian (debian.org) dan unduh file ISO untuk versi yang ingin Anda instal.
Instal VirtualBox: Unduh dan instal dari virtualbox.org. Pastikan Anda mengunduh versi yang sesuai dengan sistem operasi host Anda.
2. **Buat Mesin Virtual Baru** Buka VirtualBox dan klik tombol "New" atau "Baru".       Berikan nama untuk mesin virtual Anda, misalnya "Debian". VirtualBox biasanya akan secara otomatis memilih tipe dan versi sistem operasi berdasarkan nama yang Anda masukkan. Jika tidak, pilih "Linux" sebagai tipe dan "Debian (64-bit)" sebagai versi. 
    ![](./assets/Screenshot%202024-02-19%20104711.png) 
    Atur ukuran memori dan cpu. Disini saya menggunakan 2048 MB (2GB) dan 1 cpu, lebih banyak akan lebih baik, tergantung pada seberapa banyak RAM yang tersedia di sistem host. 
    ![](./assets/Screenshot%202024-02-19%20104719.png) 
    Pilih "Create a virtual hard disk now" untuk membuat disk baru. Klik "Create".
    ![](./assets/Screenshot%202024-02-19%20104735.png)

5. **Instalasi Debian** Mulai VM: Pilih VM dan klik "Start". Buat Pengguna dan Kata Sandi: Masukkan informasi pengguna dan kata sandi.
    ![](./assets/Screenshot%202024-02-19%20095430.png)
    ![](./assets/Screenshot%202024-02-19%20095456.png)
    Partisi Disk: Saat diminta untuk mempartisi disk, pilih "Manual" untuk konfigurasi manual. bisa membuat partisi root (biasanya dipasang sebagai /), swap, dan storage (/storage) sesuai dengan preferensi.
    ![](./assets/Screenshot%202024-02-19%20095906.png)
    ![](./assets/Screenshot%202024-02-19%20100009.png)
    ![](./assets/Screenshot%202024-02-19%20100046.png)
    ![](./assets/Screenshot%202024-02-19%20100118.png)
    Pilih Mirror Debian: Pilih mirror yang paling dekat dengan lokasi untuk mengunduh paket.
    ![](./assets/Screenshot%202024-02-19%20100353.png)
    Instal GRUB: Saat diminta, pilih untuk menginstal GRUB bootloader pada disk.
    ![](./assets/Screenshot%202024-02-19%20110956.png)
    Setelah proses instalasi selesai, mesin akan meminta Anda untuk me-restart. Setelah restart, Anda seharusnya akan disambut oleh layar login Debian baru Anda.
    Selamat! Anda sekarang telah berhasil menginstal Debian di VirtualBox dengan konfigurasi manual. Ingat untuk menginstal "Guest Additions" untuk performa dan fungsionalitas yang lebih baik.
    ![](./assets/Screenshot%202024-02-19%20111454.png)

## Perbedaan su dan su-

![](./assets/WhatsApp%20Image%202024-02-24%20at%2010.38.55.jpeg)
1. su : singkatan dari switchuser atau superuser. Dan digunakan untuk beralih akun ke User lain atau akun SuperUser. Jika su tanpa argumen tambahan, itu adalah beralih ke superUser.

2. su - : perintah ini memiliki efek yang sama dengan su sebelumnya. Namun, jika menggunakan su - akan mengganti path workspace ke superUser account. dan juga mengatur ulang seperti PATH, HOME, SHELL, dll sehingga mirip dengan login langsung sebagai superuser

## Atur Visudo
1. Buka terminal dan jalankan perintah:

```bash 
sudo visudo
```

Tambahkan baris berikut:
```bash
username ALL=(ALL) NOPASSWD: /usr/bin/apt update, /path/to/other/command
```

# perbedaan dari Debian 12 dengan Debian 11

Berikut adalah perbandingan perbedaan utama antara Debian 12 (Bookworm) dengan Debian 11 (Bullseye), termasuk versi kernel, kebutuhan sistem, penerapan systemd, dan perbedaan dalam paket-paketnya.

| Aspek             | Debian 11 (Bullseye) | Debian 12 (Bookworm) |
| ----------------- | -------------------- | -------------------- |
| Versi Kernel      | 5.10 LTS             | 6.1                  |
| Penerapan Systemd | 247                  | 252                  |

## Penjelasan /etc/groups

Perintah /etc/group digunakan untuk melihat isi dari file /etc/group menggunakan program, yang merupakan utilitas untuk membaca file teks dengan kemampuan untuk menggulir maju dan mundur.

File /etc/group adalah salah satu dari beberapa file dalam sistem Linux yang digunakan untuk mengelola informasi tentang pengguna dan grup. File ini menyimpan daftar grup yang ada di sistem, bersama dengan informasi tambahan seperti ID grup (GID) dan daftar anggota grup.

Berikut adalah beberapa informasi yang dapat Anda temukan dalam file /etc/group:

1. Nama Grup: Nama-nama grup yang terdaftar dalam sistem.
2. Kata Sandi Grup: Biasanya disimbolkan dengan "x", tetapi informasi kata sandi grup kadang-kadang disimpan di file /etc/gshadow.
3. ID Grup (GID): Identifikasi unik numerik untuk setiap grup.
4. Anggota Grup: Daftar pengguna yang merupakan anggota dari setiap grup. Jika grup memiliki lebih dari satu anggota, anggota-anggota ini biasanya dipisahkan dengan koma.
Perintah /etc/group akan membuka file ini dalam pengelolaan bacaan yang memungkinkan Anda untuk melihat isi file, gulir ke atas dan ke bawah, dan mencari teks dalam file tersebut. Ini sangat berguna ketika Anda ingin melihat daftar grup yang ada di sistem Anda atau memeriksa informasi grup tertentu.

contoh :
Baris root:x:0:root dalam file /etc/group menyimpan informasi tentang grup yang dinamakan "root". Mari kita bahas elemen-elemen dalam baris tersebut:

root: Ini adalah nama grup. Nama grup biasanya digunakan untuk mengidentifikasi grup di sistem. Dalam konteks ini, "root" adalah nama grup yang secara umum terkait dengan pengguna root, yang memiliki akses penuh ke sistem.

x: Ini adalah simbol yang menandakan bahwa kata sandi grup disimpan dalam file terpisah, biasanya dalam file /etc/gshadow. Pada sistem Linux yang lebih lama, informasi tentang kata sandi grup disimpan di sini, tetapi saat ini umumnya disimpan terpisah untuk keamanan.

0: Ini adalah ID grup (GID). ID grup adalah nomor identifikasi unik untuk setiap grup di sistem. GID 0 secara khusus diperuntukkan untuk grup "root". Grup dengan GID 0 memiliki hak akses tertinggi di sistem dan sering kali disebut sebagai "superuser" atau "root group".

root: Ini adalah nama pengguna yang umumnya terkait dengan grup. Ini menunjukkan bahwa pengguna "root" adalah anggota dari grup ini. Dalam banyak distribusi Linux, grup "root" memiliki hanya satu anggota, yaitu pengguna "root" itu sendiri.

Jadi, baris root:x:0:root menunjukkan bahwa grup dengan nama "root" memiliki GID 0, dan pengguna "root" adalah satu-satunya anggota dari grup ini. Grup ini memiliki hak akses penuh ke sistem dan merupakan bagian integral dari manajemen keamanan sistem Linux.

## Fungsi Sudo

`sudo` (superuser do) adalah sebuah perintah dalam sistem operasi berbasis Unix dan Linux yang memungkinkan pengguna untuk menjalankan program dengan keamanan tingkat keamanan lain, biasanya sebagai superuser atau root. Ini memberikan cara yang aman bagi pengguna yang terotorisasi untuk menjalankan perintah yang biasanya hanya dapat dijalankan oleh pengguna root, yang memiliki hak akses penuh ke sistem.

Berikut adalah beberapa fungsi utama dan kegunaan dari `sudo`:

1. **Elevasi Hak Akses**: Memungkinkan pengguna biasa menjalankan perintah tertentu sebagai root atau pengguna lain. Ini berguna untuk tugas-tugas administrasi yang memerlukan hak akses yang lebih tinggi.

2. **Kontrol Akses yang Dapat Dikonfigurasi**: Administrasi sistem dapat mengkonfigurasi file `/etc/sudoers` untuk mendefinisikan siapa yang dapat menjalankan perintah tertentu sebagai pengguna lain. Ini memberikan kontrol granular atas hak akses dan meningkatkan keamanan.

3. **Logging dan Audit**: `sudo` mencatat setiap perintah yang dijalankan, siapa yang menjalankannya, dan kapan itu dijalankan. Ini memudahkan untuk memantau aktivitas dan melakukan audit keamanan.

4. **Pengurangan Risiko**: Dengan menggunakan `sudo`, pengguna tidak perlu login sebagai root untuk melakukan tugas administrasi. Hal ini mengurangi risiko kerusakan atau keamanan yang tidak sengaja karena penggunaan akun root secara terus-menerus.

5. **Kemudahan Penggunaan**: `sudo` memungkinkan pengguna untuk menjalankan perintah root tanpa perlu mengganti pengguna. Ini mempercepat proses administrasi dan membuatnya lebih mudah bagi pengguna yang memiliki hak akses terbatas untuk melakukan tugas tertentu.

Secara keseluruhan, `sudo` adalah alat penting dalam manajemen sistem Linux dan Unix, memberikan keseimbangan antara kebutuhan untuk hak akses yang luas dan praktik keamanan yang baik.