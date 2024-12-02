---
name: Blockstream Green - Mobile
description: Mengatur dompet perangkat lunak seluler
---
![cover](assets/cover.webp)

Dompet perangkat lunak adalah aplikasi yang diinstal pada komputer, smartphone, atau perangkat lain yang terhubung ke Internet, memungkinkan pengelolaan dan keamanan kunci dompet Bitcoin seseorang. Berbeda dengan dompet perangkat keras, yang mengisolasi kunci privat, dompet "panas" ini beroperasi dalam lingkungan yang berpotensi terpapar serangan siber, meningkatkan risiko peretasan dan pencurian.

Dompet perangkat lunak sebaiknya digunakan untuk mengelola jumlah bitcoin yang wajar, terutama untuk transaksi harian. Ini juga bisa menjadi opsi menarik bagi orang-orang dengan portofolio Bitcoin terbatas, bagi siapa investasi dalam dompet perangkat keras mungkin terlihat tidak sebanding. Namun, paparan konstan mereka ke Internet membuatnya kurang aman untuk menyimpan tabungan jangka panjang atau dana signifikan. Untuk ini, lebih disukai untuk memilih solusi yang lebih aman, seperti dompet perangkat keras.

Dalam tutorial ini, saya akan memperkenalkan Anda kepada salah satu solusi dompet perangkat lunak seluler terbaik: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Jika Anda tertarik untuk belajar cara menggunakan Blockstream Green di komputer, silakan merujuk ke tutorial lain ini:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Pengenalan Blockstream Green

Blockstream Green adalah dompet perangkat lunak yang tersedia baik di seluler maupun komputer. Sebelumnya dikenal sebagai *Green Address*, dompet ini menjadi proyek Blockstream setelah akuisisinya pada tahun 2016.

Green adalah aplikasi yang sangat mudah digunakan, menjadikannya menarik bagi pemula. Ini menawarkan semua fitur esensial dari dompet Bitcoin yang baik, termasuk RBF (*Replace-by-Fee*), opsi untuk terhubung melalui Tor, kemampuan untuk menghubungkan node sendiri, opsi SPV (*Simple Payment Verification*), pelabelan, dan kontrol koin.

Blockstream Green juga mendukung jaringan Liquid, sidechain Bitcoin yang dikembangkan oleh Blockstream untuk melakukan transaksi cepat dan rahasia di luar blockchain utama. Tutorial ini fokus secara eksklusif pada Bitcoin, tetapi tutorial mendatang akan membahas penggunaan Liquid.

## Menginstal dan Mengatur Aplikasi Blockstream Green

Langkah pertama adalah tentu saja mengunduh aplikasi Green. Kunjungi toko aplikasi Anda:
- [Untuk Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Untuk Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Untuk pengguna Android, Anda juga memiliki opsi untuk menginstal aplikasi melalui file `.apk` [yang tersedia di GitHub Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Luncurkan aplikasi, kemudian centang kotak "*Saya menerima kondisi...*".
![GREEN](assets/fr/04.webp)

Ketika Anda membuka Green untuk pertama kalinya, layar beranda muncul tanpa dompet yang dikonfigurasi. Nanti, jika Anda membuat atau mengimpor dompet, mereka akan muncul di antarmuka ini. Sebelum melanjutkan ke pembuatan dompet, saya menyarankan Anda untuk menyesuaikan pengaturan aplikasi sesuai dengan harapan Anda. Klik pada "*Pengaturan Aplikasi*".

![GREEN](assets/fr/05.webp)

Opsi "*Privasi Tingkat Lanjut*", yang hanya tersedia di Android, meningkatkan privasi dengan menonaktifkan tangkapan layar dan menyembunyikan pratinjau aplikasi. Ini juga secara otomatis mengunci akses ke aplikasi segera setelah ponsel Anda terkunci, membuat data Anda lebih sulit untuk terpapar.

![GREEN](assets/fr/06.webp)
Bagi mereka yang ingin meningkatkan privasi mereka, aplikasi ini menawarkan untuk merutekan lalu lintas Anda melalui Tor, sebuah jaringan yang mengenkripsi semua koneksi Anda dan membuat aktivitas Anda sulit untuk dilacak. Meskipun opsi ini mungkin sedikit memperlambat kinerja aplikasi, sangat disarankan untuk melindungi privasi Anda, terutama jika Anda tidak menggunakan full node Anda sendiri.
![GREEN](assets/fr/07.webp)

Untuk pengguna yang memiliki full node mereka sendiri, Green Wallet menawarkan kemungkinan untuk terhubung ke node tersebut melalui server Electrum, memastikan kontrol penuh atas informasi jaringan Bitcoin dan penyiaran transaksi.

![GREEN](assets/fr/08.webp)

Fitur alternatif lainnya adalah opsi "*Verifikasi SPV*", yang memungkinkan verifikasi langsung terhadap data blockchain tertentu, sehingga mengurangi kebutuhan untuk mempercayai node Blockstream default, meskipun metode ini tidak memberikan semua jaminan dari full node.

![GREEN](assets/fr/09.webp)

Setelah pengaturan ini disesuaikan sesuai dengan kebutuhan Anda, klik tombol "*Simpan*" dan mulai ulang aplikasi.

![GREEN](assets/fr/10.webp)

## Membuat Dompet Bitcoin di Blockstream Green

Anda sekarang siap untuk membuat dompet Bitcoin. Klik tombol "*Mulai*".

![GREEN](assets/fr/11.webp)

Anda memiliki pilihan antara membuat dompet perangkat lunak secara lokal atau mengelola dompet dingin melalui dompet perangkat keras. Untuk tutorial ini, kami akan fokus pada pembuatan dompet panas, sehingga Anda perlu memilih opsi "*Di Perangkat Ini*". Dalam tutorial mendatang, saya akan menunjukkan cara menggunakan opsi lainnya.

Opsi "*Hanya-Lihat*", di sisi lain, memungkinkan Anda untuk mengimpor kunci publik yang diperluas (`xpub`) untuk melihat transaksi dompet tanpa dapat menghabiskan dana yang terkait, yang nyaman untuk memantau dompet pada dompet perangkat keras, misalnya.

![GREEN](assets/fr/12.webp)
Anda kemudian dapat memilih untuk memulihkan dompet Bitcoin yang sudah ada atau membuat yang baru. Untuk keperluan tutorial ini, kami akan membuat dompet baru. Namun, jika Anda perlu meregenerasi dompet Bitcoin yang sudah ada dari frasa mnemoniknya, misalnya, karena kehilangan dompet perangkat keras Anda, Anda perlu memilih opsi kedua.
![GREEN](assets/fr/13.webp)

Anda kemudian memiliki pilihan antara frasa mnemonik 12 kata atau 24 kata. Frasa ini akan memungkinkan Anda untuk memulihkan akses ke dompet Anda dari perangkat lunak apa pun yang kompatibel jika terjadi masalah dengan ponsel Anda. Saat ini, memilih frasa 24 kata tidak menawarkan lebih banyak keamanan daripada frasa 12 kata. Oleh karena itu, saya merekomendasikan memilih frasa mnemonik **12 kata**.

Green kemudian akan memberikan Anda frasa mnemonik Anda. Sebelum melanjutkan, pastikan Anda tidak sedang diamati. Klik pada "*Tampilkan frasa pemulihan*" untuk menampilkannya di layar.

![GREEN](assets/fr/14.webp)

**Frasa mnemonik ini memberikan akses penuh dan tidak terbatas ke semua bitcoin Anda.** Siapa pun yang memiliki frasa ini dapat mencuri dana Anda, bahkan tanpa akses fisik ke ponsel Anda.

Ini memungkinkan Anda untuk memulihkan akses ke bitcoin Anda dalam kasus kehilangan, pencurian, atau kerusakan pada ponsel Anda. Oleh karena itu, sangat penting untuk menyimpannya dengan hati-hati **pada media fisik (bukan digital)** dan menyimpannya di lokasi yang aman. Anda dapat menuliskannya di selembar kertas, atau untuk lebih aman, jika dompet ini penting, saya merekomendasikan mengukirnya pada media stainless steel untuk melindungi dari risiko kebakaran, banjir, atau runtuhnya bangunan (untuk dompet panas yang dimaksudkan untuk mengamankan jumlah bitcoin yang kecil, cadangan kertas sederhana mungkin sudah cukup).
*Jelas, Anda seharusnya tidak pernah membagikan kata-kata ini di internet, berbeda dengan apa yang saya lakukan dalam tutorial ini. Dompet contoh ini hanya akan digunakan pada Testnet dan akan dihapus di akhir tutorial.*
![GREEN](assets/fr/15.webp)

Setelah dengan benar mencatat frasa mnemonik Anda pada media fisik, klik pada "*Lanjutkan*". Green Wallet kemudian akan meminta Anda untuk mengonfirmasi beberapa kata dari frasa Anda untuk memverifikasi bahwa Anda telah mencatatnya dengan benar. Isi bagian yang kosong dengan kata-kata yang hilang.

![GREEN](assets/fr/16.webp)

Pilih kode PIN untuk perangkat Anda, yang akan digunakan untuk membuka kunci Green wallet Anda. Ini adalah perlindungan terhadap akses fisik yang tidak sah. Kode PIN ini tidak berperan dalam derivasi kunci kriptografis dari dompet Anda. Dengan demikian, bahkan tanpa akses ke kode PIN ini, kepemilikan frasa mnemonik 12 atau 24 kata Anda akan memungkinkan Anda untuk mendapatkan kembali akses ke bitcoin Anda.
Disarankan untuk memilih kode PIN 6 digit yang seacak mungkin. Juga, pastikan untuk mencadangkan kode ini agar Anda tidak lupa, jika tidak, Anda akan dipaksa untuk memulihkan dompet Anda menggunakan frasa mnemonik. Selanjutnya, Anda dapat menambahkan opsi penguncian biometrik untuk menghindari memasukkan PIN setiap penggunaan. Secara umum, biometrik jauh kurang aman daripada PIN itu sendiri. Oleh karena itu, secara default, saya menyarankan untuk tidak mengatur opsi pembukaan kunci ini.
![GREEN](assets/fr/17.webp)

Masukkan PIN Anda untuk kedua kalinya untuk mengonfirmasinya.

![GREEN](assets/fr/18.webp)

Tunggu hingga dompet Anda dibuat, lalu klik tombol "*Buat akun*".

![GREEN](assets/fr/19.webp)

Anda kemudian memiliki pilihan antara dompet tanda tangan tunggal standar, yang akan kami gunakan dalam tutorial ini, atau dompet yang dilindungi oleh otentikasi dua faktor (2FA).

![GREEN](assets/fr/20.webp)

Opsi 2FA pada Green menciptakan dompet multisignature 2/2, salah satu kuncinya disimpan oleh Blockstream. Ini berarti bahwa untuk melakukan transaksi, kedua kunci diperlukan: kunci lokal yang dilindungi oleh PIN Anda di ponsel, dan kunci jarak jauh yang diamankan oleh 2FA di server Blockstream. Dalam kasus kehilangan akses ke 2FA atau ketidaktersediaan layanan Blockstream, mekanisme pemulihan berbasis skrip time-lock memastikan kemungkinan pemulihan dana Anda secara independen. Meskipun pengaturan ini secara signifikan mengurangi risiko bitcoin Anda dicuri, ini lebih kompleks untuk dikelola dan sebagian bergantung pada Blockstream. Untuk tutorial ini, kami akan memilih dompet tanda tangan tunggal klasik, dengan kunci yang disimpan secara lokal di ponsel.

Dan begitulah, dompet Bitcoin Anda telah berhasil dibuat menggunakan aplikasi Green!

![GREEN](assets/fr/21.webp)

Sebelum menerima bitcoin pertama Anda di dompet Anda, **saya sangat menyarankan Anda untuk melakukan tes pemulihan dry-run**. Catat informasi referensi, seperti xpub Anda atau alamat penerimaan pertama, lalu hapus dompet Anda di aplikasi Green sementara masih kosong. Selanjutnya, coba pulihkan dompet Anda di Green menggunakan cadangan kertas Anda. Periksa bahwa informasi saksi yang dihasilkan setelah pemulihan cocok dengan yang Anda catat awalnya. Jika ini kasusnya, Anda dapat yakin bahwa cadangan kertas Anda dapat diandalkan. Untuk mempelajari lebih lanjut tentang cara melakukan tes pemulihan, saya menyarankan Anda untuk berkonsultasi dengan tutorial lain ini:

https://planb.network/tutorials/wallet/recovery-test

## Mengatur dompet Anda di Blockstream Green
Jika Anda ingin menyesuaikan portofolio Anda, klik pada tiga titik kecil di pojok kanan atas.
![GREEN](assets/fr/22.webp)
Opsi "*Rename*" memungkinkan Anda untuk menyesuaikan nama portofolio Anda, yang sangat berguna jika Anda mengelola beberapa portofolio dalam aplikasi yang sama.
![GREEN](assets/fr/23.webp)

Menu "*Unit*" memberi Anda opsi untuk mengubah unit dasar portofolio Anda. Misalnya, Anda dapat memilih untuk menampilkannya dalam satoshi daripada dalam bitcoin.

![GREEN](assets/fr/24.webp)

Menu "*Settings*" memberikan akses ke berbagai opsi dompet Bitcoin Anda.

![GREEN](assets/fr/25.webp)

Di sini, misalnya, Anda akan menemukan kunci publik terluas Anda dan *descriptor*-nya, berguna jika Anda berencana untuk mengatur dompet hanya-pantau dari dompet ini.

![GREEN](assets/fr/26.webp)

Anda juga dapat mengubah kode PIN dompet Anda dan mengaktifkan login biometrik.

![GREEN](assets/fr/27.webp)

## Menggunakan Blockstream Green

Sekarang dompet Bitcoin Anda telah disiapkan, Anda siap untuk menerima sats pertama Anda! Untuk melakukan ini, cukup klik pada tombol "*Receive*".

![GREEN](assets/fr/28.webp)

Green kemudian akan menampilkan alamat penerima kosong pertama dari dompet Anda. Anda dapat memindai kode QR yang terkait atau menyalin alamat langsung untuk mengirim bitcoin ke sana. Tipe alamat ini tidak menentukan jumlah yang harus dikirim oleh pengirim. Namun, Anda dapat menghasilkan alamat yang meminta jumlah tertentu, dengan mengklik pada tiga titik kecil di kanan atas, kemudian pada "*Request Amount*", dan memasukkan jumlah yang diinginkan.

Karena Anda menggunakan akun Segwit v0 (BIP84), alamat Anda akan dimulai dengan `bc1q...`. Dalam contoh saya, saya menggunakan dompet Testnet, jadi prefiksnya sedikit berbeda.

![GREEN](assets/fr/29.webp)

Ketika transaksi disiarkan di jaringan, itu akan muncul di dompet Anda.

![GREEN](assets/fr/30.webp)

Tunggu untuk mendapatkan cukup konfirmasi untuk menganggap transaksi sebagai final.

![GREEN](assets/fr/31.webp)

Dengan bitcoin di dompet Anda, sekarang Anda juga dapat mengirimkannya. Klik pada "*Send*".

![GREEN](assets/fr/32.webp)

Di halaman berikutnya, masukkan alamat penerima. Anda dapat memasukkannya secara manual atau memindai kode QR.

![GREEN](assets/fr/33.webp)

Pilih jumlah pembayaran.

![GREEN](assets/fr/34.webp)
Di bagian bawah layar, Anda dapat memilih tarif biaya untuk transaksi ini. Anda memiliki opsi untuk mengikuti rekomendasi aplikasi atau menyesuaikan biaya Anda. Semakin tinggi biaya dibandingkan dengan transaksi tertunda lainnya, semakin cepat transaksi Anda akan diproses. Untuk memahami pasar biaya, Anda dapat mengunjungi [Mempool.space](https://mempool.space/) di bagian "*Transaction Fees*".
![GREEN](assets/fr/35.webp)

Klik pada "*Next*" untuk mengakses layar ringkasan transaksi Anda. Verifikasi bahwa alamat, jumlah, dan biaya sudah benar.

![GREEN](assets/fr/36.webp)

Jika semuanya sesuai keinginan Anda, geser tombol hijau di bagian bawah layar ke kanan untuk menandatangani dan menyiarkan transaksi di jaringan Bitcoin.

![GREEN](assets/fr/37.webp)

Transaksi Anda sekarang akan muncul di dasbor dompet Bitcoin Anda menunggu konfirmasi.

![GREEN](assets/fr/38.webp)
*Tutorial ini berdasarkan [versi asli milik Bitstack](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) yang ditulis oleh Loïc Morel. Bitstack adalah neo-bank Bitcoin Prancis yang menawarkan kemungkinan untuk menabung dalam bitcoin, baik melalui DCA (Dollar Cost Averaging) atau melalui sistem pembulatan otomatis dari pengeluaran harian.*