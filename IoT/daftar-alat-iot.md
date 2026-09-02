# Daftar Persiapan Alat — Mata Kuliah Internet of Things

Disusun dari materi Pertemuan 1 sampai 16 (`materi_pertemuan1_iot.html` … `materi_pertemuan16_uas.html`).

## Ringkasan Cepat

| Pertanyaan | Jawaban |
|---|---|
| Pertemuan 1–14 butuh hardware? | **Tidak.** Semua di simulator Wokwi (browser) |
| Pertemuan 15 butuh hardware? | Board fisik **bersifat pilihan**; ada jalur pengganti berupa tugas tulis |
| Pertemuan 16 (UAS) butuh hardware? | Tidak. Yang dinilai sistem berjalan + laporan + demo |
| Yang benar-benar wajib | Laptop/PC, internet, beberapa software gratis |
| Kalau tetap ingin beli | Paket dasar sekitar Rp 133–225k, paket mini project sekitar Rp 220–380k |

Hardware di kuliah ini sifatnya penguat pemahaman, bukan syarat kelulusan. Pertemuan 15 menyatakan: "Papan ESP32 fisik beserta satu sensor, satu LED, dan resistor sekitar 220 ohm bersifat pilihan."

---

## A. Wajib Ada (Gratis — Tidak Perlu Beli)

Ini yang benar-benar menentukan Anda bisa mengikuti kuliah atau tidak.

| Kebutuhan | Dipakai sejak | Catatan |
|---|---|---|
| Laptop/PC + browser modern | Pertemuan 1 | HP atau tablet **tidak cukup**, karena Node-RED harus terpasang di komputer |
| Koneksi internet | Pertemuan 1 | Simulator, broker MQTT, dan layanan cloud semuanya online |
| Akun Wokwi (gratis) | Pertemuan 2 | Tanpa akun simulasi tetap jalan, tapi hasil kerja tidak tersimpan antar pertemuan |
| Aplikasi MQTTX (gratis) | Pertemuan 7 | Aplikasi desktop, berperan sebagai subscriber |
| Node.js + Node-RED + paket dashboard | Pertemuan 10 | Software baru pertama di kuliah ini, sisihkan waktu memasangnya |
| Akun ThingSpeak (gratis) | Pertemuan 11 | Perlu channel, nama field, dan write key |
| Arduino IDE + board support ESP32 | Pertemuan 15 | Hanya untuk mengunggah ke board fisik |
| Ruang penyimpanan untuk arsip proyek | Pertemuan 8 | UTS menuntut arsip proyek Pertemuan 1–7 |

Broker MQTT memakai `broker.hivemq.com` port `1883` yang publik, jadi **tidak perlu akun dan tidak perlu server sendiri**.

---

## B. Paket Dasar Hardware

Beli ini kalau Anda ingin mengerjakan Pertemuan 15 secara fisik. Isinya persis kebutuhan Bab 7 Pertemuan 15: satu sensor analog di GPIO 34, satu LED lewat resistor di GPIO 23.

| No | Komponen | Jumlah | Kisaran harga | Untuk apa |
|---|---|---|---|---|
| 1 | ESP32 DevKit V1 (30 pin, chip USB CP2102 atau CH340) | 1 | Rp 50–80k | Board utama seluruh kuliah |
| 2 | Kabel USB **data** sesuai port board (micro-USB atau USB-C) | 1 | Rp 15–25k | Unggah program + Serial Monitor |
| 3 | Breadboard 400 titik | 1 | Rp 15–25k | Tempat merakit tanpa solder |
| 4 | Kabel jumper male-male (isi 40) | 1 set | Rp 12–20k | Sambungan antar titik breadboard |
| 5 | Kabel jumper male-female (isi 40) | 1 set | Rp 12–20k | Menyambung modul sensor ke breadboard |
| 6 | Potensiometer 10 kΩ | 2 | Rp 5–10k | Sumber nilai analog, dipakai di P3, P8, P9, P15 |
| 7 | Modul LDR (dengan keluaran AO) | 1 | Rp 8–15k | Sensor cahaya untuk kasus lampu pintar |
| 8 | LED 5mm (merah, kuning, hijau) | 5–10 | Rp 5–10k | Aktuator penanda status |
| 9 | Resistor 220 Ω | 10 | Rp 3–5k | Pembatas arus LED, **wajib** di rangkaian nyata |
| 10 | Resistor 10 kΩ | 10 | Rp 3–5k | Pull-up tombol seperti pada P4 Praktik 1 |
| 11 | Push button / tact switch | 4 | Rp 5–10k | Input digital, dipakai P2, P4, P5 |

**Total paket dasar: sekitar Rp 133–225k.**

Poin 3, 4, dan 5 tidak disebut di materi karena semua praktik memang di simulator, tapi secara fisik Anda tidak bisa merakit apa pun tanpa keduanya.

---

## C. Tambahan Sesuai Kasus Proyek Anda

Materi memberi pilihan kasus, dan komponennya berbeda-beda. Beli hanya yang sesuai kasus yang Anda ambil.

### C.1 Empat kasus UTS (Pertemuan 8)

| Kasus | Input | Aktuator | Tambahan yang perlu dibeli |
|---|---|---|---|
| Alarm suhu | Potensiometer sebagai wakil suhu | LED merah + buzzer | Buzzer aktif 5V — Rp 3–8k |
| Lampu pintar | Modul LDR | LED sebagai wakil lampu | Sudah ada di paket dasar |
| Notifikasi kelembapan | Potensiometer sebagai wakil kelembapan tanah | LED kuning | Sudah ada di paket dasar |
| Penghitung kendaraan parkir | Push button | LED penanda penuh | Sudah ada di paket dasar |

Kasus alarm suhu adalah yang paling sedikit komponennya dan dipakai sebagai contoh utama di materi.

### C.2 Mini project acuan (Pertemuan 13–14)

Contoh rancangan di materi: **Pemantau dan Pengendali Suhu Ruang Baca** — suhu dibaca sensor, kipas menyala lewat relay saat suhu melewati ambang, data dikirim ke broker, dashboard menampilkan sekaligus dapat memerintah balik.

| Komponen | Jumlah | Kisaran harga | Catatan |
|---|---|---|---|
| Sensor DHT22 (AM2302) | 1 | Rp 35–55k | Satu komponen untuk suhu **dan** kelembapan |
| Modul relay 1 channel | 1 | Rp 12–20k | Pilih yang **trigger 3,3V compatible** |
| Kipas DC 5V atau 12V kecil | 1 | Rp 15–35k | Beban yang dikendalikan relay |
| Adaptor / catu daya terpisah untuk kipas | 1 | Rp 25–45k | Lihat peringatan di bagian E |

**Tambahan mini project: sekitar Rp 87–155k.** Alternatif hemat: DHT11 (~Rp 15k) bila ketelitian bukan hal utama, atau DS18B20 (~Rp 20k) bila hanya butuh suhu. Bila belum mau membeli kipas, LED boleh berperan sebagai wakil kipas seperti disebut tabel pemilihan komponen Pertemuan 13.

### C.3 Aktuator Pertemuan 4 (bila ingin dicoba fisik)

| Komponen | Jumlah | Kisaran harga | Catatan |
|---|---|---|---|
| Servo SG90 | 1 | Rp 18–30k | Kaki PWM ke GPIO, V+ ke 5V, GND ke GND |
| Buzzer aktif | 1 | Rp 3–8k | Kaki positif ke GPIO, negatif ke GND |

### C.4 Variasi kasus lain yang disebut materi

| Kalau kasus Anda | Sensor yang perlu dibeli | Kisaran harga |
|---|---|---|
| Pemantau tanaman / kelembapan tanah | Modul soil moisture (versi kapasitif lebih tahan lama) | Rp 15–35k |
| Pemantau jarak atau tempat parkir | HC-SR04 | Rp 15–25k |
| Deteksi gerak ruangan | PIR HC-SR501 | Rp 20–30k |
| Monitoring energi | Sensor arus (PZEM-004T atau ACS712) | Rp 60–150k |

Sensor di tabel ini **tidak dipakai di materi mana pun**, jadi hanya beli bila kasus mini project pilihan Anda memang menuntutnya. Nasihat Pertemuan 13 tegas soal ini: "Jangan memilih komponen yang belum pernah Anda coba untuk bagian yang paling menentukan."

---

## D. Alat Bantu (Tidak Wajib, Berguna Kalau Serius Lanjut)

Tidak satu pun disebut di materi. Beli hanya bila Anda berencana meneruskan elektronika setelah kuliah ini selesai.

| Alat | Kisaran harga | Kegunaan |
|---|---|---|
| Multimeter digital | Rp 60–150k | Memastikan tegangan 3,3V, mencari sambungan putus |
| Kotak komponen bersekat | Rp 20–40k | Komponen kecil sangat mudah hilang |
| Solder + timah + penyedot timah | Rp 80–150k | Hanya bila ingin membuat rangkaian permanen |
| Powerbank | Rp 100k+ | Menjalankan board tanpa laptop saat demo |
| Modul step-down / regulator | Rp 10–20k | Bila memakai catu daya 12V untuk beban |
| Modul logic level converter | Rp 10–20k | Menurunkan sinyal modul 5V ke 3,3V |

---

## E. Peringatan Penting Sebelum Membeli

Lima hal ini diambil langsung dari Pertemuan 15 dan menjadi penyebab kerusakan paling sering.

1. **Pastikan modul bekerja di 3,3 volt.** ESP32 bekerja pada tegangan logika 3,3V dan itu batas, bukan anjuran. Memberi 5V ke pin data bisa merusak papan secara diam-diam — papan masih hidup tapi pembacaannya tidak lagi benar. Adanya pin bertanda 5V atau VIN di papan adalah jalur masuk daya, **bukan izin memberi 5V ke pin data**. Modul 5V perlu diturunkan lewat pembagi tegangan dua resistor atau level converter.

2. **Kabel USB harus kabel data.** Kabel yang hanya mengalirkan daya membuat port board tidak pernah muncul di daftar port komputer. Ini gejala kegagalan unggah nomor satu.

3. **Beban besar butuh catu daya sendiri.** Servo, motor, relay, dan deretan lampu menarik arus besar saat mulai bergerak, tegangan jalur papan turun sesaat, dan papan reset di tengah program. Gejalanya khas: pesan pembuka Serial Monitor tercetak berulang. Bila memakai catu daya terpisah, **ground catu daya beban wajib disambung ke ground papan**, dan jalur data tetap dari pin papan 3,3V.

4. **LED tidak boleh langsung dari pin ke ground.** Resistor sekitar 220 Ω harus dipasang seri. Di simulator tidak ada yang terbakar, di rangkaian nyata LED dan pin bisa rusak.

5. **Cari gambar pinout untuk papan yang benar-benar ada di tangan Anda.** Modul ESP32 dijual dalam banyak varian dengan tata letak berbeda. Pin yang perlu dihindari: GPIO 34–39 hanya bisa jadi input, GPIO 6–11 terhubung ke memori program, GPIO 0/2/12/15 menentukan mode boot, dan kelompok analog kedua berhenti bekerja saat Wi-Fi aktif. Untuk output aman: GPIO 4, 5, 13, 16–19, 21–23. Untuk analog saat Wi-Fi hidup: GPIO 32–39.

Satu kebiasaan yang menyelamatkan komponen: **cabut kabel USB dulu sebelum memasang atau mengubah rangkaian.** Memasang rangkaian pada papan yang sedang hidup adalah cara termudah merusak komponen.

---

## F. Kapan Sebaiknya Membeli

| Waktu | Yang dilakukan |
|---|---|
| Sebelum Pertemuan 1 | Tidak beli apa pun. Siapkan laptop dan internet saja |
| Sebelum Pertemuan 7 | Pasang MQTTX |
| Sebelum Pertemuan 10 | Pasang Node.js + Node-RED, ini yang paling menyita waktu |
| **Setelah Pertemuan 13** | **Beli paket dasar + tambahan sesuai tabel pemilihan komponen di dokumen rancangan Anda** |
| Sebelum Pertemuan 15 | Pasang Arduino IDE + board support ESP32, uji unggah program kosong |

Alasan menunggu sampai Pertemuan 13: dokumen rancangan mini project di pertemuan itu memuat tabel pemilihan komponen yang menentukan sensor mana yang benar-benar Anda butuhkan. Membeli lebih awal berisiko salah komponen, dan Pertemuan 13 sendiri mengingatkan untuk menyiapkan alternatif setiap komponen "ketika komponen pilihan ternyata tidak tersedia".

---

## G. Ringkasan Biaya

| Paket | Isi | Perkiraan |
|---|---|---|
| **Tanpa beli** | Laptop + internet + software gratis. Cukup untuk lulus seluruh 16 pertemuan | Rp 0 |
| **Dasar** | Bagian B — cukup untuk Pertemuan 15 secara fisik | Rp 133–225k |
| **Mini project** | Bagian B + C.2 (DHT22, relay, kipas, adaptor) | Rp 220–380k |
| **Lengkap** | Ditambah C.3 dan multimeter | Rp 300–570k |

Semua harga adalah **kisaran kasar pasar lokal dan wajib dicek ulang** sebelum membeli. Harga komponen bergerak dan varian board sangat banyak.

---

## Catatan Sumber

Setiap kebutuhan di dokumen ini dapat dilacak ke bagian "Yang perlu siap" pada masing-masing materi:

- `materi_pertemuan2_iot.html` sampai `materi_pertemuan7_mqtt.html` — "tidak ada perangkat fisik yang perlu disiapkan"
- `materi_pertemuan7_mqtt.html` Bab 5.4 — MQTTX dan broker `broker.hivemq.com:1883`
- `materi_pertemuan10_nodered.html` — Node-RED beserta paket dasbor
- `materi_pertemuan11_data.html` — ThingSpeak, akun gratis, channel dan write key
- `materi_pertemuan13_perancangan.html` Bab 6 — tabel pemilihan komponen dan alternatifnya
- `materi_pertemuan14_miniproject.html` Bab 7 — DHT22 dan modul relay, "tidak ada perangkat keras yang dibutuhkan"
- `materi_pertemuan15_hardware.html` Bab 3–7 — kabel data, driver USB, batas pin, batas listrik, catu daya terpisah
- `materi_pertemuan16_uas.html` — "Tidak ada perangkat lunak baru yang perlu dipasang"
