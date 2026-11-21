# Tugas Mandiri 02e — Detektif Audit Blueprint Cacat

**Nama:** Husain Fadhilah Amal

## 1. Mismatch 1 (Pseudocode vs Flowchart)

Pada Pseudocode terdapat pengecekan kuota voucher menggunakan kondisi `voucher.kuota_pakai <= 0`. Jika kuota sudah habis, sistem menampilkan pesan bahwa kuota voucher sudah habis dan proses dihentikan.

Namun, pada Flowchart tidak terdapat proses pengecekan kuota voucher maupun proses pengurangan kuota setelah voucher berhasil digunakan.

**Perbaikan:** Tambahkan keputusan untuk memeriksa apakah kuota voucher masih tersedia. Jika habis, tampilkan pesan error. Jika masih tersedia dan syarat minimum belanja terpenuhi, lanjutkan perhitungan dan kurangi kuota voucher sebanyak satu.

## 2. Mismatch 2 (Logika vs Atribut ERD)

Pada Pseudocode dan Flowchart terdapat pemeriksaan `minimal_belanja`, yaitu untuk memastikan total belanja pembeli sudah memenuhi syarat penggunaan voucher.

Namun, pada ERD tabel `VOUCHER` belum memiliki atribut `minimal_belanja`.

**Perbaikan:** Tambahkan atribut `minimal_belanja` dengan tipe data `int` ke dalam tabel `VOUCHER` agar data syarat minimum belanja dapat disimpan dan digunakan oleh sistem.

## 3. Mismatch 3 (Konsistensi Penamaan)

Pada Pseudocode terdapat atribut `voucher.kuota_pakai`, sedangkan pada ERD menggunakan nama `sisa_kuota`. Kedua nama tersebut memiliki maksud yang berkaitan dengan jumlah kuota voucher yang masih tersedia, tetapi penamaannya tidak konsisten.

**Perbaikan:** Gunakan nama `sisa_kuota` secara konsisten pada Pseudocode, Flowchart, dan ERD. Dengan begitu, sistem memiliki satu nama atribut yang sama untuk menunjukkan jumlah voucher yang masih bisa digunakan.

## 4. Kesimpulan

Dari hasil pemeriksaan, saya menemukan tiga ketidaksinkronan antara Pseudocode, Flowchart, dan ERD. Ketiganya perlu diperbaiki agar alur logika, proses sistem, dan struktur penyimpanan data saling sesuai. Jika tidak diperbaiki, fitur voucher bisa mengalami kesalahan ketika dijalankan atau ketika data voucher disimpan.