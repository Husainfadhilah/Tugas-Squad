# Tugas Mandiri 02c — Flowchart Validasi Nomor WhatsApp
Nama: [fariz]

## 1. Flowchart (Sintaks Mermaid)

mermaid
flowchart TD
    Start([Mulai]) --> InputPhone[/Input: Pengguna memasukkan nomor HP/]
    InputPhone --> CekFormat{Diawali "08" atau "+62"?}
    CekFormat -- Tidak --> TampilError[Tampilkan: Format nomor tidak valid]
    TampilError --> InputPhone

    CekFormat -- Ya --> CekPanjang{Panjang 10 sampai 13 digit?}
    CekPanjang -- Tidak --> TampilPanjang[Tampilkan: Panjang nomor salah]
    TampilPanjang --> InputPhone

    CekPanjang -- Ya --> Sukses[/Tampilkan centang hijau: Nomor valid/]
    Sukses --> Selesai([Selesai])

## 2. Verifikasi Logika dengan Contoh Kasus (Dry Run)
No	Input	Format OK?	Panjang (digit)	Hasil yang Diharapkan 
1	081234567890	Ya (08)	12 → OK	✅ Sukses 
2	+62812345678	Ya (+62)	11 → OK	✅ Sukses 
3	0212345678	Tidak	—	❌ Error format → input ulang 
4	08123	Ya (08)	5 → salah	❌ Error panjang → input ulang 
5	081234567890123	Ya (08)	15 → salah	❌ Error panjang → input ulang 
Semua cabang pada flowchart terjangkau dan konsisten dengan tabel di atas. ✅