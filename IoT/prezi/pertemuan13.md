# Prezi Pertemuan 13 — Perancangan Mini Project IoT

## Kanvas utama

Saat Prezi dibuka dan sebelum zoom pertama, yang terlihat adalah satu lembar dokumen rancangan berukuran besar di tengah kanvas, dengan tujuh kotak bagian yang masih kosong dan bernomor dari kiri atas ke kanan bawah, sementara judul pertemuan berada di tepi atas lembar itu. Enam kawasan topik ditata mengelilingi lembar tersebut mengikuti urutan pengisiannya: dua kawasan pertama berada di sisi kiri lembar tempat alasan dan sasaran dibicarakan, dua kawasan tengah menempel pada kotak kebutuhan serta kotak gambar sistem, dan dua kawasan terakhir berada di sisi kanan tempat pilihan komponen ditelaah lalu dokumen dinyatakan selesai. Jalur zoom karena itu bercerita seperti satu lembar yang terisi di depan mata Anda: setiap perhentian menambahkan satu bagian, dan ketika pandangan kembali ke tampilan menyeluruh, lembar yang tadinya kosong sudah menjadi dokumen yang dapat dibaca orang lain tanpa penjelasan lisan.

- Kawasan 1: Pembuka dan Alasan Merancang — pertanyaan pemancing, capaian pembelajaran, dan biaya keputusan yang diubah di tengah jalan.
- Kawasan 2: Sasaran dan Kebutuhan — tujuan terukur, kebutuhan bernomor, serta use case singkat.
- Kawasan 3: Gambar Sistem — diagram blok lima lapis, tabel topic, contoh payload, dan arah perintah.
- Kawasan 4: Pilihan dan Telaah — pemilihan komponen beserta alasannya dan peer review rancangan teman.
- Kawasan 5: Ruang Praktik — penyusunan dokumen rancangan langkah demi langkah serta kesalahan yang sering terjadi.
- Kawasan 6: Penutup dan Tugas — ringkasan sekaligus checkpoint, lalu tugas latihan beserta pokok penilaiannya.

## Alur zoom

1. Pembuka: Rancangan Sebelum Prototipe
2. Capaian Pembelajaran Pertemuan Ini
3. Memindahkan Pekerjaan ke Tempat Termurah
4. Dari Masalah ke Tujuan Terukur
5. Kebutuhan Fungsional dan Non-Fungsional
6. Use Case Empat Baris
7. Lima Blok yang Selalu Ada
8. Alur Data dan Dua Arah
9. Memilih Komponen dengan Alasan
10. Peer Review Rancangan Teman
11. Praktik Menyusun Dokumen Rancangan
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 13
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Pembuka: Rancangan Sebelum Prototipe

Kawasan: Pembuka dan Alasan Merancang

Teks di layar:
- Pertemuan 13: Perancangan Mini Project IoT
- Hari ini tidak ada satu baris kode
- Pertanyaan: kapan rancangan dinyatakan cukup untuk dibangun?
- Keluarannya satu: dokumen rancangan mini project Anda

Yang Anda ucapkan:
> Pertemuan ini tidak menambah satu pun baris kode, dan itu disengaja, sebab yang dikerjakan adalah memutuskan lebih dahulu apa yang akan dibangun, mengapa hal itu perlu, data apa yang mengalir ke mana, dan komponen apa yang dipakai beserta alasannya.
> Pada latihan mingguan sampai Pertemuan 12 tentang keamanan dan keandalan, mengubah pikiran hampir tidak berbiaya, sedangkan pada proyek utuh satu keputusan kecil ikut menentukan bentuk topic, cara dashboard membaca angka, dan bentuk berkas riwayat.
> Simpan satu pertanyaan ini sepanjang presentasi: kapan sebuah rancangan boleh dinyatakan cukup, sehingga Anda berhenti menyusun dokumen dan mulai membangun?
> Yang perlu Anda siapkan hanya hasil latihan Pertemuan 1 sampai 12, alat tulis atau editor teks, dan satu kertas atau berkas gambar sederhana untuk diagram blok, karena tidak ada perangkat lunak baru yang perlu dipasang dan simulator baru dipakai kembali pada pertemuan berikutnya.
> Keluaran pertemuan ini satu saja, yaitu dokumen rancangan mini project Anda sendiri, dan dokumen itulah yang Anda wujudkan menjadi prototipe pada Pertemuan 14 tentang pembuatan mini project.
> Kita mulai dari sasaran pertemuan ini supaya Anda tahu apa yang harus dapat Anda lakukan sendiri setelahnya.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Pembuka dan Alasan Merancang

Teks di layar:
- Memahami alasan rancangan disusun sebelum perangkat dibangun
- Membedakan kebutuhan fungsional dan non-fungsional
- Mengubah masalah nyata menjadi tujuan yang terukur
- Menyusun use case, diagram blok, dan alur data
- Menelaah rancangan teman memakai daftar periksa

Yang Anda ucapkan:
> Ada empat hal yang perlu Anda pahami pada pertemuan ini, yaitu alasan rancangan disusun sebelum perangkat dibangun beserta biaya yang timbul bila tahap ini dilewati, perbedaan kebutuhan fungsional dan non-fungsional beserta cara mengujinya, cara membaca diagram blok dan alur data sebagai satu kesatuan dan bukan gambar hiasan, serta alasan setiap pemilihan komponen harus disertai alasan dan alternatif.
> Sisi keterampilannya juga empat, yaitu mengubah satu masalah nyata menjadi tujuan yang dapat diukur, menulis kebutuhan bernomor yang dapat diperiksa satu per satu, menyusun use case singkat bersama diagram blok dan pemetaan alur data lengkap dengan bentuk payload, lalu menelaah rancangan teman memakai daftar periksa dan memberi masukan yang dapat dikerjakan.
> Kedelapan butir itu ditata sebagai enam bagian pertemuan ini: perumusan kebutuhan, use case, diagram blok, alur data, pemilihan komponen, dan peer review.
> Perhatikan butir terakhir, karena masukan yang dapat dikerjakan untuk rancangan teman ikut dinilai pada tugas, bukan hanya dokumen Anda sendiri.
> Seluruhnya bermuara pada satu dokumen yang pada akhir mata kuliah menjadi dasar laporan serta demo, jadi pekerjaan hari ini tidak berhenti hari ini.
> Sebelum menyusun bagian pertama dokumen itu, kita perjelas dahulu mengapa tahap ini tidak boleh dilompati.

### Frame 3 — Memindahkan Pekerjaan ke Tempat Termurah

Kawasan: Pembuka dan Alasan Merancang

Teks di layar:
- Pada latihan mingguan, mengubah pikiran hampir tanpa biaya
- Satu keputusan bentuk data menyentuh device, dashboard, riwayat
- Menghapus satu kotak diagram: sepuluh detik
- Membongkar komponen yang sudah berprogram: satu sore
- Empat pertanyaan sudah cukup untuk rancangan ini

Yang Anda ucapkan:
> Pada latihan mingguan, mengubah pikiran hampir tidak berbiaya: satu baris kode diganti, program diunggah ulang, selesai.
> Pada sebuah proyek utuh biayanya berbeda, sebab keputusan bahwa data dikirim sebagai teks biasa ikut menentukan bentuk topic, cara dashboard membaca angka, dan bentuk berkas riwayat, sehingga ketika keputusan itu diubah di tengah jalan yang ikut berubah adalah program device, alur pada Node-RED, dan seluruh berkas riwayat yang sudah terkumpul.
> Karena itu perancangan bukan penundaan pekerjaan, melainkan pemindahan pekerjaan ke tempat yang paling murah: menghapus satu kotak pada diagram menghabiskan sepuluh detik, sedangkan membongkar komponen yang sudah dipasang dan sudah ditulisi program menghabiskan satu sore.
> Tidak ada tukang yang menuangkan pondasi sambil memikirkan di mana kamar mandi akan diletakkan, dan gambar rumah dibuat lebih dahulu bukan karena gambarnya berharga, melainkan karena memindahkan dinding di atas kertas jauh lebih murah daripada memindahkan dinding yang sudah berdiri.
> Rancangan pada tingkat ini juga tidak perlu tebal, sebab empat pertanyaan sudah cukup: masalah apa yang diselesaikan, dari mana angkanya datang, ke mana angkanya pergi, dan bagaimana pemakainya melihat serta memerintah.
> Dokumen contoh pada Bab 10 materi pertemuan ini memperlihatkan keempat jawaban itu dalam bentuk yang sudah selesai, dan kita mulai menyusunnya dari pertanyaan yang pertama.

### Frame 4 — Dari Masalah ke Tujuan Terukur

Kawasan: Sasaran dan Kebutuhan

Teks di layar:
- Rumusan longgar tidak dapat dinyatakan selesai
- Tujuan terukur memuat besaran, ambang, tindakan, selang waktu
- Contoh: kipas menyala ketika suhu melewati 30 derajat
- Uji kalimatnya: dapatkah dibuktikan benar atau salah?
- Ambang boleh salah, asal tertulis di rancangan

Yang Anda ucapkan:
> Rancangan yang goyah hampir selalu berawal dari masalah yang dirumuskan terlalu longgar, misalnya ruang baca terasa panas atau ingin memantau tanaman, sebab rumusan seperti itu tidak dapat dinyatakan selesai ketika pekerjaan berakhir.
> Langkah pertama perancangan adalah mengubah keluhan menjadi tujuan yang terukur, yaitu kalimat yang menyebut besaran yang diukur, ambang yang dipakai, tindakan yang terjadi, dan selang waktunya sekaligus.
> Contohnya keluhan ruang baca terasa panas berubah menjadi suhu ruang baca terpantau setiap 10 detik dan kipas menyala otomatis ketika suhu melewati 30 derajat, dan yang membedakan keduanya bukan panjang kalimat melainkan adanya angka yang dapat dibandingkan.
> Cara memeriksanya satu pertanyaan saja: bila prototipe sudah jalan, dapatkah Anda membuktikan kalimat itu benar atau salah hanya dengan melihat dashboard dan log, dan bila jawabannya belum, berarti masih ada unsur yang hilang.
> Angka 30 derajat itu mungkin terlalu rendah untuk ruangan Anda, tetapi yang penting angkanya tertulis di dalam rancangan, sehingga ketika pengujian menunjukkan kipas terlalu sering menyala, yang Anda ubah adalah satu angka yang jelas letaknya, bukan tebakan.
> Tabel rumusan pada Bab 2 materi pertemuan ini memuat tiga contoh perubahan seperti itu, dan dari tujuan yang sudah terukur inilah daftar kebutuhan diturunkan.

### Frame 5 — Kebutuhan Fungsional dan Non-Fungsional

Kawasan: Sasaran dan Kebutuhan

Teks di layar:
- Fungsional: apa yang dikerjakan sistem
- Non-fungsional: seberapa baik hal itu dikerjakan
- Bernomor `F-1` sampai `F-5`, lalu `N-1` sampai `N-4`
- "Sistem harus andal" belum dapat dibuktikan
- Nomor dipakai ulang pada pengujian dan laporan

Yang Anda ucapkan:
> Tujuan yang sudah terukur dipecah menjadi daftar kebutuhan, yaitu pernyataan tentang apa yang harus dipenuhi sistem, dan kebutuhan itu dibagi dua.
> Kebutuhan fungsional menyebut apa yang sistem lakukan, misalnya device mengirim suhu dan kelembapan ke satu topic MQTT, sedangkan kebutuhan non-fungsional menyebut seberapa baik hal itu dilakukan, misalnya pengiriman berselang 10 detik dan tetap berlanjut setelah Wi-Fi pulih.
> Pembagian ini bukan urusan istilah: kebutuhan fungsional tanpa kebutuhan non-fungsional menghasilkan sistem yang bekerja hanya di meja pengujian, yaitu data terkirim tetapi berhenti selamanya begitu Wi-Fi sekali terputus, sedangkan kebutuhan non-fungsional tanpa daftar fungsional yang jelas menghasilkan janji yang tidak dapat diperiksa.
> Cara memeriksanya pun berbeda, sebab yang fungsional dijalankan sekali lalu dilihat apakah hasilnya muncul, sedangkan yang non-fungsional diukur atau diganggu dengan sengaja lalu diamati tanggapannya.
> Tulislah setiap kebutuhan sebagai satu kalimat bernomor, `F-1` sampai `F-5` untuk yang fungsional dan `N-1` sampai `N-4` untuk yang non-fungsional, karena nomor itu dipakai lagi pada rencana pengujian, catatan kemajuan, dan laporan akhir.
> Ujilah setiap kalimat dengan pertanyaan bagaimana saya membuktikannya, sebab kalimat sistem harus andal tidak dapat dibuktikan, sedangkan kalimat tentang device yang menyambung ulang sendiri setelah jaringan pulih dapat dibuktikan dengan mematikan titik akses lalu membaca log seperti pada Pertemuan 12 tentang keamanan dan keandalan.
> Daftar kebutuhan sudah menyebut isi sistem, tetapi belum bercerita tentang pemakaiannya, dan kekosongan itu diisi oleh bentuk berikutnya.

### Frame 6 — Use Case Empat Baris

Kawasan: Sasaran dan Kebutuhan

Teks di layar:
- Empat baris: aktor, pemicu, langkah, hasil
- Aktor tidak selalu manusia, device juga aktor
- Langkah ditulis tanpa menyebut nama fungsi
- Dua sampai tiga use case sudah memadai
- Satu di antaranya berisi perintah ke device

Yang Anda ucapkan:
> Use case menuliskan satu pemakaian dari sudut pandang orang yang memakainya, dan bentuk yang cukup untuk mini project hanya empat baris, yaitu aktor, pemicu, langkah, dan hasil.
> Aktor adalah pihak yang berbuat dan tidak selalu manusia, sebab penjaga ruangan adalah aktor dan device yang membaca sensor secara berkala juga aktor, sedangkan pemicunya dapat berupa penjaga membuka dashboard atau selang 10 detik yang terlewati.
> Langkah adalah urutan yang benar-benar terjadi, ditulis singkat dan berurutan tanpa menyebut nama fungsi di dalam program, sedangkan hasil adalah keadaan akhir yang dapat dilihat, misalnya kipas menyala dan statusnya berubah.
> Contoh pada Bab 4 materi pertemuan ini berjudul menyalakan kipas secara manual: penjaga melihat suhu pada dashboard sudah 31 derajat sementara kipas masih mati karena mode manual sedang aktif, lalu ia menekan tombol Kipas Nyala, Node-RED mengirim pesan perintah ke topic perintah, device memeriksa isinya lalu menyalakan kipas, dan status terbaru ikut terkirim pada pengiriman berikutnya.
> Perhatikan bahwa langkah terakhir menyebut penundaan yang wajar dan tidak menjanjikan perubahan seketika, sehingga indikator yang berubah tiga detik kemudian tidak dianggap kerusakan ketika prototipe diuji.
> Dua sampai tiga use case sudah memadai, dan salah satunya sebaiknya berisi perintah dari pengguna ke device, karena use case yang seluruhnya berupa pemantauan menandakan arah data yang kedua belum Anda rancang.
> Setelah jelas siapa yang memakai dan bagaimana urutannya, kita gambar sistemnya supaya terlihat terdiri dari apa.

### Frame 7 — Lima Blok yang Selalu Ada

Kawasan: Gambar Sistem

Teks di layar:
- Sensor, device, jaringan, platform, pengguna
- Aktuator menempel pada device, tidak lewat jaringan
- Satu kotak satu peran, panah berketerangan isi
- Wi-Fi adalah sarana pada panah, bukan kotak
- Blok pengguna paling sering terlupa

Yang Anda ucapkan:
> Diagram blok menjawab pertanyaan terdiri dari apa sistem ini dengan gambar yang muat dalam satu halaman, dan hampir semua sistem IoT tingkat awal dapat digambar sebagai lima blok berurutan sesuai susunan lapis yang dibahas pada Pertemuan 1 tentang orientasi IoT.
> Kelimanya adalah sensor yang mengubah keadaan fisik menjadi sinyal, device yang membaca dan memutuskan, jaringan beserta broker yang mengantar pesan, platform yang menyimpan dan menggambar, serta pengguna yang membaca dan memerintah.
> Bila sistem Anda memakai aktuator, ia digambar sebagai blok tambahan yang menempel pada device karena perintahnya tidak melewati jaringan lagi, dan pada diagram jadi di Bab 10 materi pertemuan ini kelima blok itu terisi DHT22, ESP32, Wi-Fi dan broker MQTT, Node-RED, serta penjaga ruang baca, dengan kipas lewat relay sebagai blok aktuatornya.
> Aturan menggambarnya dua saja, yaitu satu kotak berisi satu peran, dan setiap panah diberi keterangan singkat berupa isi yang lewat, bukan hanya arah.
> Panah tanpa keterangan adalah sumber kesalahpahaman terbesar pada peer review, sebab pembaca tidak dapat menebak apakah yang mengalir berupa angka mentah, teks siap kirim, atau perintah.
> Tiga kekeliruan yang paling sering muncul adalah menggambar Wi-Fi sebagai kotak yang berdiri sendiri padahal ia sarana pada panah, menyatukan device dan platform dalam satu kotak sehingga tidak terlihat mana yang mengambil keputusan, serta melupakan blok pengguna sehingga sistem tampak berbicara kepada dirinya sendiri.
> Susunannya kini terlihat, jadi tinggal isi yang lewat di setiap panah yang perlu kita tetapkan.

### Frame 8 — Alur Data dan Dua Arah

Kawasan: Gambar Sistem

Teks di layar:
- Tetapkan per panah: isi, bentuk, selang, penerima
- Topic `kelas/iot/ruangbaca/telemetri`, tiap 10 detik
- Payload `{"suhu":29.4,"lembap":62,"kipas":1,"mode":"otomatis"}`
- Topic perintah dipakai hanya saat pengguna bertindak
- Device memutuskan lewat ambang, pengguna mengambil alih

Yang Anda ucapkan:
> Diagram blok memperlihatkan susunan, sedangkan alur data memperlihatkan isi, sehingga untuk setiap panah Anda menetapkan empat hal, yaitu apa yang dikirim, dalam bentuk apa, seberapa sering, dan siapa yang menerimanya.
> Keempatnya ditulis sebagai tabel topic dan bentuk pesannya ditulis sebagai satu contoh payload yang lengkap, misalnya topic `kelas/iot/ruangbaca/telemetri` yang berjalan dari device ke platform setiap 10 detik dengan payload `{"suhu":29.4,"lembap":62,"kipas":1,"mode":"otomatis"}`.
> Menulis satu contoh payload sejak tahap rancangan menghemat banyak waktu, sebab dari situlah nama kolom pada berkas riwayat dan nama medan pada dashboard ditentukan.
> Bentuk JSON memuat beberapa besaran dalam satu pesan sehingga penerima tidak perlu menghitung urutan, sedangkan bentuk teks biasa berisi satu angka juga sah dan lebih ringan seperti pada Pertemuan 7 tentang MQTT tetapi menuntut satu topic untuk tiap besaran, dan yang perlu Anda putuskan adalah memilih salah satu lalu memakainya secara taat.
> Begitu ada aktuator, arah kedua muncul dan dokumen harus menjawab siapa yang memutuskan kipas menyala, sedangkan jawaban yang aman untuk mini project adalah device memutuskan berdasarkan ambang sementara pengguna dapat mengambil alih lewat mode manual.
> Akibatnya tertulis pada tabel arah di Bab 5 materi pertemuan ini: ketika jaringan terputus, data selang itu hilang tetapi pembacaan tetap berjalan, dan perintah tidak sampai tetapi ambang otomatis tetap bekerja.
> Isi dan arah sudah tetap, jadi sekarang kita pilih komponen yang mengerjakannya.

### Frame 9 — Memilih Komponen dengan Alasan

Kawasan: Pilihan dan Telaah

Teks di layar:
- Setiap pilihan disertai alasan dan alternatif
- Pertimbangan: besaran, ketersediaan, kerumitan, tegangan kerja
- DHT22: dua besaran, tersedia di simulator, pustaka sederhana
- Komponen 5 volt langsung ke pin 3,3 volt merusak
- Jalur utama memakai komponen yang sudah dikenal

Yang Anda ucapkan:
> Pemilihan komponen dinilai bukan dari kecanggihannya, melainkan dari kecocokannya dengan kebutuhan yang sudah Anda tulis, karena itu setiap pilihan disertai dua keterangan, yaitu alasannya dan alternatif yang tidak dipilih.
> Menuliskan alternatif tampak seperti pekerjaan tambahan, padahal justru bagian itu yang menolong ketika komponen pilihan ternyata tidak tersedia atau tidak berjalan di simulator, sebab Anda tidak perlu mengulang penelusuran dari awal.
> Empat pertimbangan biasanya cukup, yaitu besaran yang ingin diukur beserta rentangnya, ketersediaan komponen pada simulator maupun di tangan Anda, kerumitan penyambungan dan pustakanya, serta kesesuaian dengan tegangan kerja device.
> Pertimbangan terakhir sering terlewat, padahal komponen 5 volt yang disambungkan langsung ke pin ESP32 yang bekerja pada 3,3 volt adalah penyebab kerusakan yang tidak terlihat di simulator.
> Bacalah tabel pada Bab 6 materi pertemuan ini sebagai contoh bentuknya: DHT22 dipilih karena satu komponen melayani dua besaran, tersedia di simulator, dan pustakanya sederhana, dengan alternatif DHT11 bila ketelitian bukan hal utama atau DS18B20 bila hanya suhu yang diukur.
> Modul relay dipilih untuk menghidupkan kipas karena memisahkan arus kipas dari pin device dan keadaannya mudah dibaca, dengan LED sebagai penggantinya pada simulator, dan pola alasan beserta alternatif yang sama berlaku untuk ESP32, broker MQTT, dan Node-RED.
> Satu peringatan sebelum dokumen ditukar: jangan memilih komponen yang belum pernah Anda coba untuk bagian yang paling menentukan, sebab bila sensor baru itu gagal dibaca, seluruh mini project ikut berhenti.

### Frame 10 — Peer Review Rancangan Teman

Kawasan: Pilihan dan Telaah

Teks di layar:
- Penyusun tidak melihat kekosongan dokumennya sendiri
- Telusuri satu nilai sensor sampai mata pengguna
- Titik penelusuran berhenti adalah temuan paling berharga
- Masukan harus dapat langsung dikerjakan
- Sebut satu bagian yang sudah baik

Yang Anda ucapkan:
> Rancangan yang baru selesai selalu terasa jelas bagi penyusunnya karena bagian yang tidak tertulis masih tersimpan di kepalanya, dan hanya pembaca lain yang dapat menemukan kekosongan itu.
> Karena itu Anda menukar dokumen dengan teman, membacanya sebagai orang yang harus membangun sistem tersebut, lalu menuliskan temuan Anda.
> Cara membacanya bukan mencari kesalahan ejaan, melainkan menelusuri satu nilai sensor dari sumbernya sampai ke mata pengguna sambil bertanya di mana penelusuran itu terhenti karena keterangannya tidak ada, dan titik berhentinya itulah temuan yang paling berharga.
> Daftar periksa pada Bab 7 materi pertemuan ini memuat enam pertanyaan, di antaranya apakah tujuannya memuat besaran, ambang, dan selang waktu, apakah setiap panah punya keterangan isi dan blok pengguna ada, serta apakah disebut apa yang terjadi ketika jaringan terputus dan ketika sensor mengirim nilai mustahil.
> Masukan ditulis agar dapat dikerjakan, sebab kalimat alur datanya kurang jelas tidak dapat diperbaiki karena tidak menunjuk apa pun, sedangkan kalimat panah dari device ke broker belum menyebut isi pesannya sehingga sebaiknya ditulis payload JSON seperti pada tabel topic langsung dapat dikerjakan.
> Sebutkan juga satu bagian yang sudah baik karena pembaca perlu tahu bagian mana yang tidak perlu ia ubah, dan terimalah temuan sebagai data dan bukan penilaian, sebab setiap temuan pada tahap dokumen adalah pekerjaan membongkar yang tidak perlu Anda lakukan pada tahap prototipe.
> Anda tidak wajib menerima semua saran, tetapi saran yang ditolak sebaiknya diberi satu baris alasan di dalam dokumen, dan sekarang kita jalankan seluruh langkahnya berurutan.

### Frame 11 — Praktik Menyusun Dokumen Rancangan

Kawasan: Ruang Praktik

Teks di layar:
- Delapan langkah berurutan, dua sampai tiga halaman
- Masalah dua kalimat, lalu satu kalimat tujuan
- Kebutuhan `F-1` sampai `F-4`, `N-1` sampai `N-3`
- Diagram blok, tabel topic, tabel komponen
- Hasil: orang lain dapat membangun tanpa bertanya

Yang Anda ucapkan:
> Kita kerjakan kedelapan langkah pada Bab 8 materi pertemuan ini dengan satu kasus di depan kelas, dan urutannya tidak boleh ditukar karena setiap langkah memakai keluaran langkah sebelumnya.
> Langkah pertama menulis satu masalah nyata dalam dua kalimat beserta siapa yang dirugikan, lalu langkah kedua mengubahnya menjadi satu kalimat tujuan yang memuat besaran, selang waktu, ambang, dan tindakan, dan kalimat itu langsung diuji dengan pertanyaan pada Bab 2 materi pertemuan ini.
> Langkah ketiga dan keempat menurunkan tujuan itu menjadi kebutuhan `F-1` sampai sekurang-kurangnya `F-4` lalu `N-1` sampai `N-3` yang menyebut selang waktu, tanggapan atas gangguan, dan hal keamanan dasar, disusul dua use case empat baris dengan salah satunya berupa perintah dari pengguna ke device.
> Langkah kelima sampai ketujuh menggambar diagram blok lima lapis pada kertas atau alat gambar seperti Draw.io dengan keterangan pada setiap panah, membuat tabel topic berisi nama topic, arah, isi, dan selang waktu beserta satu contoh payload untuk masing-masing arah, lalu menyusun tabel pemilihan komponen empat kolom, dan langkah kedelapan menukarkan dokumen dengan seorang teman untuk ditelaah.
> Yang harus terlihat di akhir ada tiga, yaitu satu dokumen berisi tujuh bagian dengan panjang dua sampai tiga halaman, satu diagram yang setiap panahnya berketerangan isi dan memuat blok pengguna, serta satu contoh payload yang sama dirujuk dari seluruh bagian dokumen.
> Ujian kelayakannya satu, seperti disebut pada Bab 9 materi pertemuan ini, yaitu orang lain yang membaca dokumen itu dapat menyebutkan komponen apa yang perlu disiapkan dan pesan apa yang mengalir ke mana tanpa bertanya kepada Anda.
> Bila Anda macet pada langkah kedua karena tujuan terasa sulit diukur, biasanya masalahnya masih terlalu besar sehingga sasarannya perlu dipersempit dari seluruh gedung menjadi satu ruangan, dan bila hasil Anda berbeda dari tiga hal tadi, gejalanya biasanya sudah ada di daftar berikut.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Praktik

Teks di layar:
- Tujuan tanpa besaran atau ambang, hanya kata sifat
- Kebutuhan bertumpuk karena dua jenis tercampur
- Panah tanpa keterangan, atau Wi-Fi digambar kotak
- Contoh payload ditulis ulang di beberapa tempat
- Dokumen tanpa angka: teman hanya menemukan ejaan

Yang Anda ucapkan:
> Tabel penelusuran masalah pada Bab 9 materi pertemuan ini memuat lima gejala, dan semuanya muncul pada dokumen, bukan pada program.
> Bila tujuan tidak dapat dinyatakan tercapai atau tidak, penyebabnya adalah besaran atau ambang yang belum ada sehingga yang tertulis hanya kata sifat, jadi kembalilah ke tabel rumusan pada Bab 2 materi pertemuan ini lalu tambahkan unsur yang hilang.
> Bila kebutuhan terasa berulang dan bertumpuk, biasanya kebutuhan fungsional dan non-fungsional tercampur dalam satu kalimat, jadi pisahkan memakai tabel pembanding pada Bab 3 materi pertemuan ini dengan aturan satu kalimat satu nomor.
> Bila teman salah membaca diagram blok Anda, periksa apakah ada panah tanpa keterangan isi atau Wi-Fi yang digambar sebagai kotak, lalu bandingkan bentuknya dengan diagram pada Bab 10 materi pertemuan ini.
> Bila bentuk payload berubah-ubah antarbagian dokumen, penyebabnya adalah contoh payload yang ditulis ulang di beberapa tempat, jadi tetapkan satu contoh pada tabel topic lalu rujuk contoh itu dari bagian lain.
> Bila tidak ada yang dapat ditelaah teman selain ejaan, dokumen Anda masih berupa daftar keinginan tanpa angka dan tanpa nama topic, sehingga langkah dua, tiga, dan enam pada Bab 8 materi pertemuan ini perlu diulang sebelum peer review dijalankan lagi.
> Sekarang kita rangkum pertemuan ini sekaligus memeriksa diri sebelum tugas dikumpulkan.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 13

Kawasan: Penutup dan Tugas

Teks di layar:
- Rancangan memindahkan pekerjaan ke tempat termurah
- Tujuan terukur, kebutuhan bernomor dan dapat diuji
- Lima blok berketerangan, alur data bercontoh payload
- Komponen beralasan, rancangan sudah ditelaah teman
- Checkpoint: satu dokumen rancangan yang sudah ditelaah

Yang Anda ucapkan:
> Mari kita kumpulkan intinya: perancangan memindahkan pekerjaan ke tempat yang paling murah, sebab memindahkan kotak pada diagram jauh lebih ringan daripada membongkar rangkaian dan program yang sudah jadi.
> Masalah diubah menjadi tujuan terukur yang memuat besaran, selang waktu, ambang, dan tindakan, lalu tujuan itu diturunkan menjadi kebutuhan fungsional dan non-fungsional yang bernomor dan harus dapat diuji.
> Use case singkat berisi aktor, pemicu, langkah, dan hasil dengan salah satunya memuat perintah dari pengguna ke device, diagram blok memperlihatkan lima lapis dengan setiap panah berketerangan isi, dan alur data memperlihatkan nama topic, arah, selang waktu, serta contoh payload.
> Setiap komponen disertai alasan dan alternatif, dan rancangan ditelaah teman memakai daftar periksa agar kekosongan yang tidak terlihat oleh penyusunnya ditemukan sebelum dibangun.
> Checkpoint pada Bab 14 materi pertemuan ini menuntut satu hal, yaitu ada satu dokumen rancangan yang memuat tujuan terukur, kebutuhan bernomor, diagram blok berketerangan, alur data beserta contoh payload, dan tabel pemilihan komponen, serta dokumen itu sudah pernah ditelaah seorang teman.
> Cara memastikannya sendiri ada empat, yaitu ambil satu butir kebutuhan secara acak lalu sebutkan cara membuktikannya pada prototipe, jelaskan diagram Anda kepada teman tanpa membuka catatan sampai ia dapat menyebut isi setiap panah, sebutkan kebutuhan yang dilayani setiap baris tabel komponen beserta alternatif yang Anda tolak, dan periksa apakah lembar temuan serta daftar perbaikan benar-benar ada dan bukan hanya percakapan lisan.
> Pertemuan ini adalah persiapan langsung menuju checkpoint keempat pada Pertemuan 16, dan setelah checkpoint hari ini terpenuhi, tinggal tugasnya yang perlu Anda kerjakan.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup dan Tugas

Teks di layar:
- Dokumen rancangan tujuh bagian, ikuti Bab 8
- Lembar temuan: tiga temuan, satu bagian baik
- Daftar perbaikan beserta alasan saran yang ditolak
- Tujuan dan kebutuhan `30%`, diagram `30%`
- Komponen `20%`, peer review `20%`

Yang Anda ucapkan:
> Tugas Anda adalah menyusun dokumen rancangan mini project Anda sendiri mengikuti kedelapan langkah pada Bab 8 materi pertemuan ini, lalu menukarkannya dengan seorang teman untuk ditelaah.
> Yang pertama dikumpulkan adalah dokumen rancangan berisi tujuh bagian, yaitu masalah dan tujuan terukur, kebutuhan fungsional bernomor, kebutuhan non-fungsional bernomor, dua use case singkat, diagram blok berketerangan, tabel topic beserta contoh payload, dan tabel pemilihan komponen empat kolom.
> Yang kedua adalah lembar temuan peer review yang Anda tulis untuk rancangan teman memakai daftar periksa pada Bab 7 materi pertemuan ini, memuat sekurang-kurangnya tiga temuan yang dapat dikerjakan dan satu bagian yang sudah baik.
> Yang ketiga adalah daftar perbaikan pada dokumen Anda sendiri setelah menerima temuan, ditambah satu baris alasan bagi setiap saran yang Anda putuskan tidak dipakai.
> Penilaiannya terbagi menjadi tujuan terukur beserta kebutuhan `30%`, diagram blok dan alur data `30%`, pemilihan komponen `20%`, serta peer review dan tindak lanjutnya `20%`, dan yang dinilai bukan kerapian tampilan dokumen melainkan apakah rancangan itu dapat dibangun oleh orang lain tanpa bertanya kepada Anda.
> Ingat pula bahwa tugas latihan mingguan berbobot dua puluh persen dari nilai akhir, sedangkan mini project yang dirancang di sini berbobot dua puluh persen tersendiri.
> Pertanyaan pembuka tadi kini terjawab: sebuah rancangan dinyatakan cukup ketika pembaca lain dapat menyebutkan komponen yang perlu disiapkan dan pesan yang mengalir ke mana tanpa bertanya kepada Anda, dan dokumen sepanjang itulah yang Anda wujudkan menjadi prototipe pada Pertemuan 14 tentang pembuatan mini project.
