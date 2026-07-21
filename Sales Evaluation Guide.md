# Panduan Lengkap Evaluasi Performa Sales  
## Metode Rolling 3 Bulan, Quartil, Consistency Gate, Trend Score, Closing Canvassing, dan RTL

---

# 1. Ringkasan Eksekutif

Dokumen ini menjelaskan metode evaluasi performa sales dengan tiga status akhir:

1. **Lanjut**
2. **Toleransi**
3. **Terminasi**

Metode tidak hanya melihat total closing, karena total yang sama dapat berasal dari pola performa yang berbeda.

Contoh:

\[
52,\ 10,\ 10
\]

dan:

\[
10,\ 10,\ 30
\]

Kedua pola tersebut memiliki arti manajerial yang berbeda:

- `52, 10, 10` menunjukkan performa awal tinggi tetapi menurun pada dua bulan terbaru.
- `10, 10, 30` menunjukkan total kumulatif lebih rendah, tetapi ada pemulihan pada bulan terbaru.

Oleh karena itu, aplikasi menggunakan kombinasi:

\[
Status\ Akhir =
Rolling\ 3\ Bulan
+
Quartil
+
Consistency\ Gate
+
Trend\ Score
+
Closing\ Canvassing
\]

Keputusan **Toleransi** selalu disertai RTL atau Rencana Tindak Lanjut untuk bulan berikutnya.

---

# 2. Dasar Pemikiran Metode

## 2.1 Mengapa Tidak Hanya Menggunakan Closing Bulan Terakhir?

Bulan terakhir memang penting karena paling dekat dengan kondisi saat ini, tetapi satu bulan saja dapat dipengaruhi oleh:

- Penutupan pipeline dari bulan sebelumnya
- Musiman
- Perubahan wilayah
- Perubahan kualitas lead
- Ketersediaan produk
- Promosi sementara
- Satu transaksi besar
- Pembatalan atau koreksi closing

Karena itu, bulan terakhir digunakan sebagai indikator kuat, tetapi tidak berdiri sendiri.

## 2.2 Mengapa Menggunakan Rolling 3 Bulan?

Rolling 3 bulan dipilih untuk menyeimbangkan:

- Stabilitas data
- Kecepatan mendeteksi perubahan
- Kesempatan memperbaiki performa
- Kemudahan evaluasi bulanan

Penelitian mengenai frekuensi kuota menunjukkan bahwa struktur periode kuota dapat memengaruhi usaha dan perilaku salesperson. Evaluasi yang terlalu jarang dapat terlambat menangkap penurunan, sementara evaluasi yang terlalu pendek dapat terlalu sensitif terhadap variasi sementara.[1][2]

Rolling 3 bulan bukan satu-satunya periode yang benar. Periode ini adalah pilihan kebijakan yang sesuai untuk organisasi yang ingin mengevaluasi secara bulanan tetapi tetap melihat pola beberapa bulan.

## 2.3 Mengapa Menggunakan Consistency Gate?

Total kumulatif dapat menyembunyikan performa terbaru yang buruk.

Contoh:

\[
52+10+10=72
\]

Total 72 sudah melewati minimum 63. Namun, dua bulan terakhir hanya menghasilkan 10 closing.

Jika perusahaan hanya menggunakan total, sales akan terlihat aman meskipun performa terbarunya menurun tajam.

Consistency Gate digunakan untuk mencegah satu bulan yang sangat tinggi menutupi dua atau tiga bulan yang lemah.

## 2.4 Mengapa Menggunakan Trend Score?

Trend Score memberikan bobot lebih besar pada periode terbaru.

Rumus:

\[
Trend\ Score =
(B1\times10\%)
+
(B2\times20\%)
+
(B3\times70\%)
\]

Tujuannya bukan menggantikan total closing, melainkan membaca arah performa.

Penting:

> Bobot 10%-20%-70% adalah desain kebijakan internal, bukan angka universal yang diwajibkan oleh satu penelitian tertentu.

Bobot ini dipilih karena perusahaan ingin sangat menekankan performa terbaru. Bobot tersebut perlu diuji kembali dengan data historis perusahaan.

## 2.5 Mengapa Closing Canvassing Digunakan?

Closing adalah hasil akhir atau lagging indicator.

Closing dari canvassing membantu menjawab:

- Apakah sales menghasilkan closing dari aktivitas pencarian pelanggan?
- Apakah sales terlalu bergantung pada inbound lead?
- Apakah aktivitas prospecting menghasilkan konversi?
- Apakah sales tetap membangun pipeline?

Namun, persentase canvassing tinggi tidak otomatis berarti performa baik.

Contoh:

\[
8,\ 8,\ 8
\]

Total:

\[
24
\]

Closing canvassing:

\[
20
\]

Persentase canvassing:

\[
\frac{20}{24}\times100\%=83{,}33\%
\]

Walaupun 83,33% berasal dari canvassing, total closing masih sangat rendah. Sales tetap berada dalam kondisi kritis.

---

# 3. Diketahui

## 3.1 Parameter Utama

| Parameter | Nilai |
|---|---:|
| Threshold closing bulanan | 30 |
| Periode evaluasi | 3 bulan |
| Kuota penuh 3 bulan | 90 |
| Minimum kuota 3 bulan | 63 |
| Minimum kuota dalam persen | 70% |
| Minimum kontribusi closing canvassing | 70% |
| Target recovery ringan | 24 |
| Bobot Bulan 1 | 10% |
| Bobot Bulan 2 | 20% |
| Bobot Bulan 3 | 70% |

## 3.2 Perhitungan Kuota

Threshold bulanan:

\[
30
\]

Kuota penuh 3 bulan:

\[
30\times3=90
\]

Minimum pencapaian 70%:

\[
90\times70\%=63
\]

Target recovery ringan:

\[
30\times80\%=24
\]

---

# 4. Input Aplikasi

Aplikasi menerima empat input:

| Input | Penjelasan |
|---|---|
| Bulan 1 | Total closing bulan pertama |
| Bulan 2 | Total closing bulan kedua |
| Bulan 3 | Total closing bulan ketiga atau bulan terbaru |
| Closing canvassing | Total closing selama 3 bulan yang berasal dari aktivitas canvassing |

## 4.1 Validasi Input

Input dianggap valid jika:

1. Semua closing berupa bilangan bulat.
2. Semua nilai minimal 0.
3. Closing canvassing tidak lebih besar dari total closing.
4. Jika total closing 0, closing canvassing harus 0.

Contoh tidak valid:

\[
B1=10,\ B2=10,\ B3=10
\]

Total:

\[
30
\]

Closing canvassing:

\[
35
\]

Input ditolak karena:

\[
35>30
\]

---

# 5. Persyaratan Quartil

| Quartil | Range Closing | Arti |
|---|---:|---|
| Q1 | ≥30 | On target |
| Q2 | 20–29 | Di bawah target ringan |
| Q3 | 10–19 | Di bawah target berat |
| Q4 | 0–9 | Kritis |

## 5.1 Fungsi Quartil

Quartil digunakan agar pola performa lebih mudah dibaca.

Contoh:

\[
52,\ 10,\ 10
\]

menjadi:

\[
Q1-Q3-Q3
\]

Contoh:

\[
10,\ 10,\ 30
\]

menjadi:

\[
Q3-Q3-Q1
\]

Walaupun kedua pola memiliki dua bulan rendah, posisi bulan Q1 sangat memengaruhi interpretasi.

## 5.2 Evaluasi Dua Bulan pada Q3 dan Q4

Selain membaca 3 bulan penuh, sistem juga perlu memberi perhatian khusus pada **dua bulan terbaru** jika keduanya berada di Q3 atau Q4.

Rumus pembacaan dua bulan terbaru:

\[
B2\ dan\ B3
\]

Jika:

\[
B2<20\ dan\ B3<20
\]

maka dua bulan terbaru masuk area rendah, karena keduanya berada pada Q3 atau Q4.

Contoh:

\[
52,\ 10,\ 10
\]

Quartil:

\[
Q1-Q3-Q3
\]

Walaupun totalnya:

\[
52+10+10=72
\]

sales tidak otomatis aman, karena dua bulan terbaru sama-sama Q3. Artinya performa terbaru sedang lemah dan perlu RTL ketat.

Jika dua bulan terbaru berada di Q4:

\[
B2<10\ dan\ B3<10
\]

maka risikonya lebih tinggi daripada Q3-Q3, karena dua bulan terakhir berada pada kondisi kritis.

Contoh:

\[
35,\ 8,\ 8
\]

Quartil:

\[
Q1-Q4-Q4
\]

Artinya sales pernah tinggi, tetapi dua bulan terbaru kritis. Kondisi ini tidak boleh dibaca sebagai performa aman hanya karena Bulan 1 tinggi.

Ringkasnya:

| Pola Dua Bulan Terbaru | Kondisi | Makna |
|---|---|---|
| Q3-Q3 | B2 10–19 dan B3 10–19 | Performa terbaru rendah, perlu toleransi/RTL ketat |
| Q3-Q4 atau Q4-Q3 | Salah satu bulan Q3 dan satu bulan Q4 | Performa terbaru memburuk atau tidak stabil |
| Q4-Q4 | B2 <10 dan B3 <10 | Dua bulan terbaru kritis, risiko terminasi lebih tinggi |

---

# 6. Rumus Utamajytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjytjyjytjytjyjytjytjytjytjytjytjytjytjytjyjytjytjytjytjytjytjytjytjytjytjytjytjytjytjy

## 6.1 Total Closing 3 Bulan

\[
Total=B1+B2+B3
\]

## 6.2 Persentase Kuota

\[
Kuota\%=
\frac{Total}{90}
\times100\%
\]

## 6.3 Trend Score

\[
Trend\ Score=
(B1\times0{,}10)
+
(B2\times0{,}20)
+
(B3\times0{,}70)
\]

## 6.4 Persentase Closing Canvassing

\[
Canvassing\%=
\frac{Closing\ Canvassing}{Total\ Closing}
\times100\%
\]

Jika:

\[
Total\ Closing=0
\]

maka:

\[
Canvassing\%=0\%
\]

---

# 7. Zona Total Closing 3 Bulan

| Total Closing | Persentase Kuota | Zona |
|---:|---:|---|
| ≥63 | ≥70% | Lulus kuota kumulatif |
| 45–62 | 50%–69,99% | Zona toleransi/recovery |
| <45 | <50% | Zona kritis |

## 7.1 Alasan Batas 45

Nilai 45 sama dengan 50% dari kuota penuh 90:

\[
90\times50\%=45
\]

Batas ini digunakan untuk membedakan antara:

- Performa yang masih mendekati level pemulihan
- Performa yang sudah terlalu jauh dari kuota

Batas 45 adalah rule kebijakan internal dan perlu divalidasi menggunakan data historis.

---

# 8. Trend Score dan Arah Tren

## 8.1 Meningkat Konsisten

\[
B1<B2<B3
\]

Contoh:

\[
10,\ 20,\ 30
\]

## 8.2 Menurun Konsisten

\[
B1>B2>B3
\]

Contoh:

\[
35,\ 25,\ 15
\]

## 8.3 Recovery

Kondisi:

\[
B3\geq30
\]

dan:

\[
B3>B2
\]

## 8.4 Stabil

\[
B1=B2=B3
\]

## 8.5 Fluktuatif

Digunakan jika pola tidak masuk kategori meningkat, menurun, recovery, atau stabil.

## 8.6 Interpretasi Trend Score

| Trend Score | Interpretasi |
|---:|---|
| ≥30 | Performa terbaru kuat |
| 20–29,99 | Ada dasar recovery |
| 15–19,99 | Risiko sedang-tinggi |
| <15 | Risiko tinggi |

Batas interpretasi di atas tidak digunakan sebagai satu-satunya keputusan.

---

# 9. Consistency Gate

Consistency Gate menguji apakah pencapaian kumulatif didukung performa yang cukup konsisten.

## 9.1 Gagal Monthly Target Gate

\[
B1<30,\ B2<30,\ B3<30
\]

Contoh:

\[
25,\ 25,\ 25
\]

Total tinggi, tetapi tidak ada bulan yang benar-benar mencapai target.

## 9.2 Dua Bulan Terakhir di Bawah 20

\[
B2<20
\]

dan:

\[
B3<20
\]

Contoh:

\[
52,\ 10,\ 10
\]

## 9.3 Tiga Bulan di Bawah 20

\[
B1<20,\ B2<20,\ B3<20
\]

## 9.4 Tiga Bulan Q4

\[
B1<10,\ B2<10,\ B3<10
\]

Ini adalah kondisi kritis.

---

# 9A. Kapan Sistem Menggunakan Window 2 Bulan vs 3 Bulan

Evaluasi tidak selalu menggunakan ketiga bulan secara setara. Sistem menggunakan dua jenis window secara bersamaan, masing-masing dengan tujuan yang berbeda.

## 9A.1 Perbedaan Fungsi

| Window | Data yang Dilihat | Tujuan |
|---|---|---|
| 3 bulan (kumulatif) | B1 + B2 + B3 | Mengukur pencapaian total terhadap kuota |
| 3 bulan (konsistensi) | Pola B1, B2, B3 | Mendeteksi pola rendah yang berulang di seluruh periode |
| 2 bulan terbaru | B2 dan B3 | Mendeteksi penurunan performa terbaru yang tersembunyi oleh B1 |

Keduanya dijalankan bersama pada setiap evaluasi. Sistem tidak memilih salah satu; hasil dari keduanya digabungkan untuk menentukan status akhir.

## 9A.2 Kapan Window 3 Bulan Digunakan

Window 3 bulan digunakan untuk:

**a. Menghitung total kumulatif dan zona**

\[
Total = B1 + B2 + B3
\]

Zona ditentukan dari total ini:
- ≥ 63 → Lulus kuota kumulatif
- 45–62 → Zona toleransi/recovery
- < 45 → Zona kritis

**b. Mendeteksi pola konsisten selama 3 bulan**

Sistem memeriksa apakah pola rendah terjadi di seluruh periode:

- Tiga bulan Q4: B1 < 10 dan B2 < 10 dan B3 < 10
- Tiga bulan di bawah 20: B1 < 20 dan B2 < 20 dan B3 < 20
- Tidak ada bulan mencapai 30: B1 < 30 dan B2 < 30 dan B3 < 30

Contoh yang memicu window 3 bulan:

\[
15,\ 15,\ 15
\]

Semua bulan Q3. Sistem membaca ini sebagai pola rendah berkepanjangan, bukan penurunan mendadak.

## 9A.3 Kapan Window 2 Bulan Terbaru Digunakan

Window 2 bulan terbaru (B2 dan B3) digunakan secara khusus untuk **mendeteksi penurunan performa terbaru** yang tidak terdeteksi oleh total kumulatif.

Kondisi yang memicu pemeriksaan 2 bulan terbaru:

\[
B2 < 20 \text{ dan } B3 < 20
\]

Ini berarti dua bulan terbaru berada di Q3 atau Q4, terlepas dari berapa nilai B1.

Contoh paling jelas:

\[
52,\ 10,\ 10
\]

- Total: 72 → lulus kuota kumulatif
- Namun B2 = 10 dan B3 = 10, keduanya < 20
- Window 2 bulan terpicu → status tidak otomatis Lanjut
- Hasil: Toleransi dengan RTL wajib 30

Jika window 2 bulan tidak ada, sales dengan pola `52, 10, 10` bisa dianggap aman hanya karena totalnya tinggi.

## 9A.4 Mengapa Dua Window Dijalankan Bersama

Satu window tidak cukup untuk mendeteksi semua masalah.

**Jika hanya menggunakan 3 bulan kumulatif:**

Pola `52, 10, 10` total 72, terlihat aman. Penurunan 2 bulan terbaru tidak terdeteksi.

**Jika hanya menggunakan 2 bulan terbaru:**

Pola `10, 10, 30` dua bulan terakhirnya 10 dan 30. Window 2 bulan menunjukkan B2 = 10 < 20, tetapi B3 = 30 ≥ 20 sehingga kondisi B2 < 20 dan B3 < 20 tidak terpenuhi. Jika hanya melihat B2 dan B3 tanpa total, evaluasi kurang lengkap karena total hanya 50.

**Dengan dua window berjalan bersama:**

Sistem dapat membedakan:

| Pola | Total | Window 2 Bln | Window 3 Bln | Hasil |
|---|---:|---|---|---|
| 52, 10, 10 | 72 | B2 dan B3 < 20 → Toleransi | Tidak ada pola 3 bln buruk | Toleransi |
| 10, 10, 30 | 50 | B3 ≥ 20, tidak terpicu | Total < 63 → zona toleransi | Toleransi |
| 25, 25, 25 | 75 | B3 ≥ 20, tidak terpicu | Tidak ada bln ≥ 30 → gate gagal | Toleransi |
| 15, 15, 15 | 45 | B3 ≥ 20, tidak terpicu | Semua < 20 → pola 3 bln buruk | Toleransi / Terminasi |
| 8, 8, 8 | 24 | B2 dan B3 < 10 | Semua < 10 → Q4 tiga bln | Terminasi |

## 9A.5 Ringkasan Aturan Pemilihan Window

```
Setiap evaluasi selalu menjalankan:

1. Window 3 bulan kumulatif → menentukan zona (lulus / toleransi / kritis)
2. Window 3 bulan pola → Consistency Gate (Q4 tiga bln, di bawah 20 tiga bln, tidak ada bln ≥ 30)
3. Window 2 bulan terbaru → mendeteksi penurunan tersembunyi (B2 < 20 dan B3 < 20)

Jika window 2 bulan terbaru terpicu (B2 < 20 dan B3 < 20):
→ Status tidak bisa Lanjut, meskipun total ≥ 63

Jika window 3 bulan pola terpicu (misalnya tiga bulan Q4):
→ Status langsung Terminasi

Jika hanya window kumulatif yang terpenuhi:
→ Status bergantung pada zona, bulan terbaru, dan canvassing
```

---

# 10. Tiga Status Keputusan

# 10.1 Status Lanjut

## Persyaratan

Sales masuk status Lanjut jika:

\[
Total\geq63
\]

dan:

\[
\max(B1,B2,B3)\geq30
\]

dan:

\[
Canvassing\%\geq70\%
\]

dan bukan kondisi:

\[
B2<20 \text{ dan } B3<20
\]

## Arti

Sales memenuhi standar kumulatif, pernah mencapai target bulanan, memiliki kontribusi canvassing yang cukup, dan tidak menunjukkan pola penurunan berat terbaru.

## RTL Lanjut

- Pertahankan minimal 30 closing per bulan.
- Pertahankan canvassing minimal 70%.
- Tetap dilakukan monitoring rutin.

---

# 10.2 Status Toleransi

Toleransi diberikan ketika performa belum memenuhi semua syarat Lanjut tetapi belum memenuhi kondisi Terminasi.

Toleransi bukan berarti sales aman.

Toleransi berarti:

- Kesempatan perbaikan
- Durasi terbatas
- Target jelas
- Hasil terukur
- Konsekuensi jelas

Praktik performance management yang efektif menekankan target yang jelas, feedback teratur, dokumentasi, serta tindak lanjut yang berorientasi perbaikan.[3][4][5]

## A. Recovery Ringan

### Persyaratan

\[
45\leq Total\leq62
\]

\[
B3\geq30
\]

\[
B3>B2
\]

\[
Canvassing\%\geq70\%
\]

### RTL

\[
Closing\ bulan\ berikutnya\geq24
\]

\[
Canvassing\%\geq70\%
\]

Durasi evaluasi:

\[
1\ bulan
\]

### Alasan Target 24

\[
24=80\%\times30
\]

Target ini diberikan karena sales sudah mencapai 30 pada bulan terbaru dan menunjukkan recovery.

Target 24 bukan standar permanen. Ini hanya target mempertahankan momentum perbaikan selama satu bulan.

---

## B. Recovery tetapi Canvassing Gagal

### Persyaratan

\[
45\leq Total\leq62
\]

\[
B3\geq30
\]

\[
Canvassing\%<70\%
\]

### RTL

\[
Closing\geq30
\]

\[
Canvassing\%\geq70\%
\]

Sales harus memperbaiki hasil sekaligus sumber closing.

---

## C. Total Lulus tetapi Tidak Pernah Mencapai 30

### Persyaratan

\[
Total\geq63
\]

dan:

\[
B1<30,\ B2<30,\ B3<30
\]

### RTL

\[
Closing\ bulan\ berikutnya\geq30
\]

\[
Canvassing\%\geq70\%
\]

### Alasan

Total kumulatif cukup, tetapi target bulanan tidak pernah tercapai selama tiga bulan.

---

## D. Dua Bulan Terakhir di Bawah 20

### Persyaratan

\[
Total\geq63
\]

\[
B2<20
\]

\[
B3<20
\]

### RTL

\[
Closing\ bulan\ berikutnya\geq30
\]

\[
Canvassing\%\geq70\%
\]

### Alasan

Satu bulan tinggi di masa lalu tidak boleh menutupi dua bulan terbaru yang rendah.

---

## E. Total Lulus tetapi Canvassing di Bawah 70%

### Persyaratan

\[
Total\geq63
\]

\[
Minimal\ satu\ bulan\geq30
\]

\[
Canvassing\%<70\%
\]

### RTL

\[
Closing\geq30
\]

\[
Canvassing\%\geq70\%
\]

---

## F. Stabil Q2 tetapi Total Belum Mencapai 63

Contoh:

\[
20,\ 20,\ 20
\]

Total:

\[
60
\]

### RTL

\[
Closing\ bulan\ berikutnya\geq30
\]

### Alasan

Performa stabil, tetapi stabil pada level di bawah target bukan berarti sudah memenuhi standar.

---

## G. Zona Kritis tetapi Bulan Terakhir Recovery

### Persyaratan

\[
Total<45
\]

\[
B3\geq30
\]

\[
Canvassing\%\geq70\%
\]

### RTL

\[
Closing\geq24
\]

\[
Canvassing\%\geq70\%
\]

Status ini sebaiknya disebut **Recovery Final** karena total tiga bulan masih kritis.

---

# 10.3 Status Terminasi

Status Terminasi pada aplikasi harus dipahami sebagai:

> Rekomendasi untuk memasuki proses review terminasi, bukan terminasi otomatis tanpa pemeriksaan HR.

## A. Tiga Bulan Berturut-turut Q4

\[
B1<10,\ B2<10,\ B3<10
\]

## B. Total di Bawah 45 dan Semua Bulan di Bawah 20

\[
Total<45
\]

dan:

\[
B1<20,\ B2<20,\ B3<20
\]

## C. Total di Bawah 45 dan Bulan Terbaru Masih di Bawah 20

\[
Total<45
\]

dan:

\[
B3<20
\]

## RTL Terminasi

Tidak ada target recovery baru.

Tindakan:

- Review dokumentasi coaching
- Review PIP
- Review kualitas lead
- Review wilayah
- Review kendala produk
- Review ketentuan perjanjian kerja
- Review proses HR
- Review ketentuan hukum

---

# 11. Matriks Keputusan Lengkap

| Total | B3 | Pola | Canvassing | Status | RTL |
|---:|---:|---|---:|---|---|
| ≥63 | ≥30 | Tidak kritis | ≥70% | Lanjut | Pertahankan 30 |
| ≥63 | ≥30 | Tidak kritis | <70% | Toleransi | 30 dan canvassing ≥70% |
| ≥63 | <30 | Tidak pernah mencapai 30 | ≥70% | Toleransi | Wajib 30 |
| ≥63 | <20 | Dua bulan terbaru <20 | Berapa pun | Toleransi | Wajib 30 |
| 45–62 | ≥30 | Recovery | ≥70% | Toleransi | Minimal 24 |
| 45–62 | ≥30 | Recovery | <70% | Toleransi | Wajib 30 |
| 45–62 | 20–29 | Q2 | Berapa pun | Toleransi | Wajib 30 |
| 45–62 | 10–19 | Q3 | Berapa pun | Toleransi | Wajib 30 |
| <45 | ≥30 | Recovery kuat | ≥70% | Toleransi | Recovery final, minimal 24 |
| <45 | 20–29 | Perbaikan | ≥70% | Toleransi | Wajib 30 |
| <45 | <20 | Kritis | Berapa pun | Terminasi | Tidak ada RTL |
| Berapa pun | Berapa pun | Q4 tiga bulan | Berapa pun | Terminasi | Tidak ada RTL |

---

# 12. Contoh Implementasi

## Contoh 1: 52, 10, 10

### Diketahui

\[
B1=52,\ B2=10,\ B3=10
\]

\[
Closing\ Canvassing=54
\]

### Total

\[
52+10+10=72
\]

### Kuota

\[
\frac{72}{90}\times100\%=80\%
\]

### Trend Score

\[
52(10\%)+10(20\%)+10(70\%)
\]

\[
5{,}2+2+7=14{,}2
\]

### Canvassing

\[
\frac{54}{72}\times100\%=75\%
\]

### Quartil

\[
Q1-Q3-Q3
\]

### Status

**Toleransi**

### Alasan

- Total kumulatif lulus
- Dua bulan terakhir di bawah 20
- Tren menurun
- Performa tinggi hanya terjadi di Bulan 1

### RTL

- Minimal 30 closing bulan berikutnya
- Canvassing minimal 70%
- Evaluasi 1 bulan

---

## Contoh 2: 10, 10, 30

### Diketahui

\[
B1=10,\ B2=10,\ B3=30
\]

\[
Closing\ Canvassing=40
\]

### Total

\[
50
\]

### Kuota

\[
55{,}56\%
\]

### Trend Score

\[
24
\]

### Canvassing

\[
80\%
\]

### Quartil

\[
Q3-Q3-Q1
\]

### Status

**Toleransi**

### Alasan

- Total belum mencapai 63
- Bulan terbaru mencapai target
- Tren recovery
- Canvassing memenuhi syarat

### RTL

- Minimal 24 closing
- Canvassing minimal 70%
- Evaluasi 1 bulan

---

## Contoh 3: 25, 25, 25

### Total

\[
75
\]

### Kuota

\[
83{,}33\%
\]

### Trend Score

\[
25
\]

### Canvassing

Jika closing canvassing 57:

\[
\frac{57}{75}\times100\%=76\%
\]

### Quartil

\[
Q2-Q2-Q2
\]

### Status

**Toleransi**

### RTL

- Wajib 30 closing
- Canvassing minimal 70%

### Alasan

Tiga bulan berturut-turut belum mencapai threshold.

---

## Contoh 4: 30, 30, 30

### Total

\[
90
\]

### Kuota

\[
100\%
\]

### Quartil

\[
Q1-Q1-Q1
\]

### Status

**Lanjut**

### RTL

- Pertahankan minimal 30
- Pertahankan canvassing minimal 70%

---

## Contoh 5: 10, 15, 10

### Total

\[
35
\]

### Kuota

\[
38{,}89\%
\]

### Quartil

\[
Q3-Q3-Q3
\]

### Status

**Terminasi**

### Alasan

- Total di bawah 45
- Seluruh bulan di bawah 20
- Tidak ada bukti recovery

---

## Contoh 6: 8, 8, 8

### Total

\[
24
\]

### Quartil

\[
Q4-Q4-Q4
\]

### Status

**Terminasi**

Walaupun canvassing tinggi, hasil akhir tetap kritis.

---

# 13. Alasan Ilmiah dan Manajerial

## 13.1 Kuota dan Frekuensi Evaluasi

Penelitian lapangan mengenai frekuensi kuota menunjukkan bahwa cara perusahaan menyusun interval target dapat memengaruhi usaha dan produktivitas sales.[1]

Implikasi:

- Evaluasi harus cukup sering untuk menangkap perubahan
- Periode evaluasi tidak boleh hanya terlalu panjang
- Performa bulanan dan kumulatif perlu dibaca bersama

## 13.2 Kombinasi Outcome dan Proses

Evidence review tentang people performance menunjukkan bahwa hasil kerja dan proses kerja sama-sama relevan. Perilaku kerja efektif, proses, dan outcome perlu dipertimbangkan bersama.[3]

Implikasi:

- Closing adalah outcome
- Closing canvassing memberi informasi mengenai proses pencarian pelanggan
- Canvassing tidak boleh menggantikan hasil akhir

## 13.3 Feedback dan RTL

Evidence review performance feedback menekankan pentingnya feedback yang spesifik, relevan, tepat waktu, dan diarahkan pada perbaikan.[4]

Implikasi:

RTL harus menyebutkan:

- Target closing
- Target canvassing
- Durasi
- Tenggat evaluasi
- Konsekuensi kegagalan
- Bentuk dukungan atau coaching

## 13.4 Performance Management sebagai Siklus

Panduan CIPD menjelaskan bahwa performance management sebaiknya menjadi siklus berkelanjutan, bukan satu kejadian terpisah.[5]

Implikasi:

- Evaluasi dilakukan rutin
- Target perlu didokumentasikan
- Perbaikan perlu dipantau
- Keputusan tidak hanya berdasarkan satu momen

## 13.5 Keadilan Prosedural

Keputusan performa yang transparan dan konsisten membantu memperkuat persepsi keadilan.

Implikasi praktis:

- Rule yang sama digunakan untuk kasus yang sama
- Sales mengetahui targetnya
- Sales mengetahui alasan status
- Sales mengetahui RTL
- Sales mengetahui konsekuensi

---

# 14. Batasan Metode

## 14.1 Bobot 10%-20%-70% Belum Otomatis Optimal

Bobot tersebut perlu diuji terhadap data historis.

Pengujian yang disarankan:

1. Ambil data minimal 12-24 bulan.
2. Hitung skor seluruh sales.
3. Bandingkan skor dengan performa bulan berikutnya.
4. Bandingkan skor dengan revenue, margin, cancellation, dan retention.
5. Uji alternatif bobot:
   - 20%-30%-50%
   - 15%-25%-60%
   - 10%-20%-70%
6. Pilih bobot dengan kemampuan prediksi terbaik dan paling mudah dijelaskan.

## 14.2 Threshold 30 Harus Relevan

Threshold perlu diperiksa berdasarkan:

- Wilayah
- Potensi pasar
- Produk
- Harga
- Seasonality
- Lead allocation
- Masa kerja sales
- Ketersediaan stok
- Perubahan kebijakan
- Jam kerja efektif

## 14.3 Canvassing 70% adalah Kebijakan Internal

Tidak ada angka universal yang mewajibkan kontribusi canvassing harus 70%.

Angka 70% harus divalidasi dengan data internal:

- Apakah sales dengan canvassing ≥70% memiliki kualitas closing lebih baik?
- Apakah retention pelanggan lebih tinggi?
- Apakah cancellation lebih rendah?
- Apakah revenue lebih stabil?

## 14.4 Closing Harus Closing Valid

Closing sebaiknya dihitung jika:

- Transaksi sah
- Tidak fraud
- Tidak dibatalkan
- Memenuhi syarat pembayaran
- Memenuhi standar kualitas
- Tidak duplikat
- Dapat diaudit

---

# 15. Rekomendasi Penguatan Aplikasi

Aplikasi sebaiknya dikembangkan dengan fitur tambahan:

## 15.1 Riwayat Toleransi

Sistem perlu mencatat:

- Tanggal toleransi
- Alasan
- RTL
- Hasil bulan berikutnya
- Lulus atau gagal

## 15.2 Fitur Gagal RTL

Jika seseorang telah mendapat Toleransi dan gagal memenuhi RTL, sistem dapat mengubah status menjadi review Terminasi.

## 15.3 Penyesuaian Faktor Eksternal

Tambahkan indikator:

- Territory potential
- Jumlah lead
- Lead quality
- Stok
- Hari kerja efektif
- Campaign
- Seasonality

## 15.4 Audit Trail

Simpan:

- Input
- Hasil perhitungan
- Rule yang aktif
- Keputusan
- Nama reviewer
- Tanggal evaluasi
- Catatan coaching

---

# 16. Catatan Hukum Indonesia

PP Nomor 35 Tahun 2021 mengatur antara lain tata cara Pemutusan Hubungan Kerja dan hak terkait PHK.[6][7]

Status Terminasi dari aplikasi tidak boleh dianggap sebagai keputusan hukum otomatis.

Sebelum PHK, perusahaan perlu meninjau:

- Perjanjian kerja
- Peraturan perusahaan
- PKB
- Surat peringatan
- Dokumentasi coaching
- PIP
- Bukti performa
- Prosedur pemberitahuan
- Hak pekerja
- Ketentuan hukum terbaru

Dokumen ini bukan nasihat hukum.

---

# 17. Referensi

[1] Chung, D. J., Kim, B., & Syam, N. B. **The Effects of Quota Frequency on Sales Force Performance: Evidence from a Field Experiment.** Harvard Business School.  
https://www.hbs.edu/ris/download.aspx?name=QuotaFrequency_2020_forthcoming.pdf

[2] Chung, D. J. **A Practical Approach to Sales Compensation: What Do We Know Now? What Should We Know in the Future?** Harvard Business School.  
https://www.hbs.edu/ris/Publication%20Files/ReviewPaper_2020_0210_final_64513e5f-6a65-43b3-aace-37af0c7a1bb1.pdf

[3] CIPD. **People Performance: An Evidence Review.**  
https://www.cipd.org/globalassets/media/knowledge/knowledge-hub/evidence-reviews/people-performance-practice-summary_tcm18-109854.pdf

[4] CIPD. **Performance Feedback: An Evidence Review.**  
https://www.cipd.org/globalassets/media/knowledge/knowledge-hub/evidence-reviews/performance-feedback-evidence-review_tcm18-111378.pdf

[5] CIPD. **Performance Management Factsheet and Evidence-Based Guide.**  
https://www.cipd.org/en/knowledge/factsheets/performance-factsheet/  
https://www.cipd.org/en/knowledge/guides/effective-performance-management/

[6] Republik Indonesia. **Peraturan Pemerintah Nomor 35 Tahun 2021 tentang PKWT, Alih Daya, Waktu Kerja dan Waktu Istirahat, dan Pemutusan Hubungan Kerja.** JDIH BPK.  
https://peraturan.bpk.go.id/Details/161904/pp-no-35-tahun-2021

[7] Kementerian Ketenagakerjaan Republik Indonesia. **Peraturan Pemerintah Nomor 35 Tahun 2021.**  
https://jdih.kemnaker.go.id/peraturan/detail/1723/peraturan-pemerintah-nomor-35-tahun-2021

---

# 18. Kesimpulan Akhir

Metode ini kuat karena tidak hanya mengandalkan satu angka.

Metode menggabungkan:

- Pencapaian kumulatif
- Target bulanan
- Pola quartil
- Konsistensi
- Tren terbaru
- Kontribusi canvassing
- RTL yang terukur

Namun, beberapa angka seperti bobot 10%-20%-70%, batas 45, target recovery 24, dan canvassing 70% adalah desain kebijakan internal. Angka tersebut perlu divalidasi menggunakan data historis perusahaan.

Aplikasi sebaiknya digunakan sebagai decision support system, bukan pengganti review manajerial dan HR.
