# Prezi Pertemuan 2 — Dasar ESP32, GPIO, Input-Output Digital

## Kanvas utama

Saat Prezi dibuka, sebelum zoom pertama, yang terlihat adalah satu papan lebar dengan judul pertemuan di tengah, sebuah pertanyaan singkat di bawahnya, dan sebuah bentuk ESP32 besar yang samar sebagai latar, sementara lima kawasan topik tersusun sebagai kelompok kartu di sekeliling papan itu. Kawasan ditata mengikuti perjalanan sinyal pada materi ini: gerbang masuk di kiri atas, otak dan pintunya di kanan atas, kerangka program di kanan bawah, bangku praktik di tengah bawah, dan penutup di kiri bawah, sehingga jalur zoom bergerak dari pengertian menuju kode, lalu menuju perangkat yang bereaksi. Susunan seperti itu membuat setiap perpindahan zoom bercerita seperti mengikuti satu perintah dari tempat ia ditulis sampai lampu benar-benar menyala.

- Kawasan 1: Gerbang Masuk — judul pertemuan, pertanyaan pemancing, dan capaian pembelajaran.
- Kawasan 2: Otak dan Pintunya — peran ESP32, pengertian GPIO, serta logika HIGH dan LOW.
- Kawasan 3: Kerangka Program — fungsi setup() dan loop(), tiga mode pin, dan alur input-output digital.
- Kawasan 4: Bangku Praktik — tiga latihan terpandu, contoh kode, pola blinking, dan penelusuran masalah.
- Kawasan 5: Penutup — ringkasan, checkpoint evaluasi, dan tugas latihan beserta penilaiannya.

## Alur zoom

1. Dasar ESP32, GPIO, dan Sinyal Digital
2. Capaian Pembelajaran Pertemuan Ini
3. Mengapa ESP32 dan GPIO Penting
4. Mengenal ESP32 dan GPIO
5. Dua Keadaan HIGH dan LOW
6. Kerangka Program setup dan loop
7. Tiga Mode Pin pada GPIO
8. Alur Kerja Input-Output Digital
9. Praktik Terpandu Tiga Latihan Bertahap
10. Contoh Kode Blink dan Tombol
11. Pola Blinking dan Perintah Kunci
12. Bila Hasilnya Belum Sesuai
13. Ringkasan dan Checkpoint Pertemuan Ini
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Dasar ESP32, GPIO, dan Sinyal Digital

Kawasan: Gerbang Masuk

Teks di layar:
- Pertemuan 2: dasar ESP32, GPIO, input-output digital
- Fokus bergeser dari gambaran besar ke device
- Bagaimana satu tombol mengatur tiga lampu?
- Jawabannya baru lengkap pada tugas di akhir

Yang Anda ucapkan:
> Selamat datang pada Pertemuan 2, dasar ESP32, GPIO, dan input-output digital. Pada pertemuan sebelumnya tentang orientasi IoT, Anda memahami gambaran besarnya, dan sekarang fokus bergeser ke otak kecil yang menjalankan sistem itu, yaitu ESP32. Pegang satu pertanyaan sepanjang presentasi ini: bagaimana satu tombol dapat mengatur tiga lampu yang berbeda? Jawabannya baru lengkap di frame terakhir, ketika tugas simulasi tiga LED dengan satu tombol mode kita bahas bersama. Untuk sampai ke sana, Anda memerlukan dua bekal lebih dulu, yaitu kerangka program dan pemahaman tentang pin. Mari kita mulai dari capaian yang harus tercapai hari ini.

### Frame 2 — Capaian Pembelajaran Pertemuan Ini

Kawasan: Gerbang Masuk

Teks di layar:
- Memahami struktur `setup()` dan `loop()`
- Memahami GPIO sebagai jalur input output
- Membuat simulasi LED blink pada ESP32
- Membaca status tombol sebagai input digital
- Menjelaskan pin yang dipakai pada rangkaian

Yang Anda ucapkan:
> Capaian pertemuan ini terbagi dua, yaitu hal yang Anda pahami dan hal yang Anda dapat lakukan. Pada sisi pemahaman, Anda perlu menguasai struktur program Arduino pada ESP32 terutama fungsi `setup()` dan `loop()`, konsep GPIO sebagai jalur input dan output digital, perbedaan digital input dan digital output pada sistem tertanam, serta hubungan antara logika program dan respons perangkat seperti LED dan tombol. Pada sisi keterampilan, Anda harus mampu membuat simulasi LED blink pada ESP32, membaca status tombol sebagai input digital, mengendalikan LED berdasarkan logika input-output digital, dan menjelaskan pin yang digunakan dalam rangkaian sederhana. Praktik yang ditekankan ada tiga, yakni simulasi LED blink, tombol untuk menyalakan dan mematikan LED, serta variasi pola blinking. Tugas latihannya satu, yaitu simulasi lampu indikator tiga LED dengan satu tombol mode. Sebelum menyentuh kode, mari kita lihat mengapa dua istilah pada judul pertemuan ini begitu menentukan.

### Frame 3 — Mengapa ESP32 dan GPIO Penting

Kawasan: Otak dan Pintunya

Teks di layar:
- ESP32 membaca input, memproses logika, mengendalikan output
- Device harus benar sebelum data dikirim keluar
- GPIO adalah pintu antara program dan fisik
- Bukan sekadar menyalakan LED, tetapi memutuskan

Yang Anda ucapkan:
> Pada pertemuan sebelumnya Anda memahami gambaran besar IoT, dan sekarang perhatiannya menyempit pada satu kotak di dalam alur itu, yaitu device. ESP32 adalah mikrokontroler yang dapat membaca input, memproses logika, lalu mengendalikan output. Urutan belajarnya disengaja: sebelum sebuah sistem IoT bisa mengirim data ke jaringan atau dashboard, device harus lebih dulu mampu menjalankan input-output digital dengan benar. Karena itu pembahasan GPIO dan struktur program menjadi fondasi, sebab dengan dasar ini Anda tidak hanya bisa menyalakan LED tetapi juga memahami bagaimana device mengambil keputusan berdasarkan keadaan di sekitarnya. Bayangkan sebuah gedung pintar: ESP32 adalah petugas kontrol di ruang panel, sedangkan GPIO adalah tombol, saklar, dan kabel yang menghubungkan petugas itu dengan dunia luar. Supaya tidak berhenti pada analogi, mari kita definisikan kedua istilah tersebut dengan tepat.

### Frame 4 — Mengenal ESP32 dan GPIO

Kawasan: Otak dan Pintunya

Teks di layar:
- ESP32: pemrograman mudah, banyak pin, nirkabel
- GPIO singkatan General Purpose Input/Output
- Pin input membaca kondisi, misalnya tombol
- Pin output memberi sinyal, misalnya LED
- Satu pin serbaguna, perannya Anda tentukan

Yang Anda ucapkan:
> ESP32 banyak dipakai dalam pembelajaran dan pengembangan IoT karena pemrogramannya relatif mudah, pinnya banyak, dan ia mendukung komunikasi nirkabel. Pada tahap ini yang paling penting bukan semua fitur lanjutannya, melainkan fungsi dasarnya sebagai device yang membaca input dan menghasilkan output. GPIO sendiri adalah singkatan dari General Purpose Input/Output, yaitu pin serbaguna yang dapat diatur menjadi jalur masuk atau jalur keluar. Ketika sebuah pin diatur sebagai input, pin itu dipakai untuk membaca kondisi, misalnya tombol sedang ditekan atau tidak; ketika diatur sebagai output, pin itu dipakai untuk memberi sinyal, misalnya menyalakan LED. Perhatikan kata serbaguna di sini, karena satu pin yang sama dapat berperan sebagai input atau output, dan Andalah yang menentukan perannya di dalam program. Pertanyaan berikutnya, apa sebenarnya yang dikirim dan dibaca melalui pin tersebut?

### Frame 5 — Dua Keadaan HIGH dan LOW

Kawasan: Otak dan Pintunya

Teks di layar:
- HIGH berarti aktif, bernilai 1
- LOW berarti tidak aktif, bernilai 0
- `digitalWrite(pin, HIGH)` menyalakan, `LOW` mematikan
- `digitalRead(pin)` membaca keadaan pin input
- Keputusan digital tegas, mudah diproses, konsisten

Yang Anda ucapkan:
> Pada sistem digital, kondisi umumnya dinyatakan dalam dua keadaan saja, yaitu HIGH atau LOW. Secara sederhana, HIGH dapat Anda pahami sebagai kondisi aktif atau bernilai satu, sedangkan LOW sebagai kondisi tidak aktif atau bernilai nol. Saat membaca tombol, program memeriksa apakah input sedang HIGH atau LOW dengan `digitalRead(pin)`; saat mengendalikan LED, program mengirim HIGH untuk menyalakan dan LOW untuk mematikan melalui `digitalWrite(pin, HIGH)` atau `digitalWrite(pin, LOW)`. Anggap saja seperti saklar lampu di rumah yang hanya punya dua keadaan utama, yaitu ON atau OFF. Prinsip dua keadaan ini justru dipakai supaya keputusan menjadi tegas, mudah diproses, dan konsisten. Nilai HIGH dan LOW itu tentu harus ditulis pada tempat yang tepat di dalam program, dan tempatnya punya nama tersendiri.

### Frame 6 — Kerangka Program setup dan loop

Kawasan: Kerangka Program

Teks di layar:
- `setup()` dijalankan sekali saat board aktif
- Di dalamnya: mode pin, komunikasi serial
- `loop()` dijalankan terus setelah `setup()` selesai
- Device bekerja terus selama mendapat daya
- Pisahkan pekerjaan sekali dan pekerjaan berulang

Yang Anda ucapkan:
> Hampir semua program dasar pada Arduino dan ESP32 berdiri di atas dua fungsi ini. Fungsi `setup()` dijalankan satu kali saat board mulai aktif dan dipakai untuk persiapan awal, misalnya menentukan mode pin, mengaktifkan komunikasi serial, atau menginisialisasi komponen lain. Kalau dianalogikan, `setup()` adalah tahap membuka toko sebelum operasional dimulai: lampu dinyalakan, meja kasir disiapkan, dan sistem diperiksa. Fungsi `loop()` berjalan terus-menerus setelah `setup()` selesai, dan semua logika yang harus berlangsung berulang diletakkan di dalamnya. Pemisahan itu penting karena device bukan program sekali jalan seperti banyak aplikasi desktop sederhana; ia bekerja terus selama mendapat daya, sehingga Anda harus jelas membedakan apa yang cukup dikerjakan satu kali dan apa yang harus diulang. Salah satu pekerjaan yang cukup satu kali adalah menetapkan mode setiap pin, dan pilihan modenya ada tiga.

### Frame 7 — Tiga Mode Pin pada GPIO

Kawasan: Kerangka Program

Teks di layar:
- `OUTPUT`: pin mengirim sinyal keluar
- `INPUT`: pin membaca sinyal dari luar
- `INPUT_PULLUP`: input dengan resistor pull-up internal
- OUTPUT untuk LED, buzzer, atau relay
- INPUT_PULLUP membuat pembacaan tombol lebih stabil

Yang Anda ucapkan:
> Mode pin ditetapkan di dalam `setup()` dan pilihannya ada tiga, seperti dirangkum pada Bab 3.1 materi pertemuan ini. Mode `OUTPUT` membuat pin mengirim sinyal keluar dari ESP32, dan itulah yang dipakai untuk menyalakan LED, mengaktifkan buzzer, atau mengontrol relay. Mode `INPUT` membuat pin membaca sinyal dari luar, misalnya dari tombol, switch, atau sensor digital. Mode `INPUT_PULLUP` adalah pin input yang memakai resistor pull-up internal sehingga pembacaan tombol menjadi lebih stabil, dan inilah mode yang dipakai pada contoh tombol nanti. Bayangkan GPIO seperti pintu dua arah pada ruang kontrol: dari satu sisi petugas menerima informasi bahwa seseorang menekan bel, dari sisi lain ia menekan saklar untuk menyalakan lampu di koridor. Sekarang mari kita satukan kedua arah tersebut menjadi satu alur kerja yang utuh.

### Frame 8 — Alur Kerja Input-Output Digital

Kawasan: Kerangka Program

Teks di layar:
- `Tombol → GPIO input → logika → LED`
- Tombol menjadi input digital yang dibaca
- ESP32 membaca nilainya lalu memutuskan aksi
- Logika `if` dan `else` menentukan keluaran
- LED menjadi output digital yang bereaksi

Yang Anda ucapkan:
> Diagram pada Bab 3.3 materi pertemuan ini merangkai semuanya menjadi satu jalur. Tombol berada di ujung kiri sebagai input digital, nilainya dibaca oleh pin GPIO yang difungsikan sebagai input, lalu masuk ke bagian logika berupa `if` dan `else`, dan hasilnya keluar pada LED sebagai output digital. Perlu Anda sadari bahwa tombol tidak pernah menyalakan LED secara langsung; ia hanya memberi sinyal, dan yang memutuskan adalah program di dalam ESP32. Ini seperti tombol bel di pintu masuk gedung yang tidak langsung menyalakan semua sistem, melainkan memberi sinyal ke panel kontrol, dan panel itulah yang memutuskan aksi berikutnya. Karena keputusan berada di program, mengubah logikanya berarti mengubah perilaku perangkat tanpa menyentuh rangkaian sama sekali. Alur ini akan jauh lebih jelas begitu Anda mengerjakannya sendiri lewat tiga latihan berikut.

### Frame 9 — Praktik Terpandu Tiga Latihan Bertahap

Kawasan: Bangku Praktik

Teks di layar:
- Latihan 1: LED blink dengan `digitalWrite()`
- Latihan 2: tombol menyalakan dan mematikan LED
- Latihan 3: variasi pola kedip LED
- LED harus berkedip sesuai selang yang ditetapkan
- Tombol harus mengubah keadaan setiap kali ditekan

Yang Anda ucapkan:
> Aktivitas inti pertemuan ini berupa tiga latihan yang disusun bertahap, dan ketiganya sekarang dijalankan di simulator di depan kelas. Pada latihan pertama, pin LED ditetapkan sebagai `OUTPUT` di dalam `setup()`, lalu di `loop()` LED dinyalakan dan dimatikan bergantian dengan `digitalWrite()` dan `delay()`; yang harus terlihat adalah LED berkedip pada selang waktu yang Anda tetapkan. Pada latihan kedua, sebuah tombol ditambahkan sebagai input digital dengan mode `INPUT_PULLUP`, nilainya dibaca di dalam `loop()`, dan hasilnya harus terlihat sebagai LED yang berubah keadaan setiap kali tombol ditekan, bukan hanya sekali. Pada latihan ketiga, nilai dan urutan `delay()` diubah untuk menghasilkan pola berbeda, misalnya dua kali kedip cepat lalu jeda yang lebih lama; yang harus terlihat adalah pola kedipnya benar-benar berubah begitu nilai waktunya diubah. Cara memeriksanya mengikuti urutan yang sama seperti saat membuatnya, jadi satu latihan dipastikan benar dulu sebelum lanjut ke berikutnya. Kalau salah satu dari ketiga hasil itu belum muncul, penyebabnya hampir selalu sama, dan itu kita bahas sesudah melihat kodenya.

### Frame 10 — Contoh Kode Blink dan Tombol

Kawasan: Bangku Praktik

Teks di layar:
- `const int ledPin = 2;` menamai pin LED
- `const int buttonPin = 4;` untuk tombol
- `pinMode(buttonPin, INPUT_PULLUP);` ditulis di `setup()`
- Tombol ditekan terbaca `LOW`, LED menyala
- Tombol dilepas, LED kembali dimatikan

Yang Anda ucapkan:
> Dua contoh kode pertama pada Bab 5 materi pertemuan ini persis menjalankan dua latihan tadi. Contoh pertama menyimpan nomor pin dengan `const int ledPin = 2;`, menetapkan `pinMode(ledPin, OUTPUT);` di dalam `setup()`, lalu di `loop()` menyalakan dan mematikan LED bergantian dengan jeda `delay(1000)`. Contoh kedua menambahkan `const int buttonPin = 4;` beserta `pinMode(buttonPin, INPUT_PULLUP);`, lalu di dalam `loop()` nilai tombol dibaca ke variabel `buttonState` memakai `digitalRead(buttonPin)`. Logikanya satu percabangan saja: bila `buttonState` bernilai `LOW`, artinya tombol sedang ditekan, maka LED dinyalakan, dan bila tidak, LED dimatikan. Perhatikan bahwa nilai yang terbaca justru `LOW` ketika tombol ditekan, dan itu konsekuensi wajar dari pemakaian mode `INPUT_PULLUP`. Dengan dua contoh tersebut Anda sudah memegang sisi output dan sisi input; yang belum adalah bermain dengan waktunya.

### Frame 11 — Pola Blinking dan Perintah Kunci

Kawasan: Bangku Praktik

Teks di layar:
- Pola: `delay(200)` dua kali, lalu `delay(800)`
- Hasilnya dua kedip cepat lalu jeda
- `pinMode()` menentukan arah sebuah pin
- `digitalWrite()` mengirim, `digitalRead()` membaca
- `delay()` mengatur tempo dan jeda aksi

Yang Anda ucapkan:
> Contoh ketiga tidak menambah komponen apa pun, ia hanya menyusun ulang waktunya. Di dalam `loop()`, LED dinyalakan dan dimatikan dengan `delay(200)` dua kali berturut-turut, lalu jeda terakhir diperpanjang menjadi `delay(800)`, sehingga hasilnya berupa pola dua kedip cepat yang diikuti jeda lebih lama. Tujuannya bukan estetika, melainkan agar Anda memahami bahwa susunan instruksi dan nilai waktu langsung mengubah perilaku output. Tabel pada Bab 5.4 merangkum perintah yang sudah dipakai sejauh ini: `pinMode()` menentukan arah sebuah pin, `digitalWrite()` mengirim logika HIGH atau LOW ke pin output, `digitalRead()` membaca kondisi pin input, dan `delay()` menunda program selama sejumlah milidetik. Anggap saja seperti instruksi kerja bagi petugas gedung: ada instruksi mendengarkan bel masuk, ada instruksi menyalakan lampu, dan ada instruksi menunggu sejenak sebelum tindakan berikutnya. Dengan bekal ini, kesalahan yang muncul pada praktik menjadi jauh lebih mudah dilacak.

### Frame 12 — Bila Hasilnya Belum Sesuai

Kawasan: Bangku Praktik

Teks di layar:
- Nomor pin rangkaian berbeda dengan program
- Mode pin belum ditetapkan di `setup()`
- Pesan merah: cek titik koma, kurawal
- LED berubah sekali saja, bukan setiap tekan
- Bandingkan lama nyala dengan nilai `delay()`

Yang Anda ucapkan:
> Bila salah satu dari tiga hasil praktik tadi belum terjadi, kesalahannya hampir selalu ada pada dua hal, yaitu nomor pin yang tidak sama antara rangkaian dan program, atau mode pin yang belum ditetapkan di dalam `setup()`. Kalau simulasi menolak berjalan dan muncul pesan kesalahan, catat nomor barisnya lalu periksa tanda titik koma serta kurung kurawal pada baris tersebut, dan bila masih belum jelas bacalah ulang Bab 2 tentang struktur `setup()` dan `loop()`. Untuk memastikan LED merespons logika dengan benar, hitung sendiri lama nyala dan lama mati LED, lalu bandingkan dengan nilai `delay()` di program Anda. Untuk latihan tombol, tekan tombolnya beberapa kali dan pastikan keadaan LED berubah setiap kali ditekan, bukan hanya sekali; bila belum, kembalilah ke Bab 3.3 tentang alur input-output digital dan Bab 5.2 tentang contoh tombol. Bila Anda belum lancar menyebutkan pin mana untuk LED, pin mana untuk tombol, dan mode apa yang dipilih untuk masing-masing, Bab 3.1 serta tabel perintah pada Bab 5.4 adalah tempat kembalinya. Perbaikan semacam ini lebih cepat selesai bila Anda tahu persis apa yang sedang diperiksa, jadi mari kita rangkum daftarnya.

### Frame 13 — Ringkasan dan Checkpoint Pertemuan Ini

Kawasan: Penutup

Teks di layar:
- ESP32 membaca input, memproses, menghasilkan output
- GPIO serbaguna: bisa input atau output
- `setup()` sekali, `loop()` terus-menerus
- Mampu membuat kontrol input-output digital dasar
- Mampu membaca alur logika sebuah program

Yang Anda ucapkan:
> Mari kita kumpulkan intinya. ESP32 adalah mikrokontroler yang membaca input, memproses logika, dan menghasilkan output; GPIO adalah jalur serbaguna yang bisa difungsikan sebagai input atau output; `setup()` dijalankan satu kali untuk inisialisasi, sedangkan `loop()` dijalankan terus-menerus. Digital input dipakai untuk membaca kondisi seperti tombol, sementara digital output dipakai untuk mengendalikan perangkat seperti LED. Latihan LED blink, tombol, dan pola blinking adalah fondasi sebelum masuk ke sensor, aktuator yang lebih kompleks, dan komunikasi data IoT. Target minimal pertemuan ini ada tiga: Anda mampu membuat kontrol input-output digital dasar pada ESP32, paham hubungan tombol sebagai input dan LED sebagai output, serta mampu membaca alur logika sederhana di dalam sebuah program. Pemeriksaannya dilakukan tanpa menyalin ulang contoh kode, dan satu butir terakhir baru dapat Anda centang setelah tugas latihan selesai dikerjakan.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup

Teks di layar:
- Tiga LED dan satu tombol mode
- Setiap tekan, mode berpindah ke berikutnya
- Mode 1 merah, 2 kuning, 3 hijau
- Pakai variabel mode untuk menentukan LED aktif
- Penilaian: pin, logika mode, kerapian, penjelasan

Yang Anda ucapkan:
> Tugas latihan pertemuan ini adalah simulasi lampu indikator tiga LED dengan satu tombol mode. Setiap kali tombol ditekan, mode berpindah ke kondisi berikutnya: mode satu menyalakan LED merah, mode dua menyalakan LED kuning, mode tiga menyalakan LED hijau, lalu kembali lagi ke mode satu. Petunjuk pengerjaannya lima langkah, yaitu tentukan pin untuk tiga LED dan satu tombol, atur mode pin dengan benar di `setup()`, baca status tombol di `loop()`, gunakan variabel mode untuk menentukan LED mana yang aktif, lalu uji apakah perpindahan mode berjalan sesuai urutan yang diinginkan. Penilaiannya empat aspek, dengan porsi terbesar pada logika mode yang berjalan benar, disusul rangkaian dan pemilihan pin serta kerapian program yang sama besar, lalu penjelasan hasil. Bacalah kriteria nilai penuh sebelum mulai mengerjakan dan bukan setelah selesai, karena di situlah terlihat apa yang sebenarnya diperiksa: nomor pin pada rangkaian harus sama dengan nomor pin di program, nomor pin ditulis sebagai konstanta bernama, dan Anda harus dapat menjelaskan urutan kerja dari tombol ditekan sampai LED berubah, termasuk peran variabel mode di dalamnya. Inilah jawaban pertanyaan pembuka kita, bahwa satu tombol dapat mengatur tiga lampu karena yang berpindah sesungguhnya bukan lampunya, melainkan nilai variabel mode di dalam program. Kemampuan ini menjadi dasar bagi pertemuan berikutnya, yaitu input analog dan pembacaan sensor virtual.
