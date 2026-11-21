## FLowchart 1

flowchart TD
    A([Mulai]) --> B[Pemilik membuka form tambah produk]
    B --> C[Memasukkan nama, harga, kategori, stok, dan tautan foto]
    C --> D{Nama produk tidak kosong?}

    D -- Tidak --> E[Tampilkan error: Nama produk wajib diisi]
    E --> B

    D -- Ya --> F{Harga berupa angka dan lebih dari 0?}
    F -- Tidak --> G[Tampilkan error: Harga harus angka dan lebih dari 0]
    G --> B

    F -- Ya --> H{Stok minimal 1?}
    H -- Tidak --> I[Tampilkan error: Stok minimal 1]
    I --> B

    H -- Ya --> J[Simpan produk ke katalog]
    J --> K[Tampilkan notifikasi: Produk berhasil ditambahkan]
    K --> L([Selesai])

## flowchart 2

flowchart TD
    A([Mulai]) --> B[Pembeli membuka detail produk]
    B --> C[Pembeli menekan tombol Pesan via WhatsApp]
    C --> D{Apakah stok tersedia?}

    D -- Tidak --> E[Tampilkan label: Maaf, Produk Ini Sedang Habis]
    E --> F[Nonaktifkan tombol pemesanan]
    F --> G[Arahkan pembeli melihat produk serupa]
    G --> H([Selesai])

    D -- Ya --> I[Pembeli mengisi nama dan jumlah pesanan]
    I --> J{Jumlah pesanan valid dan tidak melebihi stok?}
    J -- Tidak --> K[Tampilkan pesan kesalahan]
    K --> I

    J -- Ya --> L[Rakit template pesan otomatis]
    L --> M[Buka tautan WhatsApp penjual]
    M --> N([Selesai])