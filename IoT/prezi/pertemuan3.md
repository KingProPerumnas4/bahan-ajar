# Prezi Pertemuan 3 — Input Analog dan Pembacaan Sensor Virtual

## Kanvas utama

Saat Prezi dibuka, yang terlihat lebih dahulu adalah satu kanvas lebar dengan judul pertemuan di tengah dan enam kawasan yang mengelilinginya seperti perjalanan sebuah sinyal. Kawasan Pembuka berada di kiri atas, lalu jalur bergerak ke kanan: dari dua jenis data, menuju cara ESP32 mengubah sinyal menjadi angka, lalu ke sensor virtual dan serial monitor sebagai tempat angka itu diamati. Dari sana jalur menurun ke kawasan Smart Light, tempat angka berubah menjadi keputusan, dan berakhir di kawasan Penutup di kanan bawah. Urutan kawasan mengikuti urutan bab pada materi, sehingga setiap zoom terasa sebagai satu langkah maju pada cerita yang sama, yaitu bagaimana kondisi lingkungan dibaca lalu dipakai untuk bertindak.

- Kawasan 1: Pembuka — judul pertemuan, pertanyaan pemancing, dan capaian pembelajaran.
- Kawasan 2: Dua Jenis Data — ciri data digital, ciri data analog, dan alasan data analog penting dalam IoT.
- Kawasan 3: Pembacaan Analog — fungsi `analogRead()`, alur pembacaan, dan threshold sebagai dasar keputusan.
- Kawasan 4: Sensor Virtual dan Serial Monitor — potensiometer, LDR virtual, dan jendela untuk mengamati data.
- Kawasan 5: Smart Light — demo di simulator, contoh kode, dan kesalahan yang sering terjadi.
- Kawasan 6: Penutup — ringkasan, checkpoint evaluasi, serta tugas latihan beserta penilaiannya.

## Alur zoom

1. Angka di Balik Cahaya
2. Capaian Pembelajaran Pertemuan 3
3. Digital Tegas, Analog Bertingkat
4. Mengapa Analog Penting dalam IoT
5. analogRead() sebagai Penerjemah Sinyal
6. Lima Langkah Alur Pembacaan Analog
7. Threshold sebagai Dasar Keputusan
8. Potensiometer dan LDR Virtual
9. Serial Monitor sebagai Jendela Data
10. Demo Smart Light di Simulator
11. Membaca Kode Smart Light
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint Pertemuan 3
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Angka di Balik Cahaya

Kawasan: Pembuka

Teks di layar:
- Pertemuan 3: Input Analog dan Pembacaan Sensor Virtual.
- Bagaimana angka sensor menjadi keputusan menyalakan lampu?
- Cahaya berubah bertahap, bukan sekadar hidup atau mati.
- Jawabannya lengkap di akhir presentasi ini.

Yang Anda ucapkan:
> Pertemuan ini memindahkan perhatian Anda dari dunia dua keadaan ke dunia yang bertingkat.
> Pada pertemuan sebelumnya, pembahasan banyak berfokus pada input dan output digital yang nilainya hanya HIGH atau LOW.
> Sekarang ada satu pertanyaan yang akan menemani seluruh presentasi ini: bagaimana sebuah angka hasil pembacaan sensor bisa berubah menjadi keputusan menyalakan lampu?
> Cahaya di sebuah ruangan tidak berpindah tiba-tiba dari gelap ke terang, ia berubah bertahap, dan program Anda memerlukan cara untuk membaca perubahan itu.
> Jawaban utuhnya baru terbentuk pada frame terakhir, setelah Anda melihat threshold bekerja pada contoh smart light.
> Sebelum sampai ke sana, kita sepakati lebih dahulu apa yang harus Anda kuasai pada pertemuan ini.

### Frame 2 — Capaian Pembelajaran Pertemuan 3

Kawasan: Pembuka

Teks di layar:
- Anda memahami perbedaan data digital dan analog.
- Anda memahami makna `analogRead()` pada ESP32.
- Anda membaca sensor virtual secara konsisten.
- Anda menampilkan data pembacaan ke serial monitor.
- Anda memakai nilai sensor sebagai dasar keputusan.

Yang Anda ucapkan:
> Bab Capaian pada materi pertemuan ini membagi sasaran menjadi dua sisi, yaitu yang Anda pahami dan yang dapat Anda lakukan.
> Pada sisi pemahaman, Anda perlu membedakan data digital dari data analog, mengetahui makna analogRead() pada ESP32, serta memahami peran sensor virtual dan serial monitor.
> Pada sisi keterampilan, Anda perlu membaca nilai sensor analog virtual secara konsisten, menampilkannya, lalu memakainya sebagai dasar keputusan program.
> Target minimal pertemuan ini singkat: Anda mampu membaca data sensor virtual dan memakainya untuk mengambil keputusan, bukan hanya menampilkan angkanya.
> Wujud konkretnya adalah smart light sederhana yang membuat LED menyala saat cahaya yang terbaca rendah.
> Agar sampai ke sana, langkah pertama adalah memastikan Anda benar-benar paham beda data digital dan data analog.

### Frame 3 — Digital Tegas, Analog Bertingkat

Kawasan: Dua Jenis Data

Teks di layar:
- Data digital hanya punya dua keadaan tegas.
- Contohnya HIGH atau LOW, nyala atau mati.
- Data analog punya rentang nilai yang berubah bertahap.
- Saklar lampu berbeda dari keran air.

Yang Anda ucapkan:
> Data digital bersifat diskrit, artinya hanya memiliki sedikit keadaan yang jelas, umumnya dua saja seperti HIGH dan LOW atau nyala dan mati.
> Bentuk data seperti ini cocok untuk tombol, switch, sensor gerak sederhana, dan status on atau off, serta mudah diuji dengan logika if-else yang sederhana.
> Data analog berbeda karena memiliki rentang nilai yang berubah bertahap, sehingga lebih tepat untuk menggambarkan perubahan lingkungan.
> Materi pertemuan ini memakai perbandingan yang mudah diingat: saklar lampu di rumah hanya punya dua keadaan, sedangkan keran air bisa dibuka sedikit, sedang, atau penuh.
> Karena nilainya bertingkat, data analog biasanya perlu dibaca sebagai angka dan sering perlu batas tertentu sebelum bisa dipakai untuk keputusan.
> Pertanyaan berikutnya wajar muncul: mengapa perbedaan ini begitu penting dalam sistem IoT?

### Frame 4 — Mengapa Analog Penting dalam IoT

Kawasan: Dua Jenis Data

Teks di layar:
- Cahaya, suhu, kelembapan, dan suara berubah kontinu.
- Data digital saja memberi informasi yang kasar.
- Gelap dan tidak gelap kurang kaya untuk keputusan.
- LED bisa samar saat ruangan agak gelap.

Yang Anda ucapkan:
> Banyak sistem IoT dibuat untuk memahami kondisi lingkungan, dan kondisi lingkungan jarang hadir dalam dua nilai tegas.
> Intensitas cahaya, suhu, kelembapan, dan level suara umumnya berubah secara kontinu.
> Jika sistem hanya memakai data digital, informasi yang diperoleh menjadi terlalu kasar: mengetahui gelap dan tidak gelap memang berguna, tetapi mengetahui seberapa terang ruangan jauh lebih kaya untuk pengambilan keputusan.
> Dengan data analog, sistem dapat menentukan respons yang lebih cerdas, misalnya menyalakan LED samar saat ruangan agak gelap dan lebih terang saat ruangan sangat gelap.
> Perlu Anda catat bahwa gradasi terang seperti itu membutuhkan pengaturan tingkat keluaran melalui PWM, dan PWM baru diperkenalkan pada Pertemuan 4.
> Sekarang mari kita lihat bagaimana ESP32 mengubah kondisi yang bertahap itu menjadi angka yang bisa diolah program.

### Frame 5 — analogRead() sebagai Penerjemah Sinyal

Kawasan: Pembacaan Analog

Teks di layar:
- `analogRead(pin)` membaca sinyal pada pin analog.
- Hasilnya berupa angka, bukan kata terang atau gelap.
- Program yang memberi makna pada angka itu.
- Ini jembatan dunia fisik dan dunia komputasi.

Yang Anda ucapkan:
> Pada ESP32, pembacaan analog umumnya dilakukan dengan fungsi analogRead(pin).
> Fungsi ini membaca tegangan atau sinyal pada pin analog tertentu, lalu mengubahnya menjadi angka digital yang dapat diproses program, sehingga ia menjadi jembatan antara dunia fisik yang kontinu dan dunia komputasi yang berbasis angka.
> Perlu Anda perhatikan bahwa hasil pembacaan bukan kata terang atau gelap, melainkan sebuah angka.
> Programlah yang kemudian memberi makna pada angka itu, misalnya menganggap nilai di bawah batas tertentu sebagai kondisi gelap.
> Materi pertemuan ini mengibaratkan analogRead() sebagai petugas yang mengubah tinggi air pada tabung ukur menjadi angka pada lembar laporan: tinggi air itu bersifat fisik dan kontinu, tetapi harus diubah dulu menjadi angka supaya bisa dianalisis.
> Supaya lebih jelas, kita telusuri alurnya langkah demi langkah.

### Frame 6 — Lima Langkah Alur Pembacaan Analog

Kawasan: Pembacaan Analog

Teks di layar:
- Sensor menghasilkan sinyal sesuai kondisi lingkungan.
- ESP32 membaca sinyal itu pada pin tertentu.
- `analogRead()` mengembalikan nilai numerik ke program.
- Program menampilkan atau memproses nilai itu.
- Keputusan diambil bila threshold memang diperlukan.

Yang Anda ucapkan:
> Alur pembacaan analog pada materi pertemuan ini terdiri dari lima langkah yang berurutan.
> Sensor menghasilkan sinyal yang berubah-ubah sesuai kondisi lingkungan, lalu ESP32 membaca sinyal itu pada pin tertentu.
> Fungsi analogRead() mengembalikan nilai numerik, dan program menampilkan atau memproses nilai tersebut.
> Bila diperlukan, program mengambil keputusan berdasarkan sebuah batas, dan keputusan itulah yang tampak sebagai aksi pada LED.
> Diagram pada Bab 2 materi pertemuan ini menampilkan rantai yang sama, dari sensor LDR atau potensiometer, ke pin analog, ke analogRead(), ke program, lalu ke aksi.
> Langkah kelima tadi memerlukan satu konsep yang perlu kita bahas tersendiri, yaitu threshold.

### Frame 7 — Threshold sebagai Dasar Keputusan

Kawasan: Pembacaan Analog

Teks di layar:
- Threshold adalah batas pembeda antara dua kondisi.
- Contoh: nilai di bawah 500 menyalakan LED.
- Angka mentah berubah menjadi aksi nyata.
- Mirip batas nilai kelulusan yang ditetapkan 75.

Yang Anda ucapkan:
> Dalam banyak kasus, nilai analog tidak berhenti pada tampilan, tetapi dipakai untuk keputusan.
> Materi pertemuan ini memberi contoh sederhana: jika nilai sensor berada di bawah 500, maka LED dinyalakan.
> Angka 500 itu disebut threshold, yaitu batas yang dipakai program untuk membedakan satu kondisi dari kondisi lain.
> Threshold penting karena ia menjadi jembatan dari data numerik menuju aksi nyata.
> Perbandingannya mirip batas nilai kelulusan: angka hasil ujian adalah data mentah, dan ketika 75 ditetapkan sebagai batas lulus, angka-angka itu baru bisa dipakai untuk memutuskan lulus atau belum.
> Untuk memilih batas yang masuk akal, Anda perlu sensor yang nilainya mudah diamati, dan di situlah sensor virtual berperan.

### Frame 8 — Potensiometer dan LDR Virtual

Kawasan: Sensor Virtual dan Serial Monitor

Teks di layar:
- Potensiometer virtual diubah lewat penggeser atau knob.
- LDR berubah mengikuti intensitas cahaya virtual.
- Satu sensor menghasilkan rentang nilai, bukan dua status.
- Sensor virtual membuat eksperimen threshold lebih aman.

Yang Anda ucapkan:
> Materi pertemuan ini menyoroti dua sensor virtual, yaitu potensiometer dan LDR.
> Potensiometer virtual biasanya memiliki penggeser atau knob yang dapat Anda ubah secara manual, dan setiap perubahan posisinya membuat nilai analog yang dibaca ESP32 ikut berubah.
> Perbandingan yang dipakai adalah knop volume pada speaker, yang tidak hanya diam atau keras tetapi dapat diatur bertahap dari kecil ke besar.
> LDR atau Light Dependent Resistor berubah mengikuti intensitas cahaya, sehingga di dalam simulasi Anda dapat mengubah tingkat pencahayaan virtual lalu melihat angka sensor ikut bergeser.
> Sensor virtual dipakai lebih dahulu karena Anda bisa fokus pada logika pembacaan tanpa direpotkan pemasangan hardware fisik, perubahan nilainya cepat diamati dan dapat diulang, serta eksperimen threshold menjadi lebih aman.
> Agar perubahan angka itu benar-benar terlihat, Anda memerlukan satu jendela untuk mengamatinya.

### Frame 9 — Serial Monitor sebagai Jendela Data

Kawasan: Sensor Virtual dan Serial Monitor

Teks di layar:
- Serial monitor menampilkan nilai sensor secara real-time.
- Anda dapat menguji konsistensi data pembacaan.
- Threshold yang masuk akal lebih mudah ditentukan.
- Ini alat debugging pertama sebelum menyalahkan rangkaian.

Yang Anda ucapkan:
> Serial monitor adalah tampilan teks yang menunjukkan data yang dikirim dari program ke komputer atau simulator.
> Dengan alat ini Anda dapat memastikan tiga hal sekaligus: apakah sensor benar-benar menghasilkan angka, apakah nilainya berubah, dan apakah logika keputusan berjalan sesuai dugaan.
> Serial monitor juga mempermudah penentuan threshold yang masuk akal, karena Anda melihat rentang nilai yang nyata dan tidak menduga-duga.
> Dalam debugging dasar, sebelum menyalahkan sensor atau rangkaian, langkah pertama yang paling masuk akal adalah melihat data mentahnya di serial monitor.
> Materi pertemuan ini mengibaratkannya sebagai panel check-up pada kendaraan, tempat indikator dan data diagnostik dilihat lebih dahulu sebelum mesin diperbaiki.
> Sekarang ketiga bahan tadi, yaitu pembacaan analog, threshold, dan serial monitor, akan kita satukan dalam satu contoh nyata.

### Frame 10 — Demo Smart Light di Simulator

Kawasan: Smart Light

Teks di layar:
- Tambahkan LDR virtual dan LED pada proyek.
- Hubungkan LDR ke pin analog, LED ke output.
- Tampilkan nilai sensor, lalu tentukan threshold.
- Ubah cahaya virtual dan amati LED.

Yang Anda ucapkan:
> Di depan kelas ini kita mengerjakan langkah-langkah pada Bab 5 materi pertemuan ini satu per satu.
> Proyek ESP32 dibuka di Wokwi, LDR virtual dan LED ditambahkan, lalu LDR dihubungkan ke pin analog yang sesuai dan LED ke pin output.
> Setelah itu program membaca nilai sensor dengan analogRead(), menampilkan nilai itu ke serial monitor, lalu memakai threshold di dalam logika if-else untuk mengendalikan LED.
> Langkah terakhir adalah bagian yang paling perlu Anda perhatikan: intensitas cahaya virtual diubah perlahan, dari terang ke gelap lalu kembali lagi.
> Ada dua hal yang harus terlihat, yaitu angka pada serial monitor yang terbit berulang dan ikut bergeser mengikuti perubahan cahaya, serta LED yang menyala ketika nilai yang terbaca rendah dan mati ketika cahaya cukup.
> Bila keduanya sudah muncul, kita bisa membaca kodenya baris demi baris.

### Frame 11 — Membaca Kode Smart Light

Kawasan: Smart Light

Teks di layar:
- Pin `34` untuk LDR, pin `2` untuk LED.
- `int threshold = 2000;` menjadi batas keputusan.
- `Serial.begin(115200);` membuka jalur data pembacaan.
- Blok `if-else` menentukan LED nyala atau mati.
- `delay(500);` memberi jeda antar pembacaan.

Yang Anda ucapkan:
> Contoh kode pada Bab 6 materi pertemuan ini memuat seluruh sasaran pertemuan dalam satu program yang pendek.
> Bagian atas menetapkan pin, yaitu pin 34 untuk LDR dan pin 2 untuk LED, lalu sebuah variabel threshold yang bernilai 2000.
> Di dalam setup(), Serial.begin(115200) membuka jalur agar data terlihat di serial monitor, dan pinMode menyatakan pin LED sebagai output.
> Di dalam loop(), nilai sensor dibaca dengan analogRead(), dicetak bersama label Nilai LDR, lalu dibandingkan dengan threshold sehingga digitalWrite menyalakan atau mematikan LED, dan delay(500) memberi jeda agar keluarannya tidak terlalu cepat untuk dibaca.
> Perhatikan satu hal menarik di sini: nilai dari LDR bersifat analog karena berubah dalam rentang angka, tetapi keputusan LED bersifat digital karena hanya nyala atau mati.
> Karena itu materi pertemuan ini juga meminta Anda memeriksa apakah threshold 2000 benar-benar cocok dengan hasil simulasi Anda sendiri, dan pertanyaan itu membawa kita pada kesalahan yang paling sering muncul.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Smart Light

Teks di layar:
- Angka berhenti atau muncul sebagai karakter acak.
- Baud rate dan jeda pembacaan tidak cocok.
- Threshold dituliskan tetapi tidak dipakai pada `if`.
- Nilai sensor tidak berubah sama sekali.
- LED tidak beralih saat nilai melewati threshold.

Yang Anda ucapkan:
> Tabel checkpoint pada Bab 10 materi pertemuan ini menyusun kesalahan yang sering terjadi beserta jalan keluarnya.
> Bila angka di serial monitor berhenti terbit atau muncul sebagai karakter acak, periksa baris Serial.begin(115200) dan delay(500), terutama kesesuaian baud rate dan jeda antar pembacaan.
> Bila titik peralihan LED tidak bergeser ketika nilai threshold diubah, berarti threshold hanya dituliskan dan tidak benar-benar dipakai pada pembandingan di dalam if.
> Bila nilai sensor tidak berubah sama sekali, membandingkan sambungan rangkaian Anda dengan proyek contoh biasanya lebih cepat menemukan penyebabnya daripada memeriksa kode berulang kali.
> Bila LED belum beralih sebagaimana mestinya, tambahkan baris Serial.println("Lampu ON") agar Anda tahu cabang keputusan mana yang sedang dijalankan.
> Setelah rintangan-rintangan itu teratasi, kita bisa memeriksa apakah pertemuan ini sudah tuntas bagi Anda.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan 3

Kawasan: Penutup

Teks di layar:
- Digital tegas, analog punya rentang nilai.
- `analogRead()` mengubah sinyal sensor menjadi angka.
- Serial monitor membuktikan data terbaca dan berubah.
- Threshold mengubah angka menjadi keputusan LED.
- Checkpoint: data tampil, threshold dipakai, LED berubah.

Yang Anda ucapkan:
> Ringkasan pertemuan ini dapat dipadatkan menjadi beberapa butir.
> Data digital hanya punya sedikit keadaan tegas sedangkan data analog punya rentang nilai, dan pada ESP32 pembacaan analog dilakukan dengan analogRead().
> Potensiometer dan LDR virtual membantu Anda melihat perilaku sensor analog secara visual dan interaktif, serial monitor menampilkan datanya, lalu threshold mengubah angka itu menjadi keputusan seperti LED yang menyala saat kondisi dianggap gelap.
> Sebagai checkpoint, pertemuan ini dianggap tuntas bila data sensor tampil konsisten di serial monitor, ada threshold yang benar-benar dipakai di dalam program, dan LED berubah sesuai nilai input.
> Cara memastikannya sederhana: ubah cahaya virtual sampai nilai sensor melewati threshold dari dua arah, yaitu dari terang ke gelap dan sebaliknya, lalu lihat apakah LED ikut beralih secara konsisten.
> Ketiga butir itu adalah bekal langsung untuk checkpoint besar pertama, CP-1, yang jatuh pada Pertemuan 4 dan menguji penguasaan GPIO, hubungan sensor dengan aktuator, serta logika dasar.
> Satu hal terakhir yang perlu Anda kerjakan adalah tugas latihan pertemuan ini.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup

Teks di layar:
- Buat simulasi smart light berbasis LDR virtual.
- Kumpulkan kode, tangkapan layar, dan alasan threshold.
- Pembacaan sensor dan threshold masing-masing berbobot 30 persen.
- Perilaku LED 25 persen, kelengkapan 15 persen.
- Alasan threshold harus dari angka yang Anda amati.

Yang Anda ucapkan:
> Tugas pertemuan ini adalah membuat satu proyek simulasi berisi LDR virtual dan LED, dengan program yang membaca nilai cahaya, menampilkannya ke Serial Monitor, lalu memakai sebuah threshold untuk menentukan perilaku LED.
> Bentuk minimal yang dinilai adalah dua keadaan LED, yaitu menyala saat gelap dan mati saat terang; gradasi terang secara bertahap memerlukan PWM yang baru diperkenalkan pada Pertemuan 4, sehingga sifatnya hanya nilai tambah.
> Yang Anda kumpulkan ada tiga, yaitu kode yang dapat dijalankan tanpa error, tangkapan layar Serial Monitor yang memperlihatkan nilai sensor berubah pada kondisi cahaya berbeda, serta nilai threshold beserta alasan pemilihannya.
> Bobot penilaiannya perlu Anda perhatikan: pembacaan sensor dan tampilan Serial Monitor 30 persen, threshold beserta alasannya 30 persen, perilaku LED terhadap nilai sensor 25 persen, dan kelengkapan pengumpulan 15 persen.
> Bobot terbesar tidak jatuh pada kode karena kode smart light dapat disalin, sedangkan alasan pemilihan batas hanya bisa ditulis oleh orang yang benar-benar melihat datanya sendiri, sehingga alasan yang menyebut bahwa nilainya diambil dari contoh materi tidak diterima.
> Dengan itu pertanyaan pembuka tadi terjawab lengkap: angka sensor menjadi keputusan ketika Anda memilih satu batas dari data yang Anda amati sendiri, lalu membiarkan logika if-else mengubah batas itu menjadi aksi pada LED.
> Tugas latihan mingguan seperti ini berbobot 20 persen dari nilai akhir, jadi mengerjakannya sekarang jauh lebih baik daripada menundanya sampai Pertemuan 4 yang membawa aktuator dan checkpoint besar pertama.
