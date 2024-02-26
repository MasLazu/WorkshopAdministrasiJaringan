# TUGAS 2

## 1. Struktur Direktori Debian

Struktur direktori pada sistem operasi berbasis Debian, seperti Ubuntu, berlandaskan pada Filesystem Hierarchy Standard (FHS). FHS mendefinisikan struktur dan direktori standar pada sistem operasi berbasis Linux, termasuk Debian. Berikut ini adalah struktur direktori pada debian yang saya telah install:

```
/
├── bin -> usr/bin
├── boot
├── dev
├── etc
├── home
├── lib -> usr/lib
├── lib64 -> usr/lib64
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin -> usr/sbin
├── srv
├── storage
├── sys
├── tmp
├── usr
│   ├── local
│   │   ├── bin
│   │   ├── sbin
│   │   └── lib
│   ├── bin
│   ├── lib
│   ├── libexec
│   ├── sbin
│   └── share
│       ├── doc
│       └── man
└── var
    ├── backups
    ├── cache
    ├── lib
    ├── local
    ├── lock -> /run/lock
    ├── log
    ├── mail
    ├── opt
    ├── run -> /run
    ├── spool
    └── tmp

```

- **/bin -> usr/bin**: Ini berarti bahwa direktori `/bin` sebenarnya adalah symlink ke `/usr/bin`, yang berarti semua file eksekusi sistem yang biasanya ditemukan di `/bin` sekarang berada di `/usr/bin`. Perubahan ini adalah bagian dari usaha untuk menyatukan direktori biner yang terpisah ke dalam `/usr` untuk memudahkan manajemen.

- **/boot**: Direktori yang berisi file yang diperlukan untuk boot sistem, termasuk kernel Linux (`vmlinuz`) dan gambar initrd (`initrd.img`).

- **/dev**: Berisi file perangkat, yang mewakili perangkat keras atau perangkat virtual.

- **/etc**: Menyimpan file konfigurasi sistem.

- **/home**: Direktori ini biasanya berisi direktori home pengguna, tempat pengguna menyimpan file pribadi dan konfigurasi aplikasi.

- **/lib -> usr/lib**, **lib64 -> usr/lib64**: Seperti `/bin`, direktori `/lib` dan `/lib64` (untuk pustaka 64-bit) sekarang adalah symlink ke lokasi yang sesuai di dalam `/usr`. Ini menunjukkan penyatuan file sistem ke `/usr`.

- **/media**: Tempat untuk memasang perangkat penyimpanan removable.

- **/mnt**: Digunakan untuk mount sistem file sementara.

- **/opt**: Untuk perangkat lunak opsional dan paket pihak ketiga.

- **/proc**: Sistem file virtual yang menyediakan antarmuka ke informasi sistem.

- **/root**: Home direktori untuk pengguna root.

- **/run**: Digunakan untuk informasi tentang sistem yang sedang berjalan sejak boot terakhir.

- **/sbin -> usr/sbin**: Symlink, menunjukkan bahwa eksekutabel sistem penting sekarang berada di `/usr/sbin`.

- **/srv**: Untuk data layanan yang disediakan oleh sistem.

- **/storage**: Tampaknya merupakan direktori kustom, mungkin digunakan untuk penyimpanan data tambahan atau backup.

- **/sys**: Sistem file virtual yang menyediakan antarmuka ke kernel untuk akses dan manajemen perangkat keras.

- **/tmp**: Untuk file sementara yang dibuat oleh sistem dan pengguna.

- Direktori `/usr` pada sistem operasi berbasis Debian dan distribusi Linux lainnya merupakan salah satu direktori utama yang berisi mayoritas aplikasi dan file yang digunakan oleh sistem. Direktori ini dirancang untuk menyimpan data yang tidak berubah selama operasi normal sistem. Berikut adalah penjelasan untuk masing-masing subdirektori dalam `/usr`:

  1. **bin**: Menyimpan file eksekusi biner untuk banyak program dan aplikasi yang digunakan oleh pengguna sistem. Ini adalah tempat untuk perintah yang tidak esensial untuk proses booting, tetapi yang diperlukan untuk operasi normal sistem dalam mode multi-user.

  2. **games**: Berisi file eksekusi biner untuk game. Meskipun tidak semua distribusi Linux secara aktif menggunakan direktori ini, direktori ini ditujukan untuk permainan dan skor permainan.

  3. **include**: Berisi file header, yang digunakan oleh kompiler C dan C++ untuk pengembangan perangkat lunak. File header ini menyediakan deklarasi untuk fungsi standar dan konstanta yang diperlukan saat mengkompilasi program.

  4. **lib**: Menyimpan pustaka (libraries) yang diperlukan oleh file biner di `/usr/bin` dan `/usr/sbin`. Ini termasuk pustaka dinamis dan modul yang digunakan oleh aplikasi tersebut.

  5. **lib64**: Sama seperti direktori `/lib`, tapi khusus untuk pustaka 64-bit pada sistem 64-bit. Ini memastikan kompatibilitas dan efisiensi eksekusi untuk aplikasi 64-bit.

  6. **libexec**: Menyimpan program eksekusi yang dijalankan oleh program lain daripada oleh pengguna secara langsung. Program di sini biasanya merupakan bagian dari aplikasi dan tidak dimaksudkan untuk dijalankan secara independen.

  7. **local**: Bertindak sebagai sistem hierarki sekunder yang mirip dengan struktur utama `/usr`. Direktori `/usr/local` dapat digunakan untuk menginstal perangkat lunak dan data yang spesifik untuk mesin lokal, yang tidak dikelola oleh sistem manajemen paket distribusi. Ini sering digunakan untuk perangkat lunak yang diinstal dari sumber atau skrip yang tidak termasuk dalam distribusi.

  8. **sbin**: Berisi file eksekusi biner untuk tugas administrasi sistem yang biasanya hanya dijalankan oleh root atau melalui mekanisme sudo. Perintah di sini lebih berfokus pada pemeliharaan sistem daripada `/bin`.

  9. **share**: Direktori ini digunakan untuk menyimpan data arsitektur-independen, seperti konfigurasi, file teks, dokumen, dan lain-lain. Hal ini memungkinkan data yang sama digunakan di semua arsitektur tanpa perlu duplikasi.

  10. **src**: Berisi kode sumber untuk berbagai program. Meskipun banyak distribusi Linux menyediakan kode sumber melalui repositori terpisah atau paket khusus, direktori ini bisa digunakan untuk menyimpan kode sumber yang diinstal secara lokal.

- Direktori `/var` dalam sistem operasi berbasis Linux dan Unix digunakan untuk menyimpan data yang berubah-ubah selama operasi normal sistem, berbeda dengan data statis yang biasanya disimpan di direktori seperti `/usr`. Direktori ini mencakup berbagai jenis data seperti log sistem, mail, dan file sementara. Berikut penjelasan untuk masing-masing subdirektori dalam `/var` yang Anda sebutkan:

  1. **backups**: Digunakan untuk menyimpan file cadangan penting dari sistem. Ini bisa termasuk backup konfigurasi sistem atau aplikasi.

  2. **cache**: Menyimpan data cache dari aplikasi. Data ini digunakan untuk mempercepat aplikasi namun dapat dihasilkan kembali jika dihapus. Misalnya, paket dari sistem manajemen paket yang telah diunduh.

  3. **lib**: Berisi data yang dinamis yang digunakan oleh aplikasi yang berjalan pada sistem. Data ini termasuk informasi status saat ini dari aplikasi, seperti database yang digunakan oleh paket manajemen sistem.

  4. **local**: Mirip dengan `/var/lib`, direktori ini digunakan untuk data lokal yang spesifik untuk mesin yang bersangkutan.

  5. **lock -> /run/lock**: Ini adalah symlink ke `/run/lock` dan digunakan untuk menyimpan file lock. File lock digunakan untuk mencegah akses bersamaan ke sumber daya, seperti file atau perangkat, yang dapat menyebabkan konflik atau korupsi data.

  6. **log**: Berisi file log sistem dan aplikasi. Ini sangat penting untuk troubleshooting dan pemantauan sistem karena mencatat berbagai kegiatan sistem dan pesan kesalahan.

  7. **mail**: Direktori ini digunakan untuk menyimpan email pada sistem. Dalam beberapa konfigurasi, setiap pengguna dapat memiliki mailbox di direktori ini.

  8. **opt**: Digunakan untuk menyimpan paket perangkat lunak dan data yang merupakan tambahan dari distribusi Linux standar. Seringkali digunakan oleh perangkat lunak yang diinstal dari sumber yang bukan bagian dari sistem manajemen paket.

  9. **run -> /run**: Symlink ke `/run`, yang merupakan direktori untuk data runtime sistem. Ini termasuk PID dari proses yang berjalan, soket, dan informasi lain yang diperlukan sistem untuk operasinya yang tidak boleh dipertahankan antar boot.

  10. **spool**: Direktori ini digunakan untuk menyimpan data "spool", seperti pekerjaan cetak, email yang menunggu untuk dikirim, dan tugas-tugas lain yang menunggu untuk diproses.

  11. **tmp**: Menyimpan file sementara yang dibuat oleh aplikasi dan sistem. File di `/var/tmp` diharapkan bertahan lebih lama dibandingkan dengan file di `/tmp`.