---
name: Blockstream Green - Hanya-Lihat
description: Mengatur dompet hanya-lihat
---
![cover](assets/cover.webp)

Dalam tutorial ini, Anda akan belajar cara mudah mengatur dompet hanya-lihat di ponsel menggunakan aplikasi Blockstream Green.

## Apa itu Dompet Hanya-Lihat?

Dompet hanya-lihat, atau "watch-only wallet," adalah jenis perangkat lunak yang dirancang untuk memungkinkan pengguna mengamati transaksi yang terkait dengan satu atau lebih kunci publik Bitcoin tertentu, tanpa memiliki akses ke kunci privat yang bersesuaian.

Jenis aplikasi ini hanya menyimpan data yang diperlukan untuk memantau dompet Bitcoin, termasuk melihat saldo dan riwayat transaksi, tetapi tidak memiliki akses ke kunci privat. Oleh karena itu, tidak mungkin untuk menghabiskan bitcoin yang ada di dompet pada aplikasi hanya-lihat.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Umumnya, hanya-lihat digunakan bersamaan dengan dompet perangkat keras. Yang terakhir ini memungkinkan penyimpanan aman kunci privat dompet pada perangkat yang tidak terhubung ke internet, yang memiliki permukaan serangan minimal, sehingga mengisolasi kunci privat dari lingkungan yang berpotensi rentan. Di sisi lain, aplikasi hanya-lihat secara eksklusif menyimpan kunci publik yang diperluas (`xpub`, `zpub`, dll.) dari dompet Bitcoin. Kunci induk ini tidak memungkinkan untuk menemukan kunci privat yang terkait dan, akibatnya, tidak memungkinkan pengeluaran bitcoin. Namun, ini memungkinkan untuk derivasi kunci publik anak dan alamat penerimaan. Dengan mengetahui alamat dompet yang diamankan oleh dompet perangkat keras, aplikasi hanya-lihat dapat melacak transaksi ini di jaringan Bitcoin, menawarkan pengguna kemampuan untuk memantau saldo mereka dan menghasilkan alamat penerimaan baru, tanpa harus menghubungkan dompet perangkat keras mereka setiap waktu.

Dalam tutorial ini, saya mengusulkan untuk menemukan salah satu solusi dompet hanya-lihat paling populer di ponsel: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Pengenalan Blockstream Green

Blockstream Green adalah perangkat lunak yang tersedia di ponsel dan komputer. Sebelumnya dikenal sebagai Green Address, dompet ini menjadi proyek Blockstream setelah akuisisinya pada tahun 2016.

Green adalah aplikasi yang sangat mudah digunakan, membuatnya sangat cocok untuk pemula. Ini menawarkan berbagai fitur, seperti pengelolaan dompet panas, dompet perangkat keras, serta dompet di sidechain Liquid.

Dalam tutorial ini, kita akan fokus hanya pada pembuatan dompet hanya-lihat. Untuk menjelajahi penggunaan lain dari Green, saya mengundang Anda untuk berkonsultasi dengan tutorial khusus kami yang lain:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Menginstal dan Mengatur Aplikasi Blockstream Green
Langkah pertama adalah tentu saja mengunduh aplikasi Green. Kunjungi toko aplikasi Anda:
- [Untuk Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Untuk Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Untuk pengguna Android, Anda juga memiliki opsi untuk menginstal aplikasi melalui file `.apk` [yang tersedia di GitHub Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Luncurkan aplikasi, kemudian centang kotak "*Saya menerima syarat...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Ketika Anda membuka Green untuk pertama kalinya, layar utama muncul tanpa dompet yang dikonfigurasi. Nanti, jika Anda membuat atau mengimpor dompet, mereka akan muncul di antarmuka ini. Sebelum melanjutkan untuk membuat dompet, saya menyarankan Anda untuk menyesuaikan pengaturan aplikasi sesuai dengan harapan Anda. Klik pada "*Pengaturan Aplikasi*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

Opsi "*Privasi Tingkat Lanjut*", yang hanya tersedia di Android, meningkatkan privasi dengan menonaktifkan tangkapan layar dan menyembunyikan pratinjau aplikasi. Ini juga secara otomatis mengunci akses ke aplikasi segera setelah ponsel Anda terkunci, membuat data Anda lebih sulit untuk terpapar.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Bagi mereka yang ingin meningkatkan privasi mereka, aplikasi menawarkan untuk merutekan lalu lintas Anda melalui Tor, jaringan yang mengenkripsi semua koneksi Anda dan membuat aktivitas Anda sulit untuk dilacak. Meskipun opsi ini mungkin sedikit memperlambat kinerja aplikasi, sangat disarankan untuk melindungi privasi Anda, terutama jika Anda tidak menggunakan node penuh Anda sendiri.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Untuk pengguna yang memiliki node penuh mereka sendiri, Green Wallet menawarkan kemungkinan untuk terhubung ke node tersebut melalui server Electrum, memastikan kontrol penuh atas informasi jaringan Bitcoin dan penyiaran transaksi.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Fitur alternatif lainnya adalah opsi "*Verifikasi SPV*", yang memungkinkan verifikasi langsung data tertentu blockchain, sehingga mengurangi kebutuhan untuk mempercayai node default Blockstream, meskipun metode ini tidak memberikan semua jaminan dari node penuh.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Setelah pengaturan ini disesuaikan sesuai dengan kebutuhan Anda, klik tombol "*Simpan*" dan mulai ulang aplikasi.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Membuat dompet hanya-pantau di Blockstream Green
Anda sekarang siap untuk membuat dompet hanya-pantau. Klik pada tombol "*Mulai*".
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Anda akan memiliki pilihan antara beberapa jenis dompet. Untuk tutorial ini, kami ingin membuat dompet hanya-pantau, jadi klik pada tombol yang sesuai.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Pilih opsi "*Tanda Tangan Tunggal*".

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Kemudian pilih "*Bitcoin*". Dari sisi saya, saya melakukan tutorial ini pada dompet testnet, tetapi prosedurnya tetap sama di mainnet.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Anda akan diminta untuk menyediakan kunci publik yang diperluas (`xpub`, `zpub`, dll.), atau deskriptor skrip output.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Anda perlu mengambil informasi ini dari dompet yang ingin Anda ikuti melalui dompet hanya-pantau Anda. Kunci publik yang diperluas tidak sensitif dalam hal keamanan, karena tidak memungkinkan akses ke kunci privat, tetapi sensitif untuk privasi Anda, karena mengungkapkan semua kunci publik Anda dan oleh karena itu semua transaksi Bitcoin Anda.

Bayangkan Anda menggunakan Sparrow Wallet untuk mengelola dompet Anda di dompet perangkat keras, Anda akan menemukan informasi ini di bagian "*Pengaturan*". Menemukan informasi ini akan tergantung pada perangkat lunak manajemen dompet yang Anda gunakan, tetapi umumnya ditemukan di pengaturan.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Salin kunci publik yang diperluas Anda dan masukkan ke dalam aplikasi Green, kemudian klik pada "*Sambungkan*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Anda kemudian akan dapat melihat saldo yang terkait dengan kunci ini serta riwayat transaksi.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Dengan mengklik "*Receive*", Anda dapat menghasilkan alamat penerimaan untuk menerima bitcoin di dompet keras Anda. Namun, saya menyarankan agar tidak menggunakan opsi ini tanpa terlebih dahulu memverifikasi di layar dompet keras bahwa itu memegang kunci privat yang terkait dengan alamat yang dihasilkan, sebelum menggunakannya untuk mengunci bitcoin. Ini adalah praktik baik yang harus diikuti.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

Opsi "*Sweep*" memungkinkan Anda untuk memasukkan kunci privat secara manual untuk menghabiskan dana langsung dari aplikasi Green Anda. Kecuali dalam kasus yang sangat spesifik, saya menyarankan untuk tidak menggunakan fungsi ini, karena memerlukan pengungkapan kunci privat Anda di telepon, yang jauh lebih rentan terhadap serangan siber dibandingkan dengan dompet keras Anda.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
Dan begitulah, Anda sekarang tahu cara mudah untuk mengatur dompet hanya-pantau di smartphone Anda! Ini adalah alat yang sangat berguna untuk memantau dompet di dompet keras tanpa harus menghubungkan dan membukanya setiap waktu.

Jika Anda merasa tutorial ini bermanfaat, saya akan sangat menghargai jika Anda bisa meninggalkan jempol ke atas di bawah ini. Jangan ragu untuk membagikan artikel ini di jaringan sosial Anda. Terima kasih banyak!

Saya juga merekomendasikan untuk memeriksa tutorial lengkap ini tentang aplikasi Blockstream Green untuk mengatur dompet panas:

https://planb.network/tutorials/wallet/blockstream-green