# Tugas Mandiri 02d — Model Data Fitur Ulasan Produk
Nama: [Nama Kamu]

## 1. Struktur Entitas Baru: ULASAN

mermaid
erDiagram
    PRODUK ||--o ULASAN : "mendapatkan"

    ULASAN {
        string id_ulasan PK
        string id_produk FK
        string nama_pembeli
        int rating_bintang
        string komentar
        string waktu_ulasan
    }

Daftar Atribut & Tipe Data (rinci):
No	Atribut	Tipe Data	Keterangan
1	id_ulasan	string	PK — identitas unik tiap ulasan
2	id_produk	string	FK → menunjuk ke PRODUK.id_produk
3	nama_pembeli	string	Nama pengulas
4	rating_bintang	int	Nilai 1–5 (bintang)
5	komentar	string	Isi ulasan singkat
6	waktu_ulasan	string	Waktu ulasan dibuat (bisa juga datetime)
2. Penjelasan Relasi & Kunci
Relasi: Satu ke Banyak (1 : N).
Satu PRODUK dapat memiliki banyak ULASAN dari berbagai pembeli — atau nol ulasan jika belum ada yang mengulas. Sebaliknya, satu baris ULASAN hanya tertuju pada satu produk tertentu. Karena itu bukan 1:1 (banyak ulasan per produk) dan bukan N:N (ulasan tidak berdiri sendiri milik banyak produk sekaligus).

Simbol Mermaid ||--o{: sisi PRODUK bersimbol || (tepat satu produk), sisi ULASAN bersimbol o{ (nol atau banyak ulasan). Ini menangkap fakta bahwa produk baru boleh belum punya ulasan.

Primary Key (PK): id_ulasan pada ULASAN — menjamin tiap ulasan unik dan bisa dirujuk.

Foreign Key (FK): id_produk pada ULASAN — menunjuk ke id_produk (PK) milik entitas PRODUK. Inilah "jembatan" yang menghubungkan ulasan ke produknya.

3. Verifikasi Logika (Cek Ketelitian)
Cek	Hasil
PK id_ulasan unik per baris?	✅ Ya
id_produk sebagai FK menunjuk PK PRODUK?	✅ Ya
Satu produk bisa punya banyak ulasan?	✅ Ya (1:N)
Produk tanpa ulasan tetap valid?	✅ Ya (o{ = nol atau banyak)
rating_bintang bertipe int (1–5)?	✅ Ya
Tidak ada atribut yang salah jadi PK?	✅ Ya (id_produk bukan PK di ULASAN)

    ## ✅ Ringkasan Jawaban Inti

| Pertanyaan | Jawaban |
|---|---|
| **PK ULASAN** | `id_ulasan` |
| **FK ULASAN** | `id_produk` → `PRODUK.id_produk` |
| **Relasi PRODUK–ULASAN** | **1 : N** (satu produk → banyak ulasan) |
| **Simbol Mermaid** | `PRODUK \|\|--o{ ULASAN : "mendapatkan"` |