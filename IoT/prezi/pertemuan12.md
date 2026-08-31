# Prezi Pertemuan 12 — Keamanan dan Keandalan Dasar Sistem IoT

## Kanvas utama

Saat Prezi dibuka dan sebelum zoom pertama, yang terlihat adalah satu device kecil di tengah kanvas yang dikelilingi dua lapis, yaitu lapis dalam berupa saringan bundar tempat angka harus lewat, dan lapis luar berupa gerbang berpalang yang setengahnya masih terbuka. Di sisi kiri kanvas berdiri gerbang itu dengan tiga gembok yang diberi nama tanda tangan, amplop, dan kartu identitas kurir, dan seikat kunci tergantung di dekatnya; di sisi kanan, jalur jaringan yang menuju broker digambar terpotong, dengan empat celah yang makin lebar dan diberi angka satu, dua, empat, dan delapan detik. Di bawah keduanya membentang satu panel log dari kiri ke kanan, berisi baris-baris berawalan seragam, dan panel itu sengaja memayungi seluruh gambar karena di situlah semua kejadian meninggalkan jejak. Enam kawasan topik ditata mengikuti bentuk tersebut, sehingga jalur zoom bercerita seperti pemeriksaan bertahap: Anda mulai dari gerbang untuk menentukan siapa yang berhak berbicara, mampir ke seikat kunci yang selama ini ikut berpindah tangan, menyeberang ke jalur yang terputus untuk melihat apa yang terjadi ketika sambungan hilang, masuk ke saringan untuk memilih angka yang boleh lewat, lalu turun ke panel log tempat semuanya dibuktikan sebelum presentasi ditutup.

- Kawasan 1: Pembuka dan Sasaran — pertanyaan pemancing dan capaian pembelajaran pertemuan ini.
- Kawasan 2: Sisi Keamanan — alasan device diincar, autentikasi, enkripsi, dan sertifikat.
- Kawasan 3: Ruang Kredensial — kredensial sebagai tetapan bernama beserta risiko dasar dan pencegahannya.
- Kawasan 4: Sisi Keandalan — empat kegagalan yang nyata, jejak pada log, dan jeda yang bertambah.
- Kawasan 5: Ruang Saringan dan Uji — validasi nilai, demo tiga kegagalan sengaja, dan kesalahan yang sering terjadi.
- Kawasan 6: Penutup dan Tugas — ringkasan sekaligus checkpoint CP-3, lalu tugas latihan beserta penilaiannya.

## Alur zoom

1. Pembuka: Sistem yang Layak Dipercaya
2. Capaian Pembelajaran Pertemuan Ini
3. Mengapa Device Kecil Diincar
4. Autentikasi, Enkripsi, dan Otorisasi
5. Username dan Password pada MQTT
6. Broker Publik dan Sambungan Terenkripsi
7. Kredensial dan Risiko Dasar
8. Empat Kegagalan yang Nyata
9. Jeda Bertambah Menggantikan Coba Seketika
10. Validasi, Rentang Wajar, dan Penolakan
11. Demo Tiga Kegagalan yang Disengaja
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 12
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Pembuka: Sistem yang Layak Dipercaya

Kawasan: Pembuka dan Sasaran

Teks di layar:
- Pertemuan 12: Keamanan dan Keandalan Dasar IoT
- Keamanan: hanya pihak berhak mengirim dan membaca
- Keandalan: tetap masuk akal ketika jaringan terputus
- Pertanyaan: bagaimana Anda tahu sistem tahan gangguan?
- Dan mengapa kesalahan keamanan tidak memberi peringatan?

Yang Anda ucapkan:
> Dua sifat membuat sebuah sistem IoT layak dipercaya, yaitu keamanan yang berarti hanya pihak berhak yang boleh mengirim dan membaca data, dan keandalan yang berarti sistem tetap masuk akal ketika jaringan terputus, broker tidak menjawab, atau sensor mengirim angka yang tidak mungkin benar.
> Sampai sekarang program Anda belum punya keduanya, sebab sambungan dibuka tanpa identitas apa pun dan seluruh program berdiri di atas anggapan bahwa Wi-Fi selalu tersambung serta broker selalu menjawab.
> Simpan dua pertanyaan ini sampai akhir presentasi: bagaimana Anda tahu sistem Anda benar-benar tahan gangguan, dan mengapa kesalahan keamanan tidak pernah memberi peringatan.
> Pertanyaan kedua itu penting karena sistem yang topicnya dapat ditulisi siapa saja tetap berjalan dan tetap menampilkan angka, dan yang berubah hanya asal angkanya.
> Yang perlu Anda siapkan adalah program pengiriman MQTT yang sudah berjalan dari Pertemuan 7 tentang MQTT, simulator Wokwi atau board ESP32 Anda, dan Serial Monitor, tanpa pustaka baru di luar `WiFi` dan `PubSubClient`.
> Pertemuan ini sekaligus menjadi checkpoint besar CP-3, jadi kita mulai dari sasarannya supaya Anda tahu apa yang harus dapat Anda lakukan sendiri setelahnya.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Pembuka dan Sasaran

Teks di layar:
- Alasan device IoT menjadi sasaran serangan
- Membedakan pemeriksaan identitas dan penyembunyian isi
- Menyalakan autentikasi username dan password MQTT
- Menulis validasi yang menolak nilai tidak wajar
- Sambungan ulang memakai `millis()` dengan jeda bertambah

Yang Anda ucapkan:
> Capaian pemahaman pertemuan ini ada empat, yaitu alasan device IoT menjadi sasaran meski datanya tampak sederhana, perbedaan autentikasi sebagai pemeriksaan identitas dengan enkripsi sebagai penyembunyian isi, jenis kegagalan yang benar-benar terjadi pada sistem IoT beserta akibatnya bagi data, dan alasan mencoba ulang tanpa jeda justru memperburuk keadaan.
> Sisi keterampilannya juga empat, yaitu menyalakan autentikasi username dan password pada sambungan MQTT, menulis fungsi validasi yang menolak nilai sensor di luar rentang wajar, membuat logika sambungan ulang memakai `millis()` dengan jeda bertambah, dan menguji sistem dengan kegagalan yang dibuat sengaja lalu membaca buktinya pada log.
> Lima hal yang dibahas sepanjang pertemuan adalah autentikasi sederhana, kerahasiaan data pada tingkat konsep, penanganan koneksi yang gagal, mekanisme mencoba ulang, dan validasi masukan.
> Perhatikan butir keterampilan yang terakhir, sebab yang dinilai di sini bukan pernyataan Anda bahwa sistem sudah tahan gangguan, melainkan jejak yang dicetak program.
> Jalur pengirimannya berasal dari Pertemuan 7 tentang MQTT, sedangkan cara menghitung waktu tanpa `delay()` dari Pertemuan 9 tentang pengaturan waktu pengiriman dipakai agar sambungan ulang tidak membekukan program.
> Kita mulai dari pertanyaan yang paling sering dianggap tidak relevan, yaitu mengapa device sekecil itu diincar.

### Frame 3 — Mengapa Device Kecil Diincar

Kawasan: Sisi Keamanan

Teks di layar:
- Yang dicari bukan angka suhunya
- Daya komputasi dan sambungan jaringannya
- Pintu masuk ke jaringan tempat device berada
- Data yang menceritakan kebiasaan manusia
- Kesalahan keamanan tidak menimbulkan pesan kesalahan

Yang Anda ucapkan:
> Device pengukur suhu ruangan tampak terlalu remeh untuk diserang, padahal yang dicari penyerang bukan angka suhunya melainkan tiga hal lain.
> Pertama daya komputasi dan sambungan jaringannya, yang bila dikuasai secara massal dapat dipakai membanjiri sasaran lain tanpa pemiliknya merasakan apa pun; kedua pintu masuk ke jaringan tempat device berada, karena device yang lemah sering satu jaringan dengan komputer dan berkas penting; ketiga datanya sendiri, bila data itu menceritakan kebiasaan manusia.
> Contoh yang paling mudah dibayangkan, pola pemakaian listrik satu rumah sudah cukup untuk menyimpulkan kapan rumah itu kosong.
> Bayangkan jendela kamar mandi di lantai dua yang dibiarkan tidak terkunci karena tidak ada barang berharga di sana, padahal bukan kamar mandi yang diincar melainkan jalan masuk ke seluruh rumah lewat titik yang paling tidak diawasi.
> Yang membuat urusan ini licin adalah kesalahan keamanan tidak menimbulkan pesan kesalahan, sebab sistem yang topicnya dapat ditulisi siapa saja tetap berjalan dan tetap menampilkan angka.
> Karena itu keamanan dipikirkan sejak perancangan dan bukan ketika ada gejala, jadi kita mulai dengan membedakan dua istilah yang sering dipakai bergantian.

### Frame 4 — Autentikasi, Enkripsi, dan Otorisasi

Kawasan: Sisi Keamanan

Teks di layar:
- Autentikasi: siapa yang sedang berbicara
- Enkripsi: dapatkah isinya dibaca di tengah jalan
- Otorisasi: apa yang boleh Anda lakukan
- Keduanya berdiri sendiri; sistem serius memakai keduanya
- Tanpa enkripsi, sandi berjalan sebagai teks biasa

Yang Anda ucapkan:
> Autentikasi dan enkripsi sering dipakai bergantian, padahal keduanya menjawab pertanyaan yang berbeda.
> Autentikasi menjawab siapa yang sedang berbicara, yaitu broker memeriksa apakah pengirim berhak sebelum menerima pesannya, sedangkan enkripsi menjawab apakah isi pembicaraan dapat dibaca pihak lain di tengah jalan, dengan mengubah pesan menjadi bentuk yang tidak bermakna kecuali bagi pemegang kuncinya.
> Keduanya berdiri sendiri: sambungan boleh terenkripsi tanpa autentikasi sehingga isinya rahasia namun siapa pun boleh ikut mengirim, dan boleh berautentikasi tanpa enkripsi sehingga username dan sandinya berjalan sebagai teks biasa yang dapat dibaca penyadap jaringan, sementara sistem yang serius memakai keduanya sekaligus.
> Istilah ketiga adalah otorisasi, yang menentukan apa yang boleh Anda lakukan setelah dikenali, misalnya hanya boleh menulis ke `kelas/iot/lab01/` dan tidak boleh membaca topic kelompok lain.
> Bentuk paling sederhana dari keduanya juga berbeda, yaitu username dan password pada broker untuk autentikasi, dan sambungan TLS pada port terpisah untuk enkripsi.
> Kita mulai dari yang paling murah dan sudah dapat Anda kerjakan hari ini, yaitu satu baris tambahan pada pembukaan sambungan.

### Frame 5 — Username dan Password pada MQTT

Kawasan: Sisi Keamanan

Teks di layar:
- `mqtt.connect(CLIENT_ID, MQTT_USER, MQTT_PASS)`
- Perubahannya hanya sebaris pada pembukaan sambungan
- Yang memeriksa bukan program, melainkan broker
- Penolakan terbaca sebagai kode lewat `mqtt.state()`
- `CLIENT_ID` harus unik pada satu broker

Yang Anda ucapkan:
> Pada Pertemuan 7 tentang MQTT, sambungan dibuka tanpa identitas apa pun, yaitu cukup alamat broker, nomor port, dan sebuah nama klien.
> Protokol MQTT menyediakan tempat untuk username dan password di dalam paket pembuka sambungan, dan `PubSubClient` menyediakannya sebagai dua argumen tambahan, sehingga perubahannya hanya sebaris menjadi `mqtt.connect(CLIENT_ID, MQTT_USER, MQTT_PASS)`.
> Yang menentukan bukan program pengirim melainkan broker, sebab bila broker tidak diatur memeriksa identitas, username dan password diterima apa adanya dan sambungan tetap berhasil meski sandinya salah.
> Bila broker memeriksa, identitas yang salah ditolak dan penolakannya terbaca sebagai kode kegagalan lewat `mqtt.state()`, dengan catatan nilai kodenya berbeda antarversi pustaka sehingga yang perlu Anda kenali adalah polanya, yaitu sambungan gagal berulang sementara Wi-Fi jelas sudah tersambung.
> Ada satu jebakan yang mudah dikira gangguan jaringan: nama klien harus unik pada satu broker, sebab bila dua device memakai `CLIENT_ID` yang sama, broker memutus yang lebih dahulu setiap kali yang lain menyambung sehingga keduanya bergantian terputus.
> Karena brokerlah yang menentukan, pertanyaan berikutnya adalah broker seperti apa yang Anda pakai sekarang.

### Frame 6 — Broker Publik dan Sambungan Terenkripsi

Kawasan: Sisi Keamanan

Teks di layar:
- Broker publik sengaja terbuka bagi siapa saja
- Topic Anda dapat dibaca dan ditulisi
- Nama topic aneh hanya menyulitkan penebakan
- Port `1883` teks biasa, `8883` memakai TLS
- Sertifikat membuktikan broker itu memang brokernya

Yang Anda ucapkan:
> Broker publik untuk belajar sengaja dibuat terbuka, sebab siapa pun boleh menyambung, menulis, dan berlangganan ke topic apa pun.
> Artinya topic Anda dapat dibaca orang yang menebak namanya dan, yang lebih berbahaya, dapat ditulisi sehingga dashboard Anda menampilkan angka yang bukan berasal dari sensor Anda; nama topic yang panjang dan aneh hanya menyulitkan penebakan, dan keamanan yang bersandar pada kerahasiaan nama disebut keamanan lewat ketersamaran, yang bukan keamanan.
> Broker publik juga dapat dimatikan tanpa pemberitahuan, jadi untuk latihan hal itu tidak masalah, tetapi begitu data yang lewat mulai berarti pindahkan ke broker berautentikasi milik sendiri, misalnya Mosquitto di komputer Anda atau layanan broker berakun.
> Sambungan MQTT biasa berjalan pada port 1883 dan isinya lewat sebagai teks biasa, sehingga siapa pun yang mengamati lalu lintas jaringan itu, misalnya pemilik Wi-Fi umum di kafe, dapat membaca nama topic, isi pesan, serta username dan password Anda.
> Versi terenkripsinya berjalan pada port terpisah yang lazimnya 8883 dan memakai TLS, mekanisme yang sama yang mengamankan halaman web, dan TLS mengerjakan dua hal, yaitu menyembunyikan isi sehingga penyadap hanya melihat data tanpa makna, serta membuktikan lewat sertifikat bahwa broker yang dihubungi memang broker yang dimaksud.
> Bila diibaratkan pengiriman surat, autentikasi adalah tanda tangan pada suratnya, enkripsi adalah amplop tertutup, dan sertifikat adalah kartu identitas kurir.
> Anda belum perlu memasang TLS sendiri pada tahap ini, tetapi ketahuilah tuntutannya, yaitu port berbeda, sertifikat pihak terpercaya di dalam device, jam device yang kira-kira benar karena sertifikat punya masa berlaku, serta memori dan waktu pemrosesan lebih banyak; sekarang kita urus sesuatu yang sudah ada di dalam kode Anda hari ini.

### Frame 7 — Kredensial dan Risiko Dasar

Kawasan: Ruang Kredensial

Teks di layar:
- Kredensial: sandi Wi-Fi, identitas broker, kunci layanan
- Bahayanya bukan pembacaan device, tetapi kode berpindah
- Kumpulkan sebagai tetapan bernama di paling atas
- Ganti isinya dengan `"GANTI_DENGAN_SANDI_ANDA"` sebelum dikumpulkan
- Jangan tampilkan sandi pada tangkapan layar maupun log

Yang Anda ucapkan:
> Nama jaringan Wi-Fi, sandinya, username dan sandi broker, serta kunci layanan cloud dari Pertemuan 11 tentang penyimpanan data dan visualisasi tren semuanya termasuk kredensial.
> Bahayanya bukan karena orang lain dapat membaca kode di dalam device, melainkan karena kode berpindah tangan, yaitu diunggah ke penyimpanan bersama, dilampirkan pada laporan, dan disalin ke berkas contoh, sedangkan setiap perpindahan menyalin sandi Anda dan sandi yang sudah tersebar tidak dapat ditarik kembali.
> Langkah terpenting untuk tahap ini adalah memisahkan kredensial dari logika, yaitu mengumpulkan semuanya sebagai tetapan bernama di bagian paling atas program, lalu mengganti isinya dengan penanda seperti `"GANTI_DENGAN_SANDI_ANDA"` sebelum tugas dikumpulkan.
> Dua kebiasaan wajib ditinggalkan: jangan menampilkan sandi pada tangkapan layar maupun pada log karena keduanya dibaca dan dibagikan, dan jangan memakai sandi akun pribadi pada device latihan sebab device latihan adalah bagian paling lemah dari sistem apa pun.
> Tabel pada Bab 4 materi pertemuan ini memuat lima risiko yang paling sering benar-benar terjadi beserta pencegahannya, misalnya topic yang dapat ditulisi siapa saja membuat dashboard menampilkan suhu 90 derajat yang tidak pernah diukur, dan pencegahannya adalah broker berautentikasi ditambah validasi rentang pada penerima.
> Perhatikan baris terakhir tabel itu, sebab penolakan nilai yang tidak masuk akal muncul sebagai urusan keamanan sekaligus keandalan: data palsu dari penyerang dan data rusak dari sensor yang lepas sama-sama berbentuk angka mustahil, sehingga satu pemeriksaan rentang menangkap keduanya.
> Dengan begitu kita menyeberang dari sisi keamanan ke sisi keandalan, dan yang pertama perlu dikenali di sana adalah kegagalan yang benar-benar terjadi.

### Frame 8 — Empat Kegagalan yang Nyata

Kawasan: Sisi Keandalan

Teks di layar:
- Wi-Fi terputus; device membaca tanpa tujuan pengiriman
- Broker tidak terhubung meski Wi-Fi tersambung
- Sambungan hidup tetapi pesan tidak sampai
- Sensor mengirim `-127`, nol mencurigakan, atau `nan`
- Awalan seragam: `[WIFI]`, `[MQTT]`, `[TOLAK]`, `[KIRIM]`

Yang Anda ucapkan:
> Program pada pertemuan sebelumnya diam-diam berdiri di atas satu anggapan besar, yaitu Wi-Fi selalu tersambung dan broker selalu menjawab, dan selama sepuluh menit pengujian di ruangan yang sama dengan titik akses anggapan itu tampak benar, tetapi dijalankan dua hari ia hampir pasti runtuh.
> Ada empat kegagalan yang benar-benar terjadi, dan dua yang pertama adalah Wi-Fi terputus karena titik akses dinyalakan ulang, sinyal melemah, atau sandinya diganti sehingga device tetap membaca sensor tanpa tujuan pengiriman, serta broker yang tidak dapat dihubungi karena dimatikan, alamatnya salah tulis, atau identitasnya ditolak, dengan gejala khas `WiFi.status()` menunjukkan tersambung sementara `mqtt.connected()` tetap bernilai salah.
> Dua sisanya adalah sambungan yang hidup tetapi pesannya tidak sampai, terlihat dari `publish()` yang mengembalikan nilai salah atau pesan yang hilang tanpa kabar, dan sensor yang mengirim angka tidak mungkin seperti minus 127, nol yang mencurigakan, atau `nan` ketika kabel data lepas sedikit atau sensor belum siap saat dibaca.
> Yang membedakan program latihan dari program yang layak dipercaya bukan ada atau tidaknya kegagalan itu, melainkan tanggapannya, yaitu mencoba lagi, melewati satu putaran, atau mengabarkan keadaan.
> Yang tidak boleh dipilih adalah berhenti tanpa jejak, sebab device tidak punya layar dan tidak dapat ditanyai, sehingga tiap kejadian penting perlu meninggalkan jejak pada log.
> Beri awalan seragam pada setiap baris log seperti `[WIFI]`, `[MQTT]`, `[TOLAK]`, dan `[KIRIM]`, karena awalan mengubah log dari kumpulan kalimat menjadi sesuatu yang dapat disisir, dan awalan itulah yang nanti menjadi bukti bahwa penanganan kegagalan Anda benar-benar bekerja.
> Sekarang kita bahas bagian yang paling sering salah, yaitu seberapa cepat sistem boleh mencoba lagi.

### Frame 9 — Jeda Bertambah Menggantikan Coba Seketika

Kawasan: Sisi Keandalan

Teks di layar:
- Mencoba seketika: ribuan percobaan per menit
- Log terbanjiri, arus terpakai, broker dibanjiri
- Jeda `1`, `2`, `4`, `8` detik sampai batas
- Batas atas satu menit, gangguan sejam 60 baris
- Begitu pulih, jeda dikembalikan ke nilai awal

Yang Anda ucapkan:
> Ketika sambungan gagal, tindakan yang wajar adalah mencoba lagi, dan persoalannya hanya pada seberapa cepat.
> Program yang mencoba lagi seketika di dalam `loop()` mencoba ribuan kali per menit, dengan tiga akibat, yaitu log terisi ribuan baris kegagalan yang sama sehingga pesan penting tidak terlihat, arus listrik terpakai terus-menerus karena modul radio tidak pernah beristirahat, dan bila banyak device melakukannya bersamaan broker yang baru bangun langsung dibanjiri lalu jatuh lagi.
> Menelepon nomor sibuk setiap detik memberi gambaran yang sama, sebab hal itu tidak mempercepat apa pun.
> Jalan keluarnya adalah jeda yang bertambah, yang lazim disebut backoff: percobaan pertama dilakukan setelah satu detik, bila gagal jedanya dikalikan dua menjadi dua detik, lalu empat, delapan, dan seterusnya sampai batas atas yang ditetapkan, misalnya satu menit.
> Bacalah akibatnya pada tabel Bab 5 materi pertemuan ini, sebab gangguan satu jam hanya menghasilkan sekitar enam puluh baris log dan bukan puluhan ribu, sementara batas atas itu diperlukan agar jedanya tidak tumbuh tanpa henti sehingga device tidak menunggu berjam-jam meski jaringan sudah pulih.
> Begitu sambungan berhasil, jeda dikembalikan ke nilai awal supaya gangguan berikutnya ditangani cepat lagi, dan pada saat yang sama program mengirim status `"online"` sebagai pesan tersimpan di broker sehingga dashboard yang baru dibuka langsung menerima keadaan terakhir yang dilaporkan.
> Perhitungan jedanya memakai `millis()` seperti pada Pertemuan 9 tentang pengaturan waktu tanpa `delay()`, sebab menunggu dengan `delay()` membekukan seluruh program termasuk pembacaan sensor; setelah sambungan diurus, angka yang mau dikirim masih perlu disaring.

### Frame 10 — Validasi, Rentang Wajar, dan Penolakan

Kawasan: Ruang Saringan dan Uji

Teks di layar:
- Periksa bentuk, rentang, dan kewajaran perubahan
- Rentang dari kemungkinan fisik, bukan kebiasaan
- DS18B20: `-127` kabel lepas, `85` belum siap
- Nilai ditolak dilewati dan dicatat, bukan dinolkan
- Penerima di Node-RED memeriksa sekali lagi

Yang Anda ucapkan:
> Aturannya satu kalimat: setiap angka yang masuk ke sistem diperiksa sebelum dipakai, dikirim, atau disimpan, dan pemeriksaannya dilakukan sedekat mungkin dengan sumbernya, yaitu di dalam device, agar nilai buruk tidak pernah membebani jaringan dan tidak pernah masuk ke berkas riwayat.
> Penerima di Node-RED sebaiknya memeriksa sekali lagi, karena ia tidak dapat memastikan bahwa pengirimnya benar device Anda.
> Ada tiga bentuk pemeriksaan yang menutup hampir semua kasus nyata, yaitu bentuknya benar sehingga hasil pembacaan memang angka dan bukan `nan`, nilainya berada dalam rentang wajar yang ditetapkan dari kenyataan fisik tempat sensor dipasang dan bukan dari kemampuan maksimal sensornya, serta perubahannya masuk akal karena suhu ruangan tidak dapat melompat lima derajat dalam sepuluh detik.
> Tabel rentang pada Bab 6 materi pertemuan ini memuat kolom yang paling sering terlewat, yaitu nilai khas yang justru muncul ketika sensor bermasalah, misalnya pada DS18B20 nilai minus 127 berarti kabel data lepas dan nilai 85 berarti sensor dibaca sebelum selesai bersiap.
> Rentang yang terlalu sempit ikut membuang data benar, sebab bila batas atas suhu ditetapkan 35 derajat karena ruangan biasanya sejuk, pada hari yang benar-benar panas sistem Anda berhenti melaporkan tepat ketika laporannya paling dibutuhkan.
> Yang dilakukan terhadap nilai yang ditolak sama pentingnya dengan penolakannya, jadi jangan menggantinya dengan nol karena nol tampak sah dan ikut dihitung sebagai data, jangan pula menghapusnya tanpa jejak, melainkan lewati satu putaran pengiriman lalu cetak satu baris log yang menyebut nilai yang ditolak beserta alasannya.
> Dengan penolakan yang tercatat seperti itu, penolakan berulang dapat disadari sebagai gejala sensor yang perlu diperiksa; sekarang semuanya kita buktikan dengan kegagalan yang dibuat sengaja.

### Frame 11 — Demo Tiga Kegagalan yang Disengaja

Kawasan: Ruang Saringan dan Uji

Teks di layar:
- Simulator tidak punya tombol mematikan Wi-Fi
- Uji A: ketik `999` lalu `-50`
- Uji B: ketik `p` untuk memutus Wi-Fi
- Uji C: `MQTT_HOST` diganti alamat yang tidak ada
- Hasil: `[TOLAK]` tanpa `[KIRIM]`, jeda bertambah

Yang Anda ucapkan:
> Penanganan kegagalan hanya dapat dipercaya bila pernah diuji, jadi yang dijalankan sekarang adalah program pengiriman yang sudah diubah, lalu tiga kegagalan dibuat dengan sengaja dan tanggapannya dibaca pada Serial Monitor.
> Persiapannya empat langkah, yaitu salinan program dari Pertemuan 7 tentang MQTT disimpan dengan nama baru agar versi yang sudah berjalan tetap utuh, seluruh kredensial dipindahkan ke atas sebagai tetapan sekaligus sambungan diberi username dan password, tetapan batas nilai ditambahkan beserta fungsi `nilaiWajar()`, dan logika sambungan ulang diganti fungsi `jagaSambungan()` yang memakai `millis()` tanpa satu pun `delay()` yang tersisa.
> Simulator tidak menyediakan tombol untuk mematikan Wi-Fi, karena itu gangguan jaringan dibuat dari dalam program, yaitu mengetik `p` pada Serial Monitor memanggil `WiFi.disconnect()`, dan dari sudut pandang program hasilnya sama dengan titik akses yang benar-benar mati.
> Uji A menitipkan nilai di luar rentang dengan mengetik `999` lalu Enter dan diulang dengan `-50`, dan baris `[TOLAK]` harus muncul tanpa baris `[KIRIM]` untuk nilai itu.
> Uji B memutus Wi-Fi dengan mengetik `p`, dan log harus memperlihatkan percobaan penyambungan dengan jeda yang bertambah, misalnya satu, dua, empat, lalu delapan detik, kemudian kembali normal dengan jeda kembali ke nilai awal ketika sambungan pulih.
> Uji C mengganti `MQTT_HOST` menjadi alamat yang tidak ada lalu program dijalankan ulang, dan log harus memperlihatkan Wi-Fi tersambung sementara sambungan broker gagal berulang dengan jeda bertambah, sedangkan sepanjang ketiga uji itu program tetap membaca sensor sehingga lognya tidak pernah membeku.
> Simpan log ketiga uji secara terpisah karena itulah bukti yang dikumpulkan pada tugas, dan langkah lengkapnya ada pada Bab 7 materi pertemuan ini; bila yang Anda lihat berbeda, gejalanya biasanya sudah ada pada daftar berikut.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Saringan dan Uji

Teks di layar:
- Log membanjir tiap detik: jeda tidak dikalikan
- Program membeku: masih ada `delay()` tersisa
- Nilai `999` terkirim: validasi sesudah `publish()`
- Broker gagal terus: identitas atau `CLIENT_ID` bentrok
- Setelah pulih diam: jeda tidak dikembalikan

Yang Anda ucapkan:
> Tabel penelusuran masalah pada Bab 8 materi pertemuan ini memuat lima gejala, dan semuanya terletak pada urutan atau pada satu baris yang terlewat, bukan pada gagasan besarnya.
> Bila log membanjir dengan pesan gagal yang sama tiap detik, jedanya tidak pernah dikalikan atau penanda waktu percobaan tidak diperbarui, jadi periksa baris pengali jeda dan baris yang menyimpan waktu percobaan terakhir.
> Bila program berhenti menanggapi selama gangguan, masih ada `delay()` yang tersisa di jalur sambungan ulang, jadi periksa seluruh isi fungsi sambungan ulang itu.
> Bila nilai `999` tetap terkirim, hasil validasi tidak dipakai atau pemeriksaan dilakukan setelah pengiriman, jadi periksa urutan di dalam `loop()` karena validasi harus mendahului `publish()`.
> Bila sambungan broker gagal terus meski alamatnya benar, identitas Anda ditolak atau nama klien dipakai device lain, jadi baca nilai `mqtt.state()` pada log dan pastikan `CLIENT_ID` Anda unik.
> Bila setelah gangguan pulih data tidak terkirim lagi, jedanya sudah membesar dan tidak pernah dikembalikan ke nilai awal, jadi periksa baris yang mengembalikan jeda ketika sambungan sehat.
> Bila Anda macet dan penyebabnya tidak terlihat pada log, mintalah bantuan teman atau ajukan pertanyaan di kelas dengan menyertakan potongan log beserta bagian program yang Anda ubah; sekarang kita rangkum pertemuan ini.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 12

Kawasan: Penutup dan Tugas

Teks di layar:
- Device diincar karena banyak, menyala, tidak diawasi
- Autentikasi memeriksa, enkripsi menyembunyikan, sertifikat membuktikan
- Broker yang memeriksa identitas, bukan program Anda
- Jeda bertambah sampai batas, lalu kembali awal
- Checkpoint CP-3: validasi, penanganan kegagalan, risiko

Yang Anda ucapkan:
> Mari kita kumpulkan intinya: device IoT diincar bukan karena datanya berharga, melainkan karena ia banyak, selalu menyala, dan hampir tidak diawasi.
> Autentikasi memeriksa siapa yang berbicara, enkripsi menyembunyikan isinya, dan sertifikat membuktikan bahwa broker yang dihubungi memang broker yang dimaksud.
> MQTT menyediakan username dan password pada pembukaan sambungan, tetapi yang memeriksanya adalah broker, sehingga broker publik tidak layak untuk data sungguhan.
> Kredensial dikumpulkan sebagai tetapan di satu tempat karena kode selalu berpindah tangan sementara sandi yang tersebar tidak dapat ditarik kembali.
> Kegagalan yang nyata adalah Wi-Fi terputus, broker tidak terhubung, pesan tidak sampai, dan nilai sensor mustahil, sehingga mencoba ulang memakai jeda bertambah sampai batas atas lalu kembali ke nilai awal begitu pulih, sedangkan validasi memeriksa bentuk, rentang, dan kewajaran perubahan dengan nilai ditolak yang dilewati dan dicatat.
> Pertemuan ini adalah checkpoint besar CP-3, dan Bab 13 materi pertemuan ini menuntut tiga hal, yaitu ada validasi masukan yang benar-benar menolak nilai tidak wajar, ada penanganan kegagalan yang bekerja ketika sambungan terputus, dan Anda dapat menyebutkan risiko dasar sistem IoT beserta pencegahannya.
> Cara memastikannya sendiri: titipkan nilai `999` dan `-50` lewat Serial Monitor sampai keduanya muncul sebagai baris `[TOLAK]` tanpa pengiriman, putuskan Wi-Fi dengan perintah uji lalu periksa apakah jeda pada log bertambah dan kembali ke nilai awal setelah pulih, dan sebutkan tiga risiko beserta pencegahannya tanpa membuka catatan; setelah itu Anda siap mengerjakan tugasnya.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup dan Tugas

Teks di layar:
- Buat skenario kegagalan dan tunjukkan tanggapannya
- Kumpulkan program dengan kredensial sudah diganti penanda
- Tiga potongan log berketerangan dari ketiga uji
- Satu halaman: rentang, jeda, dua risiko terpilih
- Bobot: validasi `30%`, penanganan kegagalan `30%`

Yang Anda ucapkan:
> Tugas Anda adalah membuat skenario kegagalan pada sistem Anda dan menunjukkan bagaimana sistem menanggapinya, dengan ketiga uji tadi dijalankan seluruhnya.
> Buktinya berupa log, bukan pernyataan bahwa sistem sudah tahan gangguan.
> Yang dikumpulkan ada tiga, yaitu berkas program dengan kredensial yang sudah diganti penanda serta memuat fungsi validasi dan sambungan ulang berjeda bertambah, tiga potongan log yang diberi keterangan untuk nilai di luar rentang yang ditolak, Wi-Fi yang terputus lalu pulih, dan broker yang tidak dapat dihubungi, serta satu halaman penjelasan.
> Halaman penjelasan itu memuat rentang wajar yang Anda pakai beserta dasarnya, nilai jeda awal dan batas atasnya beserta alasannya, dan dua risiko dari tabel Bab 4 materi pertemuan ini yang paling mengancam sistem Anda beserta pencegahan yang Anda pilih.
> Penilaiannya terbagi menjadi validasi masukan bekerja `30%`, logika penanganan kegagalan `30%`, bukti pengujian `25%`, serta kredensial dan penjelasan risiko `15%`, dan ingat pula bahwa tugas latihan mingguan berbobot dua puluh persen dari nilai akhir.
> Nilai penuh pada dua bobot terbesar hanya diberikan bila nilai di luar rentang dan nilai bukan angka ditolak, dicatat pada log, dan tidak pernah terkirim, serta bila sambungan ulang memakai `millis()` dengan jeda bertambah dan batas atas, tanpa `delay()`, dan jedanya kembali ke awal setelah pulih.
> Dua pertanyaan pembuka tadi kini terjawab: Anda tahu sistem Anda tahan gangguan hanya bila pernah Anda rusak sendiri lalu jejaknya terbaca pada log, dan kesalahan keamanan tidak memberi peringatan karena sistem yang topicnya dapat ditulisi siapa saja tetap berjalan dengan tenang sambil menampilkan angka yang bukan berasal dari sensor Anda.
