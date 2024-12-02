---
name: Aqua
description: Bitcoin, Lightning, dan Liquid dalam satu dompet
---
![cover](assets/cover.webp)

Aqua adalah aplikasi seluler yang memungkinkan pembuatan hot wallet untuk Bitcoin dan Liquid dengan mudah, serta menawarkan kemungkinan menggunakan Lightning tanpa kompleksitas mengelola node, berkat swap terintegrasi. Aplikasi ini juga mendukung pengelolaan stablecoin USDT di berbagai jaringan.

Dikembangkan oleh perusahaan JAN3 di bawah kepemimpinan Samson Mow, aplikasi Aqua awalnya dirancang khusus untuk memenuhi kebutuhan pengguna di Amerika Latin, meskipun cocok untuk pengguna di seluruh dunia. Ini sangat menarik bagi pemula dan mereka yang menggunakan Bitcoin setiap hari untuk pembayaran mereka.

Dalam tutorial ini, kita akan menjelajahi cara menggunakan banyak fitur Aqua. Tapi sebelum itu, mari kita luangkan waktu untuk memahami apa itu sidechain pada Bitcoin dan bagaimana Liquid bekerja, yang akan memungkinkan kita untuk sepenuhnya memahami kepentingan Aqua.

![AQUA](assets/fr/01.webp)

## Apa itu sidechain?

Protokol Bitcoin memiliki batasan teknis yang disengaja yang membantu menjaga desentralisasi jaringan dan memastikan distribusi keamanan di antara semua pengguna. Namun, batasan ini terkadang dapat membuat frustrasi pengguna, terutama selama kemacetan yang disebabkan oleh volume transaksi simultan yang tinggi. Perdebatan tentang skalabilitas Bitcoin telah lama memecah belah komunitas, terutama selama Perang Ukuran Blok. Sejak episode itu, secara luas diakui dalam komunitas Bitcoin bahwa skalabilitas harus dijamin oleh solusi off-chain, pada sistem lapis kedua. Di antara solusi ini adalah sidechain, yang masih relatif tidak dikenal dan kurang digunakan dibandingkan dengan sistem lain seperti Lightning Network.

Sidechain adalah blockchain independen yang beroperasi sejajar dengan blockchain Bitcoin utama. Ini menggunakan bitcoin sebagai unit akun melalui mekanisme yang disebut "*two-way peg*". Sistem ini memungkinkan untuk mengunci bitcoin di rantai utama untuk mereplikasi nilai mereka di sidechain, di mana mereka beredar sebagai token yang didukung oleh bitcoin asli. Token ini biasanya mempertahankan paritas nilai dengan bitcoin yang terkunci di rantai utama, dan proses ini dapat dibalik untuk mengambil kembali dana di Bitcoin.
Tujuan dari sidechain adalah untuk menawarkan fungsionalitas tambahan atau perbaikan teknis, seperti transaksi yang lebih cepat, biaya yang lebih rendah, atau dukungan untuk kontrak pintar. Inovasi ini tidak selalu dapat diimplementasikan langsung di blockchain Bitcoin tanpa mengorbankan desentralisasinya atau keamanan. Sidechain dengan demikian memungkinkan untuk menguji dan menjelajahi solusi baru sambil menjaga integritas Bitcoin. Namun, protokol ini sering memerlukan kompromi, terutama dalam hal desentralisasi dan keamanan, tergantung pada model tata kelola dan mekanisme konsensus yang dipilih.
## Apa itu Liquid?

Liquid adalah sidechain terfederasi yang dibangun di atas Bitcoin, dikembangkan oleh Blockstream, bertujuan untuk meningkatkan kecepatan, privasi, dan fungsionalitas transaksi. Ini menggunakan mekanisme pengikatan bilateral yang didirikan pada federasi untuk mengunci bitcoin di rantai utama dan menciptakan Liquid-bitcoin (L-BTC), token yang beredar di Liquid sambil tetap didukung oleh bitcoin asli.

![AQUA](assets/fr/02.webp)

Jaringan Liquid didasarkan pada federasi peserta, yang terdiri dari entitas yang diakui dari ekosistem Bitcoin, yang memvalidasi blok dan mengelola pengikatan bilateral. Selain L-BTC, Liquid juga memungkinkan penerbitan aset digital lainnya, seperti stablecoin USDT atau cryptocurrency lainnya.

![AQUA](assets/fr/03.webp)

## Menginstal Aplikasi Aqua

Langkah pertama adalah tentu saja mengunduh aplikasi Aqua. Kunjungi toko aplikasi Anda:
- [Untuk Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Untuk Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
Untuk pengguna Android, Anda juga memiliki opsi untuk menginstal aplikasi melalui file `.apk` [yang tersedia di GitHub mereka](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Luncurkan aplikasi, kemudian centang kotak "*Saya telah membaca dan menyetujui Syarat Layanan & Kebijakan Privasi*".

![AQUA](assets/fr/06.webp)

## Membuat Dompet Anda di Aqua

Klik tombol "*Buat Dompet*".

![AQUA](assets/fr/07.webp)

Dan begitulah, dompet Anda sudah dibuat!

![AQUA](assets/fr/08.webp)

Namun sebelum apapun, karena ini adalah dompet self-custody, sangat penting untuk membuat cadangan fisik dari frasa mnemonik Anda. **Frasa mnemonik ini memberikan akses lengkap dan tidak terbatas ke semua bitcoin Anda**. Siapapun yang memiliki frasa ini dapat mencuri dana Anda, bahkan tanpa akses fisik ke ponsel Anda.
Ini memungkinkan Anda untuk mengembalikan akses ke bitcoin Anda dalam kasus kehilangan, pencurian, atau kerusakan pada ponsel Anda. Oleh karena itu, sangat penting untuk mencadangkannya dengan hati-hati pada media fisik (bukan digital) dan menyimpannya di lokasi yang aman. Anda dapat menuliskannya pada selembar kertas, atau untuk keamanan lebih, jika dompet ini signifikan, saya merekomendasikan untuk mengukirnya pada media stainless steel untuk melindungi dari risiko kebakaran, banjir, atau runtuhnya bangunan (untuk dompet panas yang dimaksudkan untuk mengamankan jumlah bitcoin yang kecil, cadangan kertas sederhana mungkin sudah cukup).
Untuk melakukan ini, klik pada menu pengaturan.

![AQUA](assets/fr/09.webp)

Kemudian klik pada "*Lihat Frasa Benih*". Buat cadangan fisik dari frasa 12 kata ini.

![AQUA](assets/fr/10.webp)

Di menu pengaturan yang sama, Anda juga dapat mengubah bahasa aplikasi serta mata uang fiat yang digunakan.

![AQUA](assets/fr/11.webp)

Sebelum menerima bitcoin pertama Anda di dompet, **saya sangat menyarankan Anda untuk melakukan tes pemulihan dry-run**. Catat informasi referensi, seperti xpub Anda atau alamat penerimaan pertama, kemudian hapus dompet Anda di aplikasi Aqua sementara masih kosong. Selanjutnya, coba pulihkan dompet Anda di Aqua menggunakan cadangan kertas Anda. Periksa bahwa informasi saksi yang dihasilkan setelah pemulihan cocok dengan yang Anda catat awalnya. Jika ini kasusnya, Anda dapat yakin bahwa cadangan kertas Anda dapat diandalkan. Untuk mempelajari lebih lanjut tentang cara melakukan tes pemulihan, saya menyarankan Anda untuk berkonsultasi dengan tutorial lain ini:

https://planb.network/tutorials/wallet/recovery-test

## Menerima bitcoin di Aqua

Sekarang dompet Anda sudah siap, Anda siap untuk menerima sats pertama Anda! Cukup klik pada tombol "*Terima*" di menu "*Dompet*".

![AQUA](assets/fr/12.webp)

Anda dapat memilih untuk menerima bitcoin secara onchain, di Liquid, atau melalui Lightning.

![AQUA](assets/fr/13.webp)

Untuk transaksi onchain, Aqua akan menghasilkan alamat penerimaan spesifik di mana Anda dapat menerima sats Anda.

![AQUA](assets/fr/14.webp)

Demikian pula, dengan memilih Liquid, Aqua akan menyediakan Anda dengan alamat Liquid.

![AQUA](assets/fr/15.webp)

Jika Anda lebih suka menerima dana melalui Lightning, Anda pertama-tama perlu menentukan jumlah yang diinginkan.

![AQUA](assets/fr/16.webp)

Kemudian, klik pada "*Generate Invoice*".

![AQUA](assets/fr/17.webp)
Aqua akan membuat faktur untuk menerima dana dari dompet Lightning. Penting untuk dicatat bahwa, tidak seperti opsi onchain dan Liquid, dana yang diterima melalui Lightning akan secara otomatis dikonversi ke L-BTC di Liquid menggunakan alat Boltz, karena Aqua bukan sebuah node Lightning. Proses ini memungkinkan Anda untuk menerima dan mengirim dana melalui Lightning, tetapi tanpa pernah menyimpan bitcoin Anda di Lightning. ![AQUA](assets/fr/18.webp)

Secara pribadi, saya akan mulai dengan mengirim bitcoin melalui Lightning ke Aqua. Setelah transaksi selesai dengan faktur yang disediakan, konfirmasi diterima.

![AQUA](assets/fr/19.webp)

Untuk mengikuti perkembangan pertukaran, kembali ke halaman utama dompet Anda dan klik pada akun "*L2 Bitcoin*", yang mencantumkan transaksi Lightning (melalui swap) dan Liquid.

![AQUA](assets/fr/20.webp)

Di sini, Anda dapat melihat transaksi Anda serta saldo Anda dalam L-BTC.

![AQUA](assets/fr/21.webp)

## Menukar bitcoin dengan Aqua

Sekarang Anda memiliki aset di dompet Aqua Anda, Anda memiliki opsi untuk menukarnya langsung dari aplikasi, baik untuk mentransfernya ke blockchain Bitcoin utama atau ke Liquid. Anda juga dapat mengonversi bitcoin Anda menjadi stablecoin USDT (atau lainnya). Untuk melakukan ini, akses menu "*Marketplace*".

![AQUA](assets/fr/22.webp)

Klik pada "*Swaps*".

![AQUA](assets/fr/23.webp)

Di kotak "*Transfer from*", pilih aset yang ingin Anda tukarkan. Saat ini, saya hanya memiliki L-BTC, jadi itulah yang saya pilih.

![AQUA](assets/fr/24.webp)

Di kotak "*Transfer to*", pilih aset target dari pertukaran Anda. Untuk bagian saya, saya memilih USDT di jaringan Liquid.

![AQUA](assets/fr/25.webp)

Masukkan jumlah yang ingin Anda konversi.

![AQUA](assets/fr/26.webp)

Konfirmasi dengan mengklik "*Continue*".

![AQUA](assets/fr/27.webp)

Pastikan pengaturan pertukaran sesuai dengan keinginan Anda, kemudian konfirmasi dengan menggeser tombol "*Swap*" di bagian bawah layar.

![AQUA](assets/fr/28.webp)

Pertukaran Anda sekarang dikonfirmasi.

![AQUA](assets/fr/29.webp)

Jika kita kembali ke dompet kita, kita dapat melihat bahwa sekarang kita memiliki USDT di Liquid.

![AQUA](assets/fr/30.webp)

## Mengirim bitcoin dengan Aqua

Sekarang Anda memiliki bitcoin di dompet Aqua Anda, Anda memiliki opsi untuk mengirimkannya. Klik pada tombol "*Send*".

![AQUA](assets/fr/31.webp)

Pilih aset yang ingin Anda kirim atau pilih jaringan untuk melakukan transaksi. Untuk bagian saya, saya akan mengirim bitcoin melalui Lightning.

![AQUA](assets/fr/32.webp)
Selanjutnya, masukkan informasi yang diperlukan untuk mengirim pembayaran: untuk Bitcoin onchain atau Liquid, Anda perlu memasukkan alamat penerima; untuk Lightning, faktur diperlukan. Anda dapat menempelkan informasi ini langsung ke dalam bidang yang ditentukan atau menggunakan ikon kode QR untuk membuka kamera Anda dan memindai alamat atau faktur. Kemudian klik pada "*Continue*".
![AQUA](assets/fr/33.webp)

Klik pada "*Continue*" lagi jika semua informasi tampak benar.

![AQUA](assets/fr/34.webp)
Aqua kemudian menampilkan ringkasan transaksi kepada Anda. Pastikan semua informasi sudah benar, terutama alamat tujuan, biaya, dan jumlahnya. Untuk mengonfirmasi transaksi, geser tombol "*Slide to send*" yang terletak di bagian bawah layar.
![AQUA](assets/fr/35.webp)

Kemudian, konfirmasi pengiriman akan diberikan kepada Anda.

![AQUA](assets/fr/36.webp)

Dan begitulah, Anda sekarang tahu cara menggunakan aplikasi Aqua untuk menerima dan menghabiskan dana di Bitcoin, Lightning, dan Liquid, semuanya dari satu antarmuka.

Jika Anda merasa tutorial ini bermanfaat, saya akan sangat menghargai jika Anda bisa memberikan jempol ke atas di bawah ini. Jangan ragu untuk membagikan artikel ini di jaringan sosial Anda. Terima kasih banyak!

Saya juga menyarankan Anda untuk melihat tutorial lengkap lainnya tentang aplikasi seluler Blockstream Green, yang merupakan solusi menarik lainnya untuk mengatur dompet Liquid Anda:

https://planb.network/tutorials/wallet/blockstream-green-liquid