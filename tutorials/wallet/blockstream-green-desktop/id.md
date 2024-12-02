---
name: Blockstream Green - Desktop
description: Menggunakan perangkat lunak Green Wallet di komputer
---
![cover](assets/cover.webp)

Dalam tutorial ini, kita akan menjelajahi cara menggunakan perangkat lunak Blockstream Green di komputer untuk mengelola dompet aman pada hardware wallet. Saat menggunakan hardware wallet, sangat penting untuk menggunakan perangkat lunak di komputer Anda untuk mengelola dompet ini. Perangkat lunak manajemen ini tidak memiliki akses ke kunci privat; perangkat lunak ini hanya digunakan untuk memeriksa saldo dompet Anda, menghasilkan alamat penerimaan, dan membangun serta menyiarkan transaksi yang akan ditandatangani oleh hardware wallet. Green merupakan salah satu dari banyak solusi yang tersedia untuk mengelola Bitcoin hardware wallet Anda.

Pada tahun 2024, Blockstream Green hanya kompatibel dengan perangkat Ledger Nano S (versi lama), Ledger Nano X, Trezor One, Trezor T, dan Blockstream Jade.

## Pengenalan Blockstream Green

Blockstream Green adalah perangkat lunak yang tersedia baik di mobile maupun desktop. Sebelumnya dikenal sebagai Green Address, dompet ini menjadi proyek Blockstream setelah diakuisisi pada tahun 2016.

Green adalah aplikasi yang sangat ramah pengguna, membuatnya sangat cocok untuk pemula. Ini menawarkan berbagai fitur, seperti pengelolaan hot wallets, hardware wallets, serta dompet di sidechain Liquid. Anda juga dapat menggunakannya untuk mengatur dompet hanya-lihat.

![GREEN-DESKTOP](assets/fr/01.webp)

Dalam tutorial ini, kita akan fokus hanya pada penggunaan perangkat lunak di komputer. Untuk menjelajahi penggunaan Green lainnya, saya mengundang Anda untuk melihat tutorial khusus kami lainnya:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Menginstal dan Mengatur Perangkat Lunak Blockstream Green

Mulailah dengan menginstal perangkat lunak Blockstream Green di komputer Anda. Kunjungi [situs web resmi](https://blockstream.com/green/) dan klik tombol "*Download Now*". Kemudian ikuti proses instalasi sesuai dengan sistem operasi Anda.

![GREEN-DESKTOP](assets/fr/02.webp)

Luncurkan aplikasi, kemudian centang kotak "*I accept the terms...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Ketika Anda membuka Green untuk pertama kalinya, layar beranda muncul tanpa dompet yang dikonfigurasi. Nanti, jika Anda membuat atau mengimpor dompet, mereka akan muncul di antarmuka ini. Sebelum melanjutkan ke pembuatan dompet, saya menyarankan Anda untuk menyesuaikan pengaturan aplikasi sesuai dengan harapan Anda. Klik pada ikon pengaturan di kiri bawah.

![GREEN-DESKTOP](assets/fr/04.webp)

Di menu "*General*", Anda dapat mengubah bahasa perangkat lunak dan mengaktifkan fitur eksperimental jika Anda mau.

![GREEN-DESKTOP](assets/fr/05.webp)
Di menu "*Network*", Anda dapat mengaktifkan koneksi melalui Tor, jaringan yang mengenkripsi semua koneksi Anda dan membuat aktivitas Anda sulit dilacak. Meskipun opsi ini mungkin sedikit memperlambat kinerja aplikasi, sangat disarankan untuk melindungi privasi Anda, terutama jika Anda tidak menggunakan full node Anda sendiri.
![GREEN-DESKTOP](assets/fr/06.webp)

Untuk pengguna yang memiliki full node mereka sendiri, Green menawarkan kemungkinan untuk terhubung ke node tersebut melalui server Electrum, memastikan kontrol penuh atas informasi jaringan Bitcoin dan penyiaran transaksi. Untuk melakukan ini, klik pada menu "*Custom servers and validation*", kemudian masukkan informasi server Electrum Anda.

![GREEN-DESKTOP](assets/fr/07.webp)
Fitur alternatif lainnya adalah opsi "*Verifikasi SPV*" yang memungkinkan verifikasi langsung terhadap data blockchain tertentu, sehingga mengurangi kebutuhan untuk mempercayai node default Blockstream, meskipun metode ini tidak memberikan semua jaminan dari sebuah full node. Opsi ini juga dapat ditemukan di menu "*Server dan validasi kustom*".
![GREEN-DESKTOP](assets/fr/08.webp)

Setelah pengaturan ini disesuaikan sesuai dengan kebutuhan Anda, Anda dapat keluar dari antarmuka ini.

## Mengimpor Dompet Bitcoin ke Blockstream Green

Anda sekarang siap untuk mengimpor dompet Bitcoin Anda. Klik tombol "**Mulai**".

![GREEN-DESKTOP](assets/fr/09.webp)

Anda memiliki pilihan antara membuat dompet perangkat lunak lokal atau mengelola dompet dingin melalui dompet perangkat keras. Untuk tutorial ini, kita akan fokus pada pengelolaan dompet perangkat keras, sehingga Anda perlu memilih opsi "*Di Dompet Perangkat Keras*".

Opsi "*Hanya Lihat*" di sisi lain, memungkinkan Anda untuk mengimpor kunci publik yang diperluas (`xpub`) untuk melihat transaksi dompet tanpa dapat menghabiskan dana yang terkait.

![GREEN-DESKTOP](assets/fr/10.webp)

Jika Anda menggunakan Jade, klik pada tombol yang sesuai. Jika tidak, pilih "*Sambungkan Perangkat Keras yang Berbeda*". Dalam kasus saya, saya menggunakan Ledger Nano S. Untuk pengguna Ledger, pastikan untuk menginstal aplikasi "*Bitcoin Legacy*" pada dompet perangkat keras Anda, karena Green hanya mendukung versi ini.

![GREEN-DESKTOP](assets/fr/11.webp)

Sambungkan dompet perangkat keras Anda ke komputer dan pilih di Green.

![GREEN-DESKTOP](assets/fr/12.webp)

Tunggu sementara Green mengimpor informasi dari dompet Anda, setelah itu Anda akan dapat mengaksesnya.

![GREEN-DESKTOP](assets/fr/13.webp)

Pada titik ini, dua skenario mungkin terjadi. Jika Anda sudah pernah menggunakan dompet perangkat keras Anda sebelumnya, Anda seharusnya melihat akun Anda muncul di perangkat lunak. Tetapi jika, seperti saya, Anda baru saja menginisialisasi dompet perangkat keras Anda dengan menghasilkan frasa mnemonik tanpa menggunakannya, Anda perlu membuat akun. Klik pada "*Buat Akun*".
![GREEN-DESKTOP](assets/fr/14.webp)
Pilih "*Standar*" jika Anda ingin menggunakan dompet klasik.

![GREEN-DESKTOP](assets/fr/15.webp)

Anda sekarang memiliki akses ke akun Anda.

![GREEN-DESKTOP](assets/fr/16.webp)

## Menggunakan dompet perangkat keras dengan Blockstream Green

Sekarang dompet Bitcoin Anda telah disiapkan, Anda siap untuk menerima sats pertama Anda! Untuk melakukan ini, cukup klik tombol "*Terima*".

![GREEN-DESKTOP](assets/fr/17.webp)

Klik tombol "*Salin alamat*" untuk menyalin alamat, atau pindai kode QR-nya.

![GREEN-DESKTOP](assets/fr/18.webp)

Setelah transaksi disiarkan di jaringan, itu akan muncul di dompet Anda. Tunggu untuk mendapatkan cukup konfirmasi untuk menganggap transaksi sebagai tidak dapat diubah.

![GREEN-DESKTOP](assets/fr/19.webp)

Dengan bitcoin di dompet Anda, Anda sekarang dapat mengirimkannya. Klik tombol "*Kirim*".

![GREEN-DESKTOP](assets/fr/20.webp)

Di halaman berikutnya, masukkan alamat penerima. Anda dapat memasukkannya secara manual atau memindai kode QR dengan webcam Anda.

![GREEN-DESKTOP](assets/fr/21.webp)

Pilih jumlah pembayaran.

![GREEN-DESKTOP](assets/fr/22.webp)
Di bagian bawah layar, Anda dapat memilih tarif biaya untuk transaksi ini. Anda memiliki opsi untuk mengikuti rekomendasi aplikasi atau menyesuaikan biaya Anda sendiri. Semakin tinggi biaya dibandingkan dengan transaksi tertunda lainnya, semakin cepat transaksi Anda akan diproses. Untuk mengetahui pasar biaya, Anda dapat mengunjungi [Mempool.space](https://mempool.space/) di bagian "*Biaya Transaksi*".
![GREEN-DESKTOP](assets/fr/23.webp)

Jika Anda ingin secara spesifik memilih UTXO mana yang akan digunakan dalam transaksi Anda, klik tombol "*Pemilihan koin manual*".

![GREEN-DESKTOP](assets/fr/24.webp)

Periksa pengaturan transaksi Anda dan, jika semuanya sesuai dengan yang Anda harapkan, klik pada "*Berikutnya*".

![GREEN-DESKTOP](assets/fr/25.webp)

Verifikasi sekali lagi bahwa alamat, jumlah, dan biaya sudah benar, kemudian klik pada "*Konfirmasi transaksi*".

![GREEN-DESKTOP](assets/fr/26.webp)

Pastikan semua parameter transaksi sudah benar di layar dompet keras Anda, kemudian tandatangani transaksi menggunakan itu.

![GREEN-DESKTOP](assets/fr/27.webp)

Setelah transaksi ditandatangani dari dompet keras, Green secara otomatis menyiarkannya di jaringan Bitcoin. Transaksi Anda kemudian akan muncul di dasbor dompet Bitcoin Anda, menunggu konfirmasi.

![GREEN-DESKTOP](assets/fr/28.webp)

Dan begitulah, Anda sekarang tahu cara mudah untuk mengatur perangkat lunak Blockstream Green untuk mengelola dompet Bitcoin Anda pada dompet keras.
Jika Anda merasa tutorial ini bermanfaat, saya akan sangat menghargai jika Anda bisa memberikan jempol ke atas di bawah ini. Jangan ragu untuk membagikan artikel ini di jaringan sosial Anda. Terima kasih banyak!
Saya juga merekomendasikan untuk memeriksa tutorial lengkap ini tentang aplikasi seluler Blockstream Green untuk mengatur dompet panas:

https://planb.network/tutorials/wallet/blockstream-green