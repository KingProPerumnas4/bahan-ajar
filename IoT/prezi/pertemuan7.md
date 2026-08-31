# Prezi Pertemuan 7 — Dasar Komunikasi Data IoT: MQTT

## Kanvas utama

Saat Prezi dibuka, kanvas terlihat utuh sebelum zoom pertama: judul pertemuan berada di tengah, dan enam kawasan mengelilinginya sebagai satu jalur perjalanan sebuah pesan, dari gagasan dasar MQTT, ke istilah-istilah yang menyusunnya, lalu ke bentuk aliran pesannya, dan berakhir pada bukti kerja di simulator. Kawasan di sisi kiri berisi gerbang dan gagasan pokok, kawasan tengah berisi enam istilah kunci beserta peta aliran pesan yang membandingkan MQTT dengan HTTP, sedangkan kawasan kanan berisi kode, praktik, kesalahan yang sering muncul, serta penilaian, sehingga jalur zoom bercerita dari pertanyaan menuju pembuktian. Setiap perpindahan bergerak satu langkah ke kanan, dan sesekali kamera menjauh sebentar agar Anda dapat melihat kembali posisi bahasan di dalam gambar besar sebelum layar menutup rapat pada frame berikutnya.

- Kawasan 1: Gerbang — judul pertemuan, pertanyaan pemancing, dan capaian pembelajaran.
- Kawasan 2: Gagasan MQTT — definisi MQTT, pola publish-subscribe, dan alasan kecocokannya.
- Kawasan 3: Enam Istilah Kunci — broker, topic, publisher, subscriber, payload, dan QoS.
- Kawasan 4: Peta Aliran Pesan — arsitektur publish-subscribe dan perbandingan dengan HTTP.
- Kawasan 5: Ruang Praktik — alur kode, demo publish dan subscribe, serta kesalahan yang sering muncul.
- Kawasan 6: Penutup — ringkasan, checkpoint evaluasi, dan tugas beserta penilaiannya.

## Alur zoom

1. Satu Pesan, Banyak Penerima
2. Capaian Pembelajaran Pertemuan Ini
3. MQTT: Protokol Ringan untuk IoT
4. Broker sebagai Pusat Pesan
5. Topic Memisahkan Jenis Data
6. Publisher, Subscriber, dan Payload
7. Tiga Tingkat Jaminan QoS
8. Satu Publisher, Banyak Subscriber
9. MQTT Dibandingkan dengan HTTP
10. Alur Kode Publish ESP32
11. Demo Publish dan Subscribe
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 7
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Satu Pesan, Banyak Penerima

Kawasan: Gerbang

Teks di layar:
- Pertemuan 7: dasar komunikasi data IoT, MQTT
- HTTP menunggu permintaan sebelum data berpindah
- Bagaimana satu pesan sampai ke banyak penerima?
- Jawaban lengkap menjelang frame terakhir

Yang Anda ucapkan:
> Selamat datang pada Pertemuan 7. Pada pertemuan sebelumnya Anda sudah membuat device mengirim data melalui HTTP, dan di sana setiap pertukaran data selalu dimulai oleh sebuah permintaan. Materi hari ini memperkenalkan MQTT, yaitu protokol komunikasi yang dirancang agar ringan, sederhana, dan efisien untuk pertukaran data antar perangkat dan layanan. Pertanyaan pembuka kita ada di layar, yaitu bagaimana satu pesan dari sebuah device dapat sampai ke banyak penerima sekaligus, dan kapan cara itu lebih tepat daripada HTTP. Jawabannya baru lengkap setelah kita melewati enam istilah kunci MQTT, membandingkannya dengan HTTP, lalu membuktikannya sendiri di simulator dan MQTTX. Kita mulai dari capaian yang harus Anda kuasai.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Gerbang

Teks di layar:
- Memahami MQTT sebagai protokol komunikasi ringan
- Mengenal broker, topic, publisher, subscriber, payload, QoS
- Membedakan pola MQTT dengan pola HTTP
- Publish data dari simulator ke topic
- Subscribe memakai MQTTX, uji beberapa payload

Yang Anda ucapkan:
> Capaian pertemuan ini dibagi menjadi yang perlu Anda pahami dan yang perlu Anda kerjakan. Sisi pemahaman mencakup makna MQTT sebagai protokol komunikasi ringan untuk IoT, peran broker, topic, publisher, subscriber, payload, dan QoS, perbedaan pola komunikasi MQTT dengan HTTP, serta alur data publish-subscribe dalam sistem IoT. Sisi keterampilan mencakup mem-publish data dari simulator ke topic MQTT, melakukan subscribe menggunakan MQTTX, menguji beberapa payload berbeda pada topic yang sesuai, dan menjelaskan mengapa MQTT cocok untuk komunikasi ringan dan real-time sederhana. Target minimum pertemuan ini adalah Anda memahami pola publish-subscribe, dengan checkpoint bahwa publish berhasil, subscribe berhasil, dan Anda mampu menjelaskan perbedaan HTTP dengan MQTT. Contoh konkret yang menanti di akhir pertemuan adalah sistem sensor virtual yang mem-publish suhu dan kelembapan ke dua topic berbeda. Sebelum ke sana, kita perlu tahu lebih dahulu apa yang membuat MQTT berbeda.

### Frame 3 — MQTT: Protokol Ringan untuk IoT

Kawasan: Gagasan MQTT

Teks di layar:
- MQTT dirancang ringan, sederhana, dan efisien
- Pola publish-subscribe, bukan menunggu permintaan langsung
- Pengirim tidak perlu tahu siapa penerimanya
- Satu publisher dapat melayani banyak subscriber
- Cocok untuk telemetri, pemantauan, notifikasi ringan

Yang Anda ucapkan:
> MQTT adalah protokol komunikasi yang dirancang agar ringan, sederhana, dan efisien untuk pertukaran data antar perangkat dan layanan. Perbedaan terpentingnya dari HTTP terletak pada pola kerjanya, karena MQTT memakai pola publish-subscribe, bukan pola yang menunggu permintaan langsung. Dalam pola itu pengirim data tidak perlu tahu siapa penerimanya secara spesifik, ia cukup mengirim data ke sebuah topic, lalu penerima yang berlangganan topic itu menerima datanya. Materi ini mengumpamakannya sebagai papan pengumuman digital di kampus, seseorang menempelkan pengumuman pada kategori tertentu seperti Info Akademik, dan orang yang tertarik cukup melihat papan kategori itu tanpa perlu dikirimi pesan satu per satu. Ada tiga alasan MQTT penting untuk IoT, yaitu ringan karena overhead komunikasinya relatif kecil, efisien untuk pengiriman data sensor periodik atau event sederhana, dan fleksibel karena satu publisher dapat melayani banyak subscriber melalui topic yang sama. Karena itu MQTT cocok ketika sistem membutuhkan telemetri, pemantauan status, notifikasi ringan, atau kontrol sederhana yang berlangsung terus-menerus, misalnya sensor suhu, kelembapan, status lampu, atau alarm. Kita bedah sekarang komponennya, dimulai dari pihak yang berada di tengah semua lalu lintas pesan.

### Frame 4 — Broker sebagai Pusat Pesan

Kawasan: Enam Istilah Kunci

Teks di layar:
- Semua pesan publisher masuk ke broker
- Broker meneruskan pesan ke subscriber topic itu
- Broker menjadi penghubung pengirim dan penerima
- Alamat broker harus diketahui program device

Yang Anda ucapkan:
> Broker adalah pusat lalu lintas pesan dalam MQTT. Semua pesan dari publisher masuk ke broker, kemudian broker meneruskan pesan itu ke subscriber yang berlangganan topic terkait, sehingga broker bertindak sebagai penghubung utama antara pengirim dan penerima. Materi ini mengumpamakan broker sebagai kantor pos pusat, pengirim cukup mengirim surat ke kantor pos, lalu kantor pos yang mendistribusikannya ke penerima yang tepat. Konsekuensi praktisnya terlihat pada program, karena device harus tahu ke broker mana ia mengirim data, dan itulah tugas pemanggilan `client.setServer()` yang dijelaskan pada Bab 6.2 materi pertemuan ini. Perhatikan juga bahwa broker menentukan keberhasilan seluruh praktik, sebab bila alamat broker salah, pesan tidak akan pernah sampai walau program tampak berjalan. Setelah tahu ke mana pesan dikirim, pertanyaan berikutnya adalah ke jalur mana pesan itu diletakkan.

### Frame 5 — Topic Memisahkan Jenis Data

Kawasan: Enam Istilah Kunci

Teks di layar:
- Topic adalah jalur atau kategori pesan
- Contoh: `kampus/lab/suhu` dan `kampus/lab/kelembapan`
- Subscriber hanya menerima data yang dibutuhkan
- Pemisahan topic membuat data lebih rapi

Yang Anda ucapkan:
> Topic adalah jalur atau kategori pesan di dalam MQTT. Materi ini memberi contoh yang langsung dapat Anda pakai, yaitu data suhu dikirim ke topic `kampus/lab/suhu` sedangkan data kelembapan dikirim ke topic `kampus/lab/kelembapan`. Gunanya jelas, topic memisahkan jenis data sehingga subscriber hanya menerima informasi yang memang dibutuhkan. Materi ini mengumpamakan topic sebagai label rak di perpustakaan, buku fisika dan buku sejarah ditempatkan pada kategori berbeda sehingga pembaca dapat langsung menuju rak yang sesuai minatnya. Pada praktik nanti Anda memakai dua topic terpisah untuk suhu dan kelembapan, dan alasannya dibahas pada Bab 6.4 materi pertemuan ini, yaitu jika semua data dicampur dalam satu topic tanpa struktur jelas, subscriber akan lebih sulit mengolah informasi. Kini kita lihat siapa yang menaruh pesan pada jalur itu dan siapa yang mengambilnya.

### Frame 6 — Publisher, Subscriber, dan Payload

Kawasan: Enam Istilah Kunci

Teks di layar:
- Publisher mengirim pesan ke topic tertentu
- ESP32 sering berperan sebagai publisher sensor
- Subscriber mendaftar menerima pesan dari topic
- MQTTX dapat berperan sebagai subscriber pemantau
- Payload contohnya `28.5` atau `{"suhu":28.5}`

Yang Anda ucapkan:
> Tiga istilah pada frame ini melengkapi gambaran tadi. Publisher adalah pihak yang mengirim pesan ke topic tertentu, dan dalam konteks IoT publisher sering berupa device seperti ESP32 yang mengirim data sensor. Subscriber adalah pihak yang mendaftar untuk menerima pesan dari topic tertentu, dan MQTTX dapat berperan sebagai subscriber ketika dipakai untuk memantau data dari device. Payload adalah isi pesan yang dikirim, dan bentuknya dapat berupa angka, teks, status, atau format data sederhana seperti JSON. Contoh dari materi ini, payload suhu bisa berupa `28.5` atau `{"suhu":28.5}`, jadi satu nilai yang sama dapat dikirim dalam dua bentuk penulisan. Yang perlu Anda pegang, ketiganya bertemu pada topic, bukan saling menghubungi secara langsung. Satu istilah kunci masih tersisa, yaitu seberapa kuat jaminan bahwa pesan itu benar-benar sampai.

### Frame 7 — Tiga Tingkat Jaminan QoS

Kawasan: Enam Istilah Kunci

Teks di layar:
- QoS adalah tingkat jaminan pengiriman pesan
- `QoS 0` dikirim sekali tanpa jaminan ulang
- `QoS 1` diupayakan sampai minimal sekali
- `QoS 2` dijaga diterima tepat satu kali
- Jaminan lebih tinggi, biaya komunikasi bertambah

Yang Anda ucapkan:
> QoS adalah singkatan dari Quality of Service, yaitu tingkat jaminan pengiriman pesan. Pada pertemuan pengantar ini cukup Anda pahami bahwa MQTT menyediakan beberapa pilihan tingkat keandalan pengiriman, dan semakin tinggi jaminannya umumnya semakin besar biaya komunikasi atau kompleksitasnya. Tabel pada Bab 2.6 materi pertemuan ini merangkum tiga tingkat itu, `QoS 0` berarti pesan dikirim sekali tanpa jaminan ulang, `QoS 1` berarti pesan diupayakan sampai minimal sekali, dan `QoS 2` berarti pesan dijaga agar diterima tepat satu kali. Pemilihannya mengikuti sifat datanya, misalnya suhu periodik cocok memakai tingkat paling ringan karena nilainya sering diperbarui, sedangkan tingkat yang lebih tinggi dipakai saat kehilangan pesan lebih merugikan atau saat duplikasi harus dihindari. Jadi jangan otomatis memilih jaminan tertinggi, sebab pilihan itu selalu punya harga. Dengan enam istilah tadi lengkap, kita dapat melihat bentuk keseluruhan aliran pesannya.

### Frame 8 — Satu Publisher, Banyak Subscriber

Kawasan: Peta Aliran Pesan

Teks di layar:
- Publisher dan subscriber bertemu melalui broker
- Keduanya tidak berkomunikasi langsung satu sama lain
- Sistem lebih longgar keterikatannya dan mudah dikembangkan
- Penerima bertambah tanpa mengubah logika pengiriman

Yang Anda ucapkan:
> Pola publish-subscribe adalah inti MQTT, dan pada pola itu publisher tidak berkomunikasi langsung dengan subscriber, keduanya bertemu melalui broker. Akibatnya sistem menjadi lebih longgar keterikatannya, lebih mudah dikembangkan, dan lebih fleksibel ketika jumlah device atau penerima bertambah. Diagram pada Bab 3 materi pertemuan ini menunjukkan bentuknya dengan jelas, sebuah publisher berupa ESP32 di simulator mengirim ke broker, lalu broker meneruskan pesan ke dua subscriber sekaligus, yaitu MQTTX dan sebuah dashboard atau service, dan keduanya berlangganan topic yang sama. Perhatikan bahwa satu publisher dapat melayani lebih dari satu subscriber tanpa perlu mengubah logika dasar pengiriman, dan inilah salah satu kekuatan utama MQTT dalam ekosistem IoT. Materi ini mengumpamakannya sebagai satu stasiun radio yang menyiarkan ke frekuensi tertentu, banyak pendengar dapat menerima siaran itu bersamaan selama mereka menyetel frekuensi yang sama. Sekarang perbedaannya dengan HTTP dapat kita letakkan berdampingan.

### Frame 9 — MQTT Dibandingkan dengan HTTP

Kawasan: Peta Aliran Pesan

Teks di layar:
- HTTP request-response, MQTT publish-subscribe
- HTTP: client meminta langsung ke server
- MQTT: publisher ke broker, subscriber dari topic
- Perangkat kecil: MQTT relatif lebih ringan
- Distribusi banyak penerima alami pada MQTT

Yang Anda ucapkan:
> Salah satu capaian pertemuan ini adalah Anda mampu menjelaskan perbedaan HTTP dan MQTT, jadi frame ini perlu Anda kuasai sampai dapat ditulis ulang dari ingatan. Tabel pada Bab 4 materi pertemuan ini membandingkan keduanya pada lima aspek. Pola komunikasinya berbeda, HTTP memakai request-response sedangkan MQTT memakai publish-subscribe, dan hubungan pengirim dengan penerimanya juga berbeda, pada HTTP client meminta langsung ke server sedangkan pada MQTT publisher mengirim ke broker lalu subscriber menerima dari topic. Kecocokan umumnya pun tidak sama, HTTP lebih pas untuk akses API serta pengiriman atau pengambilan data sesekali, sedangkan MQTT lebih pas untuk telemetri ringan, monitoring, notifikasi, dan kontrol sederhana. Dua aspek terakhir menyangkut efisiensi dan distribusi, untuk perangkat kecil HTTP relatif lebih berat sedangkan MQTT relatif lebih ringan, dan pengiriman ke banyak penerima tidak alami pada HTTP karena perlu mekanisme tambahan, tetapi alami pada MQTT melalui subscriber pada topic yang sama. Materi ini mengumpamakan HTTP seperti menelepon resepsionis untuk meminta informasi lalu menunggu jawaban, sedangkan MQTT seperti siaran pengumuman di speaker gedung yang diterima siapa pun yang sedang mendengarkan kanal itu. Teorinya cukup, mari kita lihat bentuknya di dalam program.

### Frame 10 — Alur Kode Publish ESP32

Kawasan: Ruang Praktik

Teks di layar:
- Sertakan pustaka WiFi dan PubSubClient
- `setupWifi()` menghubungkan device ke jaringan
- `client.setServer()` menentukan broker dan port
- `reconnectMQTT()` menyambung ulang bila koneksi putus
- `client.publish()` mengirim payload ke dua topic

Yang Anda ucapkan:
> Contoh kode pada Bab 6 materi pertemuan ini memperlihatkan empat tahap penting, dan seluruh teori tadi ada di dalamnya. Tahap pertama menyiapkan pustaka, yaitu WiFi untuk jalur jaringan dan PubSubClient untuk MQTT, lalu objek klien jaringan dibuat dan klien MQTT dibangun di atasnya. Tahap kedua menghubungkan device ke Wi-Fi melalui `setupWifi()`, sebab sebelum publish ke broker device harus lebih dahulu terhubung ke jaringan. Tahap ketiga menyiapkan koneksi ke broker dengan `client.setServer()` yang menentukan alamat broker dan port, sedangkan `reconnectMQTT()` menjaga koneksi tetap aktif dengan mencoba menyambung ulang bila koneksi putus. Tahap keempat adalah inti pola publish-subscribe, yaitu di dalam `loop()` program memeriksa koneksi, lalu nilai suhu `28.5` dan kelembapan `70.2` dikirim memakai `client.publish()` ke dua topic berbeda, kemudian program menunggu sebelum pengiriman berikutnya. Dari sudut pandang teori, inilah implementasi konkret peran device sebagai publisher. Mari kita jalankan pola itu dan buktikan pesannya benar-benar sampai.

### Frame 11 — Demo Publish dan Subscribe

Kawasan: Ruang Praktik

Teks di layar:
- Siapkan proyek simulator ESP32 pendukung MQTT
- Tentukan broker, lalu tetapkan dua topic
- Jalankan simulator sampai device mulai publish
- Subscribe topic sama di MQTTX, amati payload
- Nilai berubah di publisher, terlihat di subscriber

Yang Anda ucapkan:
> Sekarang kita ikuti langkah umum pada Bab 5.3 materi pertemuan ini, dan Anda mengerjakan urutan yang sama nanti. Proyek simulator ESP32 yang mendukung pengiriman MQTT disiapkan, broker yang dipakai ditentukan, lalu topic ditetapkan, misalnya `iot/lab/suhu` dan `iot/lab/kelembapan`. Simulator dijalankan sampai ESP32 mulai mem-publish data, kemudian MQTTX dibuka dan subscribe dilakukan pada topic yang sama. Yang harus terlihat ada di dua tempat, pada Serial Monitor koneksi ke broker berhasil dan nilai suhu serta kelembapan dikirim berulang ke dua topic yang berbeda, sedangkan pada MQTTX setiap payload yang dipublikasikan muncul di antarmukanya. Empat butir pengamatan pada Bab 7.1 materi pertemuan ini menjadi pemeriksaan Anda, yaitu koneksi ke broker berhasil, topic yang dipakai sudah benar, payload muncul sesuai format yang diharapkan, dan perubahan nilai pada publisher terlihat pada sisi subscriber. Butir terakhir itu yang paling sering dilewatkan, padahal justru di situ Anda melihat arus data secara nyata, bukan sekadar berasumsi program sudah jalan. Bila payload tidak muncul, ada beberapa tempat yang perlu Anda periksa lebih dahulu.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Praktik

Teks di layar:
- Alamat broker salah, koneksi tidak terbentuk
- Nama topic berbeda antara program dan MQTTX
- Koneksi jaringan gagal, publish tidak berjalan
- Logika publish salah, payload tidak keluar
- Hanya status koneksi ditunjukkan, bukan payload

Yang Anda ucapkan:
> Materi ini menyebut empat sumber masalah yang paling sering muncul bila payload tidak juga tampil, yaitu alamat broker, nama topic, koneksi jaringan, dan logika publish pada program. Alamat broker yang salah membuat koneksi tidak pernah terbentuk, jadi pesan tidak berpindah sama sekali meski program tampak berjalan. Nama topic yang berbeda antara program dan MQTTX juga sering terjadi, akibatnya publish memang jalan tetapi Anda menunggu pada jalur yang bukan tempat pesan itu diletakkan, sehingga penulisan topic pada Bab 2.2 materi pertemuan ini perlu Anda cocokkan huruf per huruf. Koneksi jaringan yang gagal menghentikan langkah sebelum publish, sedangkan logika publish yang salah membuat payload tidak pernah keluar walaupun koneksi sudah aman, dan obat untuk keduanya adalah membaca ulang Bab 6.2 dan Bab 6.3 materi pertemuan ini, terutama bagian koneksi ke broker dan pemanggilan publish untuk masing-masing topic. Kesalahan terakhir bersifat pembuktian, yaitu Anda hanya menunjukkan status koneksi berhasil, padahal yang diminta adalah payload dari kedua topic beserta perubahan nilainya. Mari kita padatkan seluruh pertemuan ini menjadi daftar pemeriksaan diri.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 7

Kawasan: Penutup

Teks di layar:
- MQTT ringan, komponennya broker sampai QoS
- Publish-subscribe berbeda dari request-response HTTP
- Checkpoint: publish berhasil, subscribe berhasil, perbedaan dijelaskan
- Bekal terakhir sebelum CP-2 pada Pertemuan 8

Yang Anda ucapkan:
> Mari kita rangkum. MQTT adalah protokol komunikasi ringan yang sangat cocok untuk IoT, komponen utamanya meliputi broker, topic, publisher, subscriber, payload, dan QoS, pola komunikasinya publish-subscribe yang berbeda dari HTTP yang berbasis request-response, ESP32 dapat berperan sebagai publisher yang mengirim data sensor ke broker, MQTTX membantu memantau dan menguji pesan sebagai subscriber, dan pemisahan topic membuat data lebih rapi serta mudah dikelola. Checkpoint pertemuan ini, yang rinciannya ada pada Bab 11 materi pertemuan ini, meminta tiga bukti dari Anda, yaitu publish berhasil, subscribe berhasil, dan Anda dapat menjelaskan perbedaan HTTP dengan MQTT. Cara memastikannya sudah disediakan, publish diperiksa lewat Serial Monitor yang menunjukkan koneksi ke broker berhasil serta nilai suhu dan kelembapan dikirim berulang ke dua topic, subscribe diperiksa lewat empat butir pengamatan di MQTTX, sedangkan pemahaman perbedaan diuji dengan menutup materi lalu menulis ulang minimal tiga baris tabel Bab 4 dari ingatan. Perhatikan pula letak pertemuan ini, karena Pertemuan 7 adalah bekal terakhir sebelum checkpoint besar CP-2 pada Pertemuan 8, yang berupa integrasi simulator dasar dengan sensor virtual, aktuator, dan komunikasi data dalam satu sistem kecil yang utuh. Karena itu bagian yang belum tercapai sebaiknya Anda tuntaskan sekarang, bukan ditunda. Tinggal satu hal lagi, yaitu tugas yang harus Anda kerjakan beserta cara penilaiannya.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup

Teks di layar:
- Publish suhu dan kelembapan ke dua topic
- Publish dua topic 30%, penamaan topic 20%
- Bukti hasil subscribe 25%, penjelasan hasil 25%
- Topic bertingkat, memuat penanda milik Anda
- Tugas mingguan menyumbang 20 persen nilai akhir

Yang Anda ucapkan:
> Tugas latihan pertemuan ini ada pada Bab 5.4 materi pertemuan ini, yaitu membuat sistem sensor virtual yang mem-publish data suhu dan kelembapan ke dua topic berbeda, sehingga Anda mengalami sendiri bahwa setiap parameter dapat dikelompokkan pada topic yang jelas dan subscriber dapat memilih data yang relevan. Penilaiannya terbagi empat, yaitu publish ke dua topic berhasil 30 persen, penamaan topic yang tertata 20 persen, bukti hasil subscribe 25 persen, dan penjelasan hasil 25 persen, sementara tugas latihan mingguan seperti ini berbobot 20 persen dari nilai akhir mata kuliah. Bacalah kolom kriteria nilai penuh sebelum mulai mengerjakan, sebab di situ terlihat bahwa nama topic harus tersusun bertingkat, memuat penanda milik Anda sendiri agar tidak bertabrakan dengan pengguna lain pada broker publik, dan ditulis sebagai konstanta di satu tempat di dalam program. Bukti hasil subscribe juga harus berupa tangkapan layar MQTTX yang memperlihatkan payload dari kedua topic beserta perubahan nilainya, bukan hanya status koneksi berhasil, sedangkan penjelasan hasil menuntut Anda menceritakan perjalanan satu pesan dari program sampai muncul di MQTTX serta alasan memisahkan dua topic dibanding menggabungkan keduanya menjadi satu. Ada pula tugas kecil pada Bab 10.2 materi pertemuan ini, yaitu merancang sistem monitoring ruangan dengan menentukan publisher yang dipakai, dua nama topic, contoh payload masing-masing topic, siapa subscriber-nya, dan informasi apa yang ingin dipantau pengguna. Dan inilah jawaban lengkap pertanyaan pembuka kita, satu pesan dapat sampai ke banyak penerima karena publisher hanya mengirim ke topic yang dikelola broker dan tidak menghubungi penerima satu per satu, sehingga cara ini lebih tepat daripada HTTP ketika data kecil perlu dikirim terus-menerus, hemat sumber daya, dan dipantau beberapa penerima sekaligus tanpa mengubah kode publisher.
