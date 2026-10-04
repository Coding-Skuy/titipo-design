# Layar per peran

## Rumah tangga (`route/home/...`)

- `HomeList` — daftar vendor hari ini + ETA.
- `HomeDetail` — katalog vendor + tombol titip.
- `HomeSubscription` — kelola langganan harian/mingguan/bulanan.
- `HomeTracking` — lacak status pesanan.

## Vendor (`route/vendor/...`)

- `VendorCatalog` — kelola item + stok.
- `VendorSchedule` — rute + jam keliling.
- `VendorOrders` — pesanan masuk + aksi terima/diantar/selesai.

Semua layar memakai token di `tokens/` dan mengikuti flow di `flows/`.
