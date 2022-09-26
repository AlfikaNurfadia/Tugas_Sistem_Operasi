### Nama : ALFIKA NURFADIA
### NIM : 2110131220016
---
# **STRUKTUR SISTEM OPERASI**
## **1. STRUKTUR SEDERHANA**
<p align="justify">Beberapa sistem komersial masih belum memiliki stuktur yang cukup baik. Kondisi ini menyebabkan sistem operasi yang digunakan cukup sederhana, kecil, dengan beberapa keterbatasan. Dua contoh sistem tersebut adalah MS DOS dan UNIX, dengan ciri khas :

* MS DOS = fokus pada fungsional tertentu dan tidak dapt dibagi dalam beberapa modul.

* UNIX = fokus pada setiap prosedur yang memanggil prosedur lainnya, sehingga menyebabkan tiap prosedur dapat saling berkomunikasi dan kernel berisikan semua layanan yang disediakan oleh sistem ke pengguna.

<p align="justify">Struktur sistem operasi monolitik hanya dapat digunakan pada beberapa perangkat keras saja. Hal ini disebabkan karena sistem operasi monolotik dilengkapi dengan operasi dual mode dan pelayanan system calls. Namun, Intel 8088 tidak dapat menggunakan dual mode sehingga tidak akan ada proteksi pada perangkat keras yang digunakan.

Secara umum, system calls pada sistem operasi monolitik dibuat dengan cara :

* <i>User program</i> melakukan <i>trap</i> pada kernel
* Instruksi akan berpindah dari user mode ke monitor mode
* Kontrol akan berpindah ke sistem operasi dan otomatis akan memeriksa setiap parameter dari pemanggilan tersebut
* Sistem operasi akan menuju ke tabel yang berisikan slot ke -k yang menunjukkan system call k
* Setelah selesai, kontrol akan dikembalikan ke user program

<p align="justify">Walaupun mudah digunakan, struktur monolitik memiliki kekurangan yang cukup berbahaya. Program-program malware dapat mudah memodifikasi sistem dan merusak keseluruhan sistem operasi yang anda gunakan.

<p align="justify">Selain itu, struktur ini dapat menyebabkan pemborosan jika setiap kernelnya harus menjalankan kernel monolitik yang sangat besar. Perlu diingat juga bahwa satu saja kesalahan pemrograman dari salah satu bagian kernel dapat menyebabkan matinya keseluruhan sistem monolitik yang digunakan.

## **2. PENDEKATAN BERLAPIS**
<p align="justify">Sistem operasi berlapis memiliki beberapa lapis yang beragam, mulai dari bagian atas hingga bagian bawah. Masing-masing lapisan ini memiliki fungsi dan tujuannya tersendiri yang saling mendukung satu sama lain. Lapisan paling bawah digunakan untuk perangkat keras, sedangkan lapisan paling atas digunakan untuk user interface.

<p align="justify">Sistem berlapis banyak digunakan karena dapat mengurangi kompleksitas rancangan dari implementasi sebuah sistem operasi. Setiap lapisan struktur tersebut berasal dari hasil implementasi objek abstrak.

<p align="justify">Kondisi ini menyebabkan hasil implementasi berasal dari data yang terenkapsulasi dan operasi yang dapat dimanipulasi. Salah satu contoh struktur sistem berlapis adalah The System.

Menurut Tananbaum dan Woodhull, sistem operasi berlapis memiliki 6 lapisan, yaitu :
* Lapisan 0, untuk mengatur alokasi prosesor, pertukaran antar proses, dan mendukung dasar multi programming pada CPU.
* Lapisan 1, untuk mengalokasikan ruang proses di memori utama dan menahan proses ketika tidak ada ruang di memori utama.
* Lapisan 2, untuk menangani komunikasi antar masing-masing proses dan operator console.
* Lapisan 3, untuk mengatur peranti M/K dan menampung informasi yang mengalir di dalam proses kerja sistem operasi.
* Lapisan 4, untuk tempat program pengguna.
* Lapisan 5, untuk sistem operator.

Berbeda dari Tananbaum dan Woodhull, Stallings membagi sistem operasi berlapis dalam lapisan yang lebih mendetail, yaitu :
* Lapisan 1, untuk berbagai sirkuit elektronik.
* Lapisan 2, untuk instruksi prosesor.
* Lapisan 3, untuk penambahan konsep.
* Lapisan 4, untuk penambahan interrupt.
* Lapisan 5, untuk program instruksi yang dilakukan oleh prosesor.
* Lapisan 6, untuk secondary storage device.
* Lapisan 7, untuk menciptakan alamat logika proses dan mengatur hubungan antara main memory, virtual memory, dan secondary memory.
* Lapisan 8, untuk program-program yang akan dijalankan oleh prosesor.
* Lapisan 9,untuk secondary storage device dalam membaca dan menulis head, track dan sektor.
* Lapisan 10, untuk menjalankan alamt logika proses
* Lapisan 11, untuk kumpulan instruksi dari program yang dilakukan prosesor.
* Lapisan 12, untuk berkas objek yang memiliki nama dan ukurannya masing-masing.
* Lapisan 13, untuk penyedia user interface.

Beberapa jenis lapisan yang digunakan dalam sistem operasi berlapis adalah :

* **Lapisan Perangkat Keras**

<p align="justify">Lapisan perangkat keras merupakan lapisan paling bawah pada sistem operasi berlapis. Lapisan ini terdiri dari sirkuit elektronik yang berfungsi untuk membersihkan register ataupun membaca lokasi memori, set instruksi pada prosesor, serta interupsi yang berisikan perintah yang dijalankan.

* **Lapisan Sistem Operasi**

<p align="justify">Lapisan sistem operasi merupakan sebuah lapisan yang berhubungan secara langsung dengan program spesifik pada bagian sistem operasinya.

<p align="justify">Lapisan ini memiliki kerja yang bersifat teknis dan terdiri dari penyimpanan sekunder komputer, ide dalam eksekusi program, dan lamat logic dari setiap proses yang berlangsung. Kode program sangat diperlukan pada lapisan ini agar dapat terlaksanakan dengan benar dan sesuai dengan yang diharapkan.

* **Lapisan Kelengkapan**

<p align="justify">Lapisan kelengkapan masih berhubungan dengan program karena termasuk dari kelengkapan sebuah sistem operasi. Lapisan ini memiliki tugas utama sebagai pengaturan komunikasi informasi yang berlangsung, termasuk menerima pesan-pesan dan proses pengirimannya.

<p align="justify">Lapisan ini juga memiliki tugas dalam penyimpanan jangka panjang, menyediakan akses pada perangkat keras eksternal yang menggunakan user interface standar, dan bertanggung jawab dalam hubungan identifier internal atau eksternal.

* **Lapisan Program Aplikasi**

<p align="justify">Lapisan program aplikasi bertujuan untuk menghubungkan pengguna dengan aplikasi yang digunakan, dimana sangat berhubungan erat dengan user interface. Lapisan inin akan memproses segala informasi yang dibutuhkan oleh pengguna dalam aplikasi.

## **3. KERNEL MIKRO**
<p align="justify">Kernel mikro adalah sistem operasi yang mempermudah komunikasi antara program klien dengan beragam layanan pada ruang <i>user.</i>

<p align="justify">Komunikasi yang terjadi antar <i>module user</i> menggunakan <i>passing massage</i>. Kernel mikro dapat memperluas sistem operasi dan mudah diatur jika ada transformasi ke arsitektur yang baru. Kode program yang digunakan pada sistem ini juga lebih kecil dan lebih aman.

Beberapa manfaat yang dapat anda terima dari struktur sistem mikro kernel adalah :

* Mudah untuk dikembangkan
* Mudah untuk porting sistem operasi ke arsitektur baru
* Mudah diandalkan
* Hanya menggunakan sedikit kode
* Lebih aman

<p align="justify">Walaupun demikian, struktur sistem mikro kernel sering mengalami overhead kinerja dari komunikasi ruang ke pengguna ruang kernel. Pastikan anda sudah mempertimbangkan kekurangan ini sebelum menerapkan struktur sistem mikro kernel.

Beberapa sistem operasi yang menerapkan mikro kernel adalah :

* Tru64 UNIX
* MacOSX
* QNX