# Prezi Pertemuan 10 — Dashboard IoT dengan Node-RED

## Kanvas utama

Saat Prezi dibuka dan sebelum zoom pertama, yang terlihat adalah rantai empat kotak besar yang berjajar dari kiri ke kanan, yaitu perangkat di simulator, broker, Node-RED, dan peramban, dengan judul pertemuan di atas rantai itu dan satu panah balik melengkung di bawahnya yang diberi label topik perintah. Enam kawasan topik ditata mengikuti rantai tersebut: dua kawasan pembuka berada di sekitar kotak perangkat dan broker, dua kawasan tengah menempel pada kotak Node-RED, dan dua kawasan terakhir berada di sekitar peramban serta di sepanjang panah balik. Jalur zoom karena itu bercerita seperti perjalanan satu nilai: Anda ikut sebuah angka meninggalkan perangkat, masuk ke ruang kerja Node-RED, berubah menjadi gauge dan grafik di layar, lalu berbalik arah sebagai perintah yang menggerakkan perangkat kembali.

- Kawasan 1: Pembuka dan Kedudukan — pertanyaan pemancing, capaian pembelajaran, dan tempat Node-RED dalam sistem Anda.
- Kawasan 2: Bahasa Flow — node, wire, `msg.payload`, ruang kerja, dan tombol Deploy.
- Kawasan 3: Ruang Dasbor — pemasangan paket dasbor serta empat widget yang dipakai.
- Kawasan 4: Dua Arah Pesan — topik data dan topik perintah, flow contoh, dan tambahan pada program perangkat.
- Kawasan 5: Ruang Praktik — demo membangun dasbor pertama dan kesalahan yang sering terjadi.
- Kawasan 6: Penutup dan Tugas — ringkasan sekaligus checkpoint, lalu tugas latihan beserta penilaiannya.

## Alur zoom

1. Pembuka: Memberi Wajah pada Data
2. Capaian Pembelajaran Pertemuan Ini
3. Kedudukan Node-RED dalam Sistem
4. Flow, Node, Wire, msg.payload
5. Ruang Kerja dan Tombol Deploy
6. Memasang Paket Dasbor
7. Empat Widget Dasbor
8. Dua Topik, Dua Arah
9. Membaca Flow Contoh
10. Perangkat Menyimak Topik Perintah
11. Demo Membangun Dasbor Pertama
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 10
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Pembuka: Memberi Wajah pada Data

Kawasan: Pembuka dan Kedudukan

Teks di layar:
- Pertemuan 10: Dashboard IoT dengan Node-RED
- Data Anda masih berupa teks di log
- Pertanyaan: bagaimana satu nilai sampai ke layar?
- Dan bagaimana tombol di layar menggerakkan perangkat?

Yang Anda ucapkan:
> Sampai Pertemuan 9 tentang pengaturan waktu pengiriman, data Anda hanya terlihat di log serial dan di klien MQTT yang penuh teks.
> Pertemuan ini memberi data itu wajah, yaitu sebuah dasbor berisi angka, grafik, dan lampu status yang dapat dibuka di peramban, sekaligus satu tombol yang mengirim perintah balik ke perangkat.
> Simpan dua pertanyaan ini sepanjang presentasi: bagaimana satu nilai sensor sampai ke layar, dan bagaimana satu tekanan tombol di layar sampai kembali ke perangkat.
> Yang perlu Anda siapkan adalah proyek simulator hasil Pertemuan 9 yang sudah mengirim payload JSON, ditambah Node-RED beserta paket dasbornya.
> Node-RED adalah perangkat lunak baru pada mata kuliah ini, jadi sisihkan waktu untuk pemasangannya sebelum mengerjakan bab praktik.
> Kita mulai dari sasaran pertemuan ini supaya Anda tahu apa yang harus dapat Anda lakukan sendiri setelahnya.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Pembuka dan Kedudukan

Teks di layar:
- Memahami kedudukan Node-RED di sisi penerima
- Memahami node, wire, dan `msg.payload`
- Menyusun flow yang berlangganan topik data
- Membuat switch yang menerbitkan perintah perangkat
- Menjelaskan perjalanan nilai dari sensor sampai layar

Yang Anda ucapkan:
> Ada empat hal yang perlu Anda pahami pada pertemuan ini, yaitu kedudukan Node-RED sebagai penerima dan pengolah data di sisi komputer, arti node, wire, dan `msg.payload` dalam sebuah flow, fungsi tiap widget dasbor, serta sebab kendali dari dasbor memerlukan topik perintah yang terpisah dari topik data.
> Sisi keterampilannya juga empat: menyusun flow yang berlangganan topik data dan menampilkannya, memasang paket dasbor melalui pengelola paket, membuat switch yang menerbitkan perintah ke topik yang disimak perangkat, dan menjelaskan perjalanan satu nilai dari sensor sampai muncul di layar.
> Perhatikan butir terakhir, karena kemampuan menjelaskan alur itulah yang ikut dinilai pada tugas, bukan hanya dasbor yang terlihat bagus.
> Publish dan subscribe serta broker publik yang dipakai di sini sudah Anda pelajari pada Pertemuan 7 tentang MQTT, jadi yang benar-benar baru hanyalah alat di sisi penerima.
> Sebelum menyentuh kanvas Node-RED, kita perjelas dahulu di bagian mana alat ini duduk dalam sistem Anda.

### Frame 3 — Kedudukan Node-RED dalam Sistem

Kawasan: Pembuka dan Kedudukan

Teks di layar:
- Klien MQTT berguna menguji, bukan alat pemantauan
- Node-RED berjalan di komputer Anda, berlangganan topik sama
- Urutannya: perangkat, broker, Node-RED, peramban
- Keduanya hanya sepakat pada nama topik
- Salah satu boleh diganti tanpa mengubah yang lain

Yang Anda ucapkan:
> Klien MQTT yang Anda pakai sampai sekarang berguna untuk menguji, tetapi ia bukan alat pemantauan, sebab isinya deretan teks tanpa gambaran perubahan nilai dan tidak dapat mengubah data sebelum ditampilkan.
> Node-RED mengisi celah itu sebagai perangkat lunak yang berjalan di komputer Anda, berlangganan topik yang sama, lalu mengolah dan menampilkan hasilnya.
> Kedudukannya di tengah: perangkat di satu sisi, broker sebagai penghubung, Node-RED sebagai penerima yang menyiapkan tampilan, dan peramban sebagai layar.
> Perangkat tidak perlu tahu ada dasbor dan dasbor tidak perlu tahu perangkat apa yang mengirim, karena keduanya hanya sepakat pada nama topik, sehingga Anda boleh menambah dasbor kedua atau menukar perangkat tanpa menyentuh yang lain.
> Bayangkan dapur restoran: perangkat adalah pemasok yang menaruh bahan di meja penerimaan, broker adalah meja itu, dan Node-RED adalah koki yang memotong bahan lalu menatanya di piring, sementara pengunjung hanya melihat piring yang rapi.
> Sekarang kita masuk ke dapur itu dan melihat bagaimana koki tadi menyusun pekerjaannya.

### Frame 4 — Flow, Node, Wire, msg.payload

Kawasan: Bahasa Flow

Teks di layar:
- Satu node mengerjakan satu tugas kecil
- Wire menentukan urutan; kumpulannya disebut flow
- Yang mengalir adalah pesan; intinya `msg.payload`
- `msg.payload.suhu_c` berisi angka, `msg.topic` nama topik
- Node `change` memindahkan nilai ke `msg.payload`

Yang Anda ucapkan:
> Program di Node-RED tidak ditulis baris demi baris, melainkan dirangkai dari kotak-kotak yang disebut node, dan masing-masing mengerjakan satu tugas kecil seperti menerima pesan MQTT, mengubah isinya, atau menampilkannya.
> Node dihubungkan oleh garis yang disebut wire, arah wire menentukan urutan pekerjaan, dan kumpulan node yang terhubung itulah yang disebut flow.
> Yang berjalan di sepanjang wire adalah pesan, dan bagian terpentingnya adalah `msg.payload`; bila node MQTT disetel membaca JSON, maka `msg.payload.suhu_c` berisi angka suhu sedangkan `msg.topic` berisi nama topik asalnya.
> Ingat satu kalimat ini: setiap node menerima `msg`, boleh mengubahnya, lalu meneruskannya, sehingga kebingungan Anda hampir selalu hilang begitu Anda bertanya apa isi `msg.payload` di titik ini.
> Karena widget umumnya menampilkan apa yang ada di `msg.payload`, node `change` dipakai untuk menyetel `msg.payload` menjadi `msg.payload.suhu_c` sehingga gauge menerima angka tunggal, bukan seluruh objek.
> Cara merangkai seperti ini memang terasa aneh bila Anda biasa menulis kode, tetapi urutan kerjanya terlihat sebagai gambar; itulah sebabnya Node-RED dipakai di sisi penerima sementara program perangkat tetap ditulis sebagai kode di simulator, dan sekarang kita lihat ruang kerjanya.

### Frame 5 — Ruang Kerja dan Tombol Deploy

Kawasan: Bahasa Flow

Teks di layar:
- Palette di kiri, kanvas tengah, panel kanan
- Node ditarik, diklik dua kali, lalu dihubungkan
- Sebelum Deploy, perubahan hanya tersimpan di layar
- Pasang satu node `debug` di setiap cabang
- Nama menu berbeda antarversi; kenali dari fungsinya

Yang Anda ucapkan:
> Ruang kerja Node-RED dibuka di peramban dan tampilannya terbagi tiga: palette berisi daftar node di kiri, kanvas tempat node diletakkan di tengah, serta panel samping di kanan yang dapat berganti isi antara keterangan node, keluaran `debug`, dan pengaturan tata letak dasbor.
> Cara bekerjanya selalu sama, yaitu node ditarik dari palette ke kanvas, diklik dua kali untuk diatur, lalu titik keluaran di sisi kanannya ditarik ke titik masukan node berikutnya.
> Selama tombol Deploy di kanan atas belum ditekan, semua perubahan hanya tersimpan di layar dan belum dijalankan; tombol itulah yang memindahkan rancangan Anda menjadi program yang benar-benar berjalan.
> Kebiasaan ini berbeda dari menulis program di Arduino IDE yang harus diunggah ulang setiap kali, karena Deploy hanya memuat ulang bagian yang berubah sehingga Anda dapat memperbaiki satu node lalu langsung melihat akibatnya.
> Biasakan meletakkan satu node `debug` di ujung setiap cabang yang sedang Anda bangun, sebab panel debug memperlihatkan isi `msg` yang sebenarnya sampai di titik itu dan itu jauh lebih cepat daripada menduga-duga.
> Nama menu dan letak tombol dapat berbeda antarversi, jadi kenali dari fungsinya: menu utama selalu di sudut kanan atas berlambang tiga garis, dan lewat menu itulah kita memasang paket dasbor berikutnya.

### Frame 6 — Memasang Paket Dasbor

Kawasan: Ruang Dasbor

Teks di layar:
- Node-RED berjalan di komputer, bukan di dalam simulator
- Layanannya tetap hidup meski peramban ditutup
- Node dasbor bukan paket bawaan; pasang sendiri
- Dua generasi paket: `ui_gauge` versus `ui-gauge`
- Widget wajib berada dalam grup di dalam tab

Yang Anda ucapkan:
> Node-RED berjalan di komputer Anda sendiri, bukan di dalam simulator, dan pemasangannya mengikuti petunjuk resmi untuk sistem operasi Anda; ikuti halaman resminya, jangan menyalin perintah dari sumber lama yang sering menyebut versi yang sudah tidak didukung.
> Satu hal yang membedakannya dari program biasa adalah ia tidak berhenti ketika jendela peramban ditutup, sebab yang berjalan adalah layanannya sementara peramban hanya jendela untuk melihat dan menyunting.
> Node dasbor tidak termasuk paket bawaan, jadi pasanglah dari dalam Node-RED melalui menu utama di sudut kanan atas, pilihan yang mengelola palette, lalu tab pemasangan dengan kata pencarian `dashboard`.
> Setelah pemasangan selesai, kelompok node baru muncul di bagian bawah palette.
> Perlu Anda ketahui ada dua generasi paket dasbor: yang lama memakai nama seperti `ui_gauge` dan `ui_switch`, yang lebih baru memakai nama bertanda hubung seperti `ui-gauge`, dan alamat halaman dasbornya pun berbeda sehingga cobalah keduanya bila salah satu memberi halaman kosong.
> Contoh flow pada Bab 8 materi pertemuan ini memakai nama paket lama, jadi bila Anda memasang paket yang lebih baru susunlah widget secara manual; apa pun paketnya, setiap widget harus ditempatkan pada sebuah grup di dalam sebuah tab, dan widget itulah yang kita bahas sekarang.

### Frame 7 — Empat Widget Dasbor

Kawasan: Ruang Dasbor

Teks di layar:
- Gauge menampilkan satu angka terbaru
- Chart menampilkan perubahan nilai sepanjang waktu
- Indikator teks menampilkan `msg.payload` apa adanya
- Switch menghasilkan pesan, bukan menerimanya
- Riwayat chart hilang bila layanan dijalankan ulang

Yang Anda ucapkan:
> Empat widget berikut sudah cukup untuk memantau sebuah sistem kecil sekaligus mengendalikannya.
> Gauge menampilkan satu angka terbaru sebagai jarum atau busur, sehingga yang perlu Anda atur adalah batas bawah, batas atas, satuan, dan nama grupnya, dan payload yang masuk harus berupa angka tunggal.
> Chart menampilkan perubahan nilai sepanjang waktu sebagai garis, sedangkan indikator teks menampilkan isi `msg.payload` apa adanya sehingga Anda perlu mengirim teks yang sudah siap dibaca seperti AMAN atau BAHAYA.
> Switch berbeda arah dari ketiganya: gauge, chart, dan indikator berada di ujung akhir flow karena wire hanya masuk ke sana, sementara switch berada di awal flow karena ia menghasilkan pesan setiap kali ditekan, misalnya `ON` dan `OFF`.
> Dua sifat chart perlu Anda ketahui agar tidak menyangka ada kerusakan: riwayatnya disimpan di dalam Node-RED yang sedang berjalan sehingga grafik kembali kosong setelah layanannya dijalankan ulang, dan titiknya hanya ada untuk data yang benar-benar dikirim sehingga jarak antartitik tidak sama rata karena penyaringan ambang dari Pertemuan 9.
> Untuk sistem Anda, pasangan yang paling masuk akal adalah gauge untuk `suhu_c`, chart untuk nilai yang sama, indikator teks untuk status, dan satu switch untuk aktuator; switch inilah yang menuntut kita membahas arah kedua.

### Frame 8 — Dua Topik, Dua Arah

Kawasan: Dua Arah Pesan

Teks di layar:
- Perangkat menerbitkan data; Node-RED berlangganan topik itu
- Node-RED menerbitkan perintah; perangkat yang berlangganan
- Jangan memakai satu topik untuk dua arah
- Isi pesan datang sebagai byte, susun menjadi teks
- Broker publik tidak membedakan siapa mengirim perintah

Yang Anda ucapkan:
> Dasbor yang hanya menampilkan angka baru setengah jalan, karena yang membuatnya terasa seperti sistem IoT adalah kemampuan menekan sesuatu di layar lalu melihat perangkat menanggapinya, dan kuncinya bukan teknologi baru melainkan dua topik dengan arah berlawanan.
> Pada arah pertama perangkat menerbitkan ke topik data seperti `iot/kelasA/nim12345/suhu` dan Node-RED berlangganan; pada arah kedua kedudukan mereka bertukar, Node-RED menerbitkan ke topik perintah seperti `iot/kelasA/nim12345/perintah` dan perangkatlah yang berlangganan.
> Jangan memakai satu topik untuk dua arah, sebab perangkat akan menerima kembali pesannya sendiri dan Node-RED ikut membaca perintahnya sendiri, sehingga status berkedip-kedip tanpa sebab dan sulit dilacak.
> Di sisi perangkat, berlangganan berarti dua tambahan pada program, yaitu satu fungsi yang dijalankan setiap ada pesan masuk dan satu panggilan yang mendaftarkan topik perintah setelah sambungan broker terjadi.
> Fungsi itu menerima isi pesan sebagai deretan byte sehingga perlu disusun kembali menjadi teks sebelum dibandingkan dengan `ON` atau `OFF`, karena pustaka MQTT tidak berani menebak isi pesan Anda dan menyerahkan penafsirannya kepada program Anda.
> Sadari juga bahwa broker publik tidak membedakan siapa yang mengirim perintah, jadi pakailah topik yang memuat identitas Anda sendiri dan anggap semua lalu lintasnya terbuka; berikutnya kita baca flow contohnya.

### Frame 9 — Membaca Flow Contoh

Kawasan: Dua Arah Pesan

Teks di layar:
- Satu pengaturan broker dipakai node masuk dan keluar
- `datatype` bernilai `json` membuat payload langsung diuraikan
- `wires` adalah daftar tujuan setiap keluaran node
- Dua node `change` karena satu pesan satu payload
- Gauge diberi batas 20 sampai 45

Yang Anda ucapkan:
> Flow contoh pada Bab 8 materi pertemuan ini ditulis sebagai teks JSON yang dapat diimpor melalui menu utama, dan sebelum menekan Deploy gantilah setiap `nim12345` dengan identitas Anda sendiri.
> Pengaturan broker bukan node yang tampak di kanvas melainkan sambungan yang dipakai bersama oleh node masuk dan node keluar, sehingga hanya satu sambungan dibuka untuk seluruh flow dan mengganti alamat broker cukup dilakukan sekali.
> Pada node `mqtt in`, isi `datatype` bernilai `json` inilah yang membuat teks kiriman langsung diuraikan menjadi objek sehingga `msg.payload.suhu_c` dapat diambil; tanpa setelan itu payload tetap satu teks panjang dan setiap upaya mengambil field menghasilkan nilai kosong.
> Bagian `wires` adalah daftar tujuan untuk setiap keluaran, dan di sini pesan dari `mqtt in` dikirim ke tiga tujuan sekaligus, yaitu dua node `change` dan satu `debug`, dengan satu salinan untuk tiap cabang sehingga cabang yang satu tidak merusak isi cabang lainnya.
> Dibutuhkan dua node `change` karena satu pesan hanya punya satu `msg.payload`, jadi satu node mengambil `payload.suhu_c` untuk gauge dan chart sementara satu lagi mengambil `payload.status` untuk widget teks.
> Gauge diberi batas 20 sampai 45 dengan satuan C sesuai rentang nilai program Anda, sebab skala yang jauh lebih lebar membuat pergerakan jarum hampir tidak terlihat; jalur arah baliknya tinggal menunggu satu tambahan di program perangkat.

### Frame 10 — Perangkat Menyimak Topik Perintah

Kawasan: Dua Arah Pesan

Teks di layar:
- `pesanMasuk()` dijalankan setiap ada pesan masuk
- Perulangan menyusun byte menjadi teks, lalu `isi.trim()`
- Perbandingan `ON` dan `OFF` peka huruf besar
- `mqtt.subscribe()` diulang setiap sambungan broker terbentuk
- `mqtt.loop()` wajib dipanggil setiap putaran `loop()`

Yang Anda ucapkan:
> Potongan pada bagian 8.3 materi pertemuan ini ditambahkan ke program Pertemuan 9 agar perangkat menyimak topik perintah, dan letaknya di luar `loop()`.
> Fungsi `pesanMasuk()` dijalankan pustaka MQTT setiap ada pesan di topik yang dilanggan, menerima nama topik beserta isi pesan sebagai deretan byte, lalu perulangan di dalamnya menyusun byte itu menjadi teks dan `isi.trim()` membuang spasi atau baris baru yang mungkin terbawa.
> Dua baris `if` membandingkan teks itu dengan `ON` dan `OFF`, dan perbandingannya peka huruf besar kecil sehingga nilai pada widget switch harus ditulis sama benar.
> `mqtt.setCallback()` mendaftarkan fungsi tadi, sedangkan `mqtt.subscribe()` harus dipanggil setiap kali sambungan broker baru terbentuk, karena bila diletakkan di `setup()` saja langganan hilang begitu sambungan pernah terputus lalu disambung ulang.
> `mqtt.loop()` yang sudah ada di `loop()` tetap wajib dipanggil setiap putaran, sebab fungsi penerima hanya dijalankan dari dalamnya.
> Di sini terlihat sekali lagi mengapa `delay()` panjang merugikan, karena selama program membeku perintah dari dasbor menumpuk dan sakelar di layar terasa lambat menanggapi; mari kita rangkai semuanya di depan kelas.

### Frame 11 — Demo Membangun Dasbor Pertama

Kawasan: Ruang Praktik

Teks di layar:
- Buktikan jalur data dengan `debug` lebih dahulu
- `mqtt in`, dua `change`, lalu ketiga widget
- Switch dihubungkan ke `mqtt out` topik perintah
- Putar potensiometer: gauge dan chart bergerak
- Tekan switch: LED dan log serial berubah

Yang Anda ucapkan:
> Kita ikuti urutan pada Bab 7 materi pertemuan ini, dan urutan itu tidak sembarang: jalur data dibuktikan dahulu dengan node `debug`, baru widget dipasang, sebab bila dibalik Anda akan menatap gauge kosong tanpa tahu apakah penyebabnya data yang tidak datang, payload yang belum diambil per field, atau widget yang belum punya grup.
> Langkah pertama memastikan proyek Pertemuan 9 masih mengirim payload JSON, ditambah satu field status berisi `AMAN` atau `BAHAYA` sesuai keadaan aktuator, karena indikator dasbor akan membacanya.
> Setelah Node-RED berjalan dan paket dasbor terpasang, node `mqtt in` diberi konfigurasi server berisi alamat broker dan porta `1883`, diisi topik data Anda, lalu keluarannya dipilih sebagai objek JSON yang sudah diuraikan; satu node `debug` dihubungkan dan Deploy ditekan sampai panel debug memperlihatkan objek dengan field `suhu_c` dan `status`.
> Baru sesudah itu dua node `change` dipasang, gauge dan chart disambungkan ke yang pertama dengan skala 20 sampai 45 pada tab dan grup baru, widget teks disambungkan ke yang kedua, lalu switch bernilai `ON` dan `OFF` dihubungkan ke node `mqtt out` bertopik perintah, dan program perangkat ditambahi fungsi penerima beserta pendaftaran langganan.
> Yang harus terlihat ada empat: jarum gauge berpindah beberapa saat setelah nilai sensor diubah dan chart menumbuhkan garis dari kiri ke kanan, indikator teks berganti antara AMAN dan BAHAYA, menekan switch membuat LED di simulator berubah dalam hitungan detik sambil log serial mencatat perintah yang diterima, dan menutup lalu membuka kembali halaman dasbor tidak mematikan flow.
> Butir terakhir terjadi karena flow berjalan di layanan Node-RED dan bukan di dalam halaman peramban; kalau yang Anda lihat berbeda, gejalanya biasanya sudah ada di daftar berikut.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Praktik

Teks di layar:
- Debug sepi: topik salah tulis atau perangkat diam
- Node MQTT terputus: alamat atau porta broker salah
- Gauge nol: payload masih berupa objek utuh
- Halaman dasbor kosong: widget belum punya grup
- Status berkedip sendiri: kedua topik bernama sama

Yang Anda ucapkan:
> Kesalahan paling umum pada pertemuan ini bukan salah menyusun widget, melainkan data yang sebenarnya belum pernah sampai ke Node-RED, dan tabel penelusuran masalah pada Bab 7 materi pertemuan ini memuat enam gejalanya.
> Bila panel debug tidak pernah menampilkan apa pun, bandingkan topik di node `mqtt in` dengan topik di program huruf demi huruf dan pastikan klien MQTT Anda masih menerima kiriman; bila node MQTT berlabel terputus, periksa alamat dan porta broker pada konfigurasi server lalu tekan Deploy ulang agar sambungan dicoba lagi.
> Bila gauge tetap nol padahal debug menampilkan data, payload yang masuk masih berupa objek utuh, jadi periksa node `change` apakah sasarannya `msg.payload` dan nilainya diambil dari `msg.payload.suhu_c`.
> Bila halaman dasbor kosong atau tidak ditemukan, cobalah alamat halaman dari kedua generasi paket, lalu pastikan setiap widget sudah menunjuk sebuah grup pada panel tata letak dasbor.
> Bila switch ditekan tetapi perangkat diam, pastikan pendaftaran langganan dijalankan setelah sambungan broker berhasil dan bandingkan huruf besar kecil antara nilai switch dengan pembanding di program; sedangkan status yang berkedip sendiri hampir selalu berarti topik data dan topik perintah memakai nama yang sama.
> Bila satu langkah tidak berhasil, hapus node terakhir yang Anda tambahkan dan pastikan flow sebelumnya masih bekerja, dan saat meminta bantuan sebutkan langkah keberapa yang macet beserta isi panel debug saat itu; sekarang kita rangkum pertemuan ini.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 10

Kawasan: Penutup dan Tugas

Teks di layar:
- Node-RED mengubah pesan beredar menjadi tampilan dan perintah
- Perubahan kanvas belum berlaku sebelum Deploy ditekan
- `debug` adalah alat pemeriksa pertama Anda
- Dua topik: data ke dasbor, perintah ke perangkat
- Checkpoint: data tampil, perintah sampai, alur dijelaskan

Yang Anda ucapkan:
> Mari kita kumpulkan intinya: Node-RED duduk di sisi penerima sesudah broker dan tidak menggantikan perangkat atau broker, melainkan mengubah pesan yang sudah beredar menjadi tampilan dan perintah.
> Satu flow tersusun dari node yang dihubungkan wire, yang mengalir di antaranya adalah objek pesan dengan `msg.payload` sebagai bagian yang paling sering dipakai, dan perubahan di kanvas belum berlaku sebelum Deploy ditekan sehingga node `debug` menjadi alat pemeriksa pertama ketika hasil tidak sesuai dugaan.
> Widget dasbor berasal dari paket tambahan dan setiap widget harus berada dalam grup di dalam tab, sementara nama node dan alamat halaman berbeda antargenerasi paket sehingga kenalilah dari bentuknya, bukan dari hafalan nama menu.
> Alur dua arah memakai dua topik, yaitu perangkat menerbitkan ke topik data yang dilanggan dasbor dan dasbor menerbitkan ke topik perintah yang dilanggan perangkat, dengan satu fungsi penerima dan satu langganan yang diperbarui setiap kali sambungan broker terbentuk.
> Checkpoint evaluasi pada Bab 12 materi pertemuan ini menuntut tiga hal: data tampil di dasbor, alur kendali arah balik ada, dan Anda dapat menjelaskan perjalanan dari sensor sampai layar.
> Cara memastikannya adalah membuka halaman dasbor lalu memutar potensiometer, menggeser kendali lalu mencari baris perintah masuk di log serial, dan menunjuk berurutan sensor, program perangkat, broker, node masuk, node pengolah, serta widget dengan kalimat Anda sendiri; setelah itu Anda siap mengerjakan tugasnya.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup dan Tugas

Teks di layar:
- Bangun dasbor mini untuk kasus pilihan Anda
- Wajib: indikator angka, indikator status, satu kendali
- Topik data dan perintah terpisah, memuat identitas
- Kumpulkan flow, tangkapan layar, log, catatan
- Bobot: data tampil `25%`, kendali balik `25%`

Yang Anda ucapkan:
> Tugas Anda adalah membangun satu dasbor mini untuk kasus yang Anda pilih sejak Pertemuan 8, memakai perangkat di simulator yang sudah mengirim data secara hemat sejak Pertemuan 9.
> Ketentuan wajibnya tiga: dasbor memuat sekurangnya satu indikator angka, satu indikator status nyala atau mati, dan satu kendali yang mengirim perintah ke perangkat; perangkat benar-benar menanggapi perintah itu; serta topik data dan topik perintah terpisah dan memuat nomor induk Anda.
> Yang dikumpulkan adalah berkas flow hasil ekspor atau salinan teks JSON-nya, tangkapan layar halaman dasbor yang menampilkan ketiga bagian wajib dengan nilai terisi, kutipan log serial yang memuat baris pengiriman data dan baris perintah masuk, serta catatan satu halaman.
> Catatan itu berisi gambar alur dari sensor sampai layar, nama kedua topik, dan satu paragraf tentang kendala yang Anda temui beserta cara mengatasinya.
> Penilaiannya terbagi menjadi data perangkat tampil di dasbor dan kendali arah balik bekerja masing-masing `25%`, kelengkapan bagian wajib `20%`, kerapian flow `15%`, serta penjelasan alur `15%` yang harus memakai istilah sendiri dan bukan salinan materi; ingat pula bahwa tugas latihan mingguan berbobot dua puluh persen dari nilai akhir.
> Dua pertanyaan pembuka tadi kini sudah terjawab: satu nilai sampai ke layar melalui broker, node masuk, node pengolah, lalu widget, dan satu tekanan tombol kembali ke perangkat melalui topik perintah yang dilanggan program Anda sendiri.
