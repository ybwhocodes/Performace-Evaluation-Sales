# Performace-Evaluation-Sales

Aplikasi web sederhana untuk mengevaluasi performa sales berbasis metode **Rolling 3 Bulan**. Dibangun sebagai satu file HTML statis (tanpa build step) dengan tema *Astryx Design System* (Tailwind CDN).

## Fitur

- **Tab Perhitungan** — input closing 3 bulan + closing canvassing, langsung menghasilkan status akhir (Lanjut / Toleransi / Terminasi), ringkasan metrik, dan RTL.
- **Tab Metode & Rumus** — penjelasan lengkap quartil, zona, trend score, consistency gate, canvassing, beserta matriks keputusan dan contoh.
- **Dark mode** — toggle otomatis mengikuti preferensi sistem, tersimpan di `localStorage`.
- **Cara Membaca Hasil** — penjelasan tiap indikator agar hasil mudah ditafsirkan.

## Cara Pakai

Buka `index.html` langsung di peramban (double-click). Tidak perlu server.

## Metode Singkat

Status akhir dihitung dari kombinasi:

```
Status = Rolling 3 Bulan + Quartil + Consistency Gate + Trend Score + Closing Canvassing
```

| Parameter | Nilai |
|---|---:|
| Threshold closing bulanan | 30 |
| Kuota penuh 3 bulan | 90 |
| Lanjut Produktif | ≥120 + semua Q1 |
| Lanjut Konsisten | ≥90 + semua Q1 |
| Lanjut Kumulatif | ≥90 + minimal Q2 |
| Toleransi Kuota Kumulatif | ≥75 |
| Zona Recovery / Toleransi | ≥60 |
| Zona Kritis | <60 |
| Minimum canvassing | 70% |
| Bobot trend (B1 / B2 / B3) | 10% / 20% / 70% |

Penjelasan lengkap dan contoh perhitungan ada di **[Sales Evaluation Guide.md](Sales%20Evaluation%20Guide.md)**.

## Struktur

```
index.html                 # Aplikasi utama
Sales Evaluation Guide.md  # Dokumentasi metode & rumus
```

## Catatan

Aplikasi ini adalah *decision support system*, bukan pengganti review manajerial dan HR.
