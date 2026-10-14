# AGENTS.md — titipo-design

Sistem desain TitipO: token visual, flow, dan layar (5 layar rumah tangga, 3 layar vendor, 5 halaman admin) beserta link Figma; tanpa kode produk.

Divisi TitipO (Epic E2 [#3](https://github.com/Coding-Skuy/ChefGenie-TownHall/issues/3), milestone v1.0.0). Bahasa semua artefak: Indonesia.

## Sumber kebenaran

Dokumen beku v1.0.0 ada di repo [TitipO-TownHall](https://github.com/Coding-Skuy/TitipO-TownHall). Repo ini hanya menjalankan, bukan mendefinisikan, requirement.

| Dokumen | Isi | Link |
|---|---|---|
| `platform/versions/v1.0.0/PRD/10-pengguna.md` | Pengguna dan kebutuhan | [buka](https://github.com/Coding-Skuy/TitipO-TownHall/blob/main/platform/versions/v1.0.0/PRD/10-pengguna.md) |
| `platform/versions/v1.0.0/PRD/20-alur.md` | Alur pesan sampai fee cair | [buka](https://github.com/Coding-Skuy/TitipO-TownHall/blob/main/platform/versions/v1.0.0/PRD/20-alur.md) |
| `platform/versions/v1.0.0/PRD/30-kriteria.md` | Kriteria penerimaan produk | [buka](https://github.com/Coding-Skuy/TitipO-TownHall/blob/main/platform/versions/v1.0.0/PRD/30-kriteria.md) |
| `platform/versions/v1.0.0/FRD/10-fungsional.md` | Kebutuhan fungsional FR-001..FR-304 | [buka](https://github.com/Coding-Skuy/TitipO-TownHall/blob/main/platform/versions/v1.0.0/FRD/10-fungsional.md) |
| `platform/versions/v1.0.0/FSD/10-alur.md` | Alur sistem, tulis lokal dahulu, sinkron | [buka](https://github.com/Coding-Skuy/TitipO-TownHall/blob/main/platform/versions/v1.0.0/FSD/10-alur.md) |
| `produk/10-ux-pesan-titip.md` | UX 5 layar rumah + 3 layar vendor (living) | [buka](https://github.com/Coding-Skuy/TitipO-TownHall/blob/main/produk/10-ux-pesan-titip.md) |
| `vendor/10-sla-vendor.md` | SLA vendor (living) | [buka](https://github.com/Coding-Skuy/TitipO-TownHall/blob/main/vendor/10-sla-vendor.md) |
| `KONTEKS-LINTAS-DIVISI.md` | Konteks lintas-divisi (event registry, ID, satuan, metrik) | [buka](https://github.com/Coding-Skuy/ChefGenie-TownHall/blob/main/KONTEKS-LINTAS-DIVISI.md) |
| `townhall-roadmap.md` | Epic E2 #3, milestone v1.0.0, Definisi Selesai §6 | [buka](https://github.com/Coding-Skuy/ChefGenie-TownHall/blob/main/townhall-roadmap.md) |

Aturan:
- Dilarang menduplikasi requirement di repo kode; cukup tautkan ke versi di atas.
- Requirement berubah = PR di TitipO-TownHall dahulu (versi baru), baru kode mengikuti.
- Bila dokumen divisi bertentangan dengan KONTEKS-LINTAS-DIVISI.md, laporkan; jangan memperbaiki diam-diam.

## Tech stack terkunci

- Token visual (Figma tokens + gaya Compose bersama), flow, dan layar; link Figma terdaftar di README design.
- Render acuan: Compose Multiplatform 1.8.2 (mobile) dan Svelte 5 (web admin); kontras minimal 4,5:1, target sentuh 48 dp.
- Tidak ada kode produk. Perubahan flow besar = PRD/FSD versi baru di TitipO-TownHall.
- Dilarang: layar di luar 5 rumah + 3 vendor v1.0.0, layar admin di mobile, checkout di web, harga tidak jujur (ongkir Rp5.000 selalu tampil di rincian).

Angka bisnis TitipO yang berlaku di seluruh repo: fee vendor 12% (+0,5% Prioritas), ongkir flat Rp5.000 (Rp4.000 vendor + Rp1.000 kas), pesan maksimal 20.00, serah 06.00-08.00, pokok ke Lumbung tiap Senin, denda batal sepihak Rp15.000, maksimal 50 kg per transaksi (di atasnya ditandai grosir), ID pesanan `T-2026-NNNNNN`.

## Aturan kerja AI

a. Baca AGENTS.md ini dan seluruh ADR di `docs/decisions/` sebelum menulis kode.
b. TDD merah-hijau: tulis test yang gagal dahulu. Rilis diblokir bila QA gate (SRS/40-acceptance-criteria.md) gagal.
c. Kontrak API/event hanya diubah lewat bump versi + catatan di ADR baru.
d. Pesan commit berawalan `docs:`, `feat:`, atau `fix:`; wajib memperbarui `CHANGELOG.md` repo ini.
e. Keputusan arsitektur baru = tambah ADR bernomor di `docs/decisions/`; jangan mengedit ADR lama (immutable, sama seperti aturan versi TownHall).
f. Dilarang menyentuh DB divisi lain (DB per service; Titeny read-only).
g. Khusus repo ini:
- Token milik repo ini; implementasi milik `titipo-app-kmp` dan `titipo-web`; perubahan token wajib PR ke kedua repo konsumen.

## Definisi selesai

- Dokumen versi lengkap (BRD/PRD/FRD/FSD/SRS) + `SNAPSHOT-ROADMAP.md`.
- QA gate berbasis SRS lulus (TDD merah-hijau).
- Kontrak API terbit; audit keamanan bersih (JWT audiens + DB per service).
- Bukti metrik lintas-divisi (KONTEKS §7) tercatat.
- CHANGELOG versi diperbarui; dokumen beku tidak diedit.
Sumber: [townhall-roadmap.md §6](https://github.com/Coding-Skuy/ChefGenie-TownHall/blob/main/townhall-roadmap.md)
