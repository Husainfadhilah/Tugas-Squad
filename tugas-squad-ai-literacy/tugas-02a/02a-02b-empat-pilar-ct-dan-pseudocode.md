# Computational thingking

## Dekomposisi Masalah
## Alur Pemesanan via WhatsApp & Perhitungan Tagihan (Diskon + Ongkir)


### 1. Menampilkan Katalog Produk
- Menampilkan nama produk.
- Menampilkan foto produk.
- Menampilkan deskripsi produk.
- Menampilkan harga produk.
- Menampilkan varian produk.

**Hasil:** Pelanggan mengetahui produk yang tersedia.

### 2. Memilih Produk
- Pelanggan memilih produk yang diinginkan.
- Pelanggan menentukan varian produk.
- Sistem mencatat produk yang dipilih.

**Hasil:** Daftar produk pilihan pelanggan.

### 3. Menentukan Jumlah Pembelian
- Pelanggan memasukkan jumlah produk.
- Sistem memeriksa jumlah pembelian.
- Sistem memastikan jumlah lebih dari nol.

**Hasil:** Jumlah pembelian setiap produk.

### 4. Mengelola Keranjang Belanja
- Menambahkan produk ke keranjang.
- Mengubah jumlah produk.
- Menghapus produk.
- Memeriksa daftar belanja.

**Hasil:** Keranjang belanja yang sudah sesuai keinginan pelanggan.

### 5. Menghitung Subtotal
- Mengambil harga setiap produk.
- Mengambil jumlah pembelian.
- Mengalikan harga dengan jumlah.
- Menjumlahkan seluruh harga produk.

**Rumus:**
`Subtotal = Harga Produk × Jumlah Pembelian`

**Hasil:** Total harga sebelum diskon dan ongkir.

### 6. Mengumpulkan Data Pelanggan
- Meminta nama pelanggan.
- Meminta nomor WhatsApp.
- Memeriksa kelengkapan data pelanggan.

**Hasil:** Identitas pelanggan.

### 7. Mengumpulkan Alamat Pengiriman
- Meminta alamat lengkap.
- Meminta kecamatan dan kabupaten.
- Meminta kode pos jika diperlukan.
- Memvalidasi kelengkapan alamat.

**Hasil:** Alamat tujuan pengiriman.

### 8. Mengirim Detail Pesanan ke WhatsApp
- Mengambil daftar produk.
- Mengambil jumlah pembelian.
- Mengambil subtotal.
- Mengambil data pelanggan.
- Mengambil alamat pengiriman.
- Membuat format pesan WhatsApp.
- Mengarahkan pelanggan ke WhatsApp admin.

**Hasil:** Admin menerima detail pesanan pelanggan.

### 9. Memeriksa Ketersediaan Stok
- Admin memeriksa stok setiap produk.
- Membandingkan jumlah pesanan dengan stok.
- Memastikan produk tersedia.
- Menginformasikan produk yang habis jika ada.

**Hasil:** Pesanan yang sesuai dengan ketersediaan stok.

### 10. Memeriksa dan Menentukan Diskon
- Memeriksa apakah pelanggan memiliki kode promo.
- Memvalidasi kode promo.
- Memeriksa minimum pembelian.
- Menentukan persentase atau nominal diskon.
- Menentukan apakah diskon bisa digunakan.

**Hasil:** Diskon yang valid atau tidak ada diskon.

### 11. Menghitung Potongan Diskon
- Mengambil subtotal.
- Mengambil persentase diskon.
- Menghitung nominal potongan.
- Mengurangi subtotal dengan nominal diskon.

**Rumus:**
`Diskon = Subtotal × Persentase Diskon`

`Total Setelah Diskon = Subtotal - Diskon`

**Hasil:** Harga produk setelah diskon.

### 12. Menghitung Ongkos Kirim
- Mengambil alamat tujuan.
- Menentukan wilayah pengiriman.
- Memeriksa tarif pengiriman.
- Menentukan biaya ongkos kirim.

**Hasil:** Nominal ongkos kirim.

### 13. Menghitung Total Tagihan
- Mengambil subtotal.
- Mengambil nominal diskon.
- Mengambil ongkos kirim.
- Menghitung total pembayaran.

**Rumus:**
`Total Tagihan = Subtotal - Diskon + Ongkir`

**Hasil:** Total pembayaran pelanggan.

### 14. Membuat dan Mengirim Invoice
- Menampilkan identitas pelanggan.
- Menampilkan daftar produk.
- Menampilkan jumlah pembelian.
- Menampilkan subtotal.
- Menampilkan nominal diskon.
- Menampilkan ongkos kirim.
- Menampilkan total tagihan.
- Mengirim rincian tagihan melalui WhatsApp.

**Hasil:** Pelanggan menerima rincian pembayaran.

### 15. Mengonfirmasi Pembayaran dan Menyelesaikan Pesanan
- Pelanggan mengonfirmasi pesanan.
- Admin memberikan informasi pembayaran.
- Pelanggan melakukan pembayaran.
- Pelanggan mengirim bukti pembayaran.
- Admin memverifikasi pembayaran.
- Admin menyiapkan dan mengemas produk.
- Admin menyerahkan pesanan kepada kurir.
- Admin memberikan informasi pengiriman.
- Pelanggan menerima pesanan.
- Admin memperbarui status pesanan menjadi selesai.

**Hasil:** Pesanan berhasil diselesaikan.

## Pola Logika Berulang

**1.Proses pembeli memesan produk**

memeriksa apakah produk tersedia dalam stok jika stok tidak cukup maka pesanan tidak dapat di lanjutkan

**2.Proses pedagang menambahkan produk baru**
Memeriksa apakah nama produk sudah terdaftar
jika produk sudah terdaftar, penambahan produk perlu di tolak atau di periksa kembali


 
### Abstraksi dan Penulisan Psuedocode

# Abstraksi Data Inti & Noise
## Alur Pemesanan via WhatsApp dan Perhitungan Tagihan

### 1. Tabel Skenario

| Skenario | Total Belanja | Jarak (km) | Diskon Didapat | Biaya Ongkir | Total Akhir |
|---|---|---|---|---|---|
| A | Rp50.000 | 2 km | Rp0 | Rp0 | Rp50.000 |
| B | Rp150.000 | 5 km | Rp15.000 | Rp5.000 | Rp140.000 |
| C | Rp300.000 | 1 km | Rp20.000 (maksimal) | Rp0 | Rp280.000 |

### 2. Identifikasi Data Inti

Data inti adalah informasi yang dibutuhkan aplikasi untuk menghitung total pembayaran pembeli.

| Data | Keterangan | Fungsi |
|---|---|---|
| `totalBelanja` | Total harga seluruh produk | Dasar perhitungan tagihan |
| `jarak` | Jarak pengiriman ke pembeli | Membantu menentukan ongkos kirim |
| `diskonDidapat` | Potongan harga pembeli | Mengurangi total belanja |
| `biayaOngkir` | Biaya pengiriman produk | Ditambahkan ke tagihan |
| `totalAkhir` | Total pembayaran pembeli | Menampilkan jumlah yang harus dibayar |

### 3. Identifikasi Data Noise

Noise adalah informasi yang tidak diperlukan dalam proses perhitungan total pembayaran.

Contoh noise dari dunia nyata (tidak terdapat dalam tabel):

1. Warna pakaian pembeli: Tidak memengaruhi harga produk maupun biaya pengiriman.
2. Makanan favorit pembeli: Tidak berpengaruh terhadap perhitungan tagihan.

## Pseudocode nya 

MULAI

    INPUT total_belanja
    INPUT jarak_km

    diskon = 0
    ongkir = 0

    JIKA total_belanja >= 100000 MAKA
        diskon = total_belanja * 10 / 100

        JIKA diskon > 20000 MAKA
            diskon = 20000
        AKHIR-JIKA

    LAINNYA
        diskon = 0
    AKHIR-JIKA

    JIKA jarak_km <= 3 MAKA
        ongkir = 0
    LAINNYA
        ongkir = (jarak_km - 3) * 2500
    AKHIR-JIKA

    total_akhir = total_belanja - diskon + ongkir

    OUTPUT diskon
    OUTPUT ongkir
    OUTPUT total_akhir

SELESAI




