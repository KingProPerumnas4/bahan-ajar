# Prezi Pertemuan 8 — UTS Praktik: Integrasi Sistem IoT Sederhana di Simulator

## Kanvas utama

Saat Prezi dibuka, kanvas terlihat utuh sebelum zoom pertama: judul pertemuan berada di tengah, dan enam kawasan mengelilinginya sebagai satu lintasan pengerjaan ujian, dari aturan dan bentuk ujiannya, ke pilihan kasus, lalu ke meja rancangan, ke ruang kerja tempat sistem dirakit dan dibuktikan, dan berakhir pada penilaian. Kawasan di sisi kiri berisi gerbang serta aturan yang mengikat seluruh pekerjaan, kawasan tengah berisi kasus yang dapat dipilih beserta rancangan yang harus ditulis sebelum program disentuh, sedangkan kawasan kanan berisi langkah perakitan, penelusuran masalah, bukti berupa log serial, dan bobot penilaian, sehingga jalur zoom bercerita dari aturan menuju bukti. Setiap perpindahan bergerak satu langkah ke kanan mengikuti urutan kerja yang disarankan materi, dan sesekali kamera menjauh sebentar agar Anda dapat melihat kembali posisi bahasan di dalam gambar besar sebelum layar menutup rapat pada frame berikutnya.

- Kawasan 1: Gerbang — judul pertemuan, pertanyaan pemancing, dan capaian pembelajaran.
- Kawasan 2: Aturan Ujian — bentuk ujian, apa yang dinilai, dan empat bagian yang harus menyatu.
- Kawasan 3: Pilihan Kasus — empat kasus yang dapat dipilih beserta kerangka yang sama.
- Kawasan 4: Meja Rancangan — diagram, bentuk data, ambang keputusan, dan pilihan jalur komunikasi.
- Kawasan 5: Ruang Kerja — isi laporan, langkah perakitan, penelusuran masalah, dan bukti log serial.
- Kawasan 6: Penutup — ringkasan, checkpoint evaluasi, serta pengumpulan dan bobot penilaian.

## Alur zoom

1. Mengapa Menyatukan Lebih Sulit?
2. Capaian Pembelajaran Pertemuan Ini
3. Bentuk dan Aturan Ujian Praktik
4. Empat Bagian yang Harus Menyatu
5. Empat Kasus yang Dapat Dipilih
6. Diagram dan Bentuk Data
7. Ambang dan Jarak Pengaman
8. Memilih MQTT atau HTTP
9. Isi Laporan dan Empat Pertanyaan
10. Langkah Perakitan di Simulator
11. Jika Hasilnya Tidak Seperti Itu
12. Log Serial sebagai Bukti
13. Ringkasan dan Checkpoint Pertemuan 8
14. Yang Dikumpulkan dan Bobot Penilaian

## Frame

### Frame 1 — Mengapa Menyatukan Lebih Sulit?

Kawasan: Gerbang

Teks di layar:
- Pertemuan 8: UTS praktik integrasi sistem IoT
- Sensor, aktuator, log serial, pengiriman data
- Semuanya pernah berhasil, kini harus berjalan bersama
- Mengapa penggabungan justru menuntut hal baru?
- Jawaban lengkap menjelang frame terakhir

Yang Anda ucapkan:
> Selamat datang pada Pertemuan 8, yang berbentuk UTS praktik dan sekaligus menjadi checkpoint besar kedua mata kuliah ini. Tujuh pertemuan pertama melatih bagian yang terpisah, yaitu membaca sensor, menggerakkan aktuator, mengamati log serial, dan mengirim data lewat HTTP atau MQTT, dan masing-masing sudah pernah berhasil Anda jalankan. Pada pertemuan ini keempatnya disatukan menjadi satu sistem kecil yang utuh dan berjalan di simulator, lalu Anda menjelaskan sendiri cara kerjanya. Pertanyaan pembuka kita ada di layar, yaitu mengapa penggabungan itu justru menuntut hal baru padahal setiap bagiannya sudah pernah Anda kuasai. Tidak ada materi baru hari ini, jadi seluruh waktu kita dipakai untuk aturan ujian, pilihan kasus, cara membuktikan hasil, dan cara penilaiannya. Jawaban pertanyaan pembuka baru lengkap setelah semua itu Anda lihat. Kita mulai dari capaian yang diuji.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Gerbang

Teks di layar:
- Memahami alur data satu arah sampai keluar
- Aturan logika menghubungkan angka dan reaksi
- Log serial membuktikan setiap tahap berjalan
- Merakit empat bagian dalam satu program
- Menyusun laporan berisi diagram, log, penjelasan

Yang Anda ucapkan:
> Capaian pertemuan ini dibagi menjadi yang perlu Anda pahami dan yang perlu Anda kerjakan. Sisi pemahaman mencakup alur data satu arah dari sensor sampai data keluar dari perangkat, peran aturan logika sebagai penghubung angka sensor dan reaksi aktuator, fungsi log serial sebagai bukti setiap tahap benar-benar berjalan, serta situasi yang cocok untuk MQTT dan yang cocok untuk HTTP. Sisi keterampilan mencakup merakit sensor, aktuator, log serial, dan pengiriman data dalam satu program, menentukan ambang keputusan beserta jarak pengaman agar status tidak berkedip, membuktikan data sampai ke luar perangkat dari sisi penerima, dan menyusun laporan berisi diagram, kutipan log serial, serta penjelasan alur data. Perhatikan bahwa fokus pertemuan ini adalah integrasi, bukan materi baru, sebab semua bahan sudah Anda pelajari dan yang diuji adalah kemampuan menyatukannya menjadi satu sistem yang berjalan dan dapat Anda pertanggungjawabkan. Pertemuan ini juga menjadi checkpoint besar kedua, dan nilainya masuk sebagai UTS praktik berbobot 20 persen dari nilai akhir. Karena itu aturan ujiannya perlu jelas lebih dahulu sebelum Anda menyentuh program.

### Frame 3 — Bentuk dan Aturan Ujian Praktik

Kawasan: Aturan Ujian

Teks di layar:
- Kerja praktik: bangun, jalankan, serahkan laporan
- Dari satu peramban, tanpa komponen fisik
- Sendiri atau berpasangan, keduanya harus dapat menjelaskan
- Dinilai keutuhan alur, bukan kerumitan rangkaian
- Nilainya UTS praktik, 20 persen nilai akhir

Yang Anda ucapkan:
> Ujian ini berbentuk kerja praktik, yaitu Anda membangun satu sistem IoT kecil di simulator, menjalankannya sampai terlihat bekerja, lalu menyerahkan laporan singkat sebagai bukti. Seluruh pekerjaan dapat diselesaikan dari satu peramban tanpa komponen fisik dan tanpa pemasangan perangkat lunak baru, jadi yang perlu siap hanya akun simulator yang sudah Anda pakai, koneksi internet, dan arsip proyek latihan Pertemuan 1 sampai 7. Pekerjaan boleh dikerjakan sendiri atau berpasangan, tetapi bila berpasangan keduanya harus dapat menjelaskan seluruh program. Yang dinilai bukan kerumitan rangkaian melainkan keutuhan alurnya, sehingga satu sensor sederhana yang datanya benar-benar sampai ke penerima lebih bernilai daripada rangkaian ramai yang berhenti di tengah jalan. Di sinilah kata integrasi pada judul pertemuan ini perlu dijelaskan, sebab menggabungkan bagian menuntut Anda memastikan bagian yang satu tidak merusak bagian yang lain, misalnya penyambungan Wi-Fi memakan waktu sehingga pembacaan tertunda, pin yang dipakai aktuator bertabrakan dengan pin yang dibutuhkan radio, atau kesalahan pengiriman menghentikan seluruh program bila tidak diantisipasi. Karena hasilnya dinilai sebagai UTS praktik berbobot 20 persen dari nilai akhir, sisakan tenaga untuk menguji, bukan hanya untuk menulis program, sebab sistem yang berjalan mulus dan terdokumentasi rapi lebih dihargai daripada sistem bercita-cita tinggi yang hanya berhasil sekali lalu tidak dapat diulang. Sekarang kita perinci empat bagian yang harus menyatu itu.

### Frame 4 — Empat Bagian yang Harus Menyatu

Kawasan: Aturan Ujian

Teks di layar:
- Sensor sebagai sumber angka yang berubah
- Aktuator sebagai reaksi, misalnya LED atau buzzer
- Log serial sebagai pengawas setiap tahap
- Komunikasi data ke luar lewat MQTT atau HTTP
- Alur searah: angka, status, reaksi, pengiriman

Yang Anda ucapkan:
> Sistem yang Anda bangun harus memuat empat bagian sekaligus, dan keempatnya hidup dalam satu berkas program yang sama. Bagian pertama adalah sensor sebagai sumber angka, yaitu satu masukan yang nilainya berubah saat Anda mengubah keadaan di simulator, sebab tanpa angka yang berubah sistem tidak punya apa pun untuk diolah. Bagian kedua adalah aktuator sebagai reaksi, misalnya LED atau buzzer, sehingga keputusan program terlihat langsung, sedangkan bagian ketiga adalah log serial sebagai pengawas berupa cetakan teks berisi nilai sensor, status, dan keterangan pengiriman, dan log inilah yang menunjukkan di tahap mana sistem berhenti. Bagian keempat adalah komunikasi data ke luar perangkat lewat MQTT atau HTTP, dan justru bagian inilah yang membedakan alat elektronik biasa dari sistem IoT. Urutannya searah, sensor menghasilkan angka, aturan logika mengubahnya menjadi status, lalu status itu menggerakkan aktuator dan dikirim ke luar perangkat, sementara log serial menempel di sepanjang alur sebagai pengawas. Materi ini mengumpamakannya sebagai penjaga suhu ruang server yang melihat termometer, memutuskan aman atau tidak berdasarkan batas yang disepakati, menyalakan lampu tanda bahaya, mencatat setiap pemeriksaan di buku jaga, lalu mengirim laporan ke pengawas di ruang lain, dan program Anda mengerjakan kelima hal itu berulang tanpa berhenti. Kerangka itu sama untuk semua kasus, jadi sekarang Anda tinggal memilih kasusnya.

### Frame 5 — Empat Kasus yang Dapat Dipilih

Kawasan: Pilihan Kasus

Teks di layar:
- Alarm suhu: LED merah, buzzer, status `BAHAYA`
- Lampu pintar: makin gelap, lampu justru menyala
- Notifikasi kelembapan: LED kuning, status `KERING`
- Penghitung parkir: kapasitas tercapai, status `PENUH`
- Kerangka sama, beda pin, rumus, arah perbandingan

Yang Anda ucapkan:
> Anda memilih satu dari empat kasus, dan semuanya memakai komponen yang sudah tersedia di simulator serta sudah pernah Anda pakai, sehingga waktu Anda habis untuk merakit alur, bukan untuk mengenali komponen baru. Kasus alarm suhu memakai potensiometer yang diperlakukan sebagai pembacaan suhu dengan LED merah dan buzzer, dan aturannya menyalakan keduanya lalu mengirim status `BAHAYA` bila suhu melewati ambang bahaya, serta mematikan keduanya dan mengirim `AMAN` bila suhu turun cukup jauh di bawah ambang. Kasus lampu pintar memakai sensor cahaya dengan LED yang mewakili lampu ruangan, dan aturannya berlawanan arah dengan kasus alarm karena makin gelap ruangan lampu justru menyala. Kasus notifikasi kelembapan memakai potensiometer sebagai kelembapan tanah dalam persen dengan LED kuning sebagai tanda tanah mulai kering, dan mengirim status `KERING` bila kelembapan turun di bawah batas, sedangkan kasus penghitung kendaraan parkir memakai tombol yang setiap penekanannya dihitung sebagai satu kendaraan masuk, dengan LED menyala dan status `PENUH` ketika hitungan mencapai kapasitas. Keempatnya berkerangka sama dan hanya berbeda pada tiga hal, yaitu pin masukan, rumus pengubah angka, dan arah perbandingan pada aturan logika, dan Bab 8.3 materi pertemuan ini menunjukkan bahwa berpindah kasus umumnya cukup mengganti fungsi pembaca sensor beserta fungsi penentu statusnya. Satu peringatan penting, jangan memaksakan komponen yang belum pernah Anda pakai supaya kasus Anda terlihat lebih canggih, sebab waktu akan habis untuk membaca dokumentasi komponen sementara yang dinilai adalah keutuhan alur data. Setelah kasusnya dipilih, rancangannya ditulis lebih dahulu.

### Frame 6 — Diagram dan Bentuk Data

Kawasan: Meja Rancangan

Teks di layar:
- Diagram: kotak dan panah arah informasi
- Boleh digambar dengan tangan, lalu difoto
- Kirim nilai terukur, misalnya `36.02`
- Kirim status keputusan, misalnya `BAHAYA`
- Penanda pengirim pada nama topik, `nim12345`

Yang Anda ucapkan:
> Rancangan ditulis sebelum program disentuh, dan tiga hal sudah cukup, yaitu diagram sistem, ambang keputusan, dan bentuk data yang dikirim, sebab ketiganya nanti masuk ke laporan Anda. Diagramnya cukup berupa kotak dan tanda panah, yaitu kotak sensor, kotak papan mikrokontroler, kotak aktuator, dan kotak penerima data, dengan panah yang menunjukkan arah perpindahan informasi. Diagram semacam ini boleh digambar dengan tangan lalu difoto, karena gunanya bukan keindahan melainkan memaksa Anda menyebut setiap perpindahan data sebelum menuliskannya sebagai kode. Untuk bentuk datanya, tentukan sejak awal apa yang dikirim, ke mana, dan seberapa sering, dan untuk sistem sekecil ini dua nilai sudah memadai, yaitu satu angka hasil pengukuran seperti `36.02` agar penerima dapat menilai seberapa jauh keadaan melewati batas, dan satu status hasil keputusan seperti `BAHAYA` agar penerima dapat bereaksi tanpa perlu mengetahui ambang di dalam program Anda. Tambahkan penanda pengirim sebagai bagian nama topik, misalnya `nim12345`, agar data Anda tidak tertukar dengan data orang lain. Perlu Anda ingat bahwa pada broker publik apa pun yang Anda kirim dapat dibaca siapa saja, jadi jangan mengirim data pribadi, kata sandi, atau nama lengkap, dan pakailah nomor identitas kuliah atau nama samaran sebagai penanda topik. Satu bagian rancangan masih tersisa, yaitu angka batas yang memisahkan dua status.

### Frame 7 — Ambang dan Jarak Pengaman

Kawasan: Meja Rancangan

Teks di layar:
- Ambang adalah angka pemisah dua status
- Satu batas saja: status berpindah bolak-balik
- Pakai dua batas, naik dan turun
- Selisihnya disebut jarak pengaman atau histeresis
- Contoh: bahaya `35`, kembali aman `34`

Yang Anda ucapkan:
> Ambang adalah angka batas yang memisahkan dua status, dan cara Anda menetapkannya menentukan tenang atau tidaknya sistem. Bila hanya ada satu angka batas, nilai sensor yang bergerak-gerak tepat di sekitarnya akan membuat status berpindah bolak-balik dengan cepat, sehingga LED berkedip tidak wajar dan data terkirim jauh lebih sering daripada yang diperlukan. Karena itu pakai dua batas, satu untuk naik ke status bahaya dan satu lagi sedikit lebih rendah untuk kembali aman, dan selisih di antaranya disebut jarak pengaman atau histeresis. Contoh dari materi ini, status menjadi bahaya pada 35 derajat tetapi baru kembali aman pada 34 derajat, sehingga nilai antara 34 dan 35 tidak mengubah apa pun. Materi ini mengumpamakannya sebagai pendingin ruangan yang disetel 24 derajat, kompresornya tidak menyala dan mati setiap kali suhu bergeser sepersepuluh derajat, melainkan menyala pada 25 dan berhenti pada 23, dan jeda itulah yang membuat mesinnya awet. Perhatikan bahwa bagian ini punya bobot penilaian sendiri, sebab aktuator harus berubah tepat pada ambang yang Anda tetapkan dan tidak berkedip di daerah jarak pengaman. Rancangan sudah lengkap, tinggal memilih jalur pengiriman datanya.

### Frame 8 — Memilih MQTT atau HTTP

Kawasan: Meja Rancangan

Teks di layar:
- MQTT: kirim ke topik, pelanggan langsung menerima
- HTTP: kirim permintaan, lalu tunggu jawaban
- Pengiriman berulang jarak pendek: MQTT lebih ringan
- Buktikan lewat klien MQTT atau halaman layanan
- Nama topik unik, simpan sebagai konstanta

Yang Anda ucapkan:
> Kedua jalur ini sudah Anda coba, HTTP pada pertemuan tentang pengiriman data ke layanan web dan MQTT pada Pertemuan 7 tentang publish dan subscribe, dan keduanya boleh dipakai selama data benar-benar sampai ke penerima. Tabel pada Bab 5 materi pertemuan ini meringkas perbedaannya, MQTT mengirim ke topik pada broker sehingga siapa pun yang berlangganan topik itu langsung menerimanya, sedangkan HTTP mengirim permintaan ke satu alamat layanan lalu menunggu jawaban. Kecocokannya pun berbeda, MQTT untuk pengiriman berulang dengan jarak waktu pendek dan pesan kecil, sedangkan HTTP untuk pengiriman jarang atau bila Anda memang membutuhkan jawaban dari layanan tujuan. Cara membuktikan data sampai juga berbeda, pada MQTT Anda berlangganan topik yang sama dari klien MQTT lalu melihat pesan masuk, sedangkan pada HTTP Anda membuka halaman atau riwayat data pada layanan tujuan. Untuk keempat kasus tadi MQTT biasanya lebih ringan karena datanya kecil dan dikirim berulang, dan contoh program pada Bab 8 materi pertemuan ini memang memakai MQTT, tetapi bila Anda memilih HTTP susunan programnya tetap sama dan yang berubah hanya bagian pengirimannya. Yang perlu diperhatikan, nama topik harus unik agar tidak tertukar dengan data orang lain, dan simpanlah nama topik atau alamat tujuan sebagai konstanta di bagian atas program supaya cukup satu baris yang diubah, dan nilai itulah yang dicantumkan di laporan. Sebelum mulai merakit, ketahui lebih dahulu bukti apa yang harus Anda kumpulkan.

### Frame 9 — Isi Laporan dan Empat Pertanyaan

Kawasan: Ruang Kerja

Teks di layar:
- Laporan: diagram, kutipan log, penjelasan alur
- Kutipan sepuluh sampai lima belas baris
- Kutipan harus memuat satu perpindahan status
- Empat pertanyaan dijawab dengan menunjuk baris program
- Program berjalan tanpa dijelaskan belum menunjukkan pemahaman

Yang Anda ucapkan:
> Laporan disiapkan bersamaan dengan pengerjaan, sehingga Anda tidak perlu menjalankan ulang sistem hanya untuk mengambil tangkapan layar yang terlewat. Isinya tiga hal, yaitu diagram sistem dari bagian 4.1 materi pertemuan ini yang diperbarui bila rangkaian akhirnya berbeda dari rencana, kutipan log serial sepuluh sampai lima belas baris yang memuat setidaknya satu perpindahan status, dan penjelasan alur data mulai dari asal angka, cara angka menjadi status, reaksi aktuator, sampai tujuan pengirimannya. Alasan kutipan log harus memuat perpindahan status sederhana saja, sebab kutipan dengan satu status saja tidak membuktikan aturan logika bekerja. Bagian yang paling menentukan adalah kemampuan menjelaskan program sendiri, karena program yang berjalan tetapi tidak dapat dijelaskan tidak menunjukkan pemahaman. Uji diri Anda dengan empat pertanyaan pada Bab 6 materi pertemuan ini dan jawablah dengan menunjuk baris programnya, yaitu baris mana yang mengubah angka mentah menjadi satuan bermakna beserta asal angka pengalinya, apa yang terjadi bila nilai sensor berada tepat di antara kedua ambang dan mengapa, bagian mana yang menentukan seberapa sering data dikirim beserta akibatnya bila jeda itu diperkecil, dan bagaimana Anda tahu data benar-benar keluar dari perangkat, bukan hanya tercetak di log serial. Tabel pada Bab 8.1 materi pertemuan ini dapat Anda pakai sebagai pembanding jawaban, dan bila mengerjakan berpasangan, saling melontarkan keempat pertanyaan itu adalah latihan yang paling efektif. Sekarang kita rakit sistemnya langkah demi langkah.

### Frame 10 — Langkah Perakitan di Simulator

Kawasan: Ruang Kerja

Teks di layar:
- Sensor terbaca dahulu, uji, baru tambah bagian
- Potensiometer pin `34`, LED pin `2`, buzzer `15`
- Langkah 3 sampai 6 tanpa jaringan sama sekali
- Baru sambungkan Wi-Fi, broker, lalu berlangganan topik
- Hasil: log, LED, buzzer, pesan klien cocok

Yang Anda ucapkan:
> Sekarang kita jalankan urutan pada Bab 7.2 materi pertemuan ini memakai kasus alarm suhu, dan Anda mengerjakan urutan yang sama nanti. Proyek ESP32 baru dibuat dengan nama yang memuat penanda Anda, lalu potensiometer, LED, resistor, dan buzzer dipasang sesuai tabel bagian 7.1, yaitu kaki tengah potensiometer ke pin `34`, kaki panjang LED ke pin `2` melalui resistor, dan kaki positif buzzer ke pin `15`. Programnya dibangun bertahap, mula-mula hanya membaca pin analog dan mencetaknya sampai angkanya terbukti berubah ketika potensiometer diputar, lalu perhitungan pengubah angka menjadi derajat ditambahkan, kemudian kedua pin keluaran disiapkan beserta aturan logika dengan dua ambang, dan jarak pengaman diuji dengan memutar potensiometer perlahan sampai nilainya berada di antara kedua ambang. Perhatikan bahwa langkah tiga sampai enam dikerjakan tanpa jaringan sama sekali, dan itu disengaja, sebab sensor, aturan logika, dan aktuator sepenuhnya berada di tangan Anda, sehingga ketika masalah muncul setelah jaringan masuk, yang perlu dicurigai hanyalah bagian jaringan. Baru sesudah itu penyambungan Wi-Fi ditambahkan memakai jaringan terbuka simulator dengan kata sandi kosong dan alamat IP dicetak, kemudian penyambungan ke broker beserta pengirimannya ditambahkan lengkap dengan keterangan berhasil atau gagal, lalu klien MQTT dibuka untuk berlangganan topik yang dipakai. Yang harus terlihat ada empat, log serial mencetak nilai suhu, status, dan keterangan pengiriman tanpa terputus, LED dan buzzer hidup bersamaan ketika status menjadi bahaya lalu mati bersamaan ketika kembali aman, status tidak berpindah bolak-balik ketika nilai berada di antara kedua ambang, dan klien MQTT menerima pesan pada topik Anda dengan isi yang sama dengan log serial. Simpan proyek setiap kali satu langkah berhasil supaya Anda dapat kembali ke keadaan terakhir yang baik, dan bila hasilnya belum seperti itu, materi ini sudah menyediakan daftar gejala beserta penyebabnya.

### Frame 11 — Jika Hasilnya Tidak Seperti Itu

Kawasan: Ruang Kerja

Teks di layar:
- Log kosong: kecepatan serial tidak sama
- Nilai selalu `0` atau `4095`: sambungan salah
- LED mati saat bahaya: pemasangan terbalik
- Status berkedip: kedua ambang bernilai sama
- Terkirim tetapi tidak diterima: nama topik berbeda

Yang Anda ucapkan:
> Tabel pada Bab 7.4 materi pertemuan ini memuat lima gejala yang paling sering muncul beserta cara memeriksanya. Log serial yang kosong biasanya berarti kecepatan serial pada program berbeda dengan jendela log, jadi keduanya harus sama-sama 115200. Nilai sensor yang selalu 0 atau 4095 menunjukkan kaki potensiometer tersambung ke pin yang salah atau satu kaki sisi belum tersambung, sehingga pastikan kaki tengah menuju pin 34 sedangkan kedua kaki sisi menuju 3V3 dan GND. LED yang tidak menyala meski status bahaya umumnya karena arah pemasangannya terbalik atau nomor pin di program berbeda dari rangkaian, sedangkan status yang berkedip cepat berarti kedua ambang bernilai sama sehingga tidak ada jarak pengaman, dan lebar histeresisnya harus lebih besar dari nol dengan ambang turun lebih rendah daripada ambang naik. Gejala terakhir yang paling menjebak adalah log menyatakan terkirim tetapi klien tidak menerima apa pun, dan penyebabnya nama topik atau alamat broker tidak sama persis di kedua sisi, jadi salinlah nama topik apa adanya karena huruf besar kecil dan garis miring berpengaruh. Satu keterangan yang sering diabaikan padahal paling menolong adalah kode kesalahan yang dicetak saat penyambungan broker gagal, sebab angka itu membedakan sambungan jaringan yang tidak sampai ke broker, sambungan yang terbentuk lalu ditolak, dan nama klien yang bertabrakan dengan nama klien orang lain pada broker publik yang sama. Karena itu jangan hanya mencetak kata gagal, cetak juga kodenya, dan bila satu langkah tetap macet kembalikan program ke tahap terakhir yang berhasil lalu tambahkan satu bagian saja.

### Frame 12 — Log Serial sebagai Bukti

Kawasan: Ruang Kerja

Teks di layar:
- Dua baris pertama membuktikan jaringan bekerja
- `status=BAHAYA` pada `36.02` membuktikan ambang naik
- Tetap bahaya pada `35.40`: jarak pengaman bekerja
- Kembali aman pada `33.71`, di bawah `34.00`
- Ambil log saat status berpindah, bukan diam

Yang Anda ucapkan:
> Contoh log serial pada Bab 8.2 materi pertemuan ini perlu Anda baca sebagai bukti, bukan sebagai hiasan. Dua baris pertama membuktikan bagian jaringan bekerja, karena papan mendapat alamat IP lalu broker menerima sambungannya. Baris berikutnya membuktikan sensor terbaca dan aturan logika belum memutuskan bahaya meski nilai 34,88 sudah dekat ke ambang, lalu baris dengan suhu 36,02 dan status bahaya membuktikan ambang naik bekerja. Baris sesudahnya yang menunjukkan suhu 35,40 tetapi statusnya tetap bahaya justru membuktikan jarak pengaman bekerja, sebab batas untuk kembali aman adalah 34,00 derajat, dan baris terakhir dengan 33,71 membuktikan ambang turun bekerja. Keterangan terkirim ke di ujung setiap baris membuktikan bagian keempat, yaitu komunikasi data, ikut berjalan pada setiap putaran. Karena satu kutipan log dapat membuktikan semua itu sekaligus, ambil log Anda pada saat status berpindah, bukan pada saat nilainya diam, sebab log sepanjang tiga puluh baris yang seluruhnya berstatus aman hampir tidak membuktikan apa pun selain program berjalan. Mari kita padatkan seluruh aturan tadi menjadi daftar pemeriksaan diri.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 8

Kawasan: Penutup

Teks di layar:
- Keutuhan alur dinilai, bukan kerumitan rangkaian
- Empat bagian harus ada dalam satu program
- Dua ambang membuat keputusan tetap tenang
- Bukti diterima penerima, bukan sekadar tercetak
- Checkpoint: sensor, aktuator, pengiriman, penjelasan sendiri

Yang Anda ucapkan:
> Mari kita rangkum. Yang dinilai adalah keutuhan alur bukan kerumitan rangkaian, sistem Anda harus memuat empat bagian sekaligus yaitu sensor, aktuator, log serial, dan pengiriman data ke luar perangkat, keempat kasus pada Bab 3 materi pertemuan ini berkerangka sama dan hanya berbeda pada pin masukan, rumus pengubah angka, serta arah perbandingan, ambang tunggal membuat status berkedip sedangkan dua ambang dengan jarak pengaman membuat keputusan tenang dan pengiriman tidak berlebihan, MQTT dan HTTP sama-sama boleh dengan penentunya berupa bukti data diterima di sisi penerima, dan bukti laporan dikumpulkan sambil mengerjakan. Checkpoint pertemuan ini, yang rinciannya ada pada Bab 12 materi pertemuan ini, memeriksa empat hal, yaitu sensor virtual terbaca, output aktuator bereaksi, komunikasi data keluar dari perangkat, dan program dapat Anda jelaskan sendiri bukan hanya berjalan. Cara memastikannya sudah disediakan, keadaan sensor diubah lalu perubahan angkanya dilihat pada log serial, nilai diputar melewati ambang untuk memastikan LED dan buzzer berubah bersamaan lalu daerah jarak pengaman diuji, topik Anda dilanggan dari klien MQTT lalu pesan yang masuk dicocokkan dengan baris log serial, dan keempat pertanyaan pada Bab 6 dijawab dengan menunjuk baris programnya. Target minimalnya adalah Anda mampu membangun satu sistem kecil secara utuh, dari pembacaan sensor sampai data terkirim ke luar perangkat, dan menjelaskan setiap tahapnya. Pertemuan ini adalah CP-2 dari empat checkpoint besar mata kuliah ini, dan hasilnya dinilai sebagai UTS praktik berbobot 20 persen dari nilai akhir. Tinggal satu hal lagi, yaitu apa yang dikumpulkan dan bagaimana bobot penilaiannya.

### Frame 14 — Yang Dikumpulkan dan Bobot Penilaian

Kawasan: Penutup

Teks di layar:
- Kumpulkan proyek simulator yang dapat dijalankan
- Laporan singkat dua sampai tiga halaman
- Tangkapan layar sisi penerima data
- Sensor 20%, aktuator 20%, komunikasi 20%
- Laporan 25%, penjelasan program sendiri 15%

Yang Anda ucapkan:
> Tugas pertemuan ini ada pada Bab 11 materi pertemuan ini, yaitu membangun satu sistem IoT sederhana di simulator yang memuat sensor, aktuator, log serial, dan pengiriman data melalui MQTT atau HTTP, memakai salah satu kasus pada Bab 3 atau kasus lain yang setara. Yang dikumpulkan ada empat, yaitu tautan atau berkas proyek simulator yang dapat dijalankan dengan nama proyek yang memuat penanda Anda, laporan singkat dua sampai tiga halaman berisi diagram sistem, kutipan log serial, dan penjelasan alur data sesuai Bab 6, tangkapan layar sisi penerima data berupa klien MQTT yang berlangganan topik Anda atau halaman layanan tujuan bila memakai HTTP, serta keterangan ambang yang dipakai beserta alasannya termasuk lebar jarak pengamannya. Bila Anda mengerjakan berpasangan, cantumkan pembagian pekerjaannya. Bobotnya terbagi lima, yaitu sensor virtual terbaca 20 persen, aktuator bereaksi terhadap aturan logika 20 persen, komunikasi data keluar dari perangkat 20 persen, laporan singkat 25 persen, dan kemampuan menjelaskan program sendiri 15 persen. Perhatikan bahwa laporan dan penjelasan bersama-sama berbobot 40 persen, jadi bagian tulisan bukan pelengkap melainkan setara dengan sistem yang berjalan, dan kriteria nilai penuhnya menuntut hal yang spesifik, yaitu nilai sensor sudah diubah ke satuan bermakna dan bukan angka mentah, aktuator berubah tepat pada ambang serta tidak berkedip di daerah jarak pengaman, data diterima di sisi penerima dengan isi yang sesuai log serial dan dibuktikan lewat tangkapan layar, kutipan log memuat perpindahan status, serta keempat pertanyaan pada Bab 6 dijawab dengan menunjuk baris program yang bersangkutan. Dan inilah jawaban lengkap pertanyaan pembuka kita, penggabungan menuntut hal baru karena Anda harus menjaga agar bagian yang satu tidak merusak bagian yang lain, dan karena bukti keberhasilannya kini bukan lagi satu bagian yang jalan, melainkan alur utuh dari angka sensor sampai pesan yang benar-benar diterima di sisi penerima, ditambah kemampuan Anda menjelaskan setiap tahapnya.
