---
name: Penanda Waktu Sertifikat dan Diploma Jaringan Plan ₿
description: Memahami bagaimana Jaringan Plan ₿ mengeluarkan bukti yang dapat diverifikasi untuk sertifikat dan diploma Anda
---

![cover](assets/cover.webp)

Jika Anda membaca ini, ada kemungkinan besar Anda menerima Sertifikat Bitcoin atau diploma kelulusan untuk salah satu kursus yang Anda ikuti di Jaringan Plan ₿, jadi selamat atas pencapaian ini!

Dalam tutorial ini, kita akan melihat bagaimana Jaringan Plan ₿ mengeluarkan bukti yang dapat diverifikasi untuk Sertifikat Bitcoin Anda atau Diploma Kelulusan Kursus apa pun. Kemudian di bagian kedua kita akan melihat cara memverifikasi keaslian bukti-bukti tersebut.

# Mekanisme bukti Jaringan Plan ₿

Di Jaringan Plan ₿, kami menawarkan Anda sertifikat dan diploma yang ditandatangani secara kriptografis oleh kami, dan diberi penanda waktu di Timechain (yaitu. Blockchain Bitcoin). Untuk mencapai ini, kami harus datang dengan mekanisme bukti yang bergantung pada 2 operasi kriptografis:

1. Tanda tangan GPG pada file teks yang merangkum pencapaian Anda
2. Penandaan waktu file yang ditandatangani melalui [opentimestamps](https://opentimestamps.org/).

Pada dasarnya operasi pertama memungkinkan Anda untuk memverifikasi siapa yang mengeluarkan sertifikat (atau diploma) sedangkan yang kedua memungkinkan Anda untuk memverifikasi kapan itu dikeluarkan.
Kami percaya bahwa mekanisme bukti sederhana ini memungkinkan kami untuk mengeluarkan sertifikat dan diploma dengan bukti yang tidak dapat disangkal yang siapa pun dapat memverifikasi sendiri.

![image](./assets/proof-mechanism.webp)

Perhatikan bahwa berkat mekanisme bukti ini, setiap upaya untuk mengubah bahkan detail terkecil dari sertifikat atau diploma Anda akan menciptakan hash sha256 yang sepenuhnya berbeda dari file yang ditandatangani, yang akan langsung mengungkapkan pemalsuan karena tanda tangan dan penandaan waktu tidak akan valid lagi. Selain itu, jika ada yang mencoba memalsukan beberapa sertifikat atau diploma atas nama Jaringan Plan ₿, verifikasi sederhana dari tanda tangan akan mengungkapkan penipuan.

## Bagaimana cara kerja tanda tangan GPG?

Tanda tangan GPG diperoleh dengan menggunakan perangkat lunak sumber terbuka bernama GNU Private Guard. Perangkat lunak ini memungkinkan siapa saja untuk dengan mudah membuat kunci privat, menandatangani dan memverifikasi tanda tangan dan juga mengenkripsi dan mendekripsi file. Untuk lingkup tutorial ini, ketahuilah bahwa Jaringan Plan ₿ menggunakan GPG untuk membuat kunci privat/publiknya dan untuk menandatangani Sertifikat Bitcoin atau Diploma Kelulusan Kursus apa pun.

Di sisi lain, jika seseorang ingin memverifikasi keaslian file yang ditandatangani mereka dapat menggunakan GPG untuk mengimpor kunci publik penerbit dan memverifikasi. Di bagian kedua dari tutorial ini kita akan melihat cara melakukannya dengan terminal.

Bagi mereka yang penasaran dan ingin mempelajari lebih lanjut tentang perangkat lunak fantastis ini, Anda dapat merujuk ke ["The GNU Privacy Handbook"](https://www.gnupg.org/gph/en/manual/x135.html)

## Bagaimana cara kerja penandaan waktu?

Siapa pun dapat menggunakan OpenTimestamps untuk memberi penanda waktu pada file, dan memperoleh bukti yang dapat diverifikasi dari keberadaan file. Dengan kata lain, ini tidak memberi Anda bukti kapan file itu dibuat tetapi bukti keberadaan tidak lebih dari suatu momen tertentu.
OpenTimestamps dapat menawarkan layanan ini secara gratis berkat cara yang sangat efisien untuk menyimpan bukti tersebut di Blockchain Bitcoin. Ini menggunakan hash sha256 dari file sebagai pengenal unik file Anda dan membangun pohon merkle dengan hash lain dari file yang diajukan oleh pengguna lain dan hanya mengaitkan hash dari struktur Pohon Merkle dalam Transaksi OpReturn.
Setelah transaksi ini berada dalam beberapa blok, siapa pun yang memiliki file awal dan file `.ots` yang terkait dengannya dapat memverifikasi keaslian penandaan waktu. Di bagian kedua tutorial ini, kita akan melihat cara memverifikasi Sertifikat Bitcoin Anda atau Diploma Penyelesaian Kursus dengan terminal dan dengan antarmuka grafis melalui situs web OpenTimestamps.

# Cara memverifikasi Sertifikat atau Diploma Jaringan Plan ₿

## Langkah 1. Unduh Sertifikat atau Diploma Anda

Masuk ke dashboard PBN pribadi Anda.

![image](./assets/login.webp)

Pergi ke halaman Kredensial dengan mengklik menu di sisi kiri, dan pilih sesi ujian Anda atau Diploma Penyelesaian Kursus Anda.

![image](./assets/credential.webp)

Unduh file zip.

![image](./assets/download.webp)

Ekstrak isi dengan klik kanan pada file `.zip` dan pilih "Extract". Anda akan menemukan tiga file berbeda di dalamnya:

- File teks yang ditandatangani (mis., certificate.txt)
- File Open timestamp (OTS) (mis., certificate.txt.ots)
- Sertifikat PDF (mis., certificate.pdf)

## Langkah 2: Memverifikasi Tanda Tangan File Teks

Pertama buka terminal di folder tempat file-file tersebut berada (klik kanan pada jendela folder dan klik "Open in Terminal"). Kemudian ikuti instruksi di bawah ini

1. Impor kunci PGP publik Jaringan Plan ₿ dengan perintah berikut:

```bash
curl -s https://raw.githubusercontent.com/Asi0Flammeus/pgp-public-keys/master/planb-network-pk.asc | gpg --import
```

Anda seharusnya melihat pesan seperti berikut jika Anda berhasil mengimpor Kunci PGP

```
gpg: key 8F12D0C63B1A606E: public key "PlanB Network (used for PBN platform) <admin@planb.network>" imported
gpg: Total number processed: 1
gpg:               imported: 1
```

CATATAN: jika Anda melihat bahwa 1 kunci diproses dan 0 diimpor, kemungkinan besar Anda sudah mengimpor kunci yang sama sebelumnya dan itu tidak masalah.

2. Verifikasi tanda tangan sertifikat atau diploma dengan perintah berikut:

```bash
gpg --verify certificate.txt
```

Perintah ini seharusnya menunjukkan detail tentang tanda tangan, termasuk:

- Siapa yang menandatanganinya (Jaringan Plan ₿)
- Kapan itu ditandatangani
- Apakah tanda tangan itu valid

Ini adalah contoh hasilnya:

```
gpg: Signature made lun 11 nov 2024, 00:39:04 CET
gpg:                using RSA key 5720CD577E7894C98DBD580E8F12D0C63B1A606E
gpg:                issuer "admin@planb.network"
gpg: Good signature from "PlanB Network (used for PBN platform) <admin@planb.network>" [unknown]
```

Jika Anda melihat pesan seperti "BAD signature", itu berarti file telah diubah.

## Langkah 3: Memverifikasi Open Timestamp

### Memverifikasi melalui Antarmuka Grafis

1. Kunjungi situs web OpenTimestamps: https://opentimestamps.org/
2. Klik pada tab "Stamp & Verify".
3. Seret dan lepaskan file OTS (mis., `certificate.txt.ots`) ke area yang ditentukan.
4. Seret dan lepaskan file yang diberi timestamp (mis. `certificate.txt`) ke area yang ditentukan.
5. Situs web akan secara otomatis memverifikasi open timestamp dan menampilkan hasilnya.
Jika Anda melihat pesan seperti berikut ini, timestamp Anda valid:
![cover](assets/opentimestamp_wegui_verified.webp)

### Metode CLI

CATATAN: prosedur ini **akan memerlukan node Bitcoin lokal yang berjalan**

1. Pasang klien OpenTimestamps dari repositori resmi: https://github.com/opentimestamps/opentimestamps-client dengan menjalankan perintah berikut:

```
pip install opentimestamps-client
```

2. Navigasi ke direktori yang berisi file sertifikat yang telah diekstrak.

3. Jalankan perintah berikut untuk memverifikasi timestamp terbuka:

```
ots verify certificate.txt.ots
```

Perintah ini akan:

- Memeriksa timestamp terhadap blockchain Bitcoin
- Menunjukkan kepada Anda kapan tepatnya file tersebut diberi timestamp
- Mengonfirmasi keaslian timestamp

### Hasil Akhir

Perhatikan bahwa verifikasi berhasil jika **kedua** pesan berikut ditampilkan:

1. Tanda tangan GPG dilaporkan sebagai **"Tanda tangan yang baik dari Plan ₿ Network"**
2. Verifikasi OpenTimestamps menunjukkan timestamp blok Bitcoin tertentu dan melaporkan **"Sukses! Blok Bitcoin [blockheight] membuktikan data ada per [timestamp]"**

Sekarang Anda tahu bagaimana Plan ₿ Network mengeluarkan bukti yang dapat diverifikasi untuk setiap Sertifikat Bitcoin dan Diploma Penyelesaian Kursus, Anda dapat dengan mudah memverifikasi integritasnya.