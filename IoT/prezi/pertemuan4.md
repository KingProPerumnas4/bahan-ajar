# Prezi Pertemuan 4 — Aktuator Dasar: Buzzer, Servo, dan Relay Virtual

## Kanvas utama

Saat Prezi dibuka, yang tampak lebih dahulu adalah judul pertemuan di tengah kanvas dengan enam kawasan yang tersusun sebagai satu rantai sebab-akibat. Kawasan Pembuka berada di kiri atas, lalu jalur bergerak ke kanan mengikuti pola input, proses, dan output: dari peran aktuator, menuju tiga aktuator dasar yang mewakili suara, gerak, dan saklar, lalu ke kawasan Logika Keputusan yang menjadi simpul di tengah kanvas. Dari simpul itu jalur menurun ke kawasan Portal Otomatis, tempat semua bagian bekerja bersama dalam satu skenario, dan berakhir di kawasan Penutup di kanan bawah. Susunannya mengikuti urutan bab pada materi, sehingga setiap zoom terasa seperti melangkah satu tahap pada alur sistem, bukan berpindah topik.

- Kawasan 1: Pembuka — judul pertemuan, pertanyaan pemancing, dan capaian pembelajaran.
- Kawasan 2: Dari Sensor ke Aktuator — peran aktuator dan makna output terkontrol kondisi.
- Kawasan 3: Tiga Aktuator Dasar — buzzer, servo, relay virtual, dan pengenalan PWM.
- Kawasan 4: Logika Keputusan — struktur `if-else` sebagai jembatan input menuju output.
- Kawasan 5: Portal Otomatis — alur sistem, demo di simulator, contoh kode, dan kesalahan yang sering terjadi.
- Kawasan 6: Penutup — ringkasan, checkpoint CP-1, serta tugas latihan beserta penilaiannya.

## Alur zoom

1. Satu Input, Banyak Respons
2. Capaian Pembelajaran Pertemuan 4
3. Sensor Merasakan, Aktuator Bertindak
4. Output Terkontrol Kondisi
5. Buzzer: Keluaran Berupa Bunyi
6. Servo: Kontrol Posisi Sudut
7. Relay Virtual: Saklar Elektronik
8. Pengenalan PWM Secara Sederhana
9. If-Else sebagai Jembatan Keputusan
10. Demo Portal Otomatis di Simulator
11. Membaca Kode Portal Otomatis
12. Kesalahan yang Sering Terjadi
13. Ringkasan dan Checkpoint CP-1
14. Tugas Latihan dan Pokok Penilaian

## Frame

### Frame 1 — Satu Input, Banyak Respons

Kawasan: Pembuka

Teks di layar:
- Pertemuan 4: Aktuator Dasar Buzzer, Servo, Relay Virtual.
- Bagaimana satu input memicu dua aksi sekaligus?
- Sistem tidak lagi hanya memantau keadaan.
- Jawabannya lengkap di akhir presentasi ini.

Yang Anda ucapkan:
> Sampai pertemuan sebelumnya, perhatian Anda banyak tertuju pada bagaimana perangkat membaca input, termasuk membaca sensor virtual dan memakai ambang batas pada Pertemuan 3.
> Pertemuan ini menggeser fokus ke arah sebaliknya, yaitu bagaimana sistem memberi respons melalui komponen yang disebut aktuator.
> Pertanyaan yang akan menemani seluruh presentasi ini adalah bagaimana satu input bisa memicu dua aksi sekaligus, misalnya palang yang terbuka dan bunyi yang terdengar pada saat yang sama.
> Pertanyaan itu bukan sekadar teka-teki, karena tugas pertemuan ini memang meminta perilaku seperti itu.
> Jawaban utuhnya baru lengkap pada frame terakhir, setelah Anda melihat satu blok keputusan mengendalikan servo dan buzzer secara bersamaan.
> Sebelum sampai ke sana, kita sepakati dahulu sasaran pertemuan ini.

### Frame 2 — Capaian Pembelajaran Pertemuan 4

Kawasan: Pembuka

Teks di layar:
- Anda memahami perbedaan sensor dan aktuator.
- Anda mengaktifkan buzzer pada kondisi tertentu.
- Anda menggerakkan servo virtual ke sudut tertentu.
- Anda membuat simulasi relay virtual untuk beban.
- Anda menerapkan `if-else` agar aktuator merespons benar.

Yang Anda ucapkan:
> Bab Capaian pada materi pertemuan ini membagi sasaran menjadi dua sisi, yaitu yang Anda pahami dan yang dapat Anda lakukan.
> Pada sisi pemahaman, Anda perlu membedakan sensor dari aktuator, mengetahui fungsi buzzer, servo, dan relay virtual sebagai keluaran sistem, memahami hubungan logika kondisi dengan respons aktuator, serta mengenal PWM secara sederhana.
> Pada sisi keterampilan, Anda perlu mengaktifkan buzzer saat kondisi tertentu, menggerakkan servo virtual ke sudut tertentu, membuat simulasi relay virtual untuk menghidupkan dan mematikan beban, lalu menerapkan logika if-else agar aktuator merespons input dengan benar.
> Target minimalnya cukup satu kalimat: Anda mampu menghubungkan input sensor dengan respons aktuator.
> Wujud konkretnya adalah simulasi portal otomatis sederhana yang akan kita jalankan bersama nanti.
> Langkah pertama adalah memahami mengapa aktuator berdiri di sisi yang berbeda dari sensor.

### Frame 3 — Sensor Merasakan, Aktuator Bertindak

Kawasan: Dari Sensor ke Aktuator

Teks di layar:
- Sensor membaca kondisi dari lingkungan sekitar.
- Aktuator menjalankan aksi sebagai keluaran sistem.
- Contoh sensor: LDR, potensiometer, sensor jarak.
- Contoh aktuator: LED, buzzer, servo, relay.
- Tanpa aktuator, sistem tahu tetapi tidak bertindak.

Yang Anda ucapkan:
> Materi pertemuan ini meletakkan sensor dan aktuator sebagai dua sisi dari satu alur sistem.
> Sensor bertugas merasakan kondisi lingkungan dan memasukkan informasi ke program, sedangkan aktuator menjalankan aksi sebagai akibat dari keputusan program.
> Tabel pada Bab 1 materi pertemuan ini mencantumkan contohnya, yaitu LDR, potensiometer, sensor suhu, dan sensor jarak di sisi sensor, lalu LED, buzzer, servo, relay, dan motor di sisi aktuator.
> Perbandingan yang dipakai adalah gedung dengan petugas keamanan: sensor seperti mata dan telinga yang mendeteksi keadaan, sedangkan aktuator seperti tangan dan suara yang membuka pintu atau menyalakan alarm.
> Tanpa aktuator, sistem hanya sampai pada tahap monitoring, dan begitu sistem mulai bertindak berdasarkan data, ia berkembang menuju otomasi, dengan konsep yang sama dipakai pada skala industri untuk membuka katup atau memutus aliran listrik.
> Namun aktuator tidak boleh bekerja sembarangan, dan di sinilah muncul istilah output terkontrol kondisi.

### Frame 4 — Output Terkontrol Kondisi

Kawasan: Dari Sensor ke Aktuator

Teks di layar:
- Aktuator bekerja hanya saat kondisi terpenuhi.
- Jika sensor aktif, buzzer menyala.
- Jika tombol ditekan, servo bergerak ke 90 derajat.
- Jika nilai melewati ambang, relay menjadi ON.
- Polanya tetap: input, proses, lalu output.

Yang Anda ucapkan:
> Output terkontrol kondisi berarti aktuator tidak aktif sembarangan, melainkan bekerja karena program menemukan kondisi tertentu.
> Materi pertemuan ini memberi tiga contoh yang langsung terbayang, yaitu buzzer menyala jika sensor aktif, servo bergerak ke sudut 90 derajat jika tombol ditekan, dan relay berubah dari OFF ke ON jika nilai input melewati ambang tertentu.
> Ketiganya memakai pola yang sama, yaitu input, lalu proses, lalu output, dengan ESP32 berada pada bagian proses melalui logika if-else.
> Pola inilah yang membedakan sistem yang dirancang dari sistem yang kebetulan menyala, dan pada checkpoint nanti Anda memang diminta membuktikan bahwa keluaran muncul karena kondisi yang terbaca program.
> Perlu Anda catat juga bahwa aktuator yang tidak aktif bukan berarti dibiarkan, karena ia dimatikan, dikembalikan ke posisi awal, atau ditahan pada keadaan aman.
> Setelah polanya jelas, mari kita kenali satu per satu tiga aktuator yang dipakai pada pertemuan ini.

### Frame 5 — Buzzer: Keluaran Berupa Bunyi

Kawasan: Tiga Aktuator Dasar

Teks di layar:
- Buzzer adalah aktuator yang menghasilkan bunyi.
- Sering dipakai sebagai alarm atau penanda kondisi.
- Responsnya cepat dan langsung terdengar manusia.
- Seperti bel pintu atau alarm parkir mobil.

Yang Anda ucapkan:
> Buzzer adalah aktuator yang keluarannya berupa bunyi, dan pada sistem sederhana ia sering dipakai sebagai alarm atau penanda kondisi.
> Contoh yang disebut materi pertemuan ini adalah sensor yang mendeteksi objek terlalu dekat, lalu buzzer berbunyi sebagai peringatan.
> Nilai pentingnya bagi Anda adalah buzzer memperjelas bahwa keluaran sistem tidak harus berupa cahaya, tetapi bisa berupa tanda yang langsung terdengar oleh manusia.
> Perbandingannya adalah bel pintu atau alarm parkir mobil, yang berbunyi ketika kondisi tertentu terjadi agar orang segera sadar dan merespons.
> Di dalam program, buzzer termasuk keluaran yang paling sederhana karena cukup dinyalakan dan dimatikan.
> Aktuator berikutnya menuntut lebih dari itu, sebab yang dituju bukan hidup atau mati, melainkan posisi.

### Frame 6 — Servo: Kontrol Posisi Sudut

Kawasan: Tiga Aktuator Dasar

Teks di layar:
- Servo dapat bergerak menuju sudut tertentu.
- Fokusnya kontrol posisi, bukan putaran terus-menerus.
- Cocok untuk gerbang, lengan mekanik, penunjuk sudut.
- Contohnya tertutup 0 derajat, terbuka 90 derajat.

Yang Anda ucapkan:
> Servo adalah aktuator yang dapat bergerak ke sudut tertentu, dan hal itu membuatnya berbeda dari motor DC biasa yang berputar terus.
> Fokus servo adalah kontrol posisi, sehingga ia sangat cocok untuk simulasi gerbang otomatis, lengan mekanik sederhana, atau penunjuk sudut.
> Materi pertemuan ini memakai perbandingan palang parkir otomatis: sistem tidak hanya ingin palang bergerak, tetapi ingin ia berhenti pada sudut tertentu, misalnya tertutup di 0 derajat dan terbuka di 90 derajat.
> Dua angka itu akan muncul lagi pada contoh kode, dan pada tugas Anda boleh memakai angka lain selama alasannya masuk akal.
> Karena yang dikendalikan adalah posisi, servo memerlukan sinyal yang lebih terkontrol daripada sekadar HIGH atau LOW.
> Aktuator ketiga justru mengambil sisi sebaliknya, yaitu menegaskan dua keadaan saja.

### Frame 7 — Relay Virtual: Saklar Elektronik

Kawasan: Tiga Aktuator Dasar

Teks di layar:
- Relay adalah saklar yang dikendalikan secara elektrik.
- Dipakai untuk memahami konsep ON/OFF beban.
- Tampilannya mungkin hanya simbol atau LED indikator.
- ESP32 dapat mengendalikan perangkat lain lewat saklar.

Yang Anda ucapkan:
> Relay adalah saklar yang dikendalikan secara elektrik, dan di dalam simulasi relay virtual dipakai untuk memahami konsep menghidupkan dan mematikan beban.
> Yang terlihat pada simulator mungkin hanya sebuah simbol atau LED indikator, tetapi ide dasarnya penting: device kecil seperti ESP32 dapat mengendalikan perangkat lain melalui mekanisme saklar.
> Materi pertemuan ini mengibaratkannya sebagai petugas yang menekan saklar utama lampu gedung, sehingga ESP32 tidak harus menyalakan beban besar secara langsung, tetapi cukup memberi perintah agar saklar itu berubah posisi.
> Dibandingkan servo yang punya sudut dan buzzer yang menghasilkan bunyi, relay paling menekankan dua keadaan, yaitu hidup atau mati.
> Karena itu relay menjadi contoh yang bersih untuk memperkenalkan logika saklar digital.
> Sekarang kita kembali sejenak ke servo, karena kebutuhan sinyalnya membuka satu istilah baru pada pertemuan ini.

### Frame 8 — Pengenalan PWM Secara Sederhana

Kawasan: Tiga Aktuator Dasar

Teks di layar:
- PWM mengatur output lewat lebar pulsa sinyal.
- Sebagian aktuator perlu sinyal lebih terkontrol.
- HIGH atau LOW saja belum cukup untuk servo.
- Servo butuh pola sinyal agar mencapai posisi.

Yang Anda ucapkan:
> PWM atau Pulse Width Modulation adalah teknik mengatur output dengan memanipulasi lebar pulsa sinyal.
> Pada tahap awal ini Anda tidak harus masuk ke detail elektronik yang rumit, dan yang penting dipahami adalah bahwa beberapa aktuator memerlukan sinyal yang lebih terkontrol daripada sekadar HIGH atau LOW.
> Servo menjadi contoh terbaik untuk memperkenalkan ide itu, karena ia tidak cukup diberi kondisi ON atau OFF, melainkan pola sinyal tertentu agar dapat bergerak ke posisi yang diinginkan.
> Dengan kata lain, pengenalan PWM di sini adalah jembatan menuju kontrol output yang lebih halus, bukan target yang harus Anda kuasai penuh sekarang.
> Rinciannya ada pada Bab 2 materi pertemuan ini, di bagian pengenalan PWM secara sederhana.
> Meski bentuk sinyalnya berbeda-beda, ketiga aktuator tadi dikendalikan dengan cara berpikir program yang sama.

### Frame 9 — If-Else sebagai Jembatan Keputusan

Kawasan: Logika Keputusan

Teks di layar:
- Program mengecek kondisi, lalu memilih respons.
- `if (sensorAktif)` menjalankan respons yang dikehendaki.
- Blok `else` mengembalikan sistem ke kondisi aman.
- Satu keputusan kecil menghasilkan dua perilaku sistem.

Yang Anda ucapkan:
> Tiga aktuator tadi terlihat berbeda, tetapi cara berpikir programnya serupa, yaitu program mengecek kondisi lalu memilih respons.
> Jika kondisi benar, aktuator diberi perintah tertentu, dan jika tidak, aktuator dimatikan, dikembalikan ke posisi awal, atau dibiarkan pada keadaan aman.
> Struktur if-else pada Bab 3 materi pertemuan ini hanya beberapa baris, tetapi mewakili inti otomasi, karena di situlah device berhenti menjalankan perintah kaku dan mulai memilih aksi berdasarkan input.
> Perbandingannya adalah penjaga pintu otomatis: jika kartu akses valid pintu dibuka, jika tidak valid pintu tetap tertutup, sehingga satu keputusan kecil menghasilkan dua perilaku sistem yang berbeda.
> Checkpoint pertemuan ini juga meminta Anda memahami mengapa aktuator menyala pada kondisi tertentu dan tidak menyala pada kondisi lain, bukan hanya berhasil menyalakannya.
> Pola sesederhana itu ternyata sudah cukup untuk membangun skenario yang akan kita jalankan berikutnya.

### Frame 10 — Demo Portal Otomatis di Simulator

Kawasan: Portal Otomatis

Teks di layar:
- Kondisi awal: portal tertutup, buzzer diam.
- Input aktif, program membaca perubahan di `loop()`.
- Servo bergerak dari sudut tutup ke buka.
- Buzzer berbunyi selama portal masih terbuka.
- Input mati: buzzer berhenti, servo kembali menutup.

Yang Anda ucapkan:
> Di depan kelas ini kita menjalankan skenario portal otomatis pada simulator, mengikuti alur kerja sistem pada Bab 4 materi pertemuan ini.
> Rangkaiannya memuat satu sumber input berupa tombol atau sensor virtual, satu servo, dan satu buzzer, lalu simulasi dijalankan dengan portal pada kondisi awal tertutup dan buzzer diam.
> Input kemudian diaktifkan, dan yang harus terlihat adalah servo bergerak dari sudut tutup ke sudut buka sekaligus buzzer mulai berbunyi selama portal berada pada posisi terbuka.
> Setelah itu input dikembalikan ke keadaan tidak aktif, dan yang harus terlihat adalah buzzer berhenti dan servo kembali ke sudut tutup.
> Peralihan itu diulang beberapa kali, karena aktuator yang benar akan berubah setiap kali input berubah dan tetap diam selama input tidak berubah.
> Bila buzzer berbunyi tetapi servo tidak bergerak, atau servo bergerak tanpa ada input yang memicunya, berarti hubungan input dan output belum benar.
> Untuk melihat mengapa perilaku itu bisa muncul, kita periksa kodenya.

### Frame 11 — Membaca Kode Portal Otomatis

Kawasan: Portal Otomatis

Teks di layar:
- Pustaka servo dipanggil agar sudut dapat diatur.
- Pin sensor 15, buzzer 2, servo 18.
- `portalServo.write(0);` memberi posisi awal terdefinisi.
- Saat input HIGH: buzzer nyala, servo 90.
- Blok `else` mematikan buzzer, servo kembali 0.

Yang Anda ucapkan:
> Kode pada Bab 5 materi pertemuan ini memperlihatkan satu pola inti embedded programming, yaitu membaca input, memutuskan kondisi, lalu mengendalikan output.
> Baris paling atas memanggil pustaka servo, lalu pin ditetapkan untuk sensor, buzzer, dan servo, dan sebuah objek servo dibuat agar sudutnya dapat diatur dari program.
> Di dalam setup(), pin sensor disiapkan sebagai input, buzzer sebagai output, servo dihubungkan ke pinnya, lalu servo diatur ke posisi awal 0 derajat supaya sistem punya keadaan yang terdefinisi.
> Di dalam loop(), status sensor dibaca, dan jika statusnya HIGH maka buzzer dinyalakan dan servo dibuka ke 90 derajat, sedangkan jika tidak, buzzer dimatikan dan servo kembali ke 0 derajat, dengan jeda kecil agar pembacaan lebih stabil.
> Perhatikan bahwa satu blok keputusan mengendalikan dua aktuator sekaligus, dan itulah jawaban teknis atas pertanyaan pembuka tadi.
> Relay virtual pun dapat masuk ke pola yang sama, yaitu relay ON ketika sensor aktif dan relay OFF ketika sensor tidak aktif, seperti potongan tambahan pada Bab 5 materi pertemuan ini.
> Bila hasil simulasi Anda belum seperti itu, ada beberapa titik yang perlu diperiksa lebih dahulu.

### Frame 12 — Kesalahan yang Sering Terjadi

Kawasan: Portal Otomatis

Teks di layar:
- Buzzer berbunyi tetapi servo tidak bergerak.
- Servo bergerak tanpa input yang memicunya.
- Blok `else` tidak mengembalikan kondisi aman.
- Pin pada rangkaian berbeda dari pin program.
- Telusuri dari sisi input, bukan aktuator.

Yang Anda ucapkan:
> Materi pertemuan ini menyebut dua gejala yang paling sering muncul, yaitu buzzer berbunyi tetapi servo tidak bergerak, dan servo bergerak tanpa ada input yang memicunya.
> Keduanya menunjuk pada satu penyebab yang sama, yaitu hubungan input dan output yang belum benar, sehingga logikanya harus diperbaiki lebih dahulu sebelum Anda merapikan tampilan rangkaian.
> Gejala berikutnya adalah blok else yang tidak benar-benar mengembalikan sistem ke kondisi aman, sehingga servo tidak kembali ke sudut tutup atau buzzer terus berbunyi; periksa bagian itu dengan menuliskan ulang blok if-else portal dari ingatan lalu membandingkannya dengan kode pada Bab 5 materi pertemuan ini.
> Gejala ketiga bersifat rangkaian, yaitu pin yang terpasang pada simulasi berbeda dari pin yang tertulis di dalam program, dan hal itu termasuk yang dinilai pada tugas.
> Bila aktuator tidak berubah setiap kali input berubah, bacalah kembali bagian output terkontrol kondisi pada Bab 1 dan alur eksekusi program pada Bab 5 materi pertemuan ini.
> Aturan penelusurannya hanya satu, yaitu mulai dari sisi input dan bukan dari aktuator.
> Setelah itu Anda bisa mengukur sendiri apakah pertemuan ini sudah tuntas.

### Frame 13 — Ringkasan dan Checkpoint CP-1

Kawasan: Penutup

Teks di layar:
- Aktuator menjalankan aksi sebagai keluaran sistem.
- Buzzer berbunyi, servo bersudut, relay menyaklar.
- Keluaran muncul karena kondisi, bukan kebetulan.
- Checkpoint: aktuator merespons, logika berjalan, perbedaan dijelaskan.
- Pertemuan ini sekaligus checkpoint besar CP-1.

Yang Anda ucapkan:
> Ringkasan pertemuan ini dapat dipadatkan menjadi lima butir.
> Aktuator adalah komponen yang menjalankan aksi sebagai keluaran sistem, buzzer menghasilkan bunyi, servo mengatur posisi sudut, relay virtual berfungsi sebagai saklar, output terkontrol kondisi berarti aktuator bekerja berdasarkan keputusan program, logika if-else menjadi inti penghubung input dengan respons, dan pengenalan PWM membantu Anda memahami bahwa sebagian aktuator memerlukan kontrol sinyal yang lebih spesifik.
> Sebagai checkpoint, pertemuan ini dianggap tuntas bila aktuator merespons kondisi dengan benar, logika if-else berjalan sesuai rancangan, dan Anda dapat menjelaskan perbedaan sensor dan aktuator beserta dua contoh masing-masing tanpa melihat materi.
> Cara menguji butir terakhir cukup sederhana, yaitu dengan menyebutkan arah datanya: sensor memasukkan data ke program, sedangkan aktuator menerima perintah dari program.
> Pertemuan ini sekaligus menjadi checkpoint besar pertama, yaitu CP-1, yang memeriksa penguasaan GPIO, hubungan sensor dengan aktuator, dan logika dasar, dengan cakupan diambil dari tiga pertemuan, yaitu Pertemuan 2 tentang struktur program serta input dan output digital, Pertemuan 3 tentang data analog dan pembacaan sensor virtual, dan pertemuan ini.
> Materi sesudah ini dibangun dengan asumsi ketiga butir tadi sudah terlewati, jadi menuntaskan bagian yang belum tercapai sekarang lebih baik daripada menundanya.
> Bagian terakhir yang perlu Anda kerjakan adalah tugas latihan pertemuan ini.

### Frame 14 — Tugas Latihan dan Pokok Penilaian

Kawasan: Penutup

Teks di layar:
- Bangun portal otomatis dengan input, servo, buzzer.
- Kumpulkan kode lengkap dan tangkapan layar rangkaian.
- Catat sudut tutup dan buka beserta alasannya.
- Ketepatan logika 30 persen, urutan perilaku 25 persen.
- Kelengkapan rangkaian 25 persen, catatan 20 persen.

Yang Anda ucapkan:
> Tugas pertemuan ini adalah membangun satu proyek simulasi yang memuat minimal satu sumber input berupa tombol atau sensor virtual, satu servo, dan satu buzzer, dengan logika if-else sehingga aktuator hanya bekerja ketika kondisi input terpenuhi.
> Relay virtual boleh Anda tambahkan sebagai keluaran ketiga, tetapi penambahan itu bersifat pilihan.
> Yang dikumpulkan ada tiga, yaitu kode program lengkap dalam bentuk teks agar dapat dijalankan ulang apa adanya, tangkapan layar rangkaian pada simulator yang memperlihatkan sambungan pin secara terbaca, serta catatan sudut servo untuk posisi tutup dan posisi buka beserta alasan memilih kedua angka itu.
> Sudutnya tidak wajib 0 dan 90 derajat seperti contoh, dan nilai lain diterima selama Anda dapat menjelaskan mengapa nilai itu masuk akal untuk sebuah portal, misalnya karena sudut buka yang terlalu kecil membuat portal tampak belum terbuka penuh.
> Bobot penilaiannya adalah ketepatan logika 30 persen, urutan perilaku 25 persen, kelengkapan rangkaian 25 persen, serta catatan dan penjelasan 20 persen, dan tugas latihan mingguan seperti ini berbobot 20 persen dari nilai akhir.
> Perlu Anda ingat bahwa program yang berjalan tetapi tidak dapat Anda jelaskan bernilai lebih rendah daripada program sederhana yang Anda pahami sepenuhnya.
> Dengan itu pertanyaan pembuka tadi terjawab lengkap: satu input dapat memicu dua aksi sekaligus karena satu blok keputusan menerjemahkan kondisi yang terbaca menjadi perintah bagi servo dan buzzer pada saat yang sama.
