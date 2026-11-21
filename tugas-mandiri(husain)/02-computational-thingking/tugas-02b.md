# Tugas Mandiri 02b — Jembatan Kode: Fungsi Diskon & Ongkir

**Nama:** Husain Amal

## 1. Kode JavaScript Sederhana

```javascript
function hitungTotalBayar(totalBelanja, jarakKm) {
    // 1. Menghitung diskon
    let diskon = 0;

    if (totalBelanja >= 100000) {
        diskon = totalBelanja * 0.10;

        if (diskon > 20000) {
            diskon = 20000;
        }
    } else {
        diskon = 0;
    }

    // 2. Menghitung ongkir
    let ongkir = 0;

    if (jarakKm > 3) {
        ongkir = (jarakKm - 3) * 2500;
    } else {
        ongkir = 0;
    }

    // 3. Menghitung total pembayaran
    let totalAkhir = totalBelanja - diskon + ongkir;

    return totalAkhir;
}

// Pengujian Skenario A
console.log("Skenario A:", hitungTotalBayar(50000, 2));

// Pengujian Skenario B
console.log("Skenario B:", hitungTotalBayar(150000, 5));

// Pengujian Skenario C
console.log("Skenario C:", hitungTotalBayar(300000, 1));
```

## 2. Hasil Pengujian (Console)

```text
Skenario A: 50000
Skenario B: 140000
Skenario C: 280000
```

## 3. Perbandingan dengan Dry Run

| Skenario | Total Belanja | Jarak | Diskon | Ongkir | Total Bayar |
|---|---:|---:|---:|---:|---:|
| A | Rp50.000 | 2 km | Rp0 | Rp0 | Rp50.000 |
| B | Rp150.000 | 5 km | Rp15.000 | Rp5.000 | Rp140.000 |
| C | Rp300.000 | 1 km | Rp20.000 | Rp0 | Rp280.000 |

**Hasil:** Ketiga skenario menghasilkan nilai yang sama dengan tabel Dry Run.

## 4. Refleksi Singkat

Menurut saya, mengubah pseudocode menjadi JavaScript lebih mudah karena urutan proses dan kondisi sudah ditentukan sebelumnya. Saya juga jadi lebih memahami penggunaan `if` dan `else` untuk menentukan diskon dan ongkir. Dari tugas ini saya belajar bahwa sebelum membuat kode, kita perlu memahami aturan perhitungannya terlebih dahulu.