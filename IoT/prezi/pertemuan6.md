# Prezi Pertemuan 6 — Dasar Komunikasi Data IoT: HTTP

## Kanvas utama

Saat Prezi dibuka, kanvas terlihat utuh sebelum zoom pertama: judul pertemuan berada di tengah, dan di sekelilingnya enam kawasan tersusun sebagai satu jalur mendatar yang meniru perjalanan sebuah data suhu, dari alasan data itu perlu keluar dari device, ke aturan percakapannya, ke bentuk datanya, lalu ke ruang praktik dan penutup. Kawasan di sisi kiri berisi alasan dan definisi, kawasan tengah berisi anatomi percakapan antara dua pihak, dan kawasan kanan berisi kode, praktik, serta penilaian, sehingga jalur zoom bercerita dari pertanyaan menuju bukti kerja. Setiap perpindahan bergerak satu langkah ke kanan dan sesekali menjauh sebentar, agar Anda dapat melihat kembali posisi bahasan di dalam gambar besar sebelum layar menutup rapat pada frame berikutnya.

- Kawasan 1: Gerbang — judul pertemuan, pertanyaan pemancing, dan capaian pembelajaran.
- Kawasan 2: Alasan Terhubung — mengapa device perlu berkomunikasi dan apa itu HTTP.
- Kawasan 3: Peta Percakapan — peran client dan server, isi request dan response, serta GET dan POST.
- Kawasan 4: Bentuk Data — teks biasa, JSON, kecocokan dan keterbatasan HTTP.
- Kawasan 5: Ruang Praktik — alur kode HTTP client, demo pengiriman periodik, dan kesalahan yang sering muncul.
- Kawasan 6: Penutup — ringkasan, checkpoint evaluasi, dan tugas praktik.

## Alur zoom

1. Ke Mana Data Suhu Pergi?
2. Capaian Pembelajaran Pertemuan Ini
3. Mengapa Device Perlu Berkomunikasi
4. Apa Itu HTTP
5. Peran Client dan Server
6. Isi Request dan Isi Response
7. GET Mengambil, POST Mengirim
8. Teks Biasa dan JSON
9. Kapan HTTP Cocok dan Terbatas
10. Alur Kode HTTP Client ESP32
11. Demo Pengiriman Periodik di Simulator
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 6
14. Tugas Praktik dan Pokok Penilaian

## Frame

### Frame 1 — Ke Mana Data Suhu Pergi?

Kawasan: Gerbang

Teks di layar:
- Pertemuan 6: dasar komunikasi data IoT, HTTP
- Data yang tinggal di device nilainya terbatas
- Kapan HTTP cocok, kapan mulai kurang efisien?
- Jawaban lengkap menjelang frame terakhir

Yang Anda ucapkan:
> Selamat datang pada Pertemuan 6. Sampai pertemuan lalu, ESP32 sudah Anda pakai untuk membaca input dan mengendalikan output, tetapi seluruh hasilnya tetap tinggal di dalam device. Materi hari ini berangkat dari satu kenyataan sederhana, yaitu jika data hanya tinggal di dalam device, nilainya menjadi terbatas. Sistem IoT baru terasa terhubung ketika device dapat mengirim data ke layanan lain, menerima informasi balasan, lalu bertindak berdasarkan hasil komunikasi itu. Karena itu pertanyaan pembuka kita adalah kapan HTTP sudah cukup untuk pekerjaan tersebut, dan kapan ia mulai terasa kurang efisien. Tahan dulu jawabannya, sebab baru lengkap setelah kita melewati pola request-response, bentuk data, dan praktik pengiriman. Kita mulai dari capaian yang harus Anda kuasai.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Gerbang

Teks di layar:
- Memahami pola request-response pada komunikasi IoT
- Membedakan peran client dan server
- Mengenal fungsi dasar HTTP GET dan POST
- Membedakan data teks biasa dan JSON
- Mengirim suhu virtual periodik lewat HTTP

Yang Anda ucapkan:
> Capaian pertemuan ini terbagi dua, yaitu yang perlu Anda pahami dan yang perlu Anda kerjakan. Sisi pemahaman mencakup pola request-response, perbedaan peran client dan server, fungsi dasar GET dan POST, perbedaan data teks biasa dan JSON, serta kapan HTTP cocok dipakai dan kapan ia kurang efisien untuk kebutuhan real-time ringan. Sisi keterampilan mencakup menjelaskan alur request dan response secara runtut, membaca contoh response sederhana, dan membuat simulasi device yang mengirim data suhu virtual secara periodik melalui HTTP. Target minimalnya adalah Anda memahami bahwa device IoT dapat berkomunikasi dengan layanan luar, mampu mengirim data, dan dapat menjelaskan alurnya beserta keterbatasan HTTP. Contoh konkretnya sudah menanti di akhir pertemuan, yaitu ESP32 yang mengirim nilai suhu virtual dan membaca kode status balasan dari server. Sebelum ke sana, kita perlu tahu mengapa device harus berbicara ke luar dirinya sama sekali.

### Frame 3 — Mengapa Device Perlu Berkomunikasi

Kawasan: Alasan Terhubung

Teks di layar:
- Device sudah membaca input dan mengendalikan output
- Data yang tidak dikirim nilainya terbatas
- Alur: sensor, ESP32, HTTP, server, pengguna
- Server dapat menjawab `data diterima` atau menolak

Yang Anda ucapkan:
> Selama beberapa pertemuan, device Anda bekerja sendiri, sensor dibaca lalu aktuator digerakkan, dan urusan selesai di situ. Persoalannya, data yang tidak pernah keluar dari device nilainya terbatas, karena tidak ada pihak lain yang dapat menyimpan, menampilkan, atau menanggapinya. Dalam alur IoT, HTTP biasanya muncul tepat di titik itu, yaitu ketika device perlu mengirim data ke server web, API, dashboard, atau layanan cloud. Contoh yang dipakai materi ini sederhana, sensor suhu virtual membaca nilai, device mengirim nilai itu ke server setiap beberapa detik, server menyimpannya, lalu mengirim respons seperti data diterima atau nilai tidak valid. Bayangkan sebuah kantor administrasi, Anda datang ke loket membawa permintaan, petugas memeriksa, kemudian hasilnya diberikan kembali kepada Anda. Pola itulah yang dipakai HTTP, dan sekarang kita lihat definisinya lebih dekat.

### Frame 4 — Apa Itu HTTP

Kawasan: Alasan Terhubung

Teks di layar:
- HTTP: Hypertext Transfer Protocol
- Aturan komunikasi: satu meminta, satu menjawab
- Client memulai, server memproses lalu membalas
- Di IoT, device biasanya aktif memulai komunikasi

Yang Anda ucapkan:
> HTTP adalah singkatan dari Hypertext Transfer Protocol. Secara sederhana, HTTP adalah aturan komunikasi yang digunakan ketika satu pihak meminta sesuatu dan pihak lain memberikan jawaban. Di web, browser memakai HTTP untuk meminta halaman, sedangkan dalam IoT device dapat memakainya untuk meminta data, mengirim data sensor, atau berkomunikasi dengan API. Hal terpenting yang perlu Anda pegang adalah HTTP bekerja dengan pola request-response, jadi komunikasi selalu dimulai oleh permintaan dari client, kemudian server memproses permintaan itu dan mengirim response. Konsekuensinya, dalam model HTTP device biasanya berperan aktif memulai komunikasi, bukan menunggu dikirimi. Karena ada dua pihak dengan peran berbeda, keduanya perlu kita pisahkan dengan jelas.

### Frame 5 — Peran Client dan Server

Kawasan: Peta Percakapan

Teks di layar:
- Client mengirim permintaan kepada server
- Server memproses lalu mengirim jawaban
- ESP32 sering berperan sebagai client
- Server bisa API, platform IoT, aplikasi web

Yang Anda ucapkan:
> Pada komunikasi HTTP ada dua peran utama yang harus Anda bedakan. Client adalah pihak yang mengirim permintaan, sedangkan server adalah pihak yang menerima permintaan, memprosesnya, lalu mengirim jawaban. Dalam konteks IoT, ESP32 sering berperan sebagai client ketika mengirim data, dan servernya bisa berupa API, platform IoT, atau aplikasi web. Materi ini mengumpamakannya sebagai pelanggan dan restoran, pelanggan memesan makanan, restoran menerima pesanan, menyiapkannya, lalu mengirimkan hasilnya. Yang perlu dicatat, pelanggan tidak masuk ke dapur untuk memasak sendiri, ia cukup mengirim permintaan sesuai menu yang tersedia. Begitu perannya jelas, kita dapat membuka isi pesan yang mereka pertukarkan.

### Frame 6 — Isi Request dan Isi Response

Kawasan: Peta Percakapan

Teks di layar:
- Request: method, alamat tujuan, header, body
- Header contohnya `Content-Type: application/json`
- Body membawa data, misalnya `{"suhu": 28.5}`
- Response: status code, header, isi balasan
- Status `200` berarti proses berhasil

Yang Anda ucapkan:
> Sebuah request HTTP umumnya memuat metode, alamat tujuan, dan kadang data tambahan. Metode menunjukkan jenis tindakan yang diinginkan, alamat tujuan menunjukkan ke mana request dikirim, sedangkan header memberi informasi tambahan, misalnya `Content-Type: application/json` yang memberi tahu server bahwa isinya JSON. Bagian body membawa data dan biasanya dipakai pada POST, contohnya `{"suhu": 28.5}` seperti pada tabel di Bab 2 materi pertemuan ini. Response adalah jawaban server setelah request diterima, dan isinya memuat status code, header, serta body, misalnya kode `200` yang berarti berhasil disertai pesan singkat atau data JSON. Perhatikan urutannya, client tidak tiba-tiba menerima data tanpa permintaan, sebab pada HTTP dasar data datang setelah client meminta lebih dahulu. Karena permintaan bisa berarti mengambil atau mengirim, metodenya pun dibedakan.

### Frame 7 — GET Mengambil, POST Mengirim

Kawasan: Peta Percakapan

Teks di layar:
- GET dipakai untuk mengambil data dari server
- Contoh GET: meminta konfigurasi atau waktu server
- POST dipakai untuk mengirim data ke server
- Contoh POST: nilai suhu atau status kelembapan
- Pilihan bergantung arah tujuan komunikasi

Yang Anda ucapkan:
> GET dan POST adalah dua metode yang paling sering Anda pakai. GET dipakai ketika client ingin mengambil data dari server, misalnya device meminta konfigurasi, waktu server, atau nilai tertentu dari API. POST dipakai ketika client ingin mengirim data ke server, misalnya device mengirim nilai suhu, status kelembapan, atau informasi sensor lain. Materi ini mengumpamakan GET seperti bertanya kepada petugas berapa nomor antrian saya, sedangkan POST seperti menyerahkan formulir yang sudah diisi agar diproses lebih lanjut. Contoh lain disebut pada Bab 5 materi pertemuan ini, jika GET yang dipakai, device umumnya justru mengambil nilai ambang batas suhu dari server, bukan mengirim body JSON. Jadi pemilihannya bergantung pada arah tujuan komunikasi, mengambil data atau mengirim data. Setelah metodenya ditentukan, pertanyaan berikutnya adalah bentuk data yang dibawa.

### Frame 8 — Teks Biasa dan JSON

Kawasan: Bentuk Data

Teks di layar:
- Teks biasa cukup untuk data tunggal, `28.5`
- JSON memberi pasangan kunci dan nilai
- `{"suhu": 28.5, "ruang": "lab-iot"}`
- Data IoT jarang hanya satu nilai
- Nama kunci jelas, penerima lebih mudah memproses

Yang Anda ucapkan:
> Data yang dikirim melalui HTTP tidak selalu harus rumit. Pada tahap awal, data bisa berupa teks biasa seperti `28.5` atau pesan sederhana seperti OK, dan bentuk itu sudah cukup untuk satu nilai tunggal yang tidak kompleks. Namun ketika data bertambah banyak dan perlu diberi label yang jelas, JSON menjadi lebih berguna karena setiap nilai punya pasangan kunci, seperti contoh di materi ini yang memuat suhu, ruang, dan status sekaligus. Alasannya praktis, data IoT jarang hanya satu nilai, sering kali sebuah device perlu mengirim suhu, kelembapan, ID alat, waktu pengiriman, dan status dalam satu kiriman. Materi ini mengumpamakan teks biasa seperti menulis angka suhu di secarik kertas, sedangkan JSON seperti formulir dengan kolom yang jelas. Dengan nama kunci yang jelas, server atau aplikasi penerima lebih mudah memproses datanya. Bentuk data sudah beres, sekarang kita nilai kapan HTTP memang pilihan yang tepat.

### Frame 9 — Kapan HTTP Cocok dan Terbatas

Kawasan: Bentuk Data

Teks di layar:
- Cocok untuk pengiriman berkala ke API
- Cocok saat integrasi layanan web diprioritaskan
- Setiap pertukaran selalu dimulai dari request baru
- Banyak device, jarak waktu pendek: kurang efisien
- MQTT dibahas pada Pertemuan 7

Yang Anda ucapkan:
> HTTP cocok dipakai pada beberapa keadaan yang disebut materi ini. Pertama, saat device perlu mengirim data ke API atau web service secara berkala. Kedua, saat komunikasi tidak harus super ringan dan tidak harus selalu real-time, dan ketiga, saat integrasi dengan layanan web atau kesederhanaan struktur komunikasi menjadi prioritas. Keterbatasannya justru berasal dari polanya sendiri, karena setiap pertukaran data biasanya dimulai dari request baru, sehingga bila data harus sangat sering dikirim oleh banyak device dengan overhead kecil, HTTP tidak selalu paling efisien. Untuk kebutuhan semacam itu, model komunikasi lain seperti MQTT sering lebih sesuai, dan hal itu akan dibahas pada Pertemuan 7. Sekarang kita turun ke kode dan melihat bentuk nyata pola request-response.

### Frame 10 — Alur Kode HTTP Client ESP32

Kawasan: Ruang Praktik

Teks di layar:
- Sertakan library WiFi dan HTTPClient
- Sambungkan Wi-Fi, tunggu status terhubung
- Susun payload JSON berisi suhu virtual
- `http.POST(payload)` mengirim, lalu baca kode respons
- Tutup sesi dengan `http.end()`, lalu tunggu

Yang Anda ucapkan:
> Contoh kode pada Bab 5 materi pertemuan ini dapat dibaca sebagai lima tahap. Tahap pertama menyiapkan library, yaitu WiFi dan HTTPClient, karena komunikasi HTTP memerlukan jalur jaringan. Tahap kedua mendefinisikan koneksi dan alamat tujuan, lalu tahap ketiga menghubungkan Wi-Fi dan menunggu sampai statusnya terhubung, sebab tanpa koneksi jaringan HTTP tidak dapat berjalan. Tahap keempat membuat request, yaitu menyusun payload JSON berisi nilai suhu virtual, menambahkan header format, kemudian memanggil `http.POST(payload)` yang mengembalikan kode respons. Tahap kelima membaca hasil, yaitu mencetak kode respons, dan bila nilainya positif isi balasan diambil dengan `http.getString()` lalu ditampilkan ke Serial Monitor. Sesudah itu sesi ditutup dengan `http.end()` agar sumber daya dibersihkan, dan program menunggu lima detik sebelum pengiriman berikutnya. Mari kita lihat kode itu berjalan di simulator.

### Frame 11 — Demo Pengiriman Periodik di Simulator

Kawasan: Ruang Praktik

Teks di layar:
- Siapkan proyek ESP32 di simulator
- Sambungkan ke jaringan Wi-Fi simulasi
- Kirim data suhu, lalu baca response
- Serial Monitor: `WiFi terhubung`, lalu kode respons
- Baris respons muncul berulang, bukan sekali

Yang Anda ucapkan:
> Sekarang kita jalankan urutan praktik pada Bab 4 materi pertemuan ini, dan Anda ikuti langkah yang sama nanti. Proyek ESP32 disiapkan di simulator, kode untuk menghubungkan device ke jaringan Wi-Fi simulasi ditambahkan, data suhu disusun dalam bentuk teks atau JSON, lalu dikirim ke endpoint server memakai HTTP. Yang harus terlihat pada Serial Monitor berurutan seperti ini, baris permintaan menghubungkan ke Wi-Fi muncul beberapa kali, lalu keterangan Wi-Fi terhubung, kemudian kode respons HTTP tercetak, dan bila nilainya positif isi balasan dari server ikut ditampilkan. Bagian terpenting justru pada pengulangannya, karena setelah menunggu lima detik seluruh urutan itu harus muncul lagi tanpa Anda menjalankan ulang program. Bila baris kode respons hanya muncul sekali, pengirimannya belum benar-benar periodik. Inti praktik ini bukan sekadar berhasil mengirim data, melainkan memahami siapa yang memulai komunikasi, data apa yang dibawa, bagaimana server menjawab, dan bagaimana device membaca hasilnya. Dari sini kita bahas kesalahan yang paling sering menghambat langkah tadi.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Praktik

Teks di layar:
- Wi-Fi belum terhubung, request tidak berjalan
- Kode status muncul hanya pada pengiriman pertama
- Response diabaikan, keberhasilan tidak pernah diperiksa
- Alamat dan selang waktu tidak dijadikan konstanta
- Alur request-response belum dapat diceritakan sendiri

Yang Anda ucapkan:
> Beberapa hal berikut paling sering membuat praktik tadi gagal, dan semuanya dapat Anda cegah. Pertama, Wi-Fi belum terhubung, sehingga bagian pengiriman tidak pernah dijalankan dan Serial Monitor berhenti pada pesan penghubungan, sebab tanpa koneksi jaringan HTTP tidak dapat berjalan. Kedua, kode status hanya muncul pada pengiriman pertama, padahal kriteria nilai penuh menuntut kode status keberhasilan tampil pada setiap pengiriman. Ketiga, response diabaikan, jadi program melanjutkan putaran tanpa pernah memeriksa apakah pengirimannya berhasil. Keempat, alamat tujuan dan selang waktu ditulis langsung di tengah kode, padahal keduanya seharusnya menjadi konstanta bernama agar programnya rapi dan letaknya mudah Anda tunjukkan. Kesalahan terakhir bersifat konseptual, yaitu belum mampu menceritakan sendiri alur request dan response, dan obatnya membaca ulang Bab 2 lalu Bab 5 materi pertemuan ini. Mari kita padatkan semuanya menjadi daftar pemeriksaan diri.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 6

Kawasan: Penutup

Teks di layar:
- HTTP adalah protokol berbasis request-response
- GET mengambil data, POST mengirim data
- JSON lebih cocok saat data mulai kompleks
- Data terkirim, alur dijelaskan, keterbatasan dipahami
- Bekal langsung menuju CP-2 pada Pertemuan 8

Yang Anda ucapkan:
> Mari kita rangkum. HTTP adalah protokol berbasis request-response, client mengirim request dan server memberi response, GET dipakai untuk mengambil data sedangkan POST untuk mengirim data, dan datanya dapat berupa teks biasa atau JSON dengan JSON lebih cocok saat data mulai kompleks. Checkpoint pertemuan ini, yang rinciannya ada pada Bab 9 materi pertemuan ini, meminta tiga bukti dari Anda, yaitu data benar-benar terkirim dan berulang secara periodik, alur request dan response dapat Anda tuliskan dari ingatan, serta keterbatasan HTTP untuk real-time ringan dapat Anda jelaskan sekaligus dengan satu situasi yang justru cocok ditangani HTTP. Perhatikan juga makna yang lebih besar, karena sesudah pertemuan ini device Anda tidak lagi sekadar program yang berjalan sendiri, melainkan bagian dari ekosistem data. Materi ini mengumpamakannya sebagai orang yang tadinya belajar sendiri di kamar tanpa melaporkan apa pun, lalu mulai mengirim laporan ke sistem administrasi pusat. Ketiga butir itu adalah bekal langsung menuju checkpoint besar CP-2 pada Pertemuan 8, karena integrasi yang diuji di sana menuntut adanya komunikasi data, bukan hanya sensor dan aktuator. Tinggal satu hal lagi, yaitu tugas yang harus Anda kerjakan.

### Frame 14 — Tugas Praktik dan Pokok Penilaian

Kawasan: Penutup

Teks di layar:
- Kirim suhu virtual periodik melalui HTTP
- Jelaskan client, server, data, metode, response
- Pengiriman berhasil 30%, periodik 20%
- Penjelasan alur 30%, kerapian program 20%
- Tugas mingguan menyumbang 20 persen nilai akhir

Yang Anda ucapkan:
> Tugas praktik pertemuan ini ada pada Bab 8 materi pertemuan ini, dan bentuknya satu program disertai penjelasan singkat. Buat simulasi device yang mengirimkan data suhu virtual melalui HTTP secara periodik, lalu jelaskan lima hal, yaitu siapa yang berperan sebagai client, siapa yang berperan sebagai server, data apa yang dikirim, mengapa metode yang Anda pilih sesuai dengan kebutuhan, dan apa makna response yang diterima. Penilaiannya terbagi empat, yaitu pengiriman data berhasil 30 persen, pengiriman berjalan periodik 20 persen, penjelasan alur request dan response 30 persen, dan kerapian program serta data 20 persen, sementara tugas mingguan seperti ini menyumbang 20 persen dari nilai akhir. Perhatikan bahwa penjelasan alur berbobot sama besar dengan program yang berjalan, karena tujuan pertemuan ini adalah memahami pola request-response, bukan sekadar mendapatkan kode status keberhasilan. Untuk aspek kerapian, tulis alamat tujuan dan selang waktu sebagai konstanta bernama, kirim data dalam format yang konsisten, dan periksa hasil pengiriman sebelum program melanjutkan. Dan inilah jawaban lengkap pertanyaan pembuka kita, HTTP sudah cukup ketika device mengirim data berkala ke API dan integrasi dengan layanan web menjadi prioritas, tetapi mulai kurang efisien ketika banyak device harus mengirim data dengan jarak waktu yang sangat pendek.




