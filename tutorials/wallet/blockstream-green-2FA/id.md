---
name: Blockstream Green - 2FA
description: Mengatur multisig 2/2 pada Green Wallet
---
![cover](assets/cover.webp)

Dompet perangkat lunak adalah aplikasi yang diinstal pada komputer, smartphone, atau perangkat lain yang terhubung ke Internet, memungkinkan pengelolaan dan keamanan kunci dompet Bitcoin seseorang. Berbeda dengan dompet perangkat keras, yang mengisolasi kunci privat, dompet "panas" ini beroperasi dalam lingkungan yang berpotensi terpapar pada serangan siber, meningkatkan risiko peretasan dan pencurian.

Dompet perangkat lunak sebaiknya digunakan untuk mengelola jumlah bitcoin yang wajar, terutama untuk transaksi harian. Ini juga bisa menjadi opsi menarik bagi orang dengan portofolio Bitcoin terbatas, bagi siapa investasi dalam dompet perangkat keras mungkin terasa tidak sebanding. Namun, paparan konstan mereka ke Internet membuatnya kurang aman untuk menyimpan tabungan jangka panjang atau dana signifikan. Untuk ini, lebih disukai untuk memilih solusi yang lebih aman, seperti dompet perangkat keras.

Dalam tutorial ini, saya akan menunjukkan cara meningkatkan keamanan dompet panas dengan menggunakan opsi "2FA" pada Blockstream Green.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Pengenalan ke Blockstream Green

Blockstream Green adalah dompet perangkat lunak yang tersedia di mobile dan desktop. Sebelumnya dikenal sebagai *Green Address*, dompet ini menjadi proyek Blockstream setelah akuisisinya pada tahun 2016.

Green adalah aplikasi yang sangat mudah digunakan, menjadikannya menarik bagi pemula. Ini menawarkan semua fitur esensial dari dompet Bitcoin yang baik, termasuk RBF (*Replace-by-Fee*), opsi untuk terhubung melalui Tor, kemampuan untuk menghubungkan node sendiri, opsi SPV (*Simple Payment Verification*), pelabelan, dan kontrol koin.

Blockstream Green juga mendukung jaringan Liquid, sidechain Bitcoin yang dikembangkan oleh Blockstream untuk melakukan transaksi cepat dan rahasia di luar blockchain utama. Dalam tutorial ini, kami fokus eksklusif pada Bitcoin, tetapi saya juga telah membuat tutorial lain untuk belajar cara menggunakan Liquid di Green:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## Opsi multisig 2/2 (2FA)

Di Green, Anda tentu saja dapat membuat dompet panas "singlesig" klasik. Tetapi Anda juga memiliki opsi "2FA multisig", yang memungkinkan Anda untuk meningkatkan keamanan dompet panas Anda tanpa terlalu mempersulit pengelolaannya sehari-hari.
Anda akan mengatur dompet multisig 2/2, yang berarti setiap transaksi akan memerlukan tanda tangan dari dua kunci. Kunci pertama, yang berasal dari frasa mnemonik 12 atau 24 kata Anda, diamankan secara lokal dengan kode PIN di ponsel Anda. Anda memiliki kontrol penuh atas kunci ini. Kunci kedua dipegang oleh server Blockstream, dan penggunaannya untuk menandatangani memerlukan otentikasi, yang dapat dicapai melalui kode yang diterima melalui email, SMS, panggilan telepon, atau, seperti yang akan kita lihat dalam tutorial ini, melalui aplikasi otentikasi (Authy, Google Authenticator, dll.).

Untuk memastikan otonomi Anda dalam hal kegagalan Blockstream (misalnya, jika perusahaan bangkrut atau server yang memegang kunci kedua hancur), mekanisme timelock diterapkan pada multisig Anda. Mekanisme ini mengubah multisig 2/2 menjadi 1/2 multisig setelah sekitar satu tahun (atau tepatnya 51,840 blok, tetapi nilai ini dapat diubah), setelah itu dompet Anda hanya akan memerlukan kunci lokal Anda untuk menghabiskan bitcoin. Jadi, jika Anda kehilangan akses ke server Blockstream atau ke otentikasi 2FA, Anda hanya perlu menunggu hingga satu tahun untuk dapat menggunakan bitcoin Anda secara bebas dengan aplikasi Anda, tanpa bergantung pada Blockstream.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
Metode ini secara signifikan meningkatkan keamanan dompet panas Anda, sambil membiarkan Anda mengontrol bitcoin Anda dan memfasilitasi penggunaannya sehari-hari. Namun, metode ini memerlukan pembaruan timelock secara berkala untuk mempertahankan keamanan 2FA. Hitungan mundur 360 hari, di mana dana Anda dilindungi oleh 2FA, dimulai segera setelah Anda menerima bitcoin. Jika, 360 hari setelah menerima mereka, Anda belum melakukan transaksi yang menghabiskan dana tersebut, bitcoin Anda hanya akan dilindungi oleh kunci lokal Anda, tanpa 2FA.

Keterbatasan ini membuat opsi 2FA lebih cocok untuk dompet pengeluaran, di mana transaksi reguler secara otomatis memperbarui timelock. Untuk dompet tabungan jangka panjang, ini bisa menjadi masalah, karena Anda perlu memikirkan untuk melakukan transaksi sapu ke diri sendiri setiap tahun sebelum timelock berakhir.

Kekurangan lain dari metode keamanan ini adalah Anda perlu menggunakan pola skrip minoritas. Ini berarti, dari sudut pandang privasi, hal-hal menjadi rumit: sangat sedikit orang yang menggunakan jenis skrip yang sama dengan Anda, memungkinkan pengamat eksternal untuk lebih mudah mengidentifikasi jejak dompet Anda. Selain itu, skrip ini akan menghasilkan biaya transaksi yang lebih tinggi karena ukurannya yang lebih besar.
Jika Anda lebih memilih untuk tidak menggunakan opsi 2FA dan hanya ingin mengatur dompet "singlesig" di Green, saya mengundang Anda untuk melihat tutorial lain ini:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Menginstal dan Mengatur Perangkat Lunak Blockstream Green

Langkah pertama adalah tentu saja mengunduh aplikasi Green. Kunjungi toko aplikasi Anda:
- [Untuk Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Untuk Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

Untuk pengguna Android, Anda juga memiliki opsi untuk menginstal aplikasi melalui file `.apk` [yang tersedia di GitHub Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Luncurkan aplikasi, kemudian centang kotak "*Saya menerima syarat...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Ketika Anda membuka Green untuk pertama kalinya, layar utama muncul tanpa dompet yang dikonfigurasi. Nanti, jika Anda membuat atau mengimpor dompet, mereka akan muncul di antarmuka ini. Sebelum melanjutkan untuk membuat dompet, saya menyarankan Anda untuk menyesuaikan pengaturan aplikasi sesuai dengan harapan Anda. Klik pada "*Pengaturan Aplikasi*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

Opsi "*Privasi Ditingkatkan*", yang hanya tersedia di Android, meningkatkan privasi dengan menonaktifkan tangkapan layar dan menyembunyikan pratinjau aplikasi. Ini juga secara otomatis mengunci akses ke aplikasi segera setelah ponsel Anda terkunci, membuat data Anda lebih sulit untuk terpapar.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

Bagi mereka yang ingin meningkatkan privasi mereka, aplikasi menawarkan untuk merutekan lalu lintas Anda melalui Tor, jaringan yang mengenkripsi semua koneksi Anda dan membuat aktivitas Anda sulit untuk dilacak. Meskipun opsi ini mungkin sedikit memperlambat kinerja aplikasi, sangat disarankan untuk melindungi privasi Anda, terutama jika Anda tidak menggunakan node penuh Anda sendiri.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

Untuk pengguna yang memiliki node penuh mereka sendiri, Green Wallet menawarkan kemungkinan untuk terhubung ke node tersebut melalui server Electrum, memastikan kontrol penuh atas informasi jaringan Bitcoin dan penyiaran transaksi.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
Fitur alternatif lainnya adalah opsi "*SPV Verification*", yang memungkinkan verifikasi langsung terhadap data blockchain tertentu, sehingga mengurangi kebutuhan untuk mempercayai node default Blockstream, meskipun metode ini tidak memberikan semua jaminan dari sebuah full node.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Setelah pengaturan ini disesuaikan sesuai dengan kebutuhan Anda, klik tombol "*Save*" dan restart aplikasi.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Membuat Dompet Bitcoin di Blockstream Green

Anda sekarang siap untuk membuat dompet Bitcoin. Klik tombol "*Get Started*".

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Anda memiliki pilihan antara membuat dompet perangkat lunak secara lokal atau mengelola dompet dingin melalui dompet perangkat keras. Untuk tutorial ini, kita akan fokus pada pembuatan hot wallet, sehingga Anda perlu memilih opsi "*On This Device*".

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Selanjutnya, Anda dapat memilih untuk memulihkan dompet Bitcoin yang sudah ada atau membuat yang baru. Untuk keperluan tutorial ini, kita akan membuat dompet baru. Namun, jika Anda perlu meregenerasi dompet Bitcoin yang sudah ada dari frasa mnemoniknya, misalnya, karena kehilangan ponsel lama Anda, Anda perlu memilih opsi kedua.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Kemudian Anda memiliki pilihan antara frasa mnemonik 12 kata atau 24 kata. Frasa ini akan memungkinkan Anda untuk memulihkan akses ke dompet Anda dari perangkat lunak yang kompatibel dalam kasus masalah dengan ponsel Anda. Saat ini, memilih frasa 24 kata tidak menawarkan lebih banyak keamanan daripada frasa 12 kata. Oleh karena itu, saya merekomendasikan memilih frasa mnemonik **12 kata**.

Green kemudian akan memberikan Anda frasa mnemonik Anda. Sebelum melanjutkan, pastikan Anda tidak sedang diamati. Klik pada "*Show recovery phrase*" untuk menampilkannya di layar.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**Frasa mnemonik ini memberikan akses lengkap dan tidak terbatas ke semua bitcoin Anda**. Siapa pun yang memiliki frasa ini dapat mencuri dana Anda, bahkan tanpa akses fisik ke ponsel Anda (dalam kondisi timelock yang telah berakhir atau 2FA dalam kasus dompet 2/2 di Green).

Ini memungkinkan Anda untuk memulihkan akses ke kunci lokal Anda dalam kasus kehilangan, pencurian, atau kerusakan pada ponsel Anda. Oleh karena itu, sangat penting untuk menyimpannya dengan hati-hati **pada media fisik (bukan digital)** dan menyimpannya di lokasi yang aman. Anda dapat menuliskannya di selembar kertas, atau untuk lebih amannya, jika dompet ini penting, saya merekomendasikan untuk mengukirnya pada media stainless steel untuk melindungi dari risiko kebakaran, banjir, atau runtuhnya bangunan (untuk hot wallet yang dimaksudkan untuk mengamankan jumlah bitcoin yang kecil, cadangan kertas sederhana mungkin sudah cukup).
*Jelas, Anda seharusnya tidak pernah membagikan kata-kata ini di internet, tidak seperti yang saya lakukan dalam tutorial ini. Dompet contoh ini hanya akan digunakan di Testnet dan akan dihapus di akhir tutorial.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Setelah dengan benar mencatat frasa mnemonik Anda pada media fisik, klik pada "*Continue*". Green Wallet kemudian akan meminta Anda untuk mengonfirmasi beberapa kata dari frasa Anda untuk memverifikasi bahwa Anda telah mencatatnya dengan benar. Isi bagian yang kosong dengan kata-kata yang hilang.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Pilih kode PIN untuk perangkat Anda, yang akan digunakan untuk membuka kunci dompet Green Anda. Oleh karena itu, ini merupakan perlindungan terhadap akses fisik yang tidak sah. Kode PIN ini tidak berperan dalam derivasi kunci kriptografis dompet Anda. Dengan demikian, bahkan tanpa akses ke kode PIN ini, kepemilikan frasa mnemonik 12 atau 24 kata Anda akan memungkinkan Anda untuk mendapatkan kembali akses ke kunci lokal Anda.

Disarankan untuk memilih kode PIN 6 digit seacak mungkin. Juga, pastikan untuk menyimpan kode ini agar Anda tidak lupa, jika tidak, Anda akan dipaksa untuk memulihkan dompet Anda dari frasa mnemonik. Anda kemudian dapat menambahkan opsi penguncian biometrik untuk menghindari memasukkan PIN setiap kali. Secara umum, biometrik jauh lebih tidak aman daripada PIN itu sendiri. Oleh karena itu, secara default, saya menyarankan untuk tidak mengatur opsi pembukaan kunci ini.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Masukkan PIN Anda sekali lagi untuk mengonfirmasinya.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Tunggu sambil dompet Anda dibuat, lalu klik tombol "*Buat akun*".

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Anda kemudian memiliki pilihan antara dompet tanda tangan tunggal standar atau dompet yang dilindungi oleh otentikasi dua faktor (2FA). Dalam tutorial ini, kita akan memilih opsi kedua.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

Dan begitulah, dompet multisig Bitcoin Anda telah berhasil dibuat menggunakan aplikasi Green!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Mengatur 2FA

Klik pada akun Anda.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Klik tombol hijau "*Tingkatkan keamanan akun Anda dengan menambahkan 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Anda kemudian akan memiliki opsi untuk memilih metode otentikasi untuk mengakses kunci kedua dari 2/2 multisig Anda. Untuk tutorial ini, kita akan menggunakan aplikasi otentikasi. Jika Anda tidak familiar dengan jenis aplikasi ini, saya sarankan untuk berkonsultasi dengan tutorial kami tentang Authy:
https://planb.network/tutorials/others/authy

Pilih "*Aplikasi Otentikator*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green kemudian akan menampilkan kode QR dan kunci pemulihan. Kunci ini memungkinkan Anda untuk mengembalikan akses ke 2FA Anda jika Anda kehilangan aplikasi Authy Anda. Disarankan untuk membuat cadangan aman dari kunci ini, meskipun Anda selalu dapat mendapatkan kembali akses ke bitcoin Anda setelah berakhirnya timelock, seperti yang dijelaskan sebelumnya.

Di aplikasi otentikasi Anda, tambahkan kode baru, lalu pindai kode QR yang disediakan oleh Green.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Jelas, Anda seharusnya tidak pernah membagikan kunci dan kode QR ini di internet, berbeda dengan apa yang saya lakukan dalam tutorial ini. Dompet contoh ini hanya akan digunakan pada Testnet dan akan dihapus di akhir tutorial.*

Klik tombol "*Lanjutkan*".

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Masukkan kode 6 digit dinamis yang ada di aplikasi otentikasi Anda.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

Otentikasi dua faktor sekarang diaktifkan.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Dengan menjelajahi menu ini, Anda juga dapat menyesuaikan durasi dari timelock. Hitungan mundur ini dimulai setelah menerima bitcoin, dan setelah timelock berakhir, dana Anda hanya dapat dibelanjakan dengan kunci lokal Anda, tanpa memerlukan 2FA. Durasi default diatur menjadi 12 bulan, tetapi untuk dompet tabungan, memilih 15 bulan mungkin bijaksana untuk meminimalkan frekuensi perpanjangan timelock. Sebaliknya, untuk dompet pengeluaran, timelock selama 6 bulan mungkin lebih disukai, karena akan sering diperbarui dengan transaksi harian Anda, dan timelock yang lebih pendek mengurangi waktu tunggu dalam kasus masalah dengan 2FA. Terserah Anda untuk menentukan durasi timelock yang paling cocok untuk Anda.
![GREEN 2FA MULTISIG](assets/fr/30.webp)

Anda sekarang dapat keluar dari menu ini. Dompet multisig Anda siap!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Mengatur Dompet Anda di Blockstream Green

Jika Anda ingin menyesuaikan dompet Anda, klik pada tiga titik kecil di pojok kanan atas.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
Opsi "*Rename*" memungkinkan Anda untuk menyesuaikan nama dompet Anda, yang sangat berguna jika Anda mengelola beberapa dompet dalam aplikasi yang sama.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

Menu "*Unit*" memberi Anda opsi untuk mengubah unit dasar dompet Anda. Misalnya, Anda dapat memilih untuk menampilkannya dalam satoshi daripada dalam bitcoin.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

Menu "*Settings*" memberikan akses ke berbagai opsi dompet Bitcoin Anda.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Di sini, misalnya, Anda akan menemukan kunci publik terluas Anda dan *descriptor*-nya, berguna jika Anda berencana untuk mengatur dompet hanya-pantau dari dompet ini.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

Anda juga dapat mengubah kode PIN dompet Anda dan mengaktifkan login biometrik.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Menggunakan Blockstream Green

Sekarang dompet Bitcoin Anda telah diatur, Anda siap untuk menerima sats pertama Anda! Untuk melakukan ini, cukup klik pada tombol "*Receive*".

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green kemudian akan menampilkan alamat penerima kosong pertama dari dompet Anda. Anda dapat memindai kode QR yang terkait atau menyalin alamat langsung untuk mengirim bitcoin ke sana. Tipe alamat ini tidak menentukan jumlah yang harus dikirim oleh pembayar. Namun, Anda dapat menghasilkan alamat yang meminta jumlah tertentu, dengan mengklik pada tiga titik kecil di pojok kanan atas, kemudian pada "*Request Amount*", dan memasukkan jumlah yang diinginkan.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Ketika transaksi disiarkan di jaringan, itu akan muncul di dompet Anda.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Tunggu untuk mendapatkan cukup konfirmasi untuk menganggap transaksi sebagai final.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

Dengan bitcoin di dompet Anda, Anda sekarang juga dapat mengirimkannya. Klik pada "*Send*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

Di halaman berikutnya, masukkan alamat penerima. Anda dapat memasukkannya secara manual atau memindai kode QR.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Pilih jumlah pembayaran.
![GREEN 2FA MULTISIG](assets/fr/44.webp)Di bagian bawah layar, Anda dapat memilih tarif biaya untuk transaksi ini. Anda memiliki opsi untuk mengikuti rekomendasi aplikasi atau menyesuaikan biaya Anda sendiri. Semakin tinggi biaya dibandingkan dengan transaksi yang tertunda lainnya, semakin cepat transaksi Anda akan diproses. Untuk memahami pasar biaya, Anda dapat mengunjungi [Mempool.space](https://mempool.space/) di bagian "*Biaya Transaksi*".
![GREEN 2FA MULTISIG](assets/fr/45.webp)

Klik pada "*Berikutnya*" untuk mengakses layar ringkasan transaksi Anda. Verifikasi bahwa alamat, jumlah, dan biaya sudah benar.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Jika semuanya terlihat baik bagi Anda, geser tombol hijau di bagian bawah layar ke kanan untuk menandatangani dan menyiarkan transaksi di jaringan Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

Ini adalah saatnya Anda perlu memasukkan kode otentikasi Anda untuk membuka kunci kedua dari multisig yang dipegang oleh Blockstream. Masukkan kode 6 digit yang ditampilkan di aplikasi otentikasi Anda.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Transaksi Anda sekarang akan muncul di dasbor dompet Bitcoin Anda menunggu konfirmasi.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

Dan begitulah, Anda sekarang tahu bagaimana cara mudah menyiapkan dompet multisig 2/2 menggunakan opsi 2FA Blockstream Green!

Jika Anda merasa tutorial ini bermanfaat, saya akan sangat menghargai jika Anda bisa meninggalkan jempol hijau di bawah. Jangan ragu untuk membagikan artikel ini di jaringan sosial Anda. Terima kasih banyak!

Saya juga merekomendasikan untuk memeriksa tutorial lengkap lainnya tentang aplikasi seluler Blockstream Green untuk menyiapkan dompet Liquid:

https://planb.network/tutorials/wallet/blockstream-green-liquid