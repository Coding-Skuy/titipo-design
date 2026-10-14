# ADR-0001 — Fondasi teknis titipo-design

Status: Diterima | Tanggal: 2026-10-14

## Konteks

titipo-design adalah bagian divisi TitipO (Epic E2 #3, milestone v1.0.0). Spesifikasi v1.0.0 beku sejak 2026-10-07 di [TitipO-TownHall](https://github.com/Coding-Skuy/TitipO-TownHall/blob/main/platform/versions/v1.0.0/FSD/30-kontrak.md). Repo ini memerlukan fondasi teknis yang tetap agar pengembangan oleh AI dan manusia konsisten.

## Keputusan

Keputusan kunci CEO yang berlaku untuk repo ini:

1. **Desain tanpa kode produk.** Repo hanya berisi token, flow, layar, dan tautan Figma.
2. **Layar terkunci v1.0.0.** 5 layar rumah tangga dan 3 layar vendor di mobile, 5 halaman admin di web; penambahan layar butuh versi baru di TownHall.
3. **Aksesibilitas dan harga jujur.** Kontras 4,5:1, tombol 48 dp, vendor konfirmasi dalam 2 ketukan, rincian Total item + Ongkir Rp5.000 selalu tampil, jendela serah 06.00-08.00 selalu tampil.

Keputusan lintas repo: satu DB logis per service, JWT beraudien divisi, kunci idempoten ULID klien pada semua POST, uang integer rupiah, waktu timestamptz UTC.

## Konsekuensi

Perubahan token memicu PR di app-kmp dan web. Sengketa layar diputus pemilik matriks TownHall, bukan fork token lokal.
ADR ini immutable; perubahan keputusan ditulis sebagai ADR baru yang menggantikan.
