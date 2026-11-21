
```mermaid
erDiagram
    MERCHANT ||--o{ KATEGORI : memiliki
    MERCHANT ||--o{ PRODUK : menjual
    MERCHANT ||--o{ PESANAN : menerima

    KATEGORI ||--o{ PRODUK : mengelompokkan

    PESANAN ||--|{ ITEM_PESANAN : memiliki
    PRODUK ||--o{ ITEM_PESANAN : dipesan

    MERCHANT {
        string merchant_id PK
        string nama_merchant
        string nomor_wa
        string alamat
    }

    KATEGORI {
        string kategori_id PK
        string merchant_id FK
        string nama_kategori
    }

    PRODUK {
        string produk_id PK
        string merchant_id FK
        string kategori_id FK
        string nama_produk
        int harga
        int stok
        string foto_produk
    }

    PESANAN {
        string pesanan_id PK
        string merchant_id FK
        string nama_pembeli
        string nomor_wa_pembeli
        string tanggal_pesanan
        int total_harga
        string status_pesanan
    }

    ITEM_PESANAN {
        string item_id PK
        string pesanan_id FK
        string produk_id FK
        int jumlah_beli
        int harga_satuan
        int subtotal
    }