# Prezi Pertemuan 5 — Struktur Program yang Rapi dan Debugging Dasar

## Kanvas utama

Saat Prezi dibuka, seluruh kanvas terlihat sekaligus tanpa zoom: judul pertemuan berada di tengah atas, dan di bawahnya enam kawasan tersusun berurutan dari kiri ke kanan mengikuti perjalanan sebuah program, mulai dari alasan program perlu rapi, bahan penyusunnya, alat untuk menelusurinya, sampai bengkel tempat program diperbaiki lalu dinilai. Susunan ini dipilih agar jalur zoom bercerita: semakin ke kanan, program yang tadinya hanya "asal jalan" berangsur menjadi program yang tersusun, terlacak, dan teruji. Zoom pertama masuk ke kawasan paling kiri, kemudian setiap perpindahan bergerak satu langkah ke kanan, sehingga Anda selalu dapat melihat posisi bahasan di dalam gambar besar sebelum layar menutup rapat pada satu frame.

- Kawasan 1: Gerbang — judul pertemuan, pertanyaan pemancing, dan capaian pembelajaran.
- Kawasan 2: Kerapian — alasan program perlu rapi, cirinya, dan akibat bila diabaikan.
- Kawasan 3: Bahan Dasar — variabel, konstanta, dan fungsi sebagai penyusun program.
- Kawasan 4: Alat Penelusuran — Serial Monitor serta pembedaan error sintaks dan error logika.
- Kawasan 5: Bengkel Praktik — perapian program, langkah debugging di simulator, dan kesalahan yang sering muncul.
- Kawasan 6: Penutup — ringkasan, checkpoint evaluasi, dan tugas latihan.

## Alur zoom

1. Program Berjalan, Apakah Sudah Selesai?
2. Capaian Pembelajaran Pertemuan Ini
3. Mengapa Kerapian Program Penting
4. Akibat Program yang Tidak Rapi
5. Variabel dan Konstanta
6. Fungsi Membagi Tugas Program
7. Serial Monitor sebagai Alat Debugging
8. Error Sintaks dan Error Logika
9. Dari Menumpuk Menjadi Modular
10. Praktik Debugging di Simulator
11. Kesalahan yang Sering Terjadi
12. Ringkasan dan Checkpoint Pertemuan 5
13. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Program Berjalan, Apakah Sudah Selesai?

Kawasan: Gerbang

Teks di layar:
- Pertemuan 5: struktur program dan debugging dasar
- Program menyala. Apakah pekerjaan Anda selesai?
- Rapi, mudah dibaca, mudah ditelusuri saat salah
- Jawabannya lengkap pada frame terakhir

Yang Anda ucapkan:
> Selamat datang pada Pertemuan 5. Sampai pertemuan lalu, program yang Anda tulis sudah bisa menyalakan LED dan membaca sensor, dan biasanya di titik itu program dianggap selesai. Materi hari ini menantang anggapan tersebut: program yang baik bukan hanya program yang berjalan, tetapi juga program yang terstruktur, mudah dipahami, dan mudah ditelusuri saat terjadi kesalahan. Analogi pada Bab 1 materi pertemuan ini menyebut gudang tanpa rak dan label, semua barang memang ada di dalamnya, tetapi mencari satu barang menjadi lama dan membingungkan. Jadi pertanyaan pembuka kita adalah kapan sebuah program yang sudah menyala masih pantas disebut belum selesai. Simpan pertanyaan itu, karena jawabannya baru lengkap setelah kita membahas fungsi, Serial Monitor, dan dua jenis kesalahan. Kita mulai dengan melihat apa yang harus Anda kuasai di akhir pertemuan ini.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Gerbang

Teks di layar:
- Memahami peran fungsi, variabel, dan konstanta
- Membedakan error sintaks dan error logika
- Membaca pesan error kompilasi dasar
- Menambahkan `Serial.print()` untuk melacak nilai program
- Memecah program menjadi fungsi kecil yang jelas

Yang Anda ucapkan:
> Ada dua sisi capaian pada pertemuan ini, yaitu yang perlu Anda pahami dan yang perlu Anda kerjakan. Sisi pemahaman mencakup peran fungsi, variabel, dan konstanta, perbedaan error sintaks dan error logika, serta alasan program modular lebih mudah diuji daripada program yang menumpuk dalam satu blok besar. Sisi keterampilan mencakup membaca pesan error kompilasi, menyisipkan `Serial.print()` untuk melacak nilai dan alur, memecah program menjadi fungsi kecil, dan menemukan titik kesalahan pada program ESP32 di simulator. Target minimalnya tegas: Anda tidak berhenti pada menyalin kode, tetapi mampu melacak sendiri letak kesalahan dan membuat program lebih rapi. Sebagai contoh, di akhir pertemuan Anda diminta mengambil satu program lama lalu memecahnya menjadi minimal tiga fungsi tanpa mengubah perilakunya. Sebelum sampai ke sana, kita perlu sepakat lebih dahulu mengapa kerapian itu layak diperjuangkan.

### Frame 3 — Mengapa Kerapian Program Penting

Kawasan: Kerapian

Teks di layar:
- Nama jelas: variabel dan fungsi menggambarkan perannya
- Tugas terpisah, tidak semua dicampur di `loop()`
- Mudah diuji: bagian dicek satu per satu
- Rapi bukan soal estetika, tetapi kemampuan menelusuri

Yang Anda ucapkan:
> Pada tahap awal belajar pemrograman mikrokontroler, banyak program ditulis dengan gaya asal jalan, selama lampu menyala atau sensor terbaca program dianggap beres. Persoalannya muncul ketika program bertambah panjang, karena kode seperti itu sulit dibaca, sulit diperbaiki, dan sulit dikembangkan. Materi pertemuan ini menyebut tiga ciri program yang rapi, dan ketiganya ada di layar: nama variabel serta fungsi yang menggambarkan perannya, tugas yang terpisah sehingga tidak semua dicampur di dalam `loop()`, dan bagian-bagian yang dapat dicek satu per satu saat terjadi kesalahan. Contoh paling sederhana adalah nama fungsi seperti `readButton()`, isinya dapat Anda duga tanpa perlu membukanya. Karena itu kerapian bukan urusan estetika penulisan, melainkan menyangkut kemampuan memahami, menguji, dan memperbaiki sistem. Sekarang kita lihat apa yang terjadi bila ciri-ciri itu diabaikan.

### Frame 4 — Akibat Program yang Tidak Rapi

Kawasan: Kerapian

Teks di layar:
- Pembaca sulit memahami alur program
- Kesalahan kecil sulit ditemukan karena logika bercampur
- Mengubah satu bagian dapat merusak bagian lain
- Pada IoT: input, output, log, dan jaringan

Yang Anda ucapkan:
> Program yang terlalu padat dalam satu blok biasanya menimbulkan tiga masalah berurutan. Pertama, pembaca sulit memahami alur karena semuanya tampil sekaligus. Kedua, kesalahan kecil sulit ditemukan sebab seluruh logika bercampur di satu tempat. Ketiga, mengubah satu bagian bisa merusak bagian lain tanpa Anda sengaja. Dalam konteks IoT akibatnya lebih terasa, karena satu program sering harus membaca input, mengontrol output, menampilkan log, dan nanti mengirim data ke jaringan secara bersamaan. Bayangkan `loop()` yang sekaligus membaca tombol, mencetak log, dan mengatur LED seperti pada contoh versi kurang rapi di materi ini, menambah satu sensor saja sudah membuatnya padat. Supaya tidak sampai ke keadaan itu, kita kenali lebih dahulu tiga bahan dasar penyusun program.

### Frame 5 — Variabel dan Konstanta

Kawasan: Bahan Dasar

Teks di layar:
- Variabel menyimpan data yang nilainya bisa berubah
- Konstanta menyimpan nilai tetap, misalnya nomor pin
- `int buttonState = 0;` menyimpan status tombol
- `const int ledPin = 2;` menandai acuan tetap

Yang Anda ucapkan:
> Variabel adalah tempat menyimpan data yang nilainya bisa berubah selama program berjalan, misalnya status LED, nilai sensor, atau mode kerja. Anggap variabel seperti papan tulis kecil di meja kerja, isinya boleh diganti kapan saja sesuai keadaan terbaru. Konstanta justru sebaliknya, yaitu data yang nilainya tetap dan tidak diubah selama program berjalan, misalnya nomor pin atau ambang batas yang memang sengaja dibuat tetap. Konstanta itu seperti nomor ruang kelas, dipakai terus sebagai acuan dan tidak berganti-ganti. Pada contoh program di materi ini, `const int ledPin = 2;` menyimpan nomor pin LED sebagai acuan tetap, sedangkan `int buttonState = 0;` menyimpan status tombol yang berubah mengikuti pembacaan input. Dengan dua bahan itu tersedia, kita dapat bicara soal bahan ketiga yang membagi pekerjaan program.

### Frame 6 — Fungsi Membagi Tugas Program

Kawasan: Bahan Dasar

Teks di layar:
- Fungsi adalah blok program untuk satu tugas
- Contoh: membaca tombol, mengatur LED, menampilkan log
- Program panjang dibagi menjadi bagian berperan jelas
- Seperti pembagian tugas di dalam satu tim

Yang Anda ucapkan:
> Fungsi adalah blok program yang dibuat untuk menjalankan satu tugas tertentu. Dengan fungsi, program panjang dapat dibagi menjadi bagian-bagian kecil yang masing-masing punya peran jelas, misalnya membaca tombol, mengatur LED, atau menampilkan log ke Serial Monitor. Materi ini mengumpamakannya sebagai pembagian tugas dalam sebuah tim, ada anggota yang khusus menerima data, ada yang memproses, dan ada yang melaporkan hasil, sehingga pekerjaan lebih tertata dibanding semua orang mengerjakan semuanya sekaligus. Keuntungan nyatanya muncul saat ada masalah, sebab perhatian Anda bisa langsung diarahkan ke fungsi yang berkaitan. Karena itu nama fungsi harus menjelaskan pekerjaannya, dan nama seperti `fungsi1()` tidak menolong siapa pun. Satu fungsi yang hampir selalu terpakai adalah fungsi pencetak log, dan alat di baliknya kita bahas berikutnya.

### Frame 7 — Serial Monitor sebagai Alat Debugging

Kawasan: Alat Penelusuran

Teks di layar:
- Program dapat berbicara kepada pembuatnya
- Menunjukkan apakah program masuk ke bagian tertentu
- Menampilkan nilai variabel saat program berjalan
- `Serial.begin(115200);` lalu `Serial.println()` mencetak nilai
- Mengurangi kebiasaan menebak penyebab error

Yang Anda ucapkan:
> Serial Monitor adalah alat paling dasar tetapi paling sering menyelamatkan dalam pemrograman embedded, karena membuat program dapat berbicara kepada pembuatnya. Melalui Serial Monitor, program dapat menunjukkan apakah ia benar-benar masuk ke bagian tertentu, menampilkan nilai variabel saat berjalan, dan membantu Anda membedakan apakah masalah ada pada pembacaan input, proses logika, atau output. Anggap alat ini seperti CCTV dan buku log di ruang kontrol, tanpa keduanya seseorang hanya menebak-nebak apa yang terjadi. Pemakaiannya singkat, seperti pada Bab 3 materi pertemuan ini, `Serial.begin(115200);` mengaktifkan komunikasi serial, lalu `Serial.print("Nilai tombol: ");` disusul `Serial.println(buttonState);` mencetak label beserta nilainya. Bedanya hanya satu, `println` menambahkan pindah baris sedangkan `print` tidak. Dengan keluaran serial di tangan, Anda siap memilah dua jenis kesalahan yang sifatnya sangat berbeda.

### Frame 8 — Error Sintaks dan Error Logika

Kawasan: Alat Penelusuran

Teks di layar:
- Sintaks: gagal dikompilasi karena penulisan salah
- Logika: kompilasi berhasil, hasilnya tidak sesuai harapan
- Contoh sintaks: titik koma hilang, kurung tak seimbang
- Contoh logika: LED mati saat tombol ditekan
- Sintaks dulu, logika kemudian

Yang Anda ucapkan:
> Dua jenis kesalahan ini sering tertukar, padahal sifat dan cara menanganinya berbeda. Error sintaks membuat program gagal dikompilasi karena aturan penulisan tidak dipenuhi, misalnya titik koma hilang, kurung tidak seimbang, atau nama fungsi salah tulis, dan penanganannya adalah membaca pesan kompilasi, menemukan baris terkait, lalu memperbaiki penulisan. Error logika sebaliknya, program berhasil dikompilasi tetapi hasilnya tidak sesuai harapan, dan penanganannya memakai Serial Monitor untuk memeriksa nilai variabel serta menelusuri alur keputusan. Materi ini memberi contoh pendek untuk keduanya. Menulis `Serial.begin(115200)` tanpa titik koma adalah error sintaks, sedangkan menulis `if (buttonState == HIGH) { digitalWrite(ledPin, LOW); }` padahal LED semestinya menyala saat tombol ditekan adalah error logika yang sintaksnya justru benar. Urutan kerjanya juga penting, perbaiki sintaks lebih dahulu, karena selama program belum bisa dijalankan logikanya belum bisa diuji. Setelah program berjalan, barulah kita masuk ke bengkel dan merapikannya.

### Frame 9 — Dari Menumpuk Menjadi Modular

Kawasan: Bengkel Praktik

Teks di layar:
- Versi awal: semua tugas menumpuk di `loop()`
- Pecah menjadi `readButton()`, `printDebugInfo()`, `updateLed()`
- `setupPins()` memisahkan konfigurasi pin dari logika
- `loop()` menjadi urutan pemanggilan yang ringkas
- Masalah tombol? Periksa `readButton()` lebih dahulu

Yang Anda ucapkan:
> Perbandingan pada Bab 5 materi pertemuan ini menunjukkan dua versi program tombol dan LED yang perilakunya sama. Versi pertama menaruh semua tugas di dalam `loop()`, yaitu membaca tombol, mencetak log, lalu mengatur LED, sehingga blok itu akan cepat padat begitu program berkembang. Versi kedua memecahnya menjadi `setupPins()` untuk konfigurasi pin, `readButton()` untuk pembacaan input, `printDebugInfo()` untuk log, dan `updateLed()` untuk keluaran, sedangkan `loop()` tinggal memanggil ketiganya secara berurutan. Keuntungannya langsung terasa saat ada masalah, bila pembacaan tombol mencurigakan perhatian diarahkan ke `readButton()`, dan bila format log ingin diubah cukup ubah `printDebugInfo()`. Materi ini mengumpamakannya sebagai dapur restoran dengan stasiun kerja terpisah, sehingga masalah rasa tidak perlu dijawab dengan membongkar seluruh dapur. Dengan program yang sudah tersusun seperti ini, penelusuran di simulator menjadi jauh lebih terarah.

### Frame 10 — Praktik Debugging di Simulator

Kawasan: Bengkel Praktik

Teks di layar:
- Jalankan kompilasi, baca pesan error lebih dahulu
- Tambahkan `Serial.print()` pada titik yang dicurigai
- Uji satu bagian dalam satu waktu
- Hasil: nilai tombol berubah `0` dan `1`
- Rapikan setelah program benar

Yang Anda ucapkan:
> Sekarang kita jalankan langkahnya di simulator, dan Anda ikuti urutan yang sama nanti. Program tombol dan LED versi modular dibuka lebih dahulu lalu dikompilasi, dan jika kompilasi gagal pesan error dibaca serta jenis kesalahannya ditentukan sebelum satu baris pun diubah. Setelah kompilasi lolos, Serial Monitor dibuka, dan yang harus terlihat di layar adalah baris `Button: 0` yang berubah menjadi `Button: 1` tepat pada saat tombol ditekan, disusul LED yang menyala. Bila nilai tombol ternyata selalu `0`, masalahnya ada pada pembacaan input atau wiring virtual, bukan pada bagian LED, dan bila nilainya berubah dengan benar tetapi LED tetap diam, barulah logika LED yang diperiksa. Aturannya satu, uji satu bagian dalam satu waktu, lalu rapikan setelah program benar. Cara ini sama dengan mencari sebab lampu ruangan tidak menyala, yang dimulai dari saklar dan bohlam, bukan dari membongkar instalasi seluruh gedung. Beberapa kesalahan muncul begitu sering sehingga bentuknya layak Anda kenali.

### Frame 11 — Kesalahan yang Sering Terjadi

Kawasan: Bengkel Praktik

Teks di layar:
- Titik koma hilang, program gagal dikompilasi
- Pesan menunjuk `}`, kesalahan ada di atasnya
- Deklarasi di dalam `loop()` mengulang nilai nol
- Serial Monitor menampilkan `Jumlah tekan: 1` terus
- Perbaikan: pindahkan deklarasi ke luar `loop()`

Yang Anda ucapkan:
> Dua kesalahan berikut diambil dari kunci jawaban tugas pada Bab 10 materi pertemuan ini, dan keduanya sangat khas. Yang pertama, baris `nilaiCahaya = analogRead(ldrPin)` tidak diakhiri titik koma, sehingga program gagal dikompilasi dan Serial Monitor tetap kosong, dengan pesan yang berbunyi seperti `expected ';' before '}' token`. Perhatikan bahwa pesan itu menunjuk kurung kurawal penutup, padahal yang kurang adalah titik koma pada baris di atasnya, jadi pesan error menunjukkan tempat kompiler menyadari ada masalah dan tempat itu tidak selalu sama dengan tempat kesalahan ditulis. Yang kedua, baris `int jumlahTekan = 0;` ditulis di dalam `loop()`, sehingga variabel dibuat ulang pada setiap putaran dan hasil penambahan tidak pernah menumpuk. Gejalanya juga khas, kompilasi berhasil tanpa pesan apa pun, LED tetap menyala benar saat tombol ditekan, tetapi Serial Monitor selalu menampilkan `Jumlah tekan: 1` berapa kali pun tombol ditekan. Perbaikannya memindahkan deklarasi itu keluar dari `loop()` menjadi variabel global, atau menulisnya sebagai `static int jumlahTekan = 0;` agar nilainya bertahan antarpemanggilan. Mari kita kumpulkan semuanya menjadi daftar pemeriksaan diri.

### Frame 12 — Ringkasan dan Checkpoint Pertemuan 5

Kawasan: Penutup

Teks di layar:
- Variabel berubah, konstanta tetap, fungsi membagi tugas
- Serial Monitor menunjukkan apa yang sebenarnya terjadi
- Bedakan error sintaks dan error logika
- Tunjukkan titik kesalahan memakai keluaran serial
- `loop()` baru hanya memanggil fungsi berurutan

Yang Anda ucapkan:
> Mari kita rangkum. Variabel menyimpan data yang berubah, konstanta menyimpan acuan tetap, dan fungsi membagi tugas program menjadi bagian yang jelas, sementara Serial Monitor menunjukkan apa yang sebenarnya terjadi di dalam program, dan error sintaks menggagalkan kompilasi sedangkan error logika membuat hasil salah meskipun kompilasi berhasil. Checkpoint pertemuan ini, yang rinciannya ada pada Bab 11 materi pertemuan ini, meminta tiga bukti: Anda dapat menyebut jenis kesalahan pada dua program latihan sebelum menjalankannya, dapat menunjuk baris keluaran serial tempat nilai mulai menyimpang, dan dapat menunjukkan `loop()` versi baru yang hanya berisi urutan pemanggilan fungsi. Uji cepat untuk butir pertama cukup satu pertanyaan, apakah program masih bisa dikompilasi. Bila tidak bisa, kesalahannya sintaks, dan bila bisa tetapi hasilnya salah, kesalahannya logika. Kemampuan melacak ini akan terus dipakai menjelang checkpoint besar CP-2 pada Pertemuan 8, karena program yang berhubungan dengan jaringan lebih sulit ditebak dan lebih bergantung pada log. Tinggal satu hal lagi, yaitu tugas yang harus Anda kerjakan.

### Frame 13 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup

Teks di layar:
- Tugas 1: perbaiki Program A dan B
- Tugas 2: rapikan satu program pertemuan sebelumnya
- Minimal tiga fungsi, nama menjelaskan pekerjaannya
- Ketepatan temuan 30%, penjelasan gejala 20%
- Pemecahan fungsi 30%, alasan perapian 20%

Yang Anda ucapkan:
> Tugas pertemuan ini terdiri atas dua bagian, dan rinciannya ada pada Bab 10 materi pertemuan ini. Tugas pertama menyediakan dua program, Program A memuat tepat satu kesalahan sintaks dan Program B memuat tepat satu kesalahan logika, jadi salin keduanya ke simulator, temukan kesalahannya sendiri sebelum membuka kunci jawaban, lalu kumpulkan kode yang sudah diperbaiki beserta catatan baris mana yang salah, jenis kesalahannya, gejala sebelum perbaikan, dan apa yang Anda ubah, ditambah tangkapan layar Serial Monitor sebelum dan sesudah untuk Program B. Tugas kedua meminta Anda memilih satu program lama, misalnya program tombol dan LED dari Pertemuan 2, program smart light berbasis ambang batas dari Pertemuan 3, atau portal otomatis dengan servo dan buzzer dari Pertemuan 4, lalu menyusunnya ulang menjadi minimal tiga fungsi yang namanya menjelaskan pekerjaannya tanpa mengubah perilaku program. Penilaiannya terbagi empat, yaitu ketepatan temuan 30 persen, penjelasan gejala 20 persen, pemecahan fungsi 30 persen, dan alasan perapian 20 persen, sementara tugas mingguan seperti ini berbobot 20 persen dari nilai akhir. Perhatikan bahwa menemukan kesalahan tanpa dapat menjelaskan gejalanya masih dianggap belum tuntas, sebab yang dilatih di sini adalah menghubungkan gejala dengan penyebab, bukan menghafal letak kesalahan. Dan inilah jawaban pertanyaan pembuka kita, sebuah program pantas disebut selesai bukan ketika lampunya menyala, melainkan ketika Anda dapat menunjukkan letak kesalahannya dan menjelaskan tugas setiap fungsinya dalam satu kalimat.




