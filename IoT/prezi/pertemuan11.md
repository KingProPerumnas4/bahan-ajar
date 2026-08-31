# Prezi Pertemuan 11 — Penyimpanan Data, Riwayat, dan Visualisasi Tren

## Kanvas utama

Saat Prezi dibuka dan sebelum zoom pertama, yang terlihat adalah satu garis tren panjang yang membentang dari kiri ke kanan di tengah kanvas, dengan judul pertemuan di atasnya, satu titik tunggal yang menyala di ujung kirinya, dan sebuah bagian kosong menjelang ujung kanan sebelum garis itu berlanjut kembali. Di bawah garis tersebut terpasang jalur sempit berisi baris-baris teks bercap waktu seperti isi sebuah berkas CSV, sehingga sejak awal terlihat bahwa gambar di atas berasal dari baris-baris di bawah. Enam kawasan topik ditata mengikuti garis itu: kawasan pembuka berada di sekitar titik tunggal di ujung kiri, kawasan kedua tepat di tempat titik tunggal itu berubah menjadi deretan titik, kawasan ketiga menempel pada jalur baris data di bawah, kawasan keempat mengelilingi kedua sumbu grafik, kawasan kelima berada di sekitar bagian kosong, dan kawasan terakhir menutup di ujung kanan. Jalur zoom karena itu bercerita seperti pertumbuhan ingatan sebuah sistem: satu angka yang tadinya selalu tertimpa berubah menjadi satu baris bercap waktu, baris-baris itu menjadi berkas, berkas itu menjadi garis di layar, lalu garis itu dibaca dengan jujur termasuk bagian yang kosong.

- Kawasan 1: Pembuka dan Sasaran — pertanyaan pemancing dan capaian pembelajaran pertemuan ini.
- Kawasan 2: Dari Sesaat ke Riwayat — batas data terkini, data berseri waktu, dan kedudukan cap waktu.
- Kawasan 3: Ukuran dan Tempat Penyimpanan — laju data, lama penyimpanan, dua pilihan penyimpanan, dan kolom yang dicatat.
- Kawasan 4: Ruang Grafik — rentang sumbu, bagian kosong, dan empat lapis pembacaan.
- Kawasan 5: Ruang Praktik — contoh berkas riwayat, demo pencatatan, dan kesalahan yang sering terjadi.
- Kawasan 6: Penutup dan Tugas — ringkasan sekaligus checkpoint, lalu tugas latihan beserta penilaiannya.

## Alur zoom

1. Pembuka: Sistem yang Belum Punya Ingatan
2. Capaian Pembelajaran Pertemuan Ini
3. Mengapa Satu Angka Tidak Cukup
4. Riwayat Adalah Nilai Bercap Waktu
5. Interval Menentukan Ukuran Riwayat
6. Dua Pilihan Penyimpanan Sederhana
7. Lima Kolom Riwayat yang Berguna
8. Rentang Sumbu Mengubah Kesan
9. Bagian Kosong dan Empat Lapis
10. Satu Baris CSV dan Penyusunnya
11. Demo Grafik Tren dan Pencatatan
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 11
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Pembuka: Sistem yang Belum Punya Ingatan

Kawasan: Pembuka dan Sasaran

Teks di layar:
- Pertemuan 11: Penyimpanan Data, Riwayat, Visualisasi Tren
- Dashboard Anda hanya tahu nilai sekarang
- Pertanyaan: apakah 29,4 wajar untuk jam ini?
- Dan apa yang hilang bila hanya nilai terakhir?

Yang Anda ucapkan:
> Sampai Pertemuan 10 tentang dashboard dasar, sistem Anda hidup sepenuhnya di masa kini: begitu angka baru datang, angka lama hilang tanpa bekas.
> Pertemuan ini menambahkan ingatan pada sistem itu, yaitu pencatatan data, penyimpanan riwayat, dan grafik tren yang menggambarkan perubahannya.
> Simpan dua pertanyaan ini sampai akhir presentasi: apakah nilai 29,4 wajar untuk jam ini, dan apa yang hilang bila sistem Anda hanya menyimpan nilai terakhir.
> Keduanya tidak dapat dijawab oleh satu angka, karena jawabannya memerlukan pembanding, dan pembandingnya adalah nilai yang sama pada waktu yang berbeda.
> Yang perlu Anda siapkan hanya dashboard hasil Pertemuan 10, satu sumber data yang masih mengirim nilai secara berkala, dan browser; tidak ada perangkat keras baru dan tidak ada pustaka baru pada program device.
> Kita mulai dari sasaran pertemuan ini supaya Anda tahu apa yang harus dapat Anda lakukan sendiri setelahnya.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Pembuka dan Sasaran

Teks di layar:
- Membedakan data terkini dan data berseri waktu
- Menghubungkan interval, jumlah baris, dan ukuran penyimpanan
- Menambahkan grafik tren pada dashboard yang ada
- Mencatat data ke berkas CSV bercap waktu
- Mengirim nilai ke saluran cloud memakai kunci tulis

Yang Anda ucapkan:
> Capaian pemahaman pertemuan ini ada empat, yaitu perbedaan data terkini yang selalu tertimpa dengan data berseri waktu yang disimpan bersama cap waktunya, hubungan antara interval pengiriman dengan jumlah baris dan ukuran penyimpanan, alasan memilih penyimpanan berkas lokal atau saluran pada layanan cloud, serta cara membaca grafik tren termasuk pengaruh satuan, rentang sumbu, dan data yang hilang.
> Sisi keterampilannya juga empat: menambahkan grafik tren untuk satu parameter pada dashboard yang sudah ada, mencatat data ke berkas CSV lewat node file lengkap dengan cap waktu, mengirim nilai ke sebuah saluran pada layanan cloud memakai kunci tulis, dan menentukan kolom yang perlu dicatat agar riwayatnya berguna.
> Empat hal itu saling menyambung sepanjang pertemuan: pencatatan data, penyimpanan riwayat, grafik tren, dan pemilihan penyimpanan sederhana.
> Perhatikan butir keterampilan yang terakhir, sebab menentukan kolom yang dicatat adalah keputusan yang paling sering dilewati padahal paling menentukan apakah riwayat Anda berguna.
> Bentuk dan kekerapan data yang keluar dari device sudah Anda tentukan pada Pertemuan 9 tentang penyusunan payload dan pengaturan waktu pengiriman, jadi yang benar-benar baru di sini adalah ingatannya.
> Sebelum menyentuh cara menyimpan, kita perjelas dahulu mengapa satu angka terkini tidak pernah cukup.

### Frame 3 — Mengapa Satu Angka Tidak Cukup

Kawasan: Dari Sesaat ke Riwayat

Teks di layar:
- Dashboard menjawab satu hal: berapa nilainya sekarang
- Pertanyaan pemantauan butuh pembanding pada waktu berbeda
- Arah perubahan: bertindak sebelum batas terlampaui
- Kecepatan perubahan, pola berulang, dan bagian kosong
- Analogi: saldo rekening melawan mutasi rekening

Yang Anda ucapkan:
> Dashboard dari Pertemuan 10 tentang dashboard dasar menjawab satu pertanyaan dengan baik, yaitu berapa nilainya sekarang.
> Persoalannya, pertanyaan yang benar-benar berguna dalam pemantauan berbunyi lain: apakah angka ini sedang naik, sejak kapan, dan apakah tadi malam pernah ada lonjakan yang tidak dilihat siapa pun.
> Bandingkan dengan saldo dan mutasi rekening: saldo hari ini adalah satu angka yang benar, tetapi ia tidak memberi tahu apakah Anda sedang berhemat dan tidak memberi tahu ada tarikan besar pekan lalu, dan yang menjawab itu adalah daftar mutasi yang setiap angkanya punya tanggal.
> Begitu deretan nilai digambar sebagai garis terhadap waktu, empat hal langsung terbaca, yaitu arah perubahan yang memungkinkan tindakan diambil sebelum batas terlampaui, kecepatan perubahan, pola yang berulang, dan bagian kosong yang menandakan sistem berhenti mengirim.
> Kecepatan perubahan itulah yang membedakan kenaikan dua derajat dalam satu jam yang wajar dari kenaikan dua derajat dalam dua menit yang hampir selalu berarti ada yang salah, dan tidak satu pun angka tunggal dapat memperlihatkannya.
> Karena itu langkah pertama adalah memahami bentuk data yang ikut menyimpan waktu, bukan hanya nilai.

### Frame 4 — Riwayat Adalah Nilai Bercap Waktu

Kawasan: Dari Sesaat ke Riwayat

Teks di layar:
- Data terkini: satu tempat yang selalu tertimpa
- Data berseri waktu: satu baris baru ditambahkan
- Sistem mati sepuluh menit terlihat sebagai lubang
- Tanpa cap waktu, itu hanya daftar angka
- Tulis `2026-08-30 09:15:07` agar dapat diurutkan

Yang Anda ucapkan:
> Data terkini adalah satu tempat penyimpanan yang selalu ditimpa, sehingga nilai baru menghapus nilai sebelumnya dan yang tersisa selalu satu angka; gauge pada dashboard bekerja seperti ini, dan pesan MQTT yang ditandai sebagai pesan tersimpan pada broker juga hanya menyimpan satu nilai terakhir per topic.
> Data berseri waktu adalah kumpulan baris yang masing-masing memuat satu nilai beserta waktu pengambilannya, tidak ada yang ditimpa sehingga kumpulannya terus bertambah panjang, dan dari kumpulan itulah grafik tren digambar.
> Perbedaannya paling jelas ketika sistem mati sepuluh menit: pada data terkini tidak ada bekas apa pun, sedangkan pada data berseri waktu kekosongan itu terlihat sebagai lubang.
> Cap waktu bukan pelengkap melainkan bagian dari datanya, sebab nilai 29,4 pada baris kelima tidak berarti apa pun bila tidak diketahui kapan ia diukur.
> Tulis cap waktu dalam urutan tahun-bulan-tanggal seperti `2026-08-30 09:15:07` agar dapat diurutkan sebagai teks, karena bentuk `30/08/2026` menyulitkan pengurutan dan mudah tertukar dengan kebiasaan penulisan tanggal di negara lain.
> Untuk pertemuan ini cap waktu diambil dari komputer yang menjalankan Node-RED sehingga ia menggambarkan saat data diterima, bukan saat diukur, tetapi hampir selalu benar tanggalnya.
> Setelah bentuknya jelas, kita hitung apa akibatnya bila setiap pembacaan benar-benar disimpan.

### Frame 5 — Interval Menentukan Ukuran Riwayat

Kawasan: Ukuran dan Tempat Penyimpanan

Teks di layar:
- Kirim tiap 10 detik: `8.640` baris per hari
- Sehari sekitar `380 KB` untuk satu parameter
- Interval sepuluh kali lebih rapat, berkas sepuluh kali
- Interval serapat kejadian tercepat yang Anda pedulikan
- Retensi ditentukan pertanyaan terpanjang yang ingin dijawab

Yang Anda ucapkan:
> Begitu setiap pembacaan disimpan, keputusan tentang interval pengiriman yang Anda buat pada Pertemuan 9 tentang pengaturan waktu pengiriman berubah maknanya: dulu interval dipilih agar jaringan tidak dibanjiri, sekarang interval yang sama menentukan seberapa cepat penyimpanan terisi dan seberapa padat grafik yang akan Anda baca.
> Hitungannya sederhana dan sebaiknya dilakukan sebelum pencatatan dinyalakan, sebab satu pengiriman setiap sepuluh detik berarti 8.640 baris per hari, dan untuk satu baris CSV yang panjangnya sekitar 45 karakter, sehari menghasilkan sekitar 380 kilobyte.
> Tabel pada Bab 3 materi pertemuan ini memuat lima interval lain, dan yang perlu Anda ambil bukan angka pastinya melainkan bentuk hubungannya: mempersingkat interval sepuluh kali lipat memperbesar berkas sepuluh kali lipat juga, setiap hari, dan bila Anda mencatat tiga parameter kalikan tiga.
> Interval harus cukup rapat untuk menangkap kejadian tercepat yang benar-benar Anda pedulikan dan tidak lebih rapat dari itu, sehingga suhu ruangan cukup dengan sepuluh detik sampai satu menit, sedangkan status pintu yang bisa berubah dalam dua detik akan terlewat bila intervalnya satu menit.
> Lama penyimpanan ditentukan oleh pertanyaan terpanjang yang ingin dijawab: melihat nilainya sedang naik hanya perlu 10 sampai 30 menit terakhir, memeriksa apakah tadi malam pernah melewati batas perlu 24 jam, dan melihat pola harian perlu tujuh hari.
> Dua kesalahan berikut sama merugikan, yaitu interval terlalu rapat yang membuat berkas membengkak tanpa menambah pemahaman, dan interval terlalu jarang yang membuat grafik tampak rapi tetapi berbohong karena lonjakan di antara dua titik pengambilan tidak pernah tercatat.
> Setelah tahu berapa banyak yang akan tersimpan, pertanyaan berikutnya adalah di mana data itu disimpan.

### Frame 6 — Dua Pilihan Penyimpanan Sederhana

Kawasan: Ukuran dan Tempat Penyimpanan

Teks di layar:
- Berkas CSV lewat node `file` pada Node-RED
- Saluran pada layanan cloud, misalnya ThingSpeak
- CSV: kendali penuh, tetapi tanpa grafik sendiri
- Cloud: grafik dan cap waktu otomatis, laju dibatasi
- Kunci tulis adalah kata sandi saluran Anda

Yang Anda ucapkan:
> Sistem sungguhan biasanya memakai basis data khusus untuk data berseri waktu, tetapi pada tahap ini hal itu belum diperlukan dan justru menambah sumber masalah baru.
> Pilihan pertama adalah berkas CSV, yaitu berkas teks biasa yang setiap barisnya memuat beberapa nilai dipisahkan koma dan dituliskan oleh node file pada kelompok storage tanpa perlu memasang apa pun; keunggulannya kendali penuh, kelemahannya berkas itu hanya ada di satu komputer dan tidak menggambar grafik sendiri.
> Pilihan kedua adalah saluran pada layanan cloud yang dibuat untuk data IoT, misalnya ThingSpeak, tempat Anda membuat sebuah saluran, memberi nama beberapa medan data, lalu mengirim nilai memakai sebuah kunci tulis, sementara layanan itu menyimpan tiap nilai bersama cap waktunya dan menggambar grafiknya sendiri sehingga dapat dibuka dari mana saja.
> Imbalannya, akun gratis membatasi seberapa sering satu saluran boleh diperbarui, biasanya sekitar satu pengiriman setiap lima belas detik, dan batas seperti ini dapat berubah sehingga periksa keterangan pada akun Anda.
> Pengirimannya sendiri berbentuk satu permintaan web biasa dengan metode GET yang menitipkan nilai beserta kunci tulis pada alamatnya, dan jawaban layanan berupa satu angka, yaitu nomor urut data bila diterima atau nol bila ditolak, yang hampir selalu berarti kunci tulis salah atau pengiriman terlalu rapat.
> Keduanya sebaiknya dipakai bersama, yaitu data mentah dicatat ke berkas lokal sebagai cadangan sementara nilai yang lebih jarang dikirim ke layanan cloud untuk ditampilkan; ingat bahwa kunci tulis adalah kata sandi saluran Anda sehingga jangan menuliskannya pada laporan, dan cara memisahkan kunci dari kode dibahas pada Pertemuan 12 tentang keamanan dan keandalan dasar.
> Tempatnya sudah jelas, sekarang kita tentukan apa saja yang layak masuk ke dalamnya.

### Frame 7 — Lima Kolom Riwayat yang Berguna

Kawasan: Ukuran dan Tempat Penyimpanan

Teks di layar:
- Ukurannya: tiap kolom menjawab satu pertanyaan pemantauan
- `waktu`, `device`, `parameter`, `nilai`, `satuan`
- `waktu` satu-satunya yang tidak boleh hilang
- Jangan campur pesan teknis dengan baris data
- Jangan catat nilai mustahil seperti minus 127

Yang Anda ucapkan:
> Godaan pertama ketika pencatatan mulai berfungsi adalah mencatat segalanya, dan godaan itu sebaiknya ditahan.
> Ukurannya sederhana, yaitu untuk setiap kolom yang dicatat Anda harus bisa menyebutkan satu pertanyaan pemantauan yang membutuhkan kolom itu.
> Dengan ukuran tersebut, satu baris riwayat yang berguna biasanya cukup memuat lima kolom, yaitu `waktu`, `device`, `parameter`, `nilai`, dan `satuan`, dan di antara kelimanya hanya `waktu` yang tidak boleh hilang karena tanpa cap waktu data tidak dapat diurutkan maupun digambar.
> Kolom `device` menjaga nilai dari beberapa sumber tetap dapat dipisahkan, `parameter` menjelaskan besaran yang diukur, `nilai` memuat pengukurannya, dan `satuan` membuat angka itu tetap terbaca berbulan-bulan kemudian.
> Kolom tambahan boleh ada bila menjawab pertanyaan tertentu, misalnya status koneksi.
> Sebaliknya, jangan mencatat setiap putaran `loop()`, jangan mencampur pesan teknis dengan baris data ukur karena jumlah kolom antar baris menjadi berbeda sehingga berkas tidak lagi terbaca sebagai tabel, dan jangan mencatat nilai yang jelas tidak masuk akal seperti minus 127 derajat dari sensor yang lepas.
> Nilai semacam itu merusak skala grafik, dan skala grafik justru soal berikutnya, sebab grafik yang sama bisa memberi dua kesan yang berlawanan.

### Frame 8 — Rentang Sumbu Mengubah Kesan

Kawasan: Ruang Grafik

Teks di layar:
- Empat hal wajib: sumbu waktu, nilai, rentang, judul
- Rentang otomatis selalu mengisi seluruh tinggi kotak
- 29,3 sampai 29,6 tampak seperti pegunungan bergerigi
- Rentang tetap `20` sampai `40` tampak hampir datar
- Tetapkan batas sumbu atas dasar pertimbangan

Yang Anda ucapkan:
> Grafik tren adalah alat penerjemah, dan seperti semua penerjemah ia bisa keliru menyampaikan maksud, sebab grafik yang sama bisa memberi kesan sangat gawat atau sangat tenang hanya karena satu pengaturan sumbu diubah.
> Empat hal wajib ada padanya, yaitu sumbu horizontal waktu beserta keterangan rentangnya seperti dua puluh menit terakhir, sumbu vertikal nilai beserta satuannya, rentang sumbu vertikal yang ditetapkan atas dasar pertimbangan, serta judul yang menyebut parameter dan sumbernya.
> Yang paling sering menyesatkan adalah rentang sumbu vertikal yang dibiarkan menyesuaikan diri secara otomatis, karena grafik lalu selalu mengisi seluruh tinggi kotaknya apa pun isi datanya.
> Contohnya begini: suhu yang bergerak antara 29,3 dan 29,6 derajat akan tampak seperti pegunungan bergerigi, padahal selisihnya hanya tiga persepuluh derajat.
> Dengan rentang tetap 20 sampai 40 derajat, garis yang sama tampak hampir datar, dan itulah gambaran yang jujur.
> Selain rentang, ada satu hal lain yang bisa menyembunyikan kenyataan, yaitu cara grafik memperlakukan data yang tidak pernah datang.

### Frame 9 — Bagian Kosong dan Empat Lapis

Kawasan: Ruang Grafik

Teks di layar:
- Data berhenti sepuluh menit: bagian kosong benar
- Garis lurus panjang justru menyembunyikan kekosongan itu
- Nilai pada garis lurus itu tidak pernah diukur
- Empat lapis: tinggi, kemiringan, riak, paku
- Pemastiannya selalu ada pada berkas riwayat

Yang Anda ucapkan:
> Bila data berhenti datang selama sepuluh menit, ada dua kemungkinan tampilan, dan hanya satu di antaranya jujur.
> Grafik yang benar memperlihatkan bagian kosong pada rentang itu dan kekosongan itu memberi tahu bahwa sistem sempat berhenti, sedangkan grafik yang menyambung titik sebelum dan sesudah kekosongan dengan satu garis lurus panjang justru menyembunyikannya, padahal garis lurus itu adalah nilai yang tidak pernah diukur.
> Karena itu garis lurus panjang yang mencurigakan selalu diperiksa dulu ke berkas riwayatnya.
> Sebuah grafik juga dibaca berlapis: tinggi garis menjawab apakah nilainya wajar, arah dan kemiringan menjawab sedang naik, turun, atau tetap dan seberapa cepat, riak kecil menjawab apakah pembacaannya tenang atau berisik, sedangkan paku tajam dan bagian kosong menjawab apakah ada kejadian singkat atau data yang hilang.
> Perhatikan bahwa kemiringan bergantung pada lebar jendela waktu, sehingga kemiringan yang tampak tajam pada jendela sempit belum tentu tajam pada jendela yang lebih lebar.
> Karena lapis terakhir itu selalu perlu dipastikan pada berkas riwayat, sekarang kita buka satu berkas riwayat yang sebenarnya.

### Frame 10 — Satu Baris CSV dan Penyusunnya

Kawasan: Ruang Praktik

Teks di layar:
- `2026-08-30 09:15:00,esp32-lab-01,suhu,28.9,C`
- Baris judul kolom ditulis sekali, bukan oleh Node-RED
- Lompatan 29,7 ke 31,6 patut dicurigai
- Tidak ada baris antara 09:16:00 dan 09:18:30
- Node `function` menolak data yang bukan angka

Yang Anda ucapkan:
> Ini potongan sebenarnya dari sebuah berkas riwayat suhu, dan lima kolomnya selalu muncul dengan urutan yang sama, yaitu `waktu` berisi tanggal dan jam saat nilai diterima, `device` berisi nama sumber `esp32-lab-01`, `parameter` berisi `suhu`, `nilai` berisi angka seperti `29.4` dengan titik desimal, dan `satuan` berisi `C` agar angka itu tidak mungkin salah dibaca.
> Baris pertama adalah baris judul kolom, ditulis satu kali saja ketika berkas pertama dibuat dan tidak ditulis oleh Node-RED, sebab node file yang disetel menambahkan hanya menuliskan apa yang dikirimkan kepadanya.
> Dua hal terbaca dari potongan ini tanpa perlu grafik: nilai pada 09:16:00 melompat dari 29,7 ke 31,6 dalam sepuluh detik yang terlalu cepat untuk suhu ruangan sehingga patut dicurigai sebagai gangguan pembacaan, dan tidak ada satu baris pun antara 09:16:00 dan 09:18:30 yang berarti sistem berhenti mengirim selama dua setengah menit.
> Baris seperti itu tidak muncul sendiri, melainkan disusun lebih dahulu oleh satu node function yang mengubah isi pesan menjadi angka, menolak dan memperingatkan bila hasilnya bukan angka agar berkas tidak rusak, menyusun cap waktu tahun-bulan-tanggal dengan nol di depan, lalu menggabungkan lima kolom dengan koma.
> Menambah satu parameter lagi tidak mengubah susunan itu dan hanya menambah baris, sehingga jumlah kolom tiap baris tetap lima, baris judul kolom tidak pernah perlu diubah, dan data lama tetap terbaca berdampingan dengan data baru.
> Satu peringatan ketika membuka berkasnya pada aplikasi lembar sebar: jangan klik ganda, pakai menu impor lalu tetapkan sendiri koma sebagai pemisah kolom dan titik sebagai tanda desimal, sebab pada pengaturan bahasa Indonesia nilai `28.9` bisa terbaca sebagai teks atau bahkan sebagai `289`.
> Contoh lengkapnya beserta kode penyusun barisnya ada pada Bab 9 materi pertemuan ini, dan sekarang kita bangun jalur itu sendiri di depan kelas.

### Frame 11 — Demo Grafik Tren dan Pencatatan

Kawasan: Ruang Praktik

Teks di layar:
- Pastikan sumber data di simulator masih mengirim
- Node grafik: grup sama, tipe garis, batas `20`–`40`
- Node `function` ke node `file`, tindakan menambahkan
- Hasil: garis memanjang, baris berkas bertambah
- Jeda satu menit sengaja: lubang dan lompatan

Yang Anda ucapkan:
> Urutan yang saya tunjukkan sekarang seluruhnya dikerjakan di dalam Node-RED, tanpa mengubah program pada device.
> Pertama flow dashboard dibuka, lalu satu node debug disambungkan sementara ke sumber data untuk memastikan nilai baru masih masuk berkala dari sumber data di simulator, sebab bila sumbernya diam tidak ada gunanya melanjutkan.
> Kedua node grafik ditarik ke kanvas dengan grup yang sama dengan gauge Anda, label yang menyebut parameter dan sumbernya seperti `Suhu lab esp32-lab-01`, tipe garis, rentang waktu dua puluh menit terakhir, serta batas sumbu vertikal minimum 20 dan maksimum 40; penamaan pada palet bisa berbeda antarversi, jadi kenali node itu dari tiga tanda yang tidak berubah, yaitu ia berada pada kelompok dashboard, pengaturannya meminta Group, dan ia menyediakan tipe garis.
> Masukan node grafik harus berupa satu angka pada `msg.payload`, jadi bila payload Anda masih berbentuk JSON seperti pada Pertemuan 9 tentang penyusunan payload, satu node change dipakai untuk mengambil satu bidangnya lebih dahulu.
> Ketiga jalur pencatatan dipasang, yaitu sumber angka ke node function penyusun baris lalu ke node file yang diisi alamat berkas lengkap, tindakan menambahkan, penambahan baris baru, dan pembuatan direktori, dengan baris judul kolom disiapkan lebih dahulu karena node file tidak pernah menuliskannya sendiri.
> Setelah Deploy, dua hal harus terlihat, yaitu garis pada dashboard bertambah panjang setiap kali data baru masuk, dan isi berkas CSV berupa baris yang terus bertambah dengan cap waktu berurutan, bukan satu baris yang tertimpa, dengan angka pada baris terakhirnya cocok dengan yang tampil di dashboard.
> Terakhir sumber data dihentikan sekitar satu menit lalu dihidupkan lagi, dan jeda itu harus muncul sebagai bagian tanpa titik data pada grafik dan sebagai lompatan cap waktu pada berkas; langkahnya lengkap ada pada Bab 7 materi pertemuan ini, dan bila yang Anda lihat berbeda, gejalanya biasanya sudah ada pada daftar berikut.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Praktik

Teks di layar:
- Grafik kosong meski gauge bergerak: payload bukan angka
- Garis melompat ekstrem: rentang sumbu masih otomatis
- Berkas tidak muncul: alamat atau folder salah
- Satu baris berubah terus: node `file` masih menimpa
- Isi menumpuk satu kolom: pemisah belum ditetapkan

Yang Anda ucapkan:
> Tabel penelusuran masalah pada Bab 8 materi pertemuan ini memuat lima gejala, dan hampir semuanya soal bentuk data atau pilihan pada node, bukan soal grafik yang salah dipilih.
> Bila grafik tetap kosong meski gauge bergerak, payload yang masuk bukan angka murni dan mungkin masih berupa teks JSON, jadi pasang node debug tepat sebelum grafik dan pastikan nilainya tampil sebagai angka yang tidak diapit tanda kutip.
> Bila garis melompat-lompat sangat ekstrem, rentang sumbu vertikal masih dibiarkan otomatis, jadi tetapkan sendiri batas minimum dan maksimumnya seperti yang dibahas pada Bab 6 materi pertemuan ini.
> Bila berkas CSV tidak muncul sama sekali, alamat berkasnya salah atau folder tujuannya tidak ada, jadi periksa alamat lengkap pada node file, pilihan pembuatan direktori, dan pesan merah pada panel debug; bila berkasnya hanya berisi satu baris yang terus berubah, node file masih menimpa sehingga pilihan tindakan dan pilihan penambahan baris barunya perlu diperiksa.
> Bila Anda menulis nama berkas tanpa alamat lengkap, berkasnya tetap dibuat tetapi di direktori kerja Node-RED dan bukan di tempat yang Anda duga, sedangkan bila alamatnya sudah benar tetapi berkas tidak pernah muncul, hak tulis pada folder itulah yang pertama perlu dicurigai.
> Bila seluruh isi baris menumpuk pada satu kolom di aplikasi lembar sebar, berkas Anda tidak rusak dan yang belum ditetapkan hanyalah pemisah kolom serta tanda desimalnya saat berkas dibuka.
> Bila di satu titik Anda macet dan penyebabnya tidak terlihat, mintalah bantuan teman atau ajukan pertanyaan di kelas dengan menyertakan tangkapan layar panel debug; sekarang kita rangkum pertemuan ini.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 11

Kawasan: Penutup dan Tugas

Teks di layar:
- Hanya riwayat menjawab arah, kecepatan, pola, kejadian
- Cap waktu adalah bagian datanya, bukan pelengkap
- Interval menentukan jumlah baris dan ukuran berkas
- Grafik jujur bila satuan, rentang, kekosongan dibaca
- Checkpoint: riwayat berisi, relevan, visualisasi terbaca

Yang Anda ucapkan:
> Mari kita kumpulkan intinya: data sesaat menjawab berapa nilainya sekarang, dan hanya riwayat yang dapat menjawab arah, kecepatan, pola, serta kejadian yang sudah lewat.
> Data berseri waktu adalah kumpulan baris bercap waktu yang tidak pernah ditimpa, dan cap waktu itu bagian dari datanya, bukan pelengkap.
> Interval pengiriman menentukan jumlah baris dan ukuran berkas secara langsung, sementara lama penyimpanan ditentukan oleh pertanyaan terpanjang yang ingin Anda jawab.
> Dua penyimpanan sederhana yang realistis adalah berkas CSV lewat node file dan saluran pada layanan cloud dengan kunci tulis, sedangkan satu baris riwayat yang berguna umumnya memuat waktu, device, parameter, nilai, dan satuan.
> Grafik tren hanya jujur bila satuan, rentang sumbu, dan bagian kosongnya dibaca ikut serta.
> Checkpoint evaluasi pada Bab 13 materi pertemuan ini menuntut tiga hal, yaitu ada grafik atau log riwayat yang benar-benar berisi data, data yang tersimpan relevan dengan tujuan pemantauan, dan visualisasinya terbaca dengan benar.
> Cara memastikannya sendiri: buka dashboard dan berkas riwayat berdampingan sampai grafik bergerak dan jumlah baris bertambah, sebutkan satu pertanyaan pemantauan untuk tiap kolom yang Anda catat, lalu minta teman membaca grafik Anda tanpa penjelasan sampai ia dapat menyebut parameter, satuan, dan rentang waktunya; setelah itu Anda siap mengerjakan tugasnya.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup dan Tugas

Teks di layar:
- Tambahkan grafik tren satu parameter beserta riwayatnya
- Tangkapan layar grafik berisi data minimal sepuluh menit
- Sepuluh baris pertama riwayat, atau grafik saluran
- Satu halaman: parameter, interval, rentang, pembacaan tren
- Bobot: grafik `30%`, riwayat `25%`, keterbacaan `25%`

Yang Anda ucapkan:
> Tugas Anda adalah menambahkan visualisasi tren untuk satu parameter pada dashboard yang sudah Anda bangun, lengkap dengan penyimpanan riwayatnya.
> Pilih parameter yang paling berarti bagi sistem Anda, dan pastikan grafiknya dapat dibaca orang lain tanpa penjelasan tambahan.
> Yang dikumpulkan ada tiga, yaitu tangkapan layar dashboard yang memperlihatkan grafik tren berisi data minimal sepuluh menit, sepuluh baris pertama berkas riwayat Anda atau tangkapan layar grafik pada saluran cloud, dan satu halaman penjelasan.
> Halaman penjelasan itu memuat parameter yang dipilih, interval kirim beserta alasannya, rentang sumbu yang dipakai beserta alasannya, dan satu paragraf pembacaan tren.
> Penilaiannya terbagi menjadi grafik tren berfungsi `30%`, riwayat tersimpan dan relevan `25%`, keterbacaan visualisasi `25%`, alasan interval dan retensi `10%`, serta pembacaan tren `10%`, dan ingat pula bahwa tugas latihan mingguan berbobot dua puluh persen dari nilai akhir.
> Dua bobot terakhir hanya penuh bila interval dan lama penyimpanan dikaitkan dengan pertanyaan pemantauan dan bukan sekadar disebut, serta bila penjelasan Anda menyebut apa yang tampak pada grafik beserta artinya bagi sistem.
> Dua pertanyaan pembuka tadi kini terjawab: kewajaran nilai 29,4 hanya dapat dinilai dengan membandingkannya terhadap nilai yang sama pada waktu lain, dan yang hilang bila sistem hanya menyimpan nilai terakhir adalah seluruh arah, kecepatan, pola, serta setiap kejadian yang tidak sedang Anda tonton.
