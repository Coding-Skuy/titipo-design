# 60-BLAST-RADIUS — titipo-design

> Versi: v1.0.0 | Status: disetujui | Menggantikan: -
> Acuan: [TitipO-TownHall platform/versions/v1.0.0](https://github.com/Coding-Skuy/TitipO-TownHall/tree/main/platform/versions/v1.0.0) (BRD/PRD/FRD/FSD/SRS beku 2026-10-07).

## Konsumen

- Konsumen langsung: `titipo-app-kmp` (kartu, stepper kg, banner luring) dan `titipo-web` (kartu vendor, tabel pesanan, status sinkron).
- Hulu: TownHall TitipO (aturan 20.00, 06.00–08.00, fee, repeat).
- Hilir: tidak ada runtime; hanya aset dan spesifikasi.

## Failure

- Token berubah tanpa koordinasi: tampilan mobile dan web tidak konsisten; tahan rilis dan samakan versi token.
- Alur layar berubah diam-diam: vendor bingung 2 ketukan; kembalikan ke 5 rumah dan 3 vendor v1.0.0.
- Aset berat masuk repo: unduh mobile di atas 35 MB; kompres ulang dan tolak PR.
- Teks harga tidak jujur: ongkir muncul belakangan; tolak desain dan kembalikan rincian total item tambah ongkir.

## Rollback

- Rollback berarti kembalikan paket token ke versi sebelumnya; tidak ada migrasi data.
- Layar yang sudah rilis mengikuti token lama sampai dua konsumen selesai sinkron.
- Tidak ada rollback secret karena repo desain tidak menyimpan kunci.

## Batasan

- Dampak maksimal visual dan alur; tidak menyentuh DB titipo, API, fee, atau auth.
- Sengketa layar diputus pemilik matriks TownHall dalam 1x24 jam, bukan fork token lokal.

## Boleh disentuh

Token, flow, layar, link Figma di README.

## Dilarang

Kode produk, layar di luar 5 rumah + 3 vendor v1.0.0, mengubah API/fee/auth, menyimpan kunci.

## Kontrak yang dikonsumsi

PRD/FSD TitipO-TownHall v1.0.0.

## Kontrak yang diproduksi

Paket token dan spesifikasi layar untuk `titipo-app-kmp` dan `titipo-web`.

Sumber batas: [townhall-roadmap.md §2](https://github.com/Coding-Skuy/ChefGenie-TownHall/blob/main/townhall-roadmap.md) baris TitipO (pesan <=20.00, serah 06.00-08.00; sinyal `pedaree.stok.v1` anjuran saja; fee vendor 12%) dan [KONTEKS-LINTAS-DIVISI.md](https://github.com/Coding-Skuy/ChefGenie-TownHall/blob/main/KONTEKS-LINTAS-DIVISI.md) §3, §8, §9.
