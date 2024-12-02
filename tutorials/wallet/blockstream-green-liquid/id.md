---
name: Blockstream Green - Liquid
description: Mengatur dompet di sidechain Liquid Network
---
![cover](assets/cover.webp)
Protokol Bitcoin memiliki batasan teknis yang disengaja yang membantu menjaga desentralisasi jaringan dan memastikan distribusi keamanan di antara semua pengguna. Namun, batasan ini terkadang dapat membuat frustrasi pengguna, terutama selama kemacetan yang disebabkan oleh volume transaksi yang tinggi secara simultan. Perdebatan mengenai skalabilitas Bitcoin telah lama memecah belah komunitas, khususnya selama Perang Ukuran Blok. Sejak episode tersebut, diakui secara luas dalam komunitas Bitcoin bahwa skalabilitas harus dijamin oleh solusi off-chain, pada sistem lapis kedua. Di antara solusi tersebut adalah sidechain, yang masih relatif tidak dikenal dan kurang digunakan dibandingkan dengan sistem lain seperti Lightning Network.

Sidechain adalah blockchain independen yang beroperasi secara paralel dengan blockchain Bitcoin utama. Ini menggunakan bitcoin sebagai unit akun melalui mekanisme yang disebut "*two-way peg*". Sistem ini memungkinkan penguncian bitcoin di rantai utama untuk mereplikasi nilai mereka di sidechain, di mana mereka beredar sebagai token yang didukung oleh bitcoin asli. Token ini biasanya mempertahankan paritas nilai dengan bitcoin yang dikunci di rantai utama, dan proses ini dapat dibalik untuk memulihkan dana di Bitcoin.

Tujuan dari sidechain adalah untuk menawarkan fungsionalitas tambahan atau perbaikan teknis, seperti transaksi yang lebih cepat, biaya yang lebih rendah, atau dukungan untuk kontrak pintar. Inovasi ini tidak selalu dapat diimplementasikan langsung di blockchain Bitcoin tanpa mengorbankan desentralisasinya atau keamanan. Sidechain dengan demikian memungkinkan untuk menguji dan menjelajahi solusi baru sambil menjaga integritas Bitcoin. Namun, protokol ini sering memerlukan kompromi, terutama dalam hal desentralisasi dan keamanan, tergantung pada model tata kelola dan mekanisme konsensus yang dipilih.

Hari ini, sidechain yang paling dikenal mungkin adalah Liquid. Dalam tutorial ini, saya akan pertama-tama memperkenalkan Anda kepada apa itu Liquid, dan kemudian memandu Anda tentang cara mulai menggunakannya dengan mudah melalui aplikasi Blockstream Green, untuk memanfaatkan manfaatnya.

![LIQUID GREEN](assets/fr/01.webp)

## Apa itu Liquid Network?

Liquid adalah sidechain federasi yang dibangun di atas Bitcoin, dikembangkan oleh Blockstream, bertujuan untuk meningkatkan kecepatan, privasi, dan fungsionalitas transaksi. Ini menggunakan mekanisme penguncian bilateral yang didirikan pada federasi untuk mengunci bitcoin di rantai utama dan menciptakan, sebagai gantinya, Liquid-bitcoin (L-BTC), token yang beredar di Liquid sambil tetap didukung oleh bitcoin asli.

![LIQUID GREEN](assets/fr/02.webp)
Jaringan Liquid didasarkan pada federasi peserta, yang terdiri dari entitas yang diakui dari ekosistem Bitcoin, yang memvalidasi blok dan mengelola penguncian bilateral. Selain L-BTC, Liquid juga memungkinkan penerbitan aset digital lainnya, seperti stablecoin atau cryptocurrency lainnya.
![LIQUID GREEN](assets/fr/03.webp)

## Pengenalan Blockstream Green

Blockstream Green adalah dompet perangkat lunak yang tersedia di ponsel dan desktop. Sebelumnya dikenal sebagai *Green Address*, dompet ini menjadi proyek Blockstream setelah akuisisinya pada tahun 2016.

Green adalah aplikasi yang sangat mudah digunakan, menjadikannya menarik bagi pemula. Ini menawarkan semua fitur esensial dari dompet Bitcoin yang baik, termasuk RBF (*Replace-by-Fee*), opsi untuk terhubung melalui Tor, kemampuan untuk menghubungkan node Anda sendiri, opsi SPV (*Simple Payment Verification*), pelabelan, dan kontrol koin.

Blockstream Green juga mendukung jaringan Liquid, dan itulah yang akan kita jelajahi dalam tutorial ini. Jika Anda ingin menggunakan Green untuk aplikasi lain, saya juga merekomendasikan untuk berkonsultasi dengan tutorial lain ini:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Menginstal dan Mengatur Aplikasi Blockstream Green

Langkah pertama tentu saja adalah mengunduh aplikasi Green. Kunjungi toko aplikasi Anda:
- [Untuk Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Untuk Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Untuk pengguna Android, Anda juga memiliki opsi untuk menginstal aplikasi melalui file `.apk` [yang tersedia di GitHub Blockstream](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Luncurkan aplikasi, kemudian centang kotak "*I accept the terms...*".

![LIQUID GREEN](assets/fr/06.webp)

Ketika Anda membuka Green untuk pertama kalinya, layar utama muncul tanpa dompet yang dikonfigurasi. Nanti, jika Anda membuat atau mengimpor dompet, mereka akan muncul di antarmuka ini. Sebelum melanjutkan untuk membuat dompet, saya menyarankan Anda untuk menyesuaikan pengaturan aplikasi sesuai dengan harapan Anda. Klik pada "*Application Settings*".

![LIQUID GREEN](assets/fr/07.webp)

Opsi "*Enhanced Privacy*", yang hanya tersedia di Android, meningkatkan privasi dengan menonaktifkan tangkapan layar dan menyembunyikan pratinjau aplikasi. Ini juga secara otomatis mengunci akses ke aplikasi segera setelah ponsel Anda terkunci, membuat data Anda lebih sulit untuk terpapar.
![LIQUID GREEN](assets/fr/08.webp)
Bagi mereka yang ingin meningkatkan privasi mereka, aplikasi menawarkan opsi untuk merutekan lalu lintas Anda melalui Tor, jaringan yang mengenkripsi semua koneksi Anda dan membuat aktivitas Anda sulit untuk dilacak. Meskipun opsi ini mungkin sedikit memperlambat kinerja aplikasi, sangat disarankan untuk melindungi privasi Anda, terutama jika Anda tidak menggunakan node penuh Anda sendiri.

![LIQUID GREEN](assets/fr/09.webp)

Untuk pengguna yang memiliki node penuh mereka sendiri, Green Wallet memungkinkan Anda untuk terhubung ke node tersebut melalui server Electrum, memastikan kontrol penuh atas informasi jaringan Bitcoin dan penyiaran transaksi. Namun, fitur ini relevan untuk dompet Bitcoin tradisional, jadi Anda tidak memerlukannya jika Anda menggunakan Liquid.

![LIQUID GREEN](assets/fr/10.webp)

Fitur alternatif lainnya adalah opsi "*SPV Verification*", yang memungkinkan verifikasi langsung data tertentu blockchain, sehingga mengurangi kebutuhan untuk mempercayai node default Blockstream, meskipun metode ini tidak memberikan semua jaminan dari node penuh. Sekali lagi, ini hanya akan menyangkut dompet Bitcoin onchain Anda, dan bukan Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Setelah pengaturan ini disesuaikan sesuai dengan kebutuhan Anda, klik tombol "*Save*" dan mulai ulang aplikasi.

![LIQUID GREEN](assets/fr/12.webp)

## Membuat Dompet Liquid di Blockstream Green

Anda sekarang siap untuk membuat dompet Liquid. Klik tombol "*Get Started*".

![LIQUID GREEN](assets/fr/13.webp)

Anda memiliki pilihan antara membuat dompet perangkat lunak secara lokal atau mengelola dompet dingin melalui dompet perangkat keras. Untuk tutorial ini, kami akan fokus pada pembuatan dompet panas di Liquid, jadi Anda perlu memilih opsi "*On This Device*". Anda juga dapat menggunakan dompet perangkat keras yang kompatibel, seperti Blockstream Jade, untuk mengamankan dompet Liquid Anda.

![LIQUID GREEN](assets/fr/14.webp)
Anda kemudian dapat memilih untuk memulihkan dompet Bitcoin yang sudah ada atau membuat yang baru. Untuk tujuan tutorial ini, kita akan membuat dompet baru. Namun, jika Anda perlu meregenerasi dompet Liquid yang sudah ada dari frasa mnemoniknya, misalnya karena kehilangan dompet perangkat keras Anda, Anda perlu memilih opsi kedua.
![LIQUID GREEN](assets/fr/15.webp)

Anda kemudian memiliki pilihan antara frasa mnemonik 12 kata atau 24 kata. Frasa ini akan memungkinkan Anda untuk memulihkan akses ke dompet Anda dari perangkat lunak apa pun yang kompatibel dalam kasus terjadi masalah dengan ponsel Anda. Saat ini, memilih frasa 24 kata tidak menawarkan lebih banyak keamanan daripada frasa 12 kata. Oleh karena itu, saya merekomendasikan memilih frasa mnemonik **12 kata**.
Green kemudian akan memberikan Anda frasa mnemonik Anda. Sebelum melanjutkan, pastikan Anda tidak sedang diamati. Klik pada "*Tampilkan frasa pemulihan*" untuk menampilkannya di layar.
![LIQUID GREEN](assets/fr/16.webp)

**Frasa mnemonik ini memberikan akses penuh dan tidak terbatas ke semua bitcoin Anda.** Siapa pun yang memiliki frasa ini dapat mencuri dana Anda, bahkan tanpa akses fisik ke ponsel Anda.

Ini memungkinkan Anda untuk memulihkan akses ke bitcoin Anda dalam kasus kehilangan, pencurian, atau kerusakan pada ponsel Anda. Oleh karena itu, sangat penting untuk menyimpannya dengan hati-hati **pada media fisik (bukan digital)** dan menyimpannya di lokasi yang aman. Anda dapat menuliskannya di selembar kertas, atau untuk lebih aman, jika dompet ini signifikan, saya merekomendasikan mengukirnya pada media stainless steel untuk melindungi dari risiko kebakaran, banjir, atau runtuhnya bangunan (untuk dompet panas yang dimaksudkan untuk mengamankan jumlah bitcoin yang kecil, cadangan kertas sederhana mungkin sudah cukup).

*Jelas, Anda seharusnya tidak pernah membagikan kata-kata ini di internet, berbeda dengan apa yang saya lakukan dalam tutorial ini. Dompet contoh ini hanya akan digunakan pada Liquid Testnet dan akan dihapus di akhir tutorial.*

![LIQUID GREEN](assets/fr/17.webp)

Setelah dengan benar mencatat frasa mnemonik Anda pada media fisik, klik pada "*Lanjutkan*". Dompet Green kemudian akan meminta Anda untuk mengonfirmasi beberapa kata dari frasa Anda untuk memverifikasi bahwa Anda telah mencatatnya dengan benar. Isi bagian yang kosong dengan kata-kata yang hilang.

![LIQUID GREEN](assets/fr/18.webp)

Pilih kode PIN untuk perangkat Anda, yang akan digunakan untuk membuka kunci dompet Green Anda. Ini adalah perlindungan terhadap akses fisik yang tidak sah. Kode PIN ini tidak berperan dalam derivasi kunci kriptografis dompet Anda. Dengan demikian, bahkan tanpa akses ke kode PIN ini, kepemilikan frasa mnemonik 12 atau 24 kata Anda akan memungkinkan Anda untuk mendapatkan kembali akses ke bitcoin Anda.

Disarankan untuk memilih kode PIN 6 digit seacak mungkin. Juga, pastikan untuk menyimpan kode ini agar Anda tidak lupa, jika tidak, Anda akan dipaksa untuk memulihkan dompet Anda dari frasa mnemonik. Nanti, Anda dapat menambahkan opsi penguncian biometrik untuk menghindari memasukkan PIN setiap kali Anda menggunakannya. Secara umum, biometrik jauh kurang aman daripada PIN itu sendiri. Oleh karena itu, secara default, saya menyarankan untuk tidak mengatur opsi penguncian ini.

![LIQUID GREEN](assets/fr/19.webp)

Masukkan PIN Anda untuk kedua kalinya untuk mengonfirmasinya.

![LIQUID GREEN](assets/fr/20.webp)
Tunggu hingga dompet Anda dibuat, kemudian klik tombol "*Buat akun*".
![LIQUID GREEN](assets/fr/21.webp)
Di kotak "*Assets*", pilih "*Liquid Bitcoin*". Anda kemudian memiliki pilihan antara dompet tanda tangan tunggal standar, yang akan kita gunakan dalam tutorial ini, atau dompet yang dilindungi oleh otentikasi dua faktor (2FA).
![LIQUID GREEN](assets/fr/22.webp)

Dan begitulah, dompet Liquid Anda telah berhasil dibuat menggunakan aplikasi Green!

![LIQUID GREEN](assets/fr/23.webp)

Sebelum menerima bitcoin pertama Anda di dompet Liquid Anda, **saya sangat menyarankan Anda untuk melakukan tes pemulihan kosong**. Catat informasi referensi, seperti xpub Anda atau alamat penerimaan pertama, kemudian hapus dompet Anda di aplikasi Green sementara masih kosong. Selanjutnya, coba pulihkan dompet Anda di Green menggunakan cadangan kertas Anda. Periksa bahwa informasi saksi yang dihasilkan setelah pemulihan cocok dengan yang Anda catat awalnya. Jika iya, Anda dapat yakin bahwa cadangan kertas Anda dapat diandalkan. Untuk mempelajari lebih lanjut tentang cara melakukan tes pemulihan, saya menyarankan Anda untuk berkonsultasi dengan tutorial lain ini:

https://planb.network/tutorials/wallet/recovery-test

## Menyiapkan Dompet Liquid Anda

Jika Anda ingin menyesuaikan dompet Anda, klik pada tiga titik kecil di pojok kanan atas.

![LIQUID GREEN](assets/fr/24.webp)

Opsi "*Rename*" memungkinkan Anda untuk menyesuaikan nama dompet Anda, yang sangat berguna jika Anda mengelola beberapa dompet dalam aplikasi yang sama.

![LIQUID GREEN](assets/fr/25.webp)

Menu "*Unit*" memberi Anda opsi untuk mengubah unit dasar dompet Anda. Misalnya, Anda dapat memilih untuk menampilkannya dalam satoshi daripada dalam bitcoin.

![LIQUID GREEN](assets/fr/26.webp)

Menu "*Settings*" memberikan akses ke berbagai opsi dompet Bitcoin Anda.

![LIQUID GREEN](assets/fr/27.webp)

Di sini Anda akan menemukan, misalnya, *descriptor* Anda yang bisa berguna jika Anda berencana untuk menyiapkan dompet hanya-lihat dari dompet Liquid ini.

![LIQUID GREEN](assets/fr/28.webp)

Anda juga dapat mengubah kode PIN dompet Anda dan mengaktifkan login biometrik.

![LIQUID GREEN](assets/fr/29.webp)

## Menggunakan Dompet Liquid Anda

Sekarang dompet Liquid Anda telah disiapkan, Anda siap untuk menerima L-sats pertama Anda!
Jika Anda belum memiliki L-BTC, ada beberapa opsi yang tersedia untuk Anda. Yang pertama adalah memintanya dikirim langsung kepada Anda. Jika seseorang ingin membayar Anda dalam bitcoin di Liquid, cukup berikan mereka alamat penerimaan. Solusi lain adalah menukar bitcoin onchain Anda atau yang di jaringan Lightning untuk L-BTC. Untuk melakukan ini, Anda dapat menggunakan [jembatan seperti Boltz](https://boltz.exchange/). Cukup masukkan alamat Liquid Anda di situs, kemudian lakukan pembayaran baik melalui jaringan Lightning atau onchain.
![LIQUID GREEN](assets/fr/30.webp)

Untuk menghasilkan alamat Liquid, klik pada tombol "*Receive*".

![LIQUID GREEN](assets/fr/31.webp)

Green kemudian akan menampilkan alamat penerimaan kosong pertama dompet Anda. Anda dapat memindai kode QR yang terkait atau menyalin alamat langsung untuk mengirim L-BTC ke sana.

![LIQUID GREEN](assets/fr/32.webp)

Ketika transaksi disiarkan di jaringan, itu akan muncul di dompet Anda.

![LIQUID GREEN](assets/fr/33.webp)

Tunggu untuk mendapatkan cukup konfirmasi untuk menganggap transaksi sebagai final. Di Liquid, konfirmasi seharusnya cepat, karena blok dipublikasikan setiap menit.

![LIQUID GREEN](assets/fr/34.webp)
Dengan L-sats di dompet Liquid Anda, Anda sekarang juga dapat mengirimkannya. Klik pada "*Kirim*".
![LIQUID GREEN](assets/fr/35.webp)

Di halaman berikutnya, masukkan alamat Liquid penerima. Anda dapat memasukkannya secara manual atau memindai kode QR mereka.

![LIQUID GREEN](assets/fr/36.webp)

Pilih jumlah pembayaran.

![LIQUID GREEN](assets/fr/37.webp)

Klik pada "*Berikutnya*" untuk mengakses layar ringkasan transaksi Anda. Periksa apakah alamat, jumlah, dan biaya sudah benar.

![LIQUID GREEN](assets/fr/38.webp)

Jika semuanya terlihat baik bagi Anda, geser tombol hijau di bagian bawah layar ke kanan untuk menandatangani dan menyiarkan transaksi di jaringan Bitcoin.

![LIQUID GREEN](assets/fr/39.webp)

Transaksi Anda sekarang akan muncul di dasbor dompet Bitcoin Anda menunggu konfirmasi.

![LIQUID GREEN](assets/fr/40.webp)

Dan begitulah, Anda sekarang tahu cara mudah menggunakan sidechain Liquid dengan aplikasi Blockstream Green!

Jika Anda merasa tutorial ini bermanfaat, saya akan sangat menghargai jempol ke atas di bawah ini. Jangan ragu untuk membagikan artikel ini di jaringan sosial Anda. Terima kasih banyak!

Saya juga merekomendasikan untuk menemukan tutorial lengkap lainnya tentang aplikasi seluler Blockstream Green untuk mengatur dompet panas Bitcoin onchain:

https://planb.network/tutorials/wallet/blockstream-green