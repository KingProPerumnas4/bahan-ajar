# Prezi Pertemuan 1 — Orientasi Internet of Things dan Lingkungan Kerja Simulator

## Kanvas utama

Saat Prezi dibuka, sebelum zoom pertama, yang terlihat adalah satu bidang lebar berlatar biru muda dengan judul pertemuan di tengah dan sebuah pertanyaan pendek tepat di bawahnya, sementara lima kawasan topik tampak sebagai kelompok kartu kecil yang mengelilinginya. Kawasan itu ditata mengikuti perjalanan data pada materi ini: gerbang masuk di kiri atas, wujud sistem yang sudah jadi di kanan atas, anatomi sistem di tengah, meja kerja simulator di kanan bawah, dan penutup di kiri bawah, sehingga jalur zoom membentuk lingkaran yang kembali ke pertanyaan pembuka. Dengan tata letak seperti itu, perpindahan zoom bercerita seperti bergerak dari gambaran besar, masuk ke bagian-bagiannya, turun ke tangan yang mengerjakan, lalu naik lagi untuk melihat hasilnya secara utuh.

- Kawasan 1: Gerbang Masuk — judul pertemuan, pertanyaan pemancing, dan capaian pembelajaran.
- Kawasan 2: Wujud Sistem IoT — gambaran sistem yang sudah jadi, definisi IoT, contoh penerapan, dan karakteristiknya.
- Kawasan 3: Anatomi Sistem — enam komponen utama, beda monitoring dan kontrol, serta alur lima lapisan.
- Kawasan 4: Meja Kerja Simulator — tiga alat kerja, praktik ESP32 pertama, penelusuran masalah, dan struktur kode.
- Kawasan 5: Penutup — ringkasan, checkpoint evaluasi, dan tugas latihan beserta penilaiannya.

## Alur zoom

1. Orientasi IoT dan Ruang Kerja Simulator
2. Capaian Pembelajaran Pertemuan Ini
3. Gambaran Sistem IoT yang Sudah Jadi
4. Apa Itu Internet of Things
5. Contoh Penerapan dan Karakteristik IoT
6. Enam Komponen Utama Sistem IoT
7. Beda Monitoring dan Sistem Kontrol
8. Alur Sensor Sampai Pengguna
9. Tiga Alat Kerja dan Simulator
10. Praktik Simulasi ESP32 Pertama
11. Bila Hasilnya Tidak Seperti Itu
12. Membaca Struktur Kode Blink
13. Ringkasan dan Checkpoint Pertemuan Ini
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Orientasi IoT dan Ruang Kerja Simulator

Kawasan: Gerbang Masuk

Teks di layar:
- Pertemuan 1: orientasi IoT dan lingkungan kerja simulator
- Hari ini cukup browser dan koneksi internet
- Cukupkah satu angka mengubah perilaku sebuah benda?
- Jawabannya baru lengkap setelah praktik di akhir

Yang Anda ucapkan:
> Selamat datang pada Pertemuan 1, orientasi Internet of Things dan lingkungan kerja simulator. Hari ini Anda tidak perlu membeli perangkat keras dan tidak perlu memasang perangkat lunak apa pun, karena seluruh kegiatan berjalan di browser. Ada satu pertanyaan yang sebaiknya Anda pegang sepanjang presentasi ini: cukupkah satu angka di dalam program untuk mengubah perilaku sebuah benda? Pertanyaan itu baru terjawab lengkap pada praktik di bagian akhir, ketika nilai `delay(1000)` Anda ubah menjadi `delay(200)` dan kedipan LED berubah di depan mata Anda sendiri. Sebelum sampai ke sana, mari kita sepakati lebih dulu apa yang harus Anda kuasai setelah pertemuan ini berakhir.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Gerbang Masuk

Teks di layar:
- Memahami makna IoT dan alur dasarnya
- Mengidentifikasi minimal lima komponen sistem IoT
- Menjelaskan hubungan data sensor, proses, tampilan
- Menjalankan proyek ESP32 pertama di simulator
- Membaca kode dasar Arduino/ESP32 beserta fungsinya

Yang Anda ucapkan:
> Capaian pertemuan ini terbagi dua: hal yang Anda pahami dan hal yang Anda dapat lakukan. Pada sisi pemahaman, Anda perlu menangkap makna Internet of Things sebagai sistem yang menghubungkan benda fisik dengan data dan layanan digital, alur dasar dari sensor sampai user, peran komponen inti, dan fungsi simulator sebagai ruang latihan sebelum memakai perangkat nyata. Pada sisi keterampilan, Anda harus mampu menyebut minimal lima komponen sistem IoT, menjelaskan perjalanan data dari sensor sampai tampilan, membuka dan menjalankan proyek ESP32 pertama di simulator, serta membaca kode dasarnya. Perhatikan bahwa daftar ini tidak menuntut Anda menguasai sintaks: kata `void`, tanda titik koma, dan kurung kurawal cukup Anda terima dulu sebagai bentuk baku. Aktivitas praktiknya pun satu saja, yaitu menjalankan simulasi ESP32 dengan contoh paling sederhana. Supaya arahnya jelas, mari kita lihat lebih dulu wujud akhir sistem yang sedang kita tuju.

### Frame 3 — Gambaran Sistem IoT yang Sudah Jadi

Kawasan: Wujud Sistem IoT

Teks di layar:
- ESP32 membaca suhu ruangan lalu mengirimkan angkanya
- Angka suhu bergerak pada halaman dashboard
- Melewati batas tertentu, kipas menyala sendiri
- Empat titik: mengamati, memproses, jalur, penerima
- Hari ini bagiannya dikenali satu per satu

Yang Anda ucapkan:
> Sebelum masuk ke definisi dan istilah, ada gunanya Anda melihat lebih dulu wujud akhir dari yang akan dipelajari. Bayangkan sebuah sistem yang sudah berjalan: sebuah ESP32 membaca suhu ruangan, mengirimkan angkanya keluar, dan angka itu terlihat bergerak pada sebuah halaman dashboard. Ketika suhunya melewati batas tertentu, kipas menyala dengan sendirinya tanpa disentuh siapa pun. Sistem seperti itu sebenarnya hanya terdiri dari empat titik, dan Bab 0 materi pertemuan ini merumuskannya sebagai empat pertanyaan: apa yang mengamati, apa yang memproses, lewat mana datanya, dan siapa yang menerima hasilnya. Sistem seutuhnya belum akan dibangun hari ini; hari ini bagian-bagiannya dikenali lebih dulu, lalu ditutup dengan praktik menyalakan satu lampu. Pegang keempat pertanyaan itu, sebab setiap bagian berikutnya sesungguhnya sedang menjawab salah satunya, dimulai dari pertanyaan paling dasar tentang apa itu IoT.

### Frame 4 — Apa Itu Internet of Things

Kawasan: Wujud Sistem IoT

Teks di layar:
- Benda fisik mengamati, mengirim data, menerima perintah
- Bukan sekadar alat yang terhubung ke internet
- Tiga alasan penting: monitoring, otomasi, efisiensi
- Perlu objek fisik, data relevan, proses benar
- Ditutup dengan tindak lanjut yang berguna

Yang Anda ucapkan:
> Internet of Things adalah konsep ketika benda fisik diberi kemampuan mengamati kondisi, mengirim data, menerima perintah, atau melakukan aksi otomatis melalui sistem komputasi dan jaringan. Intinya bukan sekadar alat yang terhubung ke internet, melainkan bagaimana alat itu menjadi bagian dari alur data yang menghasilkan keputusan atau tindakan. Contoh paling mudah adalah termometer ruangan digital: sendirian ia hanya menampilkan suhu di layar lokal, tetapi begitu menjadi bagian sistem IoT, angkanya dapat dikirim ke platform, disimpan, divisualisasikan, dianalisis, lalu dipakai untuk menyalakan kipas atau mengirim notifikasi. IoT penting karena tiga hal: memudahkan monitoring secara terus-menerus, memungkinkan otomasi berdasarkan aturan tertentu seperti lampu menyala saat ruangan gelap, dan membuat pemakaian sumber daya lebih efisien. Yang perlu Anda catat, sistem IoT baru bernilai bila ada objek fisik, data yang relevan, proses yang benar, dan tindak lanjut yang berguna, jadi kata internet hanyalah salah satu bagian saja. Supaya tidak berhenti pada definisi, mari kita lihat penerapannya di beberapa bidang.

### Frame 5 — Contoh Penerapan dan Karakteristik IoT

Kawasan: Wujud Sistem IoT

Teks di layar:
- Kampus: monitoring suhu ruangan laboratorium
- Rumah: lampu otomatis berbasis sensor cahaya
- Pertanian: pemantauan kelembapan tanah
- Transportasi: sistem parkir cerdas
- Empat karakteristik: menangkap, memproses, menampilkan, beraksi

Yang Anda ucapkan:
> Penerapan IoT sudah ada di sekitar Anda, dan Bab 1.2 materi pertemuan ini mendaftar empat di antaranya. Di lingkungan kampus, monitoring suhu ruangan laboratorium menjaga kenyamanan sekaligus keselamatan perangkat. Di rumah, lampu otomatis berbasis sensor cahaya atau gerak membuat pemakaian energi lebih hemat dan lebih praktis. Di pertanian, pemantauan kelembapan tanah membantu keputusan penyiraman, dan di transportasi, sistem parkir cerdas mempermudah deteksi slot kosong. Bila keempat contoh itu Anda amati bersamaan, polanya sama, dan pola itulah empat karakteristik utama sistem IoT: sistem menangkap data dari lingkungan, memproses atau mengirimnya, menampilkan atau menyimpannya pada platform, lalu menghasilkan aksi baik otomatis maupun atas perintah pengguna. Setiap karakteristik itu sesungguhnya dikerjakan oleh satu komponen yang punya nama, dan nama-nama itulah yang kita bahas berikutnya.

### Frame 6 — Enam Komponen Utama Sistem IoT

Kawasan: Anatomi Sistem

Teks di layar:
- Sensor membaca kondisi lingkungan sekitar
- Device atau mikrokontroler menjalankan program
- Network membawa data, platform mengolahnya
- Dashboard menampilkan, aktuator melakukan aksi fisik
- Data mentah belum berguna sebelum dibaca device

Yang Anda ucapkan:
> Salah satu sasaran pertemuan ini adalah Anda mampu menyebutkan minimal lima komponen IoT beserta perannya, dan di layar tersedia enam. Sensor membaca kondisi lingkungan seperti suhu, cahaya, gerakan, atau kelembapan. Device atau mikrokontroler adalah otak kecil yang membaca sensor, menjalankan program, lalu menentukan apa yang harus dilakukan; network menjadi jalur pengirimannya, misalnya Wi-Fi, dan platform menjadi tempat data diterima, diolah, disimpan, atau diteruskan. Dashboard membuat manusia dapat melihat informasi dan memberi perintah, sedangkan aktuator melakukan aksi fisik seperti menyalakan LED, motor, buzzer, atau relay. Bayangkan layanan pengiriman makanan: sensor adalah orang yang mencatat pesanan, mikrokontroler adalah kasir yang memproses, jaringan adalah jalan pengiriman, platform adalah dapur dan sistem pemesanan, dashboard adalah aplikasi pelanggan, dan aktuator adalah kurir yang benar-benar mengantarkan. Perlu Anda perhatikan, kehadiran aktuator inilah yang membuat sistem tidak lagi hanya melihat tetapi juga bertindak, dan perbedaan itu punya namanya sendiri.

### Frame 7 — Beda Monitoring dan Sistem Kontrol

Kawasan: Anatomi Sistem

Teks di layar:
- Monitoring hanya mengamati lalu melaporkan keadaan
- Kontrol bertindak saat batas tertentu terlewati
- Contoh: kipas menyala saat suhu melewati batas
- Keputusan terjadi di device, bukan dashboard
- Pilihan ini memengaruhi rangkaian, program, komunikasi

Yang Anda ucapkan:
> Tidak semua sistem IoT harus langsung mengontrol sesuatu. Sebagian sistem berhenti pada monitoring, misalnya membaca suhu lalu menampilkannya, tanpa mengubah apa pun. Sistem lain melangkah lebih jauh menjadi sistem kontrol, misalnya menyalakan kipas begitu suhu melewati batas yang ditentukan. Perbedaan ini bukan sekadar istilah, sebab ia memengaruhi desain perangkat keras, program yang Anda tulis, dan kebutuhan komunikasinya, sebagaimana dibahas pada Bab 2.3 materi pertemuan ini. Satu hal yang mudah tertukar: keputusan menyalakan atau tidak menyalakan terjadi di device, bukan di dashboard. Untuk melihat di mana device duduk di antara komponen lainnya, kita perlu satu alur besar yang merangkai semuanya.

### Frame 8 — Alur Sensor Sampai Pengguna

Kawasan: Anatomi Sistem

Teks di layar:
- `sensor → device → network → platform → user`
- Sensor mengakuisisi data, device menjalankan logika
- Network menjembatani, platform mengubah data jadi informasi
- User melihat, memahami, kadang memberi perintah
- Satu lapisan hilang, nilai sistem berkurang

Yang Anda ucapkan:
> Alur sensor, device, network, platform, lalu user adalah inti Pertemuan 1 dan menjadi peta besar bagi seluruh materi lanjutan. Lapisan sensor berfokus pada akuisisi data, sedangkan lapisan device berfokus pada logika, misalnya membaca nilai pin, membandingkan threshold, atau menyiapkan data untuk dikirim. Network adalah jembatan komunikasinya, platform mengubah data mentah menjadi informasi yang lebih berguna dalam bentuk chart, indikator, atau log, dan user adalah titik ketika manusia melihat, memahami, serta kadang memberi perintah balik kepada sistem. Bayangkan pengiriman paket: sensor adalah petugas loket yang menerima barang, device adalah petugas administrasi yang mencatat dan memberi label, network adalah jalur distribusi, platform adalah pusat sortir, dan user adalah penerima yang akhirnya mendapatkan informasi atau paketnya. Bila salah satu lapisan hilang, nilai sistemnya berkurang: sensor tanpa dashboard hanya memberi data lokal yang sulit dipantau dari jauh, sementara dashboard tanpa data sensor tidak punya isi yang bermakna. Alur inilah yang kelak Anda perdalam satu kotak demi satu kotak, dan untuk mengerjakannya Anda memerlukan alat kerja.

### Frame 9 — Tiga Alat Kerja dan Simulator

Kawasan: Meja Kerja Simulator

Teks di layar:
- Wokwi: simulator ESP32 di browser, dipakai sekarang
- MQTTX: klien penguji komunikasi MQTT, Pertemuan 7
- Node-RED: platform berbasis flow, Pertemuan 10
- Tidak ada yang perlu diinstal hari ini
- Simulator: eksperimen berulang, aman, fokus pada logika

Yang Anda ucapkan:
> Sepanjang mata kuliah ini ada tiga alat yang akan menemani Anda, tetapi hanya satu yang dipakai hari ini. Wokwi adalah simulator yang menjalankan proyek mikrokontroler secara virtual di dalam browser, sehingga Anda dapat mencoba ESP32, LED, sensor, dan rangkaian dasar tanpa menyiapkan perangkat fisik. MQTTX adalah klien untuk menguji komunikasi MQTT dan baru dipakai pada Pertemuan 7 yang membahas MQTT, sedangkan Node-RED adalah platform berbasis flow yang menjembatani device dengan tampilan bagi manusia dan baru dipakai pada Pertemuan 10 yang membahas dashboard. Keduanya diperkenalkan sekarang supaya Anda melihat ekosistemnya secara utuh, dan tidak satu pun di antaranya perlu Anda instal hari ini. Simulator penting pada tahap awal karena ia mengurangi hambatan, memudahkan eksperimen berulang, membuat Anda fokus pada logika program sebelum menghadapi masalah wiring, catu daya, atau noise, serta menciptakan lingkungan yang aman untuk debugging dasar. Anggaplah Wokwi seperti simulator mengemudi: setir, pedal, dan aturan dasar dikenali lebih dulu sebelum turun ke jalan raya, dan sekarang tiba saatnya Anda menyalakan mesinnya.

### Frame 10 — Praktik Simulasi ESP32 Pertama

Kawasan: Meja Kerja Simulator

Teks di layar:
- Rangkaian: `GPIO 2 → resistor 220 Ω → LED`
- Kaki pendek LED kembali ke GND
- Hapus panel kode, tempelkan kode Bab 6
- LED menyala sedetik, mati sedetik, berulang
- Serial Monitor bergantian: `LED menyala`, `LED mati`

Yang Anda ucapkan:
> Sekarang perhatikan langkah yang dijalankan di depan kelas satu per satu. Wokwi dibuka, New Project dipilih dengan board ESP32, lalu tiga area pada layar ditunjukkan: panel kode berisi `sketch.ino` di sisi kiri, panel rangkaian beserta tab `diagram.json` di sisi kanan, dan tombol jalankan berbentuk segitiga hijau di atas panel rangkaian. Project ESP32 yang baru dibuat hanya berisi board-nya saja, jadi rangkaian dipasang lebih dulu: GPIO 2 ke resistor 220 ohm, lanjut ke kaki panjang LED, dan kaki pendek LED kembali ke GND. Sesudah itu isi panel kode dihapus seluruhnya, kode dari Bab 6 materi pertemuan ini ditempelkan, lalu tombol jalankan ditekan. Yang harus terlihat ada tiga: LED menyala satu detik dan mati satu detik tanpa berhenti, Serial Monitor menampilkan `LED menyala` dan `LED mati` bergantian satu baris setiap detik, lalu setelah kedua `delay(1000)` diubah menjadi `delay(200)`, kedipan LED dan kemunculan barisnya menjadi jauh lebih cepat. Hasil ketiga itulah jawaban pertanyaan pembuka kita, karena satu angka di dalam kode nyata-nyata mengubah perilaku sebuah benda. Tentu tidak semua percobaan pertama langsung berhasil, dan itu hal yang normal.

### Frame 11 — Bila Hasilnya Tidak Seperti Itu

Kawasan: Meja Kerja Simulator

Teks di layar:
- LED mati tanpa error: periksa polaritas, pin
- Tulisan merah: titik koma, kurung kurawal
- Serial Monitor kosong: `Serial.begin(115200);` belum ada
- LED menyala terus: satu `digitalWrite` atau `delay`
- Simulasi berhenti sendiri: cukup jalankan ulang

Yang Anda ucapkan:
> Gagal pada percobaan pertama adalah hal yang normal dan bukan tanda ketidakmampuan. Bila LED tidak menyala sama sekali padahal tidak ada pesan error, kemungkinan besar LED belum ada di panel rangkaian, terpasang terbalik, atau angka pada `ledPin` berbeda dengan nomor pin yang tersambung. Bila simulasi menolak berjalan dan muncul tulisan merah, penyebabnya umumnya titik koma yang hilang atau kurung kurawal yang tidak berpasangan; bacalah nomor baris yang disebut, sebab kesalahannya biasanya ada di baris itu sendiri atau tepat di atasnya. Serial Monitor yang kosong meskipun LED berkedip menandakan `Serial.begin(115200);` belum ditulis di dalam `setup()`, sedangkan LED yang menyala terus tanpa berkedip berarti hanya ada satu `digitalWrite` atau salah satu `delay` terhapus. Kalau simulasi berhenti sendiri setelah berjalan beberapa saat, itu bukan kesalahan Anda, karena durasi satu kali menjalankan simulasi memang dibatasi pada penggunaan gratis, jadi cukup jalankan ulang. Kebiasaan yang perlu Anda bangun sejak hari ini adalah tidak mengganti kode secara acak: periksa satu hal, jalankan lagi, lihat perubahannya. Cara berpikir itu jauh lebih mudah dijalankan bila Anda mengenali fungsi setiap baris kodenya.

### Frame 12 — Membaca Struktur Kode Blink

Kawasan: Meja Kerja Simulator

Teks di layar:
- `const int ledPin = 2;` menyimpan nomor pin
- `setup()` berjalan sekali saat sistem mulai
- `loop()` berjalan terus selama board aktif
- `Serial.println` melaporkan keadaan device kepada manusia
- `delay(1000)` berarti menunggu satu detik

Yang Anda ucapkan:
> Kode praktik tadi hanya terdiri dari tiga bagian: deklarasi variabel, fungsi `setup()`, dan fungsi `loop()`. Baris `const int ledPin = 2;` menyimpan nomor pin yang dikendalikan, dan kata `const` berarti nilainya tetap, sehingga terlihat bahwa device perlu mengetahui jalur fisik mana yang akan digerakkan. Fungsi `setup()` dijalankan sekali saat sistem mulai, dan di dalamnya `Serial.begin(115200);` membuka jalur pelaporan ke Serial Monitor sementara `pinMode(ledPin, OUTPUT);` menetapkan pin LED sebagai keluaran. Fungsi `loop()` kemudian berjalan terus-menerus: LED dinyalakan dengan logika HIGH, keadaannya dilaporkan, sistem menunggu, LED dimatikan dengan logika LOW, keadaannya dilaporkan, lalu siklus diulang selama board masih aktif. Di sinilah teori bertemu praktik secara langsung, karena teori mengatakan aktuator melakukan aksi dan praktiknya LED menyala serta mati sesuai perintah, lalu teori mengatakan parameter memengaruhi perilaku sistem dan praktiknya perubahan `delay()` mengubah kecepatan kedip. Perlu Anda sadari bahwa tulisan di Serial Monitor adalah bentuk data yang paling awal, dan pada pertemuan berikutnya isinya akan diganti dengan angka dari sensor. Sebelum menutup, mari kita rangkum dan periksa apa yang sudah Anda capai.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan Ini

Kawasan: Penutup

Teks di layar:
- IoT menyatukan objek fisik, data, komunikasi, layanan
- Alur dasarnya sensor, device, network, platform, user
- Enam komponen inti dapat Anda sebutkan sendiri
- Simulator jalan: LED berkedip, Serial Monitor terisi
- Belum tercapai? Ulangi Bab 2, 3.1, 5.6

Yang Anda ucapkan:
> Mari kita kumpulkan apa yang sudah dilewati. IoT adalah sistem yang menghubungkan objek fisik, data, komunikasi, dan layanan digital agar monitoring atau kontrol dapat dilakukan lebih cerdas, alur dasarnya sensor, device, network, platform, lalu user, dan komponen utamanya sensor, mikrokontroler, network, platform, dashboard, serta aktuator. Wokwi dipakai hari ini, sementara MQTTX menunggu Pertemuan 7 tentang MQTT dan Node-RED menunggu Pertemuan 10 tentang dashboard. Program blink memperkenalkan struktur program, logika output, perilaku sistem yang berulang, serta laporan device ke Serial Monitor sebagai bentuk data yang paling awal. Checkpoint pertemuan ini ada tiga butir: Anda dapat menyebutkan minimal lima komponen IoT, dapat menjelaskan peran sensor, aktuator, konektivitas, dan dashboard masing-masing dalam satu kalimat, dan simulator berhasil Anda jalankan sampai LED berkedip serta Serial Monitor terisi. Cara memeriksanya sederhana: tutup materi, tulis lima komponen dari ingatan, lalu bandingkan dengan Bab 2; bila salah satu butir belum tercapai, kembalilah ke Bab 2, Bab 3.1, dan Bab 5.6 sekarang, bukan nanti. Ada satu hal lagi yang perlu Anda kerjakan setelah pertemuan ini ditutup.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup

Teks di layar:
- Tugas 1: ringkasan satu halaman, tiga sistem
- Isi lima poin: masalah, sensor, device, data, aksi
- Tugas 2: diagram blok satu kasus pilihan
- Penilaian: kelengkapan kotak dan keterangan panah
- Hindari panah sensor langsung ke dashboard

Yang Anda ucapkan:
> Ada dua tugas latihan dari pertemuan ini, dan keduanya tidak menuntut kode maupun perangkat. Tugas pertama, amati lingkungan di sekitar kampus, pilih tiga sistem yang sudah menjadi IoT atau berpotensi dijadikan IoT, lalu tulis hasilnya sebagai ringkasan satu halaman yang memuat masalah atau kebutuhannya, sensor yang mungkin digunakan, device yang memproses data, data yang perlu ditampilkan kepada pengguna, dan aksi yang mungkin dilakukan aktuator. Contoh acuan sudah tersedia di materi, yaitu lampu koridor gedung kuliah yang menyala sepanjang malam meski koridor kosong, dibaca oleh sensor gerak dan sensor cahaya, diputuskan oleh ESP32, lalu dinyalakan melalui relay. Tugas kedua, pilih satu dari tiga kasus itu dan gambar diagram bloknya dengan kotak dan panah saja; digambar dengan tangan di kertas lalu difoto pun diterima, selama nama kotak dan arah panahnya terbaca. Pokok penilaian tugas pertama adalah kelengkapan, ketepatan komponen, kejelasan alur, dan cara penyampaian, sedangkan tugas kedua menimbang paling berat pada kelengkapan kotak serta arah dan keterangan panah, lalu kesesuaian dengan kasus dan keterbacaannya. Kesalahan yang paling sering muncul adalah menggambar panah dari sensor langsung ke dashboard, padahal data sensor tidak pernah melompat ke tampilan tanpa melewati device yang membacanya. Kembali ke pertanyaan pembuka kita: satu angka pada `delay` sudah cukup mengubah perilaku sebuah benda, dan pada pertemuan berikutnya tentang dasar ESP32 serta GPIO, angka semacam itulah yang mulai Anda kendalikan dengan sadar.
