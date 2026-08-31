# Prezi Pertemuan 14 — Implementasi Mini Project di Simulator

## Kanvas utama

Saat Prezi dibuka dan sebelum zoom pertama, yang terlihat adalah sebuah tangga berisi tujuh anak tangga yang naik dari kiri bawah ke kanan atas, dengan judul pertemuan di sudut kiri atas, panel rangkaian simulator digambar di dasar tangga, dan halaman dashboard di puncaknya. Enam kawasan topik ditata mengikuti tangga itu: dua kawasan pembuka berada di dasar tangga, dua kawasan tengah menempel pada anak tangga yang berurusan dengan bentuk program dan nama topik, dan dua kawasan terakhir berada di puncak tangga serta di ruang terbuka di sebelah kanannya. Jalur zoom karena itu bercerita seperti pendakian yang tidak boleh melompat: setiap perhentian menambahkan satu lapis dan menyebutkan bukti yang harus terlihat sebelum kaki Anda pindah ke anak tangga berikutnya, sampai pada perhentian terakhir seluruh tangga terlihat sebagai satu sistem yang datanya bergerak dua arah.

- Kawasan 1: Pembuka dan Ruang Lingkup — pertanyaan pemancing, capaian pembelajaran, dan batas target minimal.
- Kawasan 2: Tangga Integrasi — tujuh tahap pembangunan beserta bukti pada tiap tahap.
- Kawasan 3: Program yang Terbaca — fungsi bertugas tunggal dan cara membaca program contoh.
- Kawasan 4: Nama dan Arah Pesan — pola penamaan topik, dashboard dua arah, dan bukti data bergerak.
- Kawasan 5: Ruang Praktik — catatan kemajuan, penyusunan prototipe tahap demi tahap, dan kesalahan yang sering terjadi.
- Kawasan 6: Penutup dan Tugas — ringkasan sekaligus checkpoint, lalu tugas latihan beserta pokok penilaiannya.

## Alur zoom

1. Pembuka: Dari Rancangan ke Prototipe
2. Capaian Pembelajaran Pertemuan Ini
3. Rancangan Diuji oleh Implementasi
4. Tujuh Tahap dengan Buktinya
5. Fungsi Bertugas Tunggal
6. Membaca Program Mulai dari loop()
7. Pola dan Aturan Nama Topik
8. Dashboard Dua Arah dan Mode
9. Bukti Data Benar-benar Bergerak
10. Catatan Kemajuan dan Permintaan Bantuan
11. Praktik Menyusun Prototipe Bertahap
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 14
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Pembuka: Dari Rancangan ke Prototipe

Kawasan: Pembuka dan Ruang Lingkup

Teks di layar:
- Pertemuan 14: Implementasi Mini Project di Simulator
- Rancangan Pertemuan 13 dijalankan, bukan dibaca lagi
- Pertanyaan: kapan prototipe boleh disebut selesai?
- Tidak ada lagi contoh yang berdiri sendiri

Yang Anda ucapkan:
> Pertemuan ini mengubah rancangan mini project menjadi prototipe yang benar-benar berjalan di simulator, yaitu ketika sensor virtual, logika kontrol, pengiriman data melalui MQTT, dan dashboard akhirnya bekerja sebagai satu sistem utuh.
> Bedanya dengan pertemuan sebelumnya adalah tidak ada lagi contoh tunggal yang berdiri sendiri, sebab semua yang pernah Anda kerjakan terpisah harus disatukan, dan pekerjaan menyatukan itulah yang punya kesulitan tersendiri.
> Simpan satu pertanyaan ini sepanjang presentasi: kapan prototipe Anda boleh disebut selesai, dan dengan bukti apa Anda menyatakannya?
> Yang perlu Anda siapkan adalah rancangan yang Anda susun pada Pertemuan 13 tentang perancangan mini project, satu proyek simulator ESP32 di browser, klien MQTT untuk memantau topik, dan Node-RED yang sudah terpasang sejak Pertemuan 10 tentang dashboard.
> Tidak ada perangkat lunak baru yang perlu dipasang dan tidak ada perangkat keras yang dibutuhkan, sedangkan mini project simulator ini berbobot dua puluh persen dari nilai akhir.
> Kita mulai dari sasaran pertemuan ini supaya Anda tahu apa yang harus dapat Anda lakukan sendiri setelahnya.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Pembuka dan Ruang Lingkup

Teks di layar:
- Memahami prototipe dibangun lapis demi lapis
- Memecah program menjadi fungsi bertugas tunggal
- Menamai topik MQTT dengan pola konsisten
- Menguji tiap lapisan sebelum menambah lapisan berikutnya
- Menyiapkan permintaan bantuan yang jelas saat macet

Yang Anda ucapkan:
> Ada empat hal yang perlu Anda pahami, yaitu alasan prototipe dibangun lapis demi lapis dan bukan dirakit sekaligus lalu diuji sekali di akhir, cara memecah program menjadi fungsi yang masing-masing punya satu tugas jelas, prinsip penamaan topik MQTT yang konsisten sehingga aliran data mudah ditelusuri, serta peran catatan kemajuan sebagai alat penelusuran kesalahan sekaligus bahan laporan akhir.
> Sisi keterampilannya juga empat, yaitu menyusun prototipe bertahap dengan urutan sensor terbaca dahulu lalu aktuator lalu publish lalu dashboard, menguji tiap lapisan secara objektif sebelum menambah lapisan berikutnya, menjalankan logika kontrol berbasis ambang dan mengendalikannya dari dashboard, serta menyiapkan permintaan bantuan yang jelas ketika pekerjaan terhenti.
> Perhatikan kata objektif pada butir kedua, sebab menguji berarti melihat bukti yang dapat ditunjuk, bukan merasa yakin bahwa bagian itu seharusnya sudah jalan.
> Fokus pertemuan ini adalah mewujudkan rancangan menjadi prototipe yang berjalan di simulator, lengkap dengan integrasi sensor virtual, MQTT, dan dashboard.
> Butir tentang meminta bantuan sengaja dijadikan capaian, karena pekerjaan yang terhenti berhari-hari hampir selalu berhenti karena pertanyaannya belum pernah disusun dengan jelas.
> Sebelum menyentuh simulator, kita perjelas dahulu hubungan antara dokumen rancangan Anda dan prototipe yang akan berjalan.

### Frame 3 — Rancangan Diuji oleh Implementasi

Kawasan: Pembuka dan Ruang Lingkup

Teks di layar:
- Dokumen belum bisa benar atau salah
- Tiap baris rancangan menjadi kode, sambungan, atau node
- Rancangan berubah sedikit itu wajar, asal dicatat
- Target minimal: satu sensor, satu aktuator, satu dashboard
- Satu sensor terbukti lebih bernilai daripada empat setengah jadi

Yang Anda ucapkan:
> Hasil kerja Pertemuan 13 tentang perancangan mini project masih berupa dokumen, yaitu daftar sensor, aktuator, aturan kontrol, daftar topik, dan gambaran dashboard, dan dokumen itu belum bisa benar atau salah karena belum pernah dijalankan.
> Pertemuan ini mengubah statusnya, sebab setiap baris rancangan diterjemahkan menjadi kode, sambungan rangkaian, atau node dashboard, lalu diuji apakah benar-benar berperilaku seperti yang tertulis.
> Terimalah sejak awal bahwa rancangan hampir selalu berubah sedikit saat diimplementasikan dan itu justru tanda implementasi sedang menguji rancangan, sedangkan yang tidak boleh terjadi adalah perubahan yang tidak dicatat, karena laporan akhir harus menjelaskan sistem yang sebenarnya berjalan.
> Rancangan seperti denah rumah yang terlihat rapi di kertas, tetapi begitu dinding didirikan ternyata jalur pipa dan jalur kabel bertemu di titik yang sama sehingga denahnya disesuaikan, dan tidak ada bangunan yang selesai tanpa penyesuaian semacam itu.
> Target minimal mini project sengaja dibuat sempit, yaitu minimal satu sensor, satu aktuator, dan satu dashboard bekerja, data benar-benar bergerak dari perangkat ke platform, dan logika kontrol berjalan sesuai rancangan.
> Karena itu sistem dengan satu sensor yang seluruh jalurnya terbukti bekerja bernilai lebih tinggi daripada sistem dengan empat sensor yang jalur datanya setengah jadi.
> Ruang lingkupnya sudah jelas, jadi sekarang kita tetapkan urutan pengerjaannya, sebab urutan itulah yang paling menentukan.

### Frame 4 — Tujuh Tahap dengan Buktinya

Kawasan: Tangga Integrasi

Teks di layar:
- Tahap 1 sampai 3: sensor, aktuator, kontrol lokal
- Tahap 4 dan 5: jaringan, lalu publish berkala
- Tahap 6 dan 7: dashboard, lalu perintah balik
- Tiap tahap punya bukti sebelum lapisan berikutnya
- Simpan salinan setiap tahap yang sudah berhasil

Yang Anda ucapkan:
> Yang paling menentukan keberhasilan pertemuan ini bukan kemampuan menulis kode melainkan urutan pengerjaan, sebab bila seluruh program ditulis sekaligus lalu angka tidak muncul di dashboard, penyebabnya bisa berada di tujuh tempat sekaligus tanpa petunjuk, yaitu pin sensor, nilai ambang, koneksi Wi-Fi, alamat broker, nama topik, bentuk payload, atau sambungan node dashboard.
> Bila lapisan ditambahkan satu per satu dan tiap lapisan sudah terbukti bekerja, penyebab kerusakan hampir pasti ada pada penambahan terakhir, sama seperti instalasi listrik rumah yang dipasang dan diuji per jalur dan tidak pernah disambung seluruhnya lebih dahulu.
> Tiga tahap pertama seluruhnya di dalam perangkat, yaitu satu sensor terbaca di Serial Monitor dengan angka wajar yang berubah ketika nilai sensor digeser, satu aktuator dipaksa hidup-mati langsung dari kode tanpa sensor supaya masalah aktuator terpisah dari masalah logika, lalu keduanya dihubungkan aturan ambang sehingga aktuator berubah tepat di titik ambang dan Serial Monitor mencetak alasannya.
> Tahap keempat dan kelima membawa perangkat ke jaringan, yaitu koneksi Wi-Fi dan broker yang dibuktikan dengan alamat IP serta keterangan broker terhubung, baru sesudah itu nilai sensor dikirim berkala ke topik telemetri sampai klien MQTT dari Pertemuan 7 tentang MQTT menerimanya pada topik yang benar dengan periode tetap.
> Tahap keenam dan ketujuh berada di sisi dashboard, yaitu flow yang berlangganan topik telemetri sampai nilai di dashboard sama dengan nilai di klien MQTT, lalu tombol yang mengirim ke topik perintah sampai keadaan aktuator berubah dan isi perintah tercetak di Serial Monitor sebagai bukti data dua arah.
> Aturan yang sama berlaku dalam ukuran kecil di dalam tiap tahap, yaitu ubah satu hal, jalankan, amati, baru ubah hal berikutnya, seperti yang sudah dilatih pada Pertemuan 5 tentang penggabungan sensor-aktuator dan penelusuran kesalahan.
> Setiap kali satu tahap terbukti bekerja, simpan salinannya dengan nama seperti `miniproject-tahap3-kontrol-lokal` supaya selalu ada titik aman untuk kembali, dan supaya program sepanjang itu tetap terbaca, bentuknya kita atur sekarang.

### Frame 5 — Fungsi Bertugas Tunggal

Kawasan: Program yang Terbaca

Teks di layar:
- Semua ditumpuk di `loop()` sulit ditelusuri
- Satu fungsi satu hal, namanya kata kerja
- `bacaSensor()` mengambil nilai, memeriksa, lalu menyimpannya
- `setKipas()` satu-satunya tempat mengubah pin aktuator
- Butuh kata "dan" untuk menamai? Pecah fungsinya

Yang Anda ucapkan:
> Program mini project jauh lebih panjang daripada latihan mingguan sebelumnya, dan bila seluruh isinya ditumpuk di dalam `loop()`, tiga masalah muncul sekaligus, yaitu sulit dibaca ulang keesokan hari, sulit dicari letak kesalahannya, dan sulit dijelaskan saat demo akhir.
> Aturan praktisnya satu, yaitu satu fungsi mengerjakan satu hal dan namanya adalah kata kerja yang menyebutkan hal itu, sehingga bila Anda sulit memberi nama sebuah fungsi tanpa memakai kata dan, biasanya fungsi itu mengerjakan dua hal dan sebaiknya dipecah.
> Tabel pada Bab 3 materi pertemuan ini memuat lima contoh: `bacaSensor()` mengambil nilai sensor, memeriksa kewajarannya, lalu menyimpannya ke satu variabel tanpa menyalakan aktuator atau mengirim data, sedangkan `kendaliOtomatis()` membandingkan nilai itu dengan ambang tanpa membaca sensor lagi, karena nilai baru bisa berbeda dari yang dipakai keputusan sebelumnya.
> Sisanya mengikuti pola yang sama, yaitu `setKipas()` mengubah keadaan aktuator dan melaporkan keadaan barunya tanpa mengambil keputusan sendiri, `kirimTelemetri()` menyusun payload lalu mengirimkannya ke topik telemetri tanpa mengubah nilai apa pun, dan `saatPerintahMasuk()` menerjemahkan perintah dari dashboard menjadi tindakan tanpa pekerjaan panjang, sebab fungsi itu dipanggil tepat saat pesan tiba.
> Pembagian ini langsung menolong ketika dashboard berhenti diperbarui, sebab Anda tidak perlu membaca seluruh program: nilai di Serial Monitor yang masih berubah berarti `bacaSensor()` sehat, sehingga pemeriksaan menyempit ke `kirimTelemetri()` dan koneksi broker.
> Bentuk seperti ini sudah dipakai pada program contoh pertemuan ini, dan cara membacanya perlu satu catatan tersendiri.

### Frame 6 — Membaca Program Mulai dari loop()

Kawasan: Program yang Terbaca

Teks di layar:
- Mulai membaca dari `loop()` di bagian bawah
- Seluruh alur kerja terlihat dalam sepuluh baris
- Konstanta di atas: pin, jaringan, broker, topik
- `AMBANG_NYALA` 30,0 dan `AMBANG_MATI` 28,5 berjarak
- `suhuTerakhir` diberi nilai awal `NAN`

Yang Anda ucapkan:
> Program contoh pada Bab 9 materi pertemuan ini menggabungkan seluruh lapisan menjadi satu berkas, memakai sensor suhu DHT22 pada pin 15 dan kipas pada pin 23, sedangkan nama, pin, dan topiknya perlu Anda ganti sesuai rancangan sendiri.
> Cara membacanya sebaiknya dibalik, yaitu mulai dari `loop()` di bagian paling bawah, sebab di sana terlihat seluruh alur kerja sistem dalam sepuluh baris, yaitu menjaga koneksi, melayani pesan masuk, lalu setiap lima detik membaca sensor, memutuskan keadaan aktuator, dan mengirim data.
> Setelah alur besar itu jelas, barulah naik ke setiap fungsi untuk melihat rinciannya, karena membaca dari baris pertama justru menghabiskan perhatian Anda pada deklarasi sebelum Anda tahu untuk apa deklarasi itu dipakai.
> Bagian atas berisi konstanta, yaitu nomor pin, nama jaringan, alamat broker, dan tiga nama topik, sehingga satu perubahan cukup dilakukan di satu tempat, dan di bawahnya ada empat variabel yang menjadi ingatan sistem, yaitu waktu pengiriman terakhir, nilai suhu terakhir, keadaan kipas, dan penanda mode manual.
> Keempat variabel itu ditulis di luar semua fungsi supaya nilainya tetap hidup di antara putaran `loop()`, dan `suhuTerakhir` diberi nilai awal `NAN` sebagai penanda bukan angka supaya nilai nol yang terlihat wajar tidak pernah dianggap hasil pengukuran sebelum sensor sempat dibaca.
> Dua ambang sengaja dibuat berbeda, yaitu `AMBANG_NYALA` bernilai 30,0 dan `AMBANG_MATI` bernilai 28,5, dan jarak sebesar 1,5 derajat itulah yang mencegah kipas hidup-mati berulang di sekitar satu nilai.
> Satu hal pada program itu berulang di tiga tempat berbeda dan paling sering menjadi sumber kesalahan, yaitu nama topik, jadi polanya kita bahas sekarang.

### Frame 7 — Pola dan Aturan Nama Topik

Kawasan: Nama dan Arah Pesan

Teks di layar:
- Nama topik dipakai di program, klien, flow
- Pola `<nama-proyek>/<id-perangkat>/<besaran-atau-alat>/<arah>`
- Contoh `miniproject/esp32-01/kipas/perintah`
- Huruf kecil semua, telemetri terpisah dari perintah
- Tulis nama topik sekali sebagai konstanta

Yang Anda ucapkan:
> Pada mini project, tiap nama topik dipakai di tiga tempat sekaligus, yaitu program perangkat, klien MQTT saat pengujian, dan flow dashboard, sehingga satu huruf berbeda di salah satu tempat membuat data seolah hilang tanpa pesan kesalahan.
> Broker tidak pernah mengeluh soal nama topik yang salah, sebab ia hanya meneruskan pesan kepada yang berlangganan nama yang persis sama, karena itu tentukan polanya sekali di awal, tulis polanya di catatan Anda, lalu ikuti tanpa kecuali.
> Pola pada Bab 4 materi pertemuan ini menyusun nama proyek, identitas perangkat, besaran atau alat, lalu arah, sehingga muncul tiga topik, yaitu `miniproject/esp32-01/suhu/data` untuk nilai suhu terbaru, `miniproject/esp32-01/kipas/status` untuk keadaan aktuator berupa `ON` atau `OFF`, dan `miniproject/esp32-01/kipas/perintah` untuk permintaan pengguna berupa `ON`, `OFF`, atau `AUTO`.
> Lima aturan menjaga topik tetap terkendali, yaitu pakai huruf kecil semua dan pemisah yang seragam karena bagi broker `Suhu` dan `suhu` adalah dua topik berbeda, pisahkan topik telemetri dari topik perintah agar perangkat tidak menerima kembali pesan yang ia kirim sendiri, sertakan identitas perangkat pada setiap topik, hindari spasi serta tanda `+` dan `#` yang punya arti khusus saat berlangganan, dan tulis setiap nama topik hanya sekali sebagai konstanta di bagian atas program.
> Aturan terakhir itu paling sering diabaikan, padahal nama topik yang diketik ulang di beberapa tempat adalah sumber kesalahan satu huruf yang paling sulit ditemukan, sebab program tetap berjalan tanpa keluhan apa pun.
> Ingat juga bahwa broker publik dipakai bersama banyak orang sehingga awalan yang terlalu umum seperti `test/suhu` hampir pasti sudah dipakai orang lain dan dashboard Anda bisa menampilkan angka dari perangkat yang bukan milik Anda, jadi pakailah awalan unik yang menyertakan nomor identitas Anda dan jangan mengirim data pribadi melalui broker terbuka, sebagai lanjutan Pertemuan 12 tentang keamanan dan keandalan.
> Dengan nama topik yang tertib, dashboard kini dapat dipasang di ujung jalur data sekaligus dipakai memerintah.

### Frame 8 — Dashboard Dua Arah dan Mode

Kawasan: Nama dan Arah Pesan

Teks di layar:
- Dashboard menampilkan data dan mengirim perintah
- Keduanya dibangun serta diuji terpisah
- Kipas menyala sedetik lalu mati sendiri
- Dua pengambil keputusan berebut satu aktuator
- Penanda mode: `ON` dan `OFF` manual, `AUTO` otomatis

Yang Anda ucapkan:
> Dashboard punya dua pekerjaan yang arahnya berlawanan, yaitu menampilkan data dari topik telemetri dan mengubah tekanan tombol menjadi pesan ke topik perintah, dan keduanya dibangun serta diuji terpisah sesuai tahap keenam dan tahap ketujuh.
> Cara membangun flow-nya sudah Anda pelajari pada Pertemuan 10 tentang dashboard Node-RED, dan yang baru di sini hanyalah bahwa flow itu harus cocok dengan payload perangkat Anda sendiri, bukan payload contoh.
> Penamaan node dan susunan panel tidak selalu sama antarversi dan node dashboard tersedia dalam beberapa generasi, jadi kenali node dari fungsinya, yaitu yang menerima pesan dari broker, yang mengubah teks menjadi objek, dan yang menampilkan nilai pada halaman.
> Begitu dashboard dapat memerintah, muncul persoalan yang sering disalahartikan sebagai kerusakan: Anda menekan tombol untuk menyalakan kipas, kipas menyala satu detik, lalu mati sendiri karena logika otomatis melihat suhu masih di bawah ambang dan mematikannya kembali.
> Yang terjadi adalah dua pengambil keputusan sedang berebut satu aktuator, dan penyelesaiannya menyimpan satu penanda mode di dalam perangkat, sehingga perintah manual mengubah mode menjadi manual dan logika ambang berhenti ikut campur, sedangkan perintah `AUTO` menyerahkan kendali kembali kepada aturan ambang.
> Setelah kedua arah bekerja, tinggal satu hal yang harus Anda jawab dengan bukti, yaitu apakah angka yang tampil itu benar-benar datang dari perangkat Anda.

### Frame 9 — Bukti Data Benar-benar Bergerak

Kawasan: Nama dan Arah Pesan

Teks di layar:
- Angka di dashboard bisa berasal dari nilai tertinggal
- Geser nilai sensor, amati dashboard mengikutinya
- Sertakan satu nilai yang selalu berubah
- Tekan tombol, cari pesannya di Serial Monitor
- Tombol menampilkan keadaan sendiri, bukan keadaan perangkat

Yang Anda ucapkan:
> Salah satu butir penilaian adalah data benar-benar bergerak dari perangkat ke platform, bukan sekadar angka yang muncul di dashboard, sebab angka itu bisa saja berasal dari nilai yang tertinggal, dari data lama yang disimpan broker, atau dari pekerjaan orang lain pada topik yang sama.
> Cara membuktikannya sederhana, yaitu geser nilai sensor di simulator lalu perhatikan apakah angka di dashboard mengikutinya dalam satu periode pengiriman.
> Bukti itu menjadi lebih kuat bila payload Anda membawa satu nilai yang selalu berubah, misalnya nomor urut pengiriman atau waktu berjalan perangkat dalam detik, karena dashboard yang berhenti diperbarui langsung terlihat dari nomor yang berhenti bertambah.
> Tanpa nilai seperti itu, angka suhu bisa saja kebetulan bernilai sama beberapa kali berturut-turut dan menyembunyikan masalah, sedangkan pada demo akhir penguji dapat melihat sendiri bahwa data yang tampil benar-benar baru tanpa Anda perlu menjelaskannya.
> Lakukan pembuktian yang sama pada arah sebaliknya, yaitu tekan tombol dashboard lalu perhatikan Serial Monitor perangkat, sebab pesan perintah yang tercetak di sana adalah bukti bahwa perintah benar-benar menempuh jalur dashboard, broker, dan perangkat.
> Bila aktuator berubah tetapi tidak ada pesan yang tercetak, yang berubah bukan perangkat Anda melainkan tampilan pada dashboard saja, dan kekeliruan itu paling sering terjadi ketika tombol dashboard diatur menampilkan keadaannya sendiri alih-alih keadaan yang dilaporkan perangkat melalui topik status.
> Pekerjaan sebesar ini berjalan beberapa hari, jadi sebelum masuk ke ruang praktik kita siapkan dahulu cara mencatatnya.

### Frame 10 — Catatan Kemajuan dan Permintaan Bantuan

Kawasan: Ruang Praktik

Teks di layar:
- Ingatan memburuk lebih cepat daripada dugaan Anda
- Satu tabel: tanggal, tahap, dicoba, hasil, keputusan
- Contoh: kedua ambang sama, kipas hidup-mati cepat
- Saat macet siapkan gejala, log terakhir, percobaan
- Jangan menunda sampai tenggat sudah dekat

Yang Anda ucapkan:
> Pekerjaan mini project berjalan beberapa hari dan ingatan tentang apa saja yang sudah dicoba memburuk lebih cepat daripada dugaan Anda, sehingga catatan kemajuan bukan formalitas, sebab ia mencegah Anda mengulangi percobaan yang sudah gagal sekaligus menjadi bahan laporan akhir pada Pertemuan 16 tentang demo akhir dan laporan.
> Bentuknya cukup satu tabel berisi tanggal, tahap, yang dicoba, hasil, dan keputusan berikutnya, lalu diisi setiap kali Anda berhenti bekerja.
> Dua contoh baris pada Bab 6 materi pertemuan ini memperlihatkan bentuk yang benar, yaitu ambang nyala dan ambang mati sama-sama bernilai 30 sehingga kipas hidup-mati cepat di sekitar nilai itu, dengan keputusan berikutnya memberi jarak antara kedua ambang.
> Baris kedua mencatat angka yang disambungkan langsung dari node masukan MQTT sehingga yang tampil satu baris teks JSON dan bukan angka, dengan keputusan menambahkan penguraian payload sebelum node tampilan.
> Akan ada saat ketika satu tahap tidak mau bergerak walaupun sudah diperiksa berulang kali, dan itu bagian normal dari pekerjaan membangun sistem sehingga Anda boleh meminta bantuan, sedangkan yang perlu dihindari hanya dua hal, yaitu menunda sampai tenggat sudah dekat dan meminta bantuan dengan keterangan kabur sehingga penolong harus menebak lebih dahulu.
> Siapkan tiga hal, yaitu gejalanya berupa apa yang Anda harapkan, apa yang sebenarnya terjadi, dan pada tahap keberapa, lalu beberapa baris terakhir Serial Monitor yang disalin apa adanya termasuk pesan kesalahan beserta angka kodenya dan bukan diringkas dengan kata sendiri, serta daftar singkat pemeriksaan yang sudah Anda lakukan beserta hasilnya.
> Dengan catatan yang rapi, kita masuk ke ruang praktik dan menyusun prototipenya tahap demi tahap.

### Frame 11 — Praktik Menyusun Prototipe Bertahap

Kawasan: Ruang Praktik

Teks di layar:
- Catat nomor pin yang benar-benar dipakai
- Cetak sensor tiap dua detik, geser nilainya
- Ambang berjarak: nyala 30,0 dan mati 28,5
- Publish tiap lima detik memakai pembanding `millis()`
- Tombol `ON`, `OFF`, `AUTO` ke topik perintah

Yang Anda ucapkan:
> Kita ikuti kedelapan langkah pada Bab 7 materi pertemuan ini di depan kelas, dan aturannya satu, yaitu jangan lanjut ke langkah berikutnya sebelum bukti pada langkah itu benar-benar terlihat.
> Langkah pertama membuka proyek simulator ESP32 baru, memasang satu sensor dan satu aktuator sesuai rancangan, lalu mencatat nomor pin yang benar-benar dipakai di panel rangkaian, dan langkah kedua menulis kerangka program yang hanya membaca sensor dan mencetaknya ke Serial Monitor tiap dua detik sampai angkanya mengikuti ketika nilai sensor digeser.
> Langkah ketiga menambahkan `pinMode` untuk aktuator lalu memaksa keadaannya berganti tiap dua detik tanpa melibatkan sensor sampai perubahan terlihat di panel rangkaian, dan pemaksaan itu dihapus sesudahnya, sedangkan langkah keempat menambahkan aturan ambang dengan dua nilai berjarak, yaitu nyala pada 30,0 dan mati pada 28,5, sampai Serial Monitor mencetak alasan tiap perubahan.
> Langkah kelima menambahkan koneksi Wi-Fi simulator dan koneksi broker tanpa mengirim data sampai alamat IP beserta keterangan broker terhubung tercetak, dan langkah keenam menambahkan pengiriman berkala ke topik telemetri memakai pembanding `millis()` dengan periode lima detik, lalu isi yang diterima klien MQTT dibandingkan dengan Serial Monitor.
> Langkah ketujuh membuat flow Node-RED yang berlangganan topik telemetri, menguraikan payload JSON, lalu menampilkannya sebagai angka dan grafik, sedangkan langkah kedelapan menambahkan tombol yang mengirim `ON`, `OFF`, dan `AUTO` ke topik perintah lalu mendaftarkan perangkat pada topik itu beserta penanda modenya.
> Yang harus terlihat di akhir ada tiga, yaitu klien MQTT menerima payload pada topik telemetri dengan periode tetap dan isi yang sama dengan Serial Monitor, dashboard menampilkan angka, indikator keadaan aktuator, dan grafik tren yang bergerak mengikuti nilai sensor, serta tombol dashboard mengubah keadaan aktuator dalam hitungan detik dengan perintah `AUTO` yang mengembalikan kendali kepada aturan ambang.
> Bila yang Anda lihat berbeda dari ketiga hal itu, gejalanya biasanya sudah ada di daftar berikut.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Praktik

Teks di layar:
- Nilai sensor nol: pin atau `begin()` terlewat
- Aktuator hidup-mati cepat: kedua ambang bernilai sama
- Berhenti sebelum wifi terhubung: kata sandi diisi
- Klien menerima, dashboard kosong: payload belum diuraikan
- Perintah tidak sampai: langganan belum didaftarkan ulang

Yang Anda ucapkan:
> Tabel penelusuran masalah pada Bab 8 materi pertemuan ini memuat lima gejala, dan urutannya mengikuti tahap tempat gejala itu biasanya muncul.
> Bila nilai sensor tercetak nol atau tidak berupa angka, kemungkinannya pin salah, sensor belum diinisialisasi, atau pembacaan terlalu rapat, jadi bandingkan nomor pin dengan panel rangkaian lalu periksa pemanggilan `begin()` dan jarak antarpembacaan.
> Bila aktuator hidup-mati sangat cepat, ambang nyala dan ambang mati bernilai sama, sehingga keduanya perlu diberi jarak seperti pada langkah keempat.
> Bila program berhenti setelah baris pertama dan tidak pernah mencapai keterangan wifi terhubung, biasanya nama jaringan salah atau kata sandi diisi padahal jaringan simulator tidak memakai kata sandi, jadi tulis nama jaringan tepat seperti yang disediakan simulator dan biarkan kata sandinya berupa teks kosong, sebab fungsi penyambung memang menunggu sampai berhasil sehingga program yang tampak menggantung di titik itu hampir selalu berarti sambungan belum pernah terjadi.
> Bila klien MQTT menerima data tetapi dashboard tetap kosong, topik pada flow tidak sama atau payload JSON belum diuraikan, jadi bandingkan nama topik huruf per huruf lalu periksa node penguraiannya.
> Bila data terkirim tetapi perintah dari dashboard tidak pernah sampai, pastikan pendaftaran langganan berada tepat setelah koneksi berhasil dan bukan di dalam `setup()` saja, bandingkan nama topik perintah di kedua sisi, lalu cetak setiap pesan yang masuk lebih dahulu sebelum memeriksa isinya supaya pesan yang tidak sampai dapat dibedakan dari pesan yang sampai tetapi tidak dikenali.
> Sekarang kita rangkum pertemuan ini sekaligus memeriksa diri sebelum tugas dikumpulkan.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 14

Kawasan: Penutup dan Tugas

Teks di layar:
- Rancangan baru terbukti benar setelah dijalankan
- Tujuh tahap, tiap tahap punya bukti objektif
- Fungsi bertugas tunggal memudahkan penelusuran dan demo
- Nama topik satu pola, ditulis sebagai konstanta
- Checkpoint: sensor, aktuator, dashboard, data bergerak

Yang Anda ucapkan:
> Mari kita kumpulkan intinya: rancangan baru terbukti benar setelah dijalankan, dan perubahan kecil saat implementasi wajar asalkan dicatat.
> Prototipe dibangun tujuh tahap berurutan dan tiap tahap punya bukti objektif sebelum lapisan berikutnya ditambahkan, sedangkan program dipecah menjadi fungsi bertugas tunggal supaya mudah dibaca, mudah ditelusuri, dan mudah dijelaskan saat demo.
> Nama topik ditetapkan satu pola di awal lalu ditulis sebagai konstanta karena kesalahan satu huruf tidak menghasilkan pesan kesalahan apa pun, sementara catatan kemajuan mencegah percobaan yang sama diulang dan permintaan bantuan disiapkan dengan gejala, log terakhir, serta daftar yang sudah dicoba.
> Checkpoint pada Bab 13 materi pertemuan ini menuntut target minimal berupa satu sensor, satu aktuator, dan satu dashboard bekerja, data benar-benar bergerak dari perangkat ke platform, serta logika kontrol berjalan sesuai rancangan.
> Cara memastikannya sendiri ada lima, yaitu jalankan simulasi tanpa menyentuh kode sampai sensor terbaca dan aktuator berubah sendiri, geser nilai sensor lalu amati klien MQTT dan dashboard mengikuti dalam satu periode kirim, lewati kedua ambang dan pastikan Serial Monitor mencetak alasan tiap perubahan, tekan tombol lalu kembalikan kendali dengan perintah `AUTO`, dan periksa apakah tiap baris catatan punya kolom hasil dan keputusan berikutnya.
> Bila satu butir belum tercapai, materi pertemuan ini menunjuk tempat kembalinya, misalnya ulangi langkah pertama sampai keempat pada Bab 7 bila prototipe belum berjalan, atau baca ulang Bab 5 bila dashboard belum dapat memerintah.
> Pertemuan ini adalah bagian dari perjalanan menuju checkpoint keempat pada Pertemuan 16 tentang demo akhir dan laporan, dan setelah checkpoint hari ini terpenuhi, tinggal tugasnya yang perlu Anda selesaikan.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup dan Tugas

Teks di layar:
- Mini project berjalan utuh di simulator
- Kumpulkan program dan tangkapan layar rangkaian
- Tangkapan dashboard saat menampilkan dan saat memerintah
- Catatan kemajuan sekurang-kurangnya lima baris kejadian
- Bobot: aliran data `25%`, dashboard dua arah `25%`

Yang Anda ucapkan:
> Tugas Anda adalah menyelesaikan mini project sampai berjalan utuh di simulator, yaitu sensor virtual terbaca, logika kontrol berjalan, data terkirim melalui MQTT, dan dashboard menampilkan data sekaligus dapat mengirim perintah.
> Yang dikumpulkan ada tiga, yaitu berkas program prototipe yang berjalan beserta tangkapan layar rangkaian simulator, tangkapan layar dashboard saat menampilkan data dan saat perintah dikirim, serta catatan kemajuan berisi sekurang-kurangnya lima baris kejadian ditambah tangkapan layar Serial Monitor yang menunjukkan alasan perubahan aktuator.
> Penilaiannya terbagi menjadi sensor dan aktuator bekerja `20%`, logika kontrol `20%`, aliran data MQTT `25%`, dashboard dua arah `25%`, dan catatan kemajuan `10%`.
> Kriteria nilai penuhnya perlu Anda perhatikan, yaitu nilai sensor wajar dan berubah serta aktuator berubah sesuai keputusan program, aturan ambang berjalan dengan dua nilai berjarak dan alasan tiap perubahan tercetak, pengiriman berkala pada topik berpola konsisten yang terbukti diterima klien MQTT, perintah dari dashboard yang benar-benar mengubah keadaan perangkat, serta kejadian yang ditulis sebagai kenyataan teramati beserta keputusan berikutnya.
> Bobot terbesar berada pada dua butir yang menuntut bukti pergerakan data, jadi tuntaskan dahulu jalur satu sensor sebelum menambah apa pun, sesuai target minimal yang sengaja dibuat sempit.
> Ingat pula bahwa mini project simulator ini berbobot dua puluh persen dari nilai akhir, sedangkan tugas latihan mingguan berbobot dua puluh persen tersendiri.
> Pertanyaan pembuka tadi kini terjawab: prototipe Anda disebut selesai ketika satu sensor, satu aktuator, dan satu dashboard bekerja, ketika angka di dashboard bergerak mengikuti nilai sensor yang Anda geser, dan ketika perintah yang Anda tekan tercetak di Serial Monitor sebagai bukti bahwa data menempuh kedua arah.
