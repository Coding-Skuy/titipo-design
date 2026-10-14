# 40-TECHSTACK — titipo-design

> Versi: v1.0.0 | Status: disetujui | Menggantikan: -
> Acuan: [TitipO-TownHall platform/versions/v1.0.0](https://github.com/Coding-Skuy/TitipO-TownHall/tree/main/platform/versions/v1.0.0) (BRD/PRD/FRD/FSD/SRS beku 2026-10-07).

## 1. Target stack

| Lapisan | Teknologi + versi | Keterangan |
|---|---|---|
| Token | Figma tokens + gaya Compose bersama | Sumber token visual |
| Mobile render | Kotlin 2.2.20 + Compose 1.8.2 + Navigation3 1.0.0 | 5 layar rumah + 3 layar vendor |
| Web render | Bun 1.4.x + Svelte 5 + Kit 2 + TS 5.9.x | 5 halaman admin |
| Aset | SVG + foto contoh terkompres | Tanpa aset rahasia |
| Kontras | Minimal 4,5:1 tombol 48 dp | Aturan 2 ketukan vendor |

Aturan yang dijaga desain: harga jujur total item tambah ongkir Rp5.000, banner luring kuning, timer 15:00 bayar dan 30 menit konfirmasi, jendela serah 06.00–08.00 selalu tampil.

## 2. Konfigurasi kunci

- Token milik repo ini; implementasi milik app-kmp dan web; perubahan token wajib PR ke dua repo konsumen.
- Alur file: tokens, flows, screens; tanpa duplikat layar admin di mobile dan tanpa checkout di web.
- Contoh teks mengikat: pindai QRIS Rp52.000 dan push konfirmasi sebelum menit batas.

## Batasan

- Hanya token, alur, dan layar; bukan pemilik API, fee 12 persen, atau repeat 40 persen.
- Dilarang menambah layar di luar 5 rumah dan 3 vendor v1.0.0 tanpa versi baru TownHall.
