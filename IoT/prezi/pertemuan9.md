# Prezi Pertemuan 9 — Pengaturan Waktu Pengiriman Data dan Penyusunan Payload

## Kanvas utama

Saat Prezi dibuka dan sebelum zoom pertama, yang terlihat adalah satu lingkaran besar bertuliskan `loop()` di tengah kanvas dengan judul pertemuan di atasnya, serta lima kata kunci kecil yang mengapung di sekelilingnya: interval pembacaan, `millis()`, payload terstruktur, penanda waktu, polling dan event-driven. Enam kawasan topik ditata mengelilingi lingkaran itu mengikuti arah jarum jam, mulai dari kiri atas dan berakhir di kiri bawah, sehingga jalur zoom bercerita seperti satu putaran program yang utuh. Anda mulai dari pertanyaan kapan sebuah data layak dikirim, masuk ke cara papan mengatur waktunya sendiri, menyaring apa yang layak keluar, membentuk isi pesannya, membuktikannya di simulator, lalu keluar dari lingkaran menuju ringkasan dan tugas.

- Kawasan 1: Alasan dan Sasaran — pembuka, capaian pembelajaran, dan sebab jeda pengiriman perlu diatur.
- Kawasan 2: Mesin Waktu Program — kerugian `delay()` dan pola penjadwalan dengan `millis()`.
- Kawasan 3: Menyaring Kiriman — dua jeda berbeda, ambang perubahan, polling dan event-driven.
- Kawasan 4: Bentuk Pesan — payload JSON yang rapi dan penanda waktu `uptime_ms`.
- Kawasan 5: Ruang Praktik — program lengkap, demo perbaikan di simulator, dan kesalahan yang sering terjadi.
- Kawasan 6: Penutup dan Tugas — ringkasan sekaligus checkpoint, lalu tugas latihan beserta penilaiannya.

## Alur zoom

1. Pembuka: Kapan Data Layak Dikirim
2. Capaian Pembelajaran Pertemuan Ini
3. Mengapa Jeda Pengiriman Perlu Diatur
4. delay() Membekukan Seluruh Program
5. millis() dan Pola Penjadwalan
6. Membaca Sering, Mengirim Disaring Ambang
7. Polling dan Event-Driven
8. Payload JSON yang Rapi
9. uptime_ms dan Batas Waktunya
10. Tiga Pekerjaan dalam Satu loop()
11. Demo Perbaikan di Simulator
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 9
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Pembuka: Kapan Data Layak Dikirim

Kawasan: Alasan dan Sasaran

Teks di layar:
- Pertemuan 9: waktu pengiriman dan penyusunan payload
- Sistem hasil UTS Anda sudah bekerja, tetapi boros
- Pertanyaan pemancing: kapan data layak dikirim?
- Jawabannya baru lengkap di akhir presentasi

Yang Anda ucapkan:
> Proyek yang Anda selesaikan pada UTS praktik sudah berhasil mengirim data ke broker, dan itu pencapaian yang nyata.
> Masalahnya, program seperti itu biasanya masih mengirim pada setiap putaran `loop()` dan masih memakai `delay(2000)` yang menghentikan segalanya.
> Pertemuan ini memperbaiki dua hal tersebut: mengatur kapan data layak dikirim, dan menyusun isi kiriman agar rapi serta mudah dibaca penerima.
> Simpan satu pertanyaan di kepala Anda sepanjang presentasi ini, yaitu kapan sebuah data benar-benar layak dikirim.
> Tidak ada rangkaian baru yang dirakit dan tidak ada perangkat lunak baru yang dipasang; semuanya dikerjakan pada program yang sudah berjalan.
> Kita mulai dari sasaran pertemuan ini lebih dahulu, supaya Anda tahu apa yang harus bisa Anda lakukan setelah ini.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Alasan dan Sasaran

Teks di layar:
- Memahami alasan pengiriman data perlu dijadwalkan
- Menjadwalkan dua pekerjaan berjeda berbeda tanpa berhenti
- Menerapkan ambang perubahan agar kiriman berarti
- Menyusun payload JSON beserta penanda waktu relatif
- Membandingkan jumlah kiriman sebelum dan sesudah perbaikan

Yang Anda ucapkan:
> Ada empat hal yang perlu Anda pahami dan empat hal yang perlu Anda kerjakan sendiri setelah pertemuan ini.
> Sisi pemahaman berisi alasan penjadwalan, sebab `delay()` merugikan dan cara `millis()` menggantikannya, perbedaan polling dengan event-driven, serta bagian-bagian payload yang baik.
> Sisi keterampilan menuntut Anda menjadwalkan dua pekerjaan dengan jeda berbeda, menerapkan ambang perubahan, menyusun payload JSON, dan membaca bukti penghematan dari log serial.
> Perhatikan butir terakhir, karena angka jumlah kiriman sebelum dan sesudah perbaikan itulah yang nanti Anda laporkan pada tugas.
> Yang perlu Anda siapkan hanya proyek simulator hasil Pertemuan 8, klien MQTT untuk berlangganan topik Anda, dan akses ke log serial.
> Sebelum menyentuh program, kita lihat dahulu mengapa mengirim sesering mungkin justru merugikan.

### Frame 3 — Mengapa Jeda Pengiriman Perlu Diatur

Kawasan: Alasan dan Sasaran

Teks di layar:
- Setiap putaran `loop()` bisa berarti puluhan kiriman
- Radio Wi-Fi adalah bagian paling haus daya
- Broker dapat memutus perangkat yang dianggap membanjiri
- Grafik dari data terlalu rapat sulit dibaca
- Pembungkus pesan bisa lebih besar daripada datanya

Yang Anda ucapkan:
> Program yang mengirim pada setiap putaran `loop()` dapat menghasilkan puluhan kiriman per detik, dan di simulator itu hanya membuat log serial berlarian.
> Pada perangkat sungguhan akibatnya nyata: baterai cepat habis karena radio Wi-Fi bagian paling haus daya, kuota terpakai untuk isi yang sama, dan broker publik dapat memutus perangkat Anda.
> Di sisi penerima, ribuan titik dalam satu menit justru menutupi bentuk perubahan yang ingin dilihat, dan penyimpanan terisi angka yang hampir seluruhnya sama.
> Ada pula hal yang jarang disadari, yaitu setiap pengiriman MQTT membawa nama topik, keterangan pesan, dan lalu lintas balasan broker, sehingga pembungkusnya bisa lebih besar daripada payload belasan karakter.
> Bandingkan dua penjaga gudang: yang pertama menelepon setiap sepuluh detik untuk melapor bahwa suhu masih normal, yang kedua menelepon ketika suhu berubah cukup jauh ditambah satu laporan singkat tiap jam sebagai tanda ia masih berjaga.
> Keduanya sama-sama rajin, tetapi hanya laporan kedua yang berguna, dan untuk membangunnya kita harus lebih dahulu melepaskan diri dari `delay()`.

### Frame 4 — delay() Membekukan Seluruh Program

Kawasan: Mesin Waktu Program

Teks di layar:
- `delay(2000)` menghentikan segalanya, bukan satu pekerjaan
- Tombol dan pesan MQTT terlewat selama menunggu
- `loop()` dipanggil berulang; satu pemanggilan harus selesai
- Papan tetap sibuk penuh tanpa menghasilkan apa pun
- Jeda sangat singkat dan `setup()` masih wajar

Yang Anda ucapkan:
> Anda memakai `delay(2000)` sejak pertemuan awal karena bentuknya sederhana, yaitu program berhenti dua detik lalu lanjut.
> Masalahnya kata berhenti itu berlaku untuk segalanya, sehingga selama `delay()` berjalan program tidak dapat membaca tombol, memeriksa pesan MQTT yang masuk, atau memperbarui apa pun.
> Sebabnya ada pada cara papan menjalankan program Anda: `loop()` adalah fungsi yang dipanggil berulang-ulang, dan selama satu pemanggilan belum selesai tidak ada baris lain yang mendapat kesempatan.
> Jadi papan sebenarnya tetap sibuk penuh, hanya saja kesibukannya berupa berputar di tempat sampai waktunya habis.
> Akibatnya terasa begitu program punya lebih dari satu pekerjaan, misalnya LED tanda hidup yang berkedip tersendat, atau nanti pada Pertemuan 10 tentang Node-RED perintah dari dasbor bisa terlewat karena `mqtt.loop()` tidak dipanggil cukup sering.
> Jangan menyimpulkan `delay()` selalu salah, karena menahan buzzer lima puluh milidetik atau menunggu di dalam `setup()` masih wajar; yang perlu diganti adalah `delay()` panjang di dalam `loop()`, dan penggantinya kita bahas sekarang.

### Frame 5 — millis() dan Pola Penjadwalan

Kawasan: Mesin Waktu Program

Teks di layar:
- `millis()` mengembalikan milidetik sejak papan mulai berjalan
- Pola tetap: `if (sekarang - waktuTerakhir >= jeda)`
- Variabel waktu wajib bertipe `unsigned long`
- Jangan lupa `waktuTerakhir = sekarang;` di dalam blok
- Baca `millis()` sekali di awal `loop()`

Yang Anda ucapkan:
> Fungsi `millis()` mengembalikan jumlah milidetik sejak papan mulai berjalan, dan nilainya hanya Anda baca, tidak pernah Anda atur sendiri.
> Dengan mencatat kapan sebuah pekerjaan terakhir dilakukan, program dapat menghitung sendiri apakah jedanya sudah terlampaui tanpa perlu berhenti menunggu, sedangkan baris di luar blok `if` tetap dijalankan setiap putaran.
> Variabel penyimpan waktu harus bertipe `unsigned long`, sebab dengan `int` nilainya meluap setelah sekitar tiga puluh dua detik dan jadwal Anda kacau.
> `millis()` sendiri kembali ke nol setelah kurang lebih 49,7 hari, dan justru bentuk pengurangan `sekarang - waktuTerakhir` yang tetap benar melewati titik itu, karena bilangan tanpa tanda tidak mengenal hasil negatif sehingga selisihnya tetap jarak waktu yang sebenarnya.
> Bentuk penjumlahan `millis() >= waktuTerakhir + jeda` tidak punya keberuntungan itu, sebab penjumlahannya sudah meluap sebelum dibandingkan sehingga pekerjaan Anda bisa berhenti selamanya.
> Satu baris yang paling sering terlupa adalah `waktuTerakhir = sekarang;` di awal blok, karena tanpa itu catatan waktu tidak pernah maju dan pekerjaan berjadwal berjalan setiap putaran; setelah pola ini aman, kita pakai untuk dua pekerjaan yang berbeda jedanya.

### Frame 6 — Membaca Sering, Mengirim Disaring Ambang

Kawasan: Menyaring Kiriman

Teks di layar:
- Membaca itu murah, mengirim itu mahal
- Ambang perubahan atau deadband menyaring kiriman
- Bandingkan dengan nilai terakhir dikirim, bukan dibaca
- Tambahkan pengiriman wajib berkala sebagai tanda hidup

Yang Anda ucapkan:
> Membaca sensor dan mengirim data adalah dua pekerjaan berbeda dan tidak harus seirama, karena membaca hanya mengambil angka dari pin sedangkan mengirim melibatkan radio, sambungan, dan penerima di ujung lain.
> Penentu paling berguna adalah besar perubahan, dan selisih minimal yang dianggap berarti itu disebut ambang perubahan atau deadband.
> Dengan ambang 0,5 derajat, pembacaan 27,14 lalu 27,33 tidak dikirim, sedangkan 28,05 dikirim karena selisihnya melewati ambang.
> Yang dibandingkan harus nilai yang terakhir dikirim, bukan yang terakhir dibaca, sebab kenaikan lambat sebesar 0,1 derajat setiap dua detik tidak akan pernah melewati ambang padahal dalam sepuluh menit suhu sudah naik jauh.
> Ambang terlalu kecil membuat derau terhitung sebagai perubahan, ambang terlalu besar menahan perubahan yang penting, jadi lihatlah dahulu berapa besar nilai bergoyang ketika keadaan sebenarnya diam lalu pasang ambang sedikit di atas goyangan itu.
> Terakhir, penerima tidak boleh bingung membedakan nilai yang tidak berubah dengan perangkat yang mati, karena itu tetap kirim satu kabar berkala seperti petugas pengukur air yang tetap datang meski rumah sedang kosong; cara berpikir ini punya nama resmi yang kita bahas berikutnya.

### Frame 7 — Polling dan Event-Driven

Kawasan: Menyaring Kiriman

Teks di layar:
- Polling: program memeriksa sendiri secara berkala
- Event-driven: program bertindak ketika sesuatu terjadi
- Polling cocok untuk suhu; event untuk tombol
- Sekali per peristiwa, bukan sekali per pemeriksaan
- Gabungan: polling membaca, event mengirim, berkala berkabar

Yang Anda ucapkan:
> Ada dua cara program mengetahui keadaan dunia luar, yaitu polling yang memeriksa sendiri secara berkala dan event-driven yang bertindak ketika sesuatu terjadi.
> Pemicu polling adalah jadwal yang Anda tetapkan sehingga cocok untuk nilai yang berubah perlahan seperti suhu atau kelembapan, sedangkan pemicu event-driven adalah peristiwa dari luar atau perubahan nilai sehingga cocok untuk kejadian jarang tetapi penting seperti penekanan tombol atau perintah masuk.
> Keduanya punya kelemahan: polling bisa melewatkan perubahan yang terjadi di antara dua pemeriksaan, sementara peristiwa yang sangat cepat atau bergetar dapat terbaca berkali-kali sebagai satu kejadian.
> Perlu Anda sadari bahwa event-driven pada papan seperti ESP32 sering tetap dibangun di atas polling, karena program memeriksa keadaan tombol atau kotak pesan MQTT setiap putaran `loop()` lalu bertindak hanya bila ada yang berubah.
> Yang membuatnya terasa event-driven bukan cara memeriksanya melainkan cara menanggapinya, yaitu pekerjaan dilakukan sekali per peristiwa dan bukan sekali per pemeriksaan, sehingga pemeriksaan yang sering justru menjadi syarat dan itu mustahil selama `loop()` masih dibekukan `delay()`.
> Pola gabungan inilah yang dipakai pada contoh program Bab 9 materi pertemuan ini: polling untuk membaca, event untuk mengirim, ditambah satu kiriman berkala sebagai tanda hidup; sekarang kita bahas isi kiriman itu.

### Frame 8 — Payload JSON yang Rapi

Kawasan: Bentuk Pesan

Teks di layar:
- Satu angka `36.02` memaksa penerima menebak maknanya
- JSON: pasangan nama dan nilai dalam kurawal
- Nama field huruf kecil dengan garis bawah
- Sertakan satuan pada namanya: `suhu_c`, `uptime_ms`
- Angka ditulis tanpa tanda kutip

Yang Anda ucapkan:
> Payload adalah isi pesan yang dikirim, dan pada Pertemuan 8 payload Anda mungkin baru berupa satu angka seperti `36.02`.
> Bentuk itu bekerja, tetapi penerima harus menebak angka apa itu, satuannya apa, dari perangkat mana, dan diukur kapan.
> Karena itu bungkus data dalam JSON sederhana, misalnya `{"perangkat":"esp32-nim12345","suhu_c":28.05,"uptime_ms":10214,"alasan":"berubah"}`, yang dapat dibaca manusia sekaligus dimengerti hampir semua penerima.
> Ada bentuk lain yang lebih hemat berupa nilai berurutan dipisahkan koma, tetapi maknanya bergantung pada urutan sehingga menyisipkan satu nilai baru di tengah membuat penerima lama salah membaca tanpa memberi tanda apa pun.
> Kebiasaan penamaannya sederhana: huruf kecil dengan garis bawah, satuan menempel pada namanya seperti `suhu_c`, angka tanpa tanda kutip, dan nama field dipertahankan selamanya karena mengganti `suhu_c` menjadi `temp` di tengah jalan akan mematahkan semua penerima yang sudah bekerja.
> Jangan pernah memasukkan nama lengkap, nomor telepon, atau apa pun yang bersifat pribadi ke dalam payload, sebab broker publik dapat dibaca siapa saja; satu field terakhir yang layak dibahas sendiri adalah penanda waktunya.

### Frame 9 — uptime_ms dan Batas Waktunya

Kawasan: Bentuk Pesan

Teks di layar:
- `uptime_ms` mengirim nilai `millis()` apa adanya
- ESP32 tidak memiliki jam bertahan baterai
- Angka kembali kecil setiap papan menyala ulang
- Dua perangkat tidak dapat dibandingkan lewat `uptime_ms`
- Tugas ini: penerima mencatat jam kedatangan

Yang Anda ucapkan:
> Penerima sering perlu tahu kapan sebuah nilai diukur, dan cara termurah adalah mengirim nilai `millis()` apa adanya sebagai field `uptime_ms`.
> Angka itu bukan jam dinding melainkan lama papan sudah berjalan, tetapi penerima tetap dapat menghitung jarak waktu antar kiriman dan mengenali papan yang baru menyala ulang karena angkanya kembali kecil.
> Yang tidak dapat dilakukan papan adalah menyebut tanggal dan jam yang sebenarnya, sebab ESP32 tidak memiliki jam bertahan baterai sehingga saat menyala ia tidak tahu hari ini tanggal berapa.
> Batasnya ada tiga: angkanya kembali ke nol setiap papan menyala ulang, pencacahnya berputar ulang setelah sekitar 49,7 hari, dan dua perangkat berbeda tidak dapat dibandingkan karena masing-masing menghitung dari saat menyala sendiri-sendiri.
> Pilihan lainnya adalah papan mengambil waktu dari layanan waktu jaringan, yang menambah pustaka dan menuntut sambungan sehingga belum diperlukan sekarang, atau penerima yang mencatat jam kedatangan pesan, yang cukup akurat untuk pemantauan biasa.
> Untuk tugas pertemuan ini kirim `uptime_ms` dan biarkan penerima mencatat jam kedatangan, lalu sebutkan pilihan itu beserta alasannya di laporan Anda; berikutnya kita lihat semua gagasan tadi bekerja bersama dalam satu program.

### Frame 10 — Tiga Pekerjaan dalam Satu loop()

Kawasan: Ruang Praktik

Teks di layar:
- Tiga pekerjaan: kedip LED, baca sensor, kirim
- Tiga variabel `waktu...Terakhir` menjaga jadwal tidak bertabrakan
- `suhuTerkirim` diisi `-999.0`, kiriman pertama pasti terjadi
- `fabs()` memperlakukan penurunan sama penting dengan kenaikan
- Field `alasan` berisi `berubah` atau `berkala`

Yang Anda ucapkan:
> Program lengkap pada Bab 9 materi pertemuan ini menjalankan tiga pekerjaan tanpa pernah berhenti menunggu: mengedipkan LED setiap lima ratus milidetik, membaca sensor setiap dua ribu milidetik, dan mengirim payload hanya ketika perlu.
> Sumber nilai suhunya masih potensiometer pada pin 34 seperti Pertemuan 8, jadi Anda dapat memutar sendiri nilainya untuk menguji ambang.
> Tiga variabel `waktu...Terakhir` mencatat kapan masing-masing pekerjaan terakhir dijalankan sehingga jadwalnya tidak saling mengganggu, sementara `suhuTerkirim` diisi `-999.0` yang mustahil dicapai sensor agar kiriman pertama selalu terjadi.
> Di dalam blok pembacaan, selisih dihitung dengan `fabs()` supaya penurunan suhu diperlakukan sama pentingnya dengan kenaikan, lalu data dikirim bila selisih mencapai ambang atau sudah enam puluh ribu milidetik tanpa kabar.
> Dua pembaruan setelah pengiriman tidak boleh dilupakan, yaitu nilai terkirim yang memindahkan patokan ambang dan waktu kirim yang menyetel ulang hitungan kiriman berkala, dan alasan pengiriman ikut dikirim di field `alasan` agar penerima tahu kiriman itu datang karena berubah atau karena sudah waktunya berkabar.
> Bacalah program itu dengan satu pertanyaan: pada satu putaran `loop()`, apa saja yang dikerjakan? Jawabannya hampir selalu sedikit sekali, dan justru karena murah itulah papan sempat menanggapi apa pun yang datang; mari kita buktikan di simulator.

### Frame 11 — Demo Perbaikan di Simulator

Kawasan: Ruang Praktik

Teks di layar:
- Catat pesan proyek lama sebagai pembanding
- Hapus `delay(2000)`, pindahkan pembacaan ke blok `millis()`
- Tambahkan kedip LED `500` lalu ambang perubahan
- Cetak baris kirim dan baris lewati
- Hasil: LED rata, kiriman jauh lebih sedikit

Yang Anda ucapkan:
> Di depan kelas kita kerjakan urutan pada Bab 8 materi pertemuan ini satu langkah sekali jalan, dan setiap langkah diuji sebelum langkah berikutnya, sebab bila tiga hal diubah bersamaan dan hasilnya salah Anda tidak tahu perubahan mana yang bersalah.
> Langkah pertama menjalankan proyek lama dengan klien MQTT berlangganan topik Anda lalu mencatat jumlah pesan yang masuk, karena setelah program diubah keadaan lama tidak dapat diulang lagi.
> Sesudah proyek disalin menjadi proyek baru, `delay(2000)` dihapus dari akhir `loop()` dan pembacaan dipindahkan ke blok pemeriksaan `millis()` berjeda dua ribu milidetik, lalu ditambahkan kedip LED berjeda lima ratus milidetik sebagai pekerjaan kedua.
> Baru setelah itu ambang perubahan, kiriman wajib berkala, payload JSON, dan dua jenis baris log dipasang di atas dasar yang sudah bersih.
> Yang harus terlihat ada empat: LED berkedip rata setengah detik walau pembacaan dan pengiriman berjalan, baris seperti `lewati -> suhu=27.33 selisih hanya 0.19` ketika nilai hampir sama, baris berisi payload utuh ketika nilai berubah cukup jauh, dan satu kiriman beralasan berkala bila sensor dibiarkan diam lama.
> Jumlah pesan pada percobaan kedua harus jauh lebih sedikit daripada proyek lama; kalau yang Anda lihat berbeda, gejalanya biasanya sudah ada di daftar berikut.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Ruang Praktik

Teks di layar:
- LED tersendat: masih ada `delay()` panjang
- Tidak pernah terkirim: ambang terlalu besar
- Terkirim terus: nilai terkirim belum diperbarui
- Jadwal tidak wajar: variabel waktu bertipe `int`
- Payload dianggap rusak: tanda kutip tanpa garis miring

Yang Anda ucapkan:
> Lima gejala inilah yang paling sering muncul, dan tabel penelusuran masalah pada Bab 8 materi pertemuan ini menyediakan penyebab beserta yang perlu diperiksa.
> Bila LED berkedip tersendat, cari seluruh `delay()` di dalam `loop()` dan sisakan hanya yang sangat singkat atau yang berada di `setup()`.
> Bila data tidak pernah terkirim, ambangnya terlalu besar atau nilai awal pembanding terlalu mirip pembacaan, jadi turunkan ambang dan buat nilai pembanding awal sengaja mustahil seperti `-999.0`.
> Bila data terkirim terus seperti sebelumnya, blok pengiriman berada di luar pemeriksaan ambang atau variabel nilai terkirim tidak diperbarui tepat setelah pengiriman, sedangkan jadwal yang kacau setelah beberapa saat hampir selalu berarti variabel waktu masih bertipe `int`.
> Bila penerima menganggap payload rusak, periksa setiap tanda kutip pada teks format apakah sudah diberi garis miring, dan besarkan penyangga teks bila payload terpotong.
> Kalau Anda macet, kembalikan proyek ke langkah terakhir yang berhasil lalu ulangi satu perubahan saja, dan saat meminta bantuan sebutkan langkah yang sudah berhasil beserta dua baris log terakhir; sekarang kita rangkum semuanya.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 9

Kawasan: Penutup dan Tugas

Teks di layar:
- Jeda diatur karena setiap kiriman memakai sumber daya
- `millis()` menjadwalkan; `delay()` panjang keluar dari `loop()`
- Ambang menyaring, kiriman berkala menandai perangkat hidup
- Payload JSON bernama tetap dengan satuan jelas
- Checkpoint: hitung pesan per menit, lalu bandingkan

Yang Anda ucapkan:
> Mari kita kumpulkan enam butir pentingnya: jeda pengiriman perlu diatur karena setiap kiriman memakai energi, kuota, dan sumber daya broker, sementara data terlalu rapat jarang menambah pengetahuan.
> `delay()` membekukan seluruh program dan hanya aman untuk jeda sangat singkat atau untuk persiapan di `setup()`, sedangkan `millis()` dipakai dengan membandingkan selisih waktu terhadap catatan terakhir memakai variabel `unsigned long`.
> Membaca boleh sering karena murah, mengirim disaring dengan ambang perubahan, dan kiriman berkala wajib menjaga agar diamnya perangkat tidak disalahartikan sebagai mati; polling dan event-driven pun sering dipakai bersama.
> Payload rapi berbentuk JSON dengan nama field tetap, satuan jelas, angka tanpa tanda kutip, dan penanda perangkat, sementara `uptime_ms` hanya memberi waktu relatif karena waktu absolut harus datang dari luar.
> Checkpoint evaluasi pada Bab 13 materi pertemuan ini menuntut empat hal yang Anda periksa sendiri: pengiriman lebih hemat daripada versi sebelumnya, program tidak lagi berhenti menunggu, payload rapi dan konsisten, serta Anda dapat menunjuk baris mana yang berjadwal dan baris mana yang bertindak karena syarat terpenuhi.
> Cara memastikannya sederhana, yaitu menghitung pesan yang masuk ke klien MQTT pada proyek lama dan proyek baru dengan putaran potensiometer yang mirip; setelah itu Anda siap mengerjakan tugasnya.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup dan Tugas

Teks di layar:
- Kerjakan pada salinan proyek, bukan aslinya
- Wajib: `millis()`, pekerjaan tambahan, ambang, kiriman berkala
- Kumpulkan program, log sepuluh baris, tangkapan layar
- Catatan satu halaman: pesan sebelum dan sesudah
- Bobot: penjadwalan `25%`, penyaringan `25%`, payload `20%`

Yang Anda ucapkan:
> Tugas Anda adalah mengubah proyek UTS dari Pertemuan 8 sehingga data hanya dikirim ketika terjadi perubahan yang berarti, dengan payload yang lebih rapi, dan dikerjakan pada salinan agar versi lama tetap ada.
> Ketentuan wajibnya empat: penjadwalan memakai `millis()` tanpa `delay()` panjang di `loop()`, satu pekerjaan tambahan berjeda berbeda sebagai bukti program tidak membeku, pengiriman disaring ambang pilihan Anda beserta kiriman berkala wajib, dan payload JSON berisi penanda perangkat, nilai bersatuan, serta `uptime_ms`.
> Yang dikumpulkan adalah berkas program atau tautan proyek simulator beserta nama proyeknya, kutipan log serial minimal sepuluh baris yang memuat baris terkirim dan terlewat, tangkapan layar klien MQTT yang menampilkan payload JSON, dan catatan satu halaman.
> Catatan itu memuat jumlah pesan sebelum dan sesudah perubahan, nilai ambang beserta alasannya, dan satu paragraf tentang polling dan event-driven pada program Anda sendiri, bukan definisi umum.
> Penilaiannya terbagi menjadi penjadwalan dengan `millis()` dan penyaringan pengiriman masing-masing `25%`, bentuk payload `20%`, bukti penghematan `15%`, serta penjelasan polling dan event-driven `15%`; perlu Anda ingat bahwa tugas latihan mingguan berbobot dua puluh persen dari nilai akhir.
> Sekarang pertanyaan pembuka tadi sudah dapat dijawab utuh: sebuah data layak dikirim ketika nilainya berubah melewati ambang yang Anda pilih, atau ketika sudah cukup lama tidak ada kabar sehingga penerima perlu tanda bahwa perangkat Anda masih hidup.
