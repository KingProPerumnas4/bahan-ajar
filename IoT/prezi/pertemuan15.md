# Prezi Pertemuan 15 — Dari Simulator ke Perangkat Fisik

## Kanvas utama

Saat Prezi dibuka dan sebelum zoom pertama, yang terlihat adalah dua bidang besar yang berdampingan, yaitu diagram simulator yang bersih di kiri dengan garis rapi dan angka yang tenang, dan siluet papan ESP32 di kanan dengan nomor pin tercetak di kedua tepinya, sementara di antara keduanya terbentang satu jembatan mendatar berlabel jalur unggah dan judul pertemuan berdiri di atas jembatan itu. Enam kawasan topik ditata mengikuti gambar tersebut: kawasan pembuka menempel pada bidang kiri, kawasan jalur unggah duduk tepat di atas jembatan, kawasan peta pin dan kawasan batas listrik mengelilingi siluet papan di kanan, sedangkan kawasan praktik dan kawasan penutup berada di bawah keduanya sebagai meja kerja. Jalur zoom karena itu bercerita seperti perjalanan satu program: Anda meninggalkan dunia yang sudah disederhanakan di kiri, menyeberangi jembatan unggah, mendarat di papan yang memiliki aturan pin dan aturan listriknya sendiri, lalu kembali ke meja kerja untuk menyandingkan angka dari kedua sisi.

- Kawasan 1: Dua Dunia — pertanyaan pemancing, capaian pembelajaran, lapisan fisik, dan tabel perbandingan.
- Kawasan 2: Jalur Unggah — kabel data, pengenalan chip, port, pilihan papan, dan kecepatan serial.
- Kawasan 3: Peta Pin — kelompok pin yang tidak bebas dipakai serta cara memilih pin yang aman.
- Kawasan 4: Batas Listrik dan Derau — tegangan kerja, resistor LED, catu daya beban, dan perata-rataan sampel.
- Kawasan 5: Ruang Praktik — program uji, demo satu sensor dan satu keluaran, serta kesalahan yang sering terjadi.
- Kawasan 6: Penutup dan Tugas — ringkasan sekaligus checkpoint, lalu tugas latihan beserta penilaiannya.

## Alur zoom

1. Pembuka: Dari Simulator ke Papan Nyata
2. Capaian Pembelajaran Pertemuan Ini
3. Lapisan Fisik yang Belum Teruji
4. Enam Baris Daftar Periksa Perbedaan
5. Rantai Mata Jalur Unggah
6. Pin yang Sudah Punya Tugas
7. Memilih Pin dan Membaca Pinout
8. Batas Listrik dan Catu Daya
9. Derau Selalu Ada, Redam Akibatnya
10. Membaca Program Uji Perangkat Keras
11. Demo Menguji Sensor dan Keluaran
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 15
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Pembuka: Dari Simulator ke Papan Nyata

Kawasan: Dua Dunia

Teks di layar:
- Pertemuan 15: Dari Simulator ke Perangkat Fisik
- Program Anda sudah berjalan rapi di simulator
- Pertanyaan: apa yang berubah di papan nyata?
- Dan ke mana kecurigaan pertama diarahkan?

Yang Anda ucapkan:
> Sampai Pertemuan 14 tentang implementasi mini project, seluruh sistem Anda hidup di dalam simulator, dan di sana nilai sensor selalu tepat seperti yang Anda atur sementara kabel pada diagram selalu tersambung sempurna.
> Pertemuan ini memindahkan program yang sama ke papan ESP32 yang nyata, dan yang berubah bukan logikanya melainkan lapisan fisik di bawahnya, yaitu pengkabelan, derau pembacaan, catu daya, dan pin papan yang sebenarnya.
> Simpan dua pertanyaan ini sepanjang presentasi: apa saja yang benar-benar berubah ketika program berpindah ke papan, dan ke mana kecurigaan pertama sebaiknya Anda arahkan ketika hasilnya berbeda.
> Yang perlu Anda siapkan adalah program mini project Anda dari Pertemuan 14, satu perangkat lunak pengunggah seperti Arduino IDE beserta dukungan papan ESP32, dan satu kabel USB yang benar-benar kabel data.
> Papan ESP32 fisik beserta satu sensor, satu LED, dan resistor sekitar 220 ohm bersifat pilihan, sebab bila Anda belum memilikinya bagian perbandingan dikerjakan dari data simulator ditambah analisis perbedaan berdasarkan bab-bab pada materi pertemuan ini.
> Perlu ditegaskan sejak awal bahwa simulator tidak dibuang setelah pertemuan ini, karena ia tetap menjadi tempat termurah untuk menguji logika sedangkan papan nyata menjadi tempat menguji apakah asumsi listrik Anda benar.
> Kita mulai dari sasaran pertemuan ini supaya Anda tahu apa yang harus dapat Anda lakukan sendiri setelahnya.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Dua Dunia

Teks di layar:
- Alasan program mulus di simulator masih gagal
- Sifat nilai sensor nyata beserta derau
- Batas listrik papan: `3,3` volt dan arus
- Menyiapkan jalur unggah sampai keluaran terbaca
- Meredam derau dengan merata-ratakan beberapa sampel

Yang Anda ucapkan:
> Ada empat hal yang perlu Anda pahami pada pertemuan ini, yaitu alasan program yang berjalan mulus di simulator masih bisa gagal ketika dipindahkan ke papan nyata, perbedaan sifat nilai sensor pada rangkaian nyata termasuk derau yang selalu ada dan tidak bisa dihilangkan sepenuhnya, batas listrik papan ESP32 berupa tegangan kerja 3,3 volt beserta kemampuan arus tiap pin, dan sebab kegagalan unggah yang paling sering terjadi.
> Sisi keterampilannya juga empat: menyiapkan jalur unggah sampai program benar-benar masuk ke papan dan jendela pemantau serial menampilkan keluaran yang terbaca, membaca pinout papan Anda sendiri lalu memilih pin yang aman untuk satu sensor dan satu keluaran, meredam derau pembacaan analog dengan merata-ratakan beberapa sampel, serta menyusun catatan perbandingan antara hasil simulator dan hasil perangkat fisik.
> Perhatikan butir terakhir, karena catatan perbandingan itulah tugas pertemuan ini, dan yang paling berbobot di dalamnya adalah analisis penyebab perbedaan, bukan banyaknya angka yang Anda kumpulkan.
> Kegiatan intinya sederhana untuk diucapkan tetapi menuntut ketelitian, yaitu mengunggah program ke papan ESP32 nyata, menguji satu sensor dan satu keluaran, lalu membandingkan hasilnya dengan hasil di simulator.
> Perlu Anda catat bahwa sebab kegagalan unggah membentuk lapisan tersendiri yang tidak pernah Anda temui pada pertemuan sebelumnya, mulai dari driver USB, pemilihan port, pilihan papan, sampai kecepatan serial.
> Sebelum menyentuh kabel apa pun, kita perjelas dahulu mengapa program yang sudah terbukti benar masih bisa berperilaku lain di papan nyata.

### Frame 3 — Lapisan Fisik yang Belum Teruji

Kawasan: Dua Dunia

Teks di layar:
- Simulator menyederhanakan: sensor tepat, kabel sempurna
- Papan nyata menambah hambatan, sambungan longgar, arus terbatas
- Logika sudah terbukti, lapisan fisik belum
- Arahkan kecurigaan pertama ke lapisan fisik
- Membongkar kode karena kabel tertukar memboroskan waktu

Yang Anda ucapkan:
> Simulator menjalankan program Anda di dalam dunia yang sudah disederhanakan, sebab sensor virtual mengembalikan angka yang persis Anda atur, kabel pada diagram selalu tersambung sempurna, tegangan selalu pas, dan papan tidak pernah kehabisan arus.
> Semua penyederhanaan itu berguna karena membuat Anda dapat berkonsentrasi pada logika program, jadi jangan menganggapnya latihan palsu.
> Papan ESP32 yang nyata menambahkan satu lapisan yang tidak ada di simulator, yaitu lapisan fisik berisi konduktor yang punya hambatan, sambungan yang bisa longgar, catu daya yang bisa turun, dan sensor yang mengeluarkan angka sedikit berbeda pada setiap pembacaan.
> Konsekuensi praktisnya perlu Anda pegang sejak awal: ketika program yang sama memberi hasil berbeda di papan nyata, kecurigaan pertama diarahkan ke lapisan fisik dan bukan ke logika program, karena logika itu sudah terbukti berjalan di simulator sedangkan lapisan fisik belum pernah diuji sama sekali.
> Membongkar ulang kode di saat yang sebenarnya bermasalah adalah satu kabel yang tertukar hanya akan menghabiskan waktu Anda.
> Bandingkan dengan berlatih di simulator kemudi lalu turun ke jalan sebenarnya: Anda benar-benar sudah belajar kapan menekan pedal dan ke arah mana memutar roda, tetapi di jalan muncul aspal yang licin, angin dari samping, dan kendaraan lain yang tidak mengikuti aturan, sehingga yang perlu ditambahkan adalah kesiagaan terhadap hal-hal fisik itu.
> Supaya kesiagaan itu punya bentuk yang dapat diperiksa, materi pertemuan ini menyandingkan kedua dunia dalam satu tabel yang kita baca sekarang.

### Frame 4 — Enam Baris Daftar Periksa Perbedaan

Kawasan: Dua Dunia

Teks di layar:
- Nilai sensor: identik versus bergoyang beberapa satuan
- Kabel: garis diagram versus sambungan bisa longgar
- Arus: tanpa batas versus papan mati sendiri
- Boot dan unggah: ada lapisan tambahan
- Biaya kesalahan: nol versus kerusakan permanen

Yang Anda ucapkan:
> Tabel pada Bab 2 materi pertemuan ini merangkum enam perbedaan yang paling sering Anda rasakan, dan kedua kolomnya disandingkan agar Anda tahu ekspektasi mana yang perlu diubah ketika berpindah, bukan agar salah satu dunia dianggap lebih rendah.
> Pada baris kestabilan nilai, pembacaan berulang di simulator memberi angka identik sedangkan di papan nyata pembacaan berulang hampir tidak pernah identik; pada baris kabel, sambungan yang tampak masuk belum tentu bersentuhan; dan pada baris catu daya, beban besar dapat membuat papan mati sendiri atau melakukan reset.
> Tiga baris berikutnya menambahkan hal yang jarang Anda pikirkan, yaitu adanya jeda boot beserta pesan awal dari sistem papan, adanya lapisan kegagalan unggah berupa driver USB dan pemilihan port, serta biaya kesalahan yang di papan nyata benar-benar nyata karena tegangan berlebih atau hubungan singkat dapat merusak sensor maupun papan secara permanen.
> Pakai tabel ini sebagai daftar periksa dan bukan bacaan sekali lewat: ketika ada sesuatu yang berperilaku lain di papan, tentukan dahulu baris mana yang paling mungkin menjelaskannya, lalu periksa baris itu sebelum menyentuh program.
> Contohnya begini, nilai yang bergoyang mengarah ke baris kestabilan nilai, keluaran yang mati sama sekali mengarah ke baris kabel, dan papan yang seperti mulai dari awal mengarah ke baris catu daya.
> Kebiasaan itu memotong waktu penelusuran karena Anda memeriksa satu dugaan yang beralasan, bukan mencoba banyak perubahan sekaligus.
> Baris tentang kegagalan unggah adalah yang paling awal Anda hadapi, jadi mata rantai itulah yang kita bereskan lebih dahulu.

### Frame 5 — Rantai Mata Jalur Unggah

Kawasan: Jalur Unggah

Teks di layar:
- Kabel USB harus kabel data, bukan daya
- Chip `CP2102` atau `CH340` perlu dikenali
- Bandingkan daftar port sebelum dan sesudah dipasang
- Kecepatan pemantau serial harus sama: `115200`
- Titik-titik berulang: tahan tombol BOOT saat unggah

Yang Anda ucapkan:
> Mengunggah program ke papan nyata adalah rantai yang terdiri dari beberapa mata, dan bila salah satu mata belum benar, pesan galat yang muncul biasanya terasa tidak berhubungan dengan penyebab sebenarnya, sehingga memeriksa rantai secara berurutan lebih cepat daripada menebak.
> Mata pertama adalah kabel USB yang harus benar-benar kabel data dan bukan kabel yang hanya mengalirkan daya; mata kedua adalah chip penerjemah USB ke serial di dalam papan, umumnya seri CP2102 atau CH340, yang perlu dikenali komputer Anda sebelum sistem operasi memunculkan port baru.
> Cara mengenali port yang benar tanpa menebak adalah membuka daftar port sebelum kabel dipasang dan mencatat isinya, lalu memasang kabel papan dan membuka daftar itu kembali, karena nama yang baru muncul adalah port papan Anda.
> Setelah port diketahui, perangkat lunak pengunggah perlu diberi tahu dua hal, yaitu papan apa yang dipakai dan port mana yang menuju papan itu; pada pemilihan papan carilah entri yang berisi kata ESP32, dan entri generik seperti modul pengembangan ESP32 generik adalah pilihan pertama yang paling aman bila merek papan Anda tidak terdaftar.
> Mata terakhir adalah kecepatan jendela pemantau serial yang harus sama dengan angka pada `Serial.begin` di program Anda, sebab bila program memakai `115200` sementara jendela pemantau diatur pada angka lain, keluaran tetap muncul tetapi berupa karakter acak yang sering disalahartikan sebagai program rusak.
> Sebagian papan juga tidak masuk mode unggah dengan sendirinya, dan tandanya adalah pesan yang menampilkan titik-titik atau garis putus-putus berulang saat mencoba menyambung lalu berhenti dengan galat; pada papan seperti itu tekan dan tahan tombol bertuliskan BOOT atau IO0 tepat ketika proses unggah mulai mencari papan, lalu lepaskan setelah proses unggah berjalan.
> Nama menu berbeda antarversi perangkat lunak pengunggah sehingga kenalilah dari fungsinya, dan begitu program masuk ke papan, pertanyaan berikutnya adalah pin mana yang boleh Anda sentuh.

### Frame 6 — Pin yang Sudah Punya Tugas

Kawasan: Peta Pin

Teks di layar:
- `GPIO 34` sampai `39` hanya dapat menjadi masukan
- Pin memori program: papan gagal boot
- `GPIO 0`, `2`, `12`, `15` penentu mode boot
- Kelompok analog kedua terganggu ketika Wi-Fi aktif
- LED bawaan papan membuat pengamatan menyesatkan

Yang Anda ucapkan:
> Di simulator hampir semua pin dapat dipakai untuk apa saja dan diagram tetap berjalan, tetapi pada papan nyata sebagian pin sudah memiliki tugas sendiri sejak papan dinyalakan, dan memakainya untuk keperluan lain menimbulkan gejala yang membingungkan seperti papan gagal boot, proses unggah gagal, atau pembacaan analog yang selalu bernilai nol.
> Kelompok pertama adalah GPIO 34 sampai 39 yang hanya dapat menjadi masukan dan tidak memiliki resistor pull-up internal, sehingga perintah keluaran tidak berpengaruh sama sekali dan LED atau relai yang disambung ke pin ini tidak pernah menyala.
> Kelompok kedua adalah pin yang terhubung ke memori program, pada banyak modul di sekitar GPIO 6 sampai 11, yang dipakai papan untuk membaca program yang tersimpan sehingga papan gagal boot atau melakukan reset berulang segera setelah dinyalakan.
> Kelompok ketiga adalah pin penentu mode saat boot, antara lain GPIO 0, 2, 12, dan 15, karena keadaan pin ini pada saat papan menyala menentukan apakah papan masuk mode jalan atau mode unggah, dan akibatnya proses unggah gagal atau program tidak pernah berjalan.
> Kelompok keempat adalah kelompok pin analog kedua yang pada banyak papan mencakup GPIO 0, 2, 4, 12 sampai 15, dan 25 sampai 27, yang berbagi sumber daya dengan radio Wi-Fi sehingga pembacaan analognya berhenti bekerja atau selalu memberi angka tetap ketika Wi-Fi aktif.
> Kelompok terakhir adalah pin yang tersambung ke LED bawaan papan, sering GPIO 2, yang tetap bekerja tetapi sudah punya beban terpasang sehingga LED bawaan menyala mengikuti sinyal Anda dan pengamatan Anda bisa menyesatkan.
> Daftar ini terlihat menakutkan, padahal setelah semua kelompok itu dikeluarkan masih tersisa cukup banyak pin yang bebas, jadi mari kita lihat cara memilihnya.

### Frame 7 — Memilih Pin dan Membaca Pinout

Kawasan: Peta Pin

Teks di layar:
- Keluaran aman: sekitar `GPIO 4`, `5`, `13`, `23`
- Analog saat Wi-Fi: `GPIO 32` sampai `39`
- Tiga pertanyaan: keluaran, analog, tercetak di papan
- `GPIO 16` dan `17` bisa terpakai memori tambahan
- Nomor pin berbeda antarvarian papan

Yang Anda ucapkan:
> Untuk keluaran biasa seperti LED, relai, atau servo, pin di sekitar GPIO 4, 5, 13, 16 sampai 19, dan 21 sampai 23 umumnya aman, sedangkan untuk pembacaan analog yang harus tetap bekerja ketika Wi-Fi aktif pilihlah dari kelompok GPIO 32 sampai 39.
> Ingat pembagian di dalam kelompok itu, yaitu GPIO 34 sampai 39 hanya dapat menjadi masukan sementara GPIO 32 dan 33 masih dapat menjadi keluaran, sehingga tidak ada alasan memaksakan pin yang bermasalah.
> Cara memastikan satu pilihan pin cukup memerlukan tiga pertanyaan berurutan: apakah pin itu perlu menjadi keluaran, sebab bila ya kelompok GPIO 34 sampai 39 langsung tersisih; apakah pin itu perlu membaca nilai analog sementara Wi-Fi menyala, sebab bila ya hanya kelompok GPIO 32 sampai 39 yang dapat dipakai; dan apakah nomor pin itu tercetak di tepi papan Anda dan bukan hanya ada di gambar dari papan lain.
> Bila salah satu jawabannya tidak sesuai, ganti nomor pinnya sekarang sebelum ada kabel yang terpasang, karena mengubah satu angka di dalam program jauh lebih murah daripada mencari penyebab papan yang tidak mau boot.
> Ada satu pengecualian yang perlu Anda ketahui, yaitu pada modul yang dilengkapi memori tambahan GPIO 16 dan 17 dapat sudah terpakai oleh memori itu, dan gejalanya adalah papan gagal boot ketika kedua pin tersebut dibebani.
> Perlu ditegaskan bahwa modul ESP32 dijual dalam banyak versi dengan jumlah pin dan tata letak yang tidak sama, sehingga tidak ada satu daftar yang berlaku untuk semuanya dan Anda wajib mencocokkan tulisan yang tercetak di tepi papan dengan gambar pinout papan yang benar-benar ada di tangan Anda.
> Menyambung berdasarkan ingatan dari papan lain adalah penyebab kerusakan yang paling mudah dihindari, dan penyebab kerusakan berikutnya adalah salah menghitung listrik, jadi itulah bahasan kita sekarang.

### Frame 8 — Batas Listrik dan Catu Daya

Kawasan: Batas Listrik dan Derau

Teks di layar:
- Tegangan `3,3` volt adalah batas, bukan anjuran
- Pin 5V adalah jalur daya, bukan izin
- LED wajib resistor seri sekitar `220` ohm
- Servo, motor, relai, lampu: catu daya sendiri
- Ground beban disambungkan ke ground papan

Yang Anda ucapkan:
> ESP32 bekerja pada tegangan logika 3,3 volt, dan angka itu bukan anjuran melainkan batas, sebab memberi 5 volt pada pin masukan berarti memberi tegangan di luar rancangan dan akibatnya bisa langsung merusak pin atau merusak papan secara diam-diam sehingga papan masih hidup tetapi pembacaannya tidak lagi benar.
> Banyak papan memang memiliki pin bertanda 5V atau VIN, tetapi pin itu adalah jalur masuk daya untuk papan dan bukan izin untuk memberi 5 volt pada pin data, jadi bila sebuah modul hanya tersedia dalam versi 5 volt keluarannya perlu diturunkan lebih dahulu, misalnya dengan pembagi tegangan dua resistor atau dengan modul penurun taraf tegangan.
> Untuk keluaran, LED tidak boleh disambung langsung dari pin ke ground, karena di atas tegangan nyalanya LED hampir tidak menahan arus sehingga arus dapat melampaui kemampuan pin dan merusak LED maupun pin itu; resistor sekitar 220 ohm yang dipasang seri menjalankan tugas pembatas itu dan nyala LED tetap terang.
> Simulator tidak menghukum kelalaian ini karena tidak ada komponen yang bisa terbakar, sehingga kebiasaan memasang resistor justru harus Anda bangun sekarang, saat berpindah ke papan nyata.
> Beban yang menarik arus besar, terutama servo, motor, relai, dan deretan lampu, sebaiknya mendapat catu daya sendiri karena lonjakan arus saat beban mulai bergerak membuat tegangan pada jalur papan turun sesaat, dan penurunan itu cukup untuk membuat papan melakukan reset di tengah program dengan gejala khas berupa pesan pembuka yang tercetak berulang.
> Bayangkan lampu di rumah yang meredup sesaat ketika pompa air menyala: papan ESP32 berada pada posisi lampu itu, hanya saja papan tidak sekadar meredup melainkan langsung memulai dirinya dari awal begitu tegangannya turun melewati batas kerja, dan memberi pompa jalurnya sendiri adalah cara rumah mengatasinya.
> Dua hal wajib saat memakai catu daya terpisah adalah ground catu daya beban disambungkan ke ground papan karena tanpa acuan bersama sinyal kendali tidak punya arti, dan jalur data tetap berasal dari pin papan dengan tegangan 3,3 volt; setelah listriknya aman, masalah berikutnya ada pada angkanya sendiri.

### Frame 9 — Derau Selalu Ada, Redam Akibatnya

Kawasan: Batas Listrik dan Derau

Teks di layar:
- Rentang pembacaan analog bawaan `0` sampai `4095`
- Derau tidak dapat dihilangkan sepenuhnya
- Enam belas sampel dirata-ratakan menenangkan angka
- Perpendek kabel, jauhkan dari motor, kokohkan ground
- Ukur lebar goyangan sebelum menentukan ambang

Yang Anda ucapkan:
> Pembacaan analog pada ESP32 mengubah tegangan pada pin menjadi angka bulat dengan rentang bawaan 0 sampai 4095, dan di simulator memutar potensiometer virtual ke satu posisi menghasilkan satu angka yang tetap, sedangkan di papan nyata angka itu bergoyang beberapa satuan atau bahkan beberapa puluh satuan meski tidak ada yang disentuh.
> Goyangan itu disebut derau dan penyebabnya berlapis, yaitu tegangan catu yang tidak sepenuhnya rata, kabel yang menangkap gangguan dari lingkungan, sambungan yang tidak sempurna, serta keterbatasan ketelitian pengubah sinyal itu sendiri, sehingga derau tidak dapat dihilangkan dan yang perlu Anda lakukan adalah membuat program tidak mudah tertipu olehnya.
> Cara paling sederhana adalah merata-ratakan beberapa sampel, misalnya mengambil enam belas pembacaan berurutan dengan jeda sangat singkat lalu menjumlahkan dan membaginya, karena derau bergerak naik turun di sekitar nilai sebenarnya sehingga sebagian goyangan saling menghapus dan hasilnya jauh lebih tenang.
> Harganya adalah waktu, sebab enam belas sampel dengan jeda dua milidetik memakan sekitar tiga puluh dua milidetik untuk setiap pembacaan, dan itu tidak terasa untuk suhu, kelembapan, atau intensitas cahaya, tetapi justru merugikan untuk sesuatu yang harus ditangkap seketika seperti tombol yang ditekan cepat.
> Perata-rataan bekerja pada angkanya dan bukan pada penyebabnya, jadi perbaiki dahulu sisi rangkaiannya dengan memperpendek kabel sensor karena kabel panjang bekerja seperti antena, menjauhkan kabel sensor dari kabel motor, servo, atau relai, dan memastikan sambungan ground benar-benar kokoh karena acuan yang goyah membuat seluruh pembacaan goyah.
> Kenali lebar goyangan sebelum menentukan ambang dengan menjalankan program pembacaan sekitar tiga puluh detik dalam keadaan yang sengaja dibuat tidak berubah, lalu catat angka terkecil dan terbesar yang muncul karena selisih keduanya adalah lebar goyangan pada rangkaian Anda.
> Ambang yang jaraknya lebih kecil daripada lebar goyangan akan tersentuh sendiri oleh derau sehingga keluaran hidup mati tanpa sebab, dan karena itu prinsip dua ambang berjarak yang Anda pakai pada Pertemuan 14 tentang implementasi mini project menjadi semakin penting di papan nyata; sekarang kita lihat wujudnya di dalam program uji.

### Frame 10 — Membaca Program Uji Perangkat Keras

Kawasan: Ruang Praktik

Teks di layar:
- Tanpa Wi-Fi dan MQTT; hanya tiga uji
- Nomor pin ditulis sebagai konstanta bernama
- Ambang `2100` dan `1900` berjarak `200` satuan
- `millis()` menggantikan `delay(1000)` untuk penjadwalan cetak
- `nilaiMin` dan `nilaiMax` mengukur lebar goyangan

Yang Anda ucapkan:
> Program uji pada Bab 9 materi pertemuan ini sengaja dibuat sekecil mungkin dan tidak memuat Wi-Fi maupun MQTT, karena yang diuji hanya tiga hal, yaitu apakah program masuk ke papan, apakah sensor terbaca, dan apakah keluaran bergerak.
> Nomor pin ditulis sebagai konstanta bernama sehingga ketika pinout papan Anda ternyata berbeda hanya ada satu tempat yang perlu diubah, dan `PIN_SENSOR` diberi nilai 34 karena pin itu termasuk kelompok hanya-masukan yang pembacaan analognya tetap bekerja meski Wi-Fi dinyalakan, sedangkan `PIN_LED` diberi nilai 23 sebagai pin serbaguna untuk keluaran.
> Ambang nyala 2100 dan ambang mati 1900 diberi jarak 200 satuan, dan jarak itu harus lebih lebar daripada goyangan pada rangkaian Anda sehingga angkanya disesuaikan setelah Anda mengukur lebar goyangan sendiri.
> Pada fungsi `bacaRataRata`, penjumlahnya bertipe `long` karena enam belas pembacaan bernilai maksimum menghasilkan angka yang melampaui batas aman tipe bilangan pendek, sementara `delay(2)` memberi jarak antarsampel supaya keenam belas sampel tidak diambil pada satu titik gangguan yang sama.
> Baris pertama `loop()` membandingkan `millis()` dengan waktu cetak terakhir lalu keluar lebih awal memakai `return` bila belum satu detik, dan pola ini menggantikan `delay(1000)` sehingga papan tetap bebas mengerjakan hal lain dan program ini dapat Anda kembangkan menjadi program bersambungan Wi-Fi tanpa mengubah cara penjadwalannya.
> Variabel `nilaiMin` dan `nilaiMax` dimulai dari nilai yang sengaja dibalik, yaitu 4095 untuk yang terkecil dan 0 untuk yang terbesar, supaya pembacaan pertama apa pun langsung menggantikan keduanya, dan selisih kedua angka pada baris terakhir itulah lebar goyangan yang Anda pakai untuk menentukan jarak ambang.
> Keluarannya dicetak sebagai baris bernilai ganda yang dipisahkan titik koma tanpa satu pun kata agar langsung dapat ditempelkan ke lembar kerja lalu dipecah menjadi kolom, dan sekarang program ini kita jalankan sampai ke papan di depan kelas.

### Frame 11 — Demo Menguji Sensor dan Keluaran

Kawasan: Ruang Praktik

Teks di layar:
- Jalankan di simulator dahulu, catat sepuluh baris
- Unggah ke papan kosong, buktikan jalur serial
- Cabut kabel USB, baru pasang rangkaian
- Sensor ke `GPIO 34`, LED lewat resistor
- Yang terlihat: rata lebih tenang daripada mentah

Yang Anda ucapkan:
> Kita ikuti urutan pada Bab 7 materi pertemuan ini, dan urutan itu tidak sembarang karena pemasangan rangkaian ditunda sampai program terbukti masuk ke papan, sehingga setiap kegagalan hanya punya satu kemungkinan penyebab baru dan penelusuran tidak bercabang.
> Langkah pertama menjalankan program uji di simulator lebih dahulu lalu mencatat sepuluh baris keluaran pertama beserta nilai mentah dan nilai rata-ratanya, sebab angka inilah pembanding Anda nanti; langkah berikutnya mengenali port papan dengan membandingkan daftar port sebelum dan sesudah kabel USB dipasang, lalu memilih entri papan yang mengandung kata ESP32.
> Program itu kemudian diunggah ke papan dalam keadaan belum ada rangkaian apa pun yang tersambung, jendela pemantau serial dibuka pada kecepatan 115200, dan nilai sensor pada tahap ini boleh bernilai apa saja karena yang dibuktikan hanyalah jalur unggah dan jalur serial.
> Baru sesudah itu kabel USB dicabut sehingga papan tidak bertegangan, sensor analog disambungkan ke GPIO 34 dengan catu sensor ke pin 3V3 dan ground sensor ke pin GND papan, LED disambungkan melalui resistor 220 ohm ke GPIO 23 dengan kaki lainnya ke GND, lalu setiap sambungan diperiksa ulang sambil melihat gambar pinout papan sendiri dan dipastikan tidak ada kabel yang menghubungkan 3V3 langsung ke GND.
> Setelah kabel USB dipasang kembali, rangkaian dibiarkan tidak diganggu selama tiga puluh detik lalu sepuluh baris keluaran dicatat beserta nilai terkecil dan terbesarnya, dan sesudah itu keadaan sensor diubah secara nyata, misalnya menutup sensor cahaya dengan tangan atau memutar potensiometer.
> Ada empat hal yang harus terlihat: program masuk ke papan tanpa galat dengan baris keluaran yang terbaca dan bukan karakter acak, nilai pada papan nyata bergoyang dalam rentang yang dapat Anda sebut angkanya sedangkan nilai di simulator tetap, kolom rata jauh lebih tenang daripada kolom mentah pada baris yang sama, serta LED berpindah keadaan ketika nilai melewati ambang dan tidak berpindah sendiri ketika sensor dibiarkan diam.
> Bila Anda belum memiliki papan, langkah pertama tetap dikerjakan penuh sebagai data simulator, langkah selanjutnya diganti dengan rencana pengkabelan lengkap bernomor pin beserta pembuktian keamanan pin dan perkiraan perbedaan yang disebut terus terang di dalam catatan, karena yang dinilai adalah ketepatan penalarannya; dan kalau yang Anda lihat berbeda dari empat hal tadi, gejalanya biasanya sudah ada di daftar berikut.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Praktik

Teks di layar:
- Port tidak muncul: kabel daya atau izin
- Titik berulang: tutup pemantau, tahan tombol BOOT
- Karakter acak: kecepatan pemantau tidak cocok
- Analog nol atau maksimum: sambungan atau pin
- Papan mulai dari awal: cabut beban bergantian

Yang Anda ucapkan:
> Tabel penelusuran masalah pada Bab 8.1 materi pertemuan ini memuat enam gejala, dan hampir semuanya berada di lapisan fisik atau di lapisan penyiapan, bukan di logika program Anda.
> Bila port papan tidak muncul di daftar, kemungkinannya kabel hanya mengalirkan daya, chip USB ke serial belum dikenali, atau port ada tetapi tidak dapat dibuka oleh pengguna biasa; bandingkan daftar port sebelum dan sesudah kabel dipasang lalu coba kabel lain, dan bila nama port terlihat tetapi gagal dibuka maka masalahnya izin akses dan bukan driver.
> Bila proses unggah gagal dengan pesan titik atau garis putus-putus berulang, tutup dahulu semua jendela pemantau serial karena port hanya dapat dipakai satu jendela pada satu waktu, dan bila pesan itu tetap muncul tekan serta tahan tombol BOOT atau IO0 tepat saat proses unggah mulai mencari papan.
> Bila keluaran serial berupa karakter acak, cocokkan kecepatan jendela pemantau dengan angka pada `Serial.begin` pada 115200, dan bila keduanya sudah sama tetapi tetap acak maka papan mungkin melakukan reset berulang.
> Bila nilai analog selalu nol atau selalu maksimum, telusuri satu per satu kabel sensor ke nomor pin di program, pastikan ground sudah menjadi acuan bersama, lalu bandingkan nomor pin dengan tabel kelompok pin; sedangkan bila LED tidak pernah menyala, periksa apakah pin keluaran itu termasuk kelompok hanya-masukan, tukar arah kaki LED, dan pastikan resistor berada seri pada jalur yang sama dengan LED.
> Gejala terakhir adalah papan yang seperti mulai dari awal berulang kali sehingga baris judul kolom tercetak lagi dan lagi, dan penyebab yang paling sering adalah tegangan yang turun sesaat karena beban menarik arus besar, jalur daya yang tidak cukup kuat, atau dua titik yang bersentuhan sehingga terjadi hubungan singkat.
> Cara memastikannya adalah mencabut beban satu per satu sambil memperhatikan pada beban mana reset berhenti terjadi, karena beban itulah yang menuntut catu daya sendiri, dan bila reset tetap terjadi tanpa beban apa pun periksa ulang seluruh sambungan untuk mencari titik yang bersentuhan; sekarang kita rangkum pertemuan ini.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 15

Kawasan: Penutup dan Tugas

Teks di layar:
- Curigai lapisan fisik lebih dahulu, bukan logika
- Jalur unggah adalah rantai; periksa berurutan
- Derau selalu ada; beri jarak antarambang
- Pilihan pin dibuktikan terhadap pinout papan Anda
- Checkpoint: unggah, pin aman, derau, catatan

Yang Anda ucapkan:
> Mari kita kumpulkan intinya: simulator menyederhanakan dunia fisik sedangkan papan nyata menambahkan lapisan listrik yang belum pernah diuji, sehingga kecurigaan pertama saat hasil berbeda diarahkan ke lapisan itu dan bukan ke logika program.
> Jalur unggah adalah rantai berisi kabel data, pengenalan chip USB ke serial, port, pilihan papan, dan kecepatan serial, dan memeriksanya berurutan selalu lebih cepat daripada menebak.
> Tegangan kerja 3,3 volt adalah batas, LED menuntut resistor pembatas, beban berarus besar menuntut catu daya sendiri dengan ground bersama, sementara derau selalu ada sehingga perata-rataan sampel dan jarak antara dua ambang membuat program tidak tertipu goyangan.
> Sebagian pin ESP32 sudah memiliki tugas sendiri dan nomornya berbeda antarvarian papan, karena itu pilihan pin dibuktikan lebih dahulu terhadap gambar pinout papan yang benar-benar Anda pegang, bukan diambil dari ingatan atau dari contoh papan lain.
> Checkpoint evaluasi pada Bab 13 materi pertemuan ini memuat lima butir, yaitu program berhasil diunggah dan keluaran serial terbaca, pilihan pin terbukti aman untuk papan Anda, derau dikenali dan diredam bukan diabaikan, batas listrik dipahami dan diterapkan, serta catatan perbandingan tersusun beserta analisisnya.
> Target minimalnya adalah papan fisik dapat diprogram, ada pembacaan data nyata yang tercatat angkanya, dan ada analisis perbedaan terhadap hasil simulator; bila papan belum tersedia, target minimalnya adalah rencana pengkabelan yang terbukti aman disertai analisis perbedaan yang diperkirakan.
> Empat checkpoint besar mata kuliah ini berada pada Pertemuan 4, Pertemuan 8, Pertemuan 12, dan Pertemuan 16 sebagai CP-4, dan Pertemuan 15 adalah pemeriksaan mingguan yang menyiapkan Anda menuju CP-4, jadi tugas berikut sebaiknya Anda kerjakan tanpa menunda.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup dan Tugas

Teks di layar:
- Susun catatan perbandingan simulator dan papan
- Minimal sepuluh baris dari masing-masing sisi
- Sertakan nilai terkecil, terbesar, dan lebar goyangan
- Analisis sebab fisik, bukan dugaan kesalahan program
- Bobot: analisis `30%`, kelengkapan data `25%`

Yang Anda ucapkan:
> Tugas Anda adalah menyusun satu catatan perbandingan antara hasil simulator dan hasil perangkat fisik untuk satu sensor dan satu keluaran, dan catatan itu harus memuat angka dari kedua sisi, selisihnya, serta analisis penyebab selisih tersebut.
> Isi wajibnya tiga: tabel perbandingan berisi minimal sepuluh baris pembacaan dari simulator dan sepuluh baris dari papan nyata lengkap dengan nilai mentah dan nilai rata-rata, lalu nilai terkecil, nilai terbesar, dan lebar goyangan pada papan nyata beserta nilai ambang tempat keluaran benar-benar berpindah keadaan, dan terakhir analisis perbedaan sepanjang beberapa paragraf.
> Analisis itu harus menyebut sebab fisiknya dan bukan hanya menyatakan bahwa hasilnya berbeda, karena itulah bagian yang paling berbobot.
> Bila Anda belum memiliki papan, kerjakan versi tanpa papan seperti dijelaskan pada Bab 7 materi pertemuan ini dan sebutkan hal itu secara terbuka di bagian awal catatan.
> Penilaiannya terbagi menjadi analisis penyebab perbedaan `30%`, kelengkapan data pembanding `25%`, ketepatan penyajian angka `20%`, pemeriksaan pin dan keselamatan listrik `15%`, serta kerapian penulisan `10%` yang berarti catatan Anda harus dapat dibaca orang lain tanpa penjelasan tambahan; ingat pula bahwa tugas latihan mingguan berbobot dua puluh persen dari nilai akhir.
> Dua pertanyaan pembuka tadi kini sudah terjawab: yang berubah di papan nyata adalah nilai sensor yang bergoyang, sambungan yang bisa longgar, arus yang terbatas, jeda boot, lapisan kegagalan unggah, dan biaya kesalahan yang nyata.
> Kecurigaan pertama Anda arahkan ke lapisan fisik, dengan tabel perbandingan sebagai penunjuk baris mana yang perlu diperiksa lebih dahulu sebelum satu baris program pun Anda ubah.






