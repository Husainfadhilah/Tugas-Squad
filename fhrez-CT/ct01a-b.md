# Tugas Mandiri 02b — Jembatan Kode: Fungsi Diskon & Ongkir
Nama: [fariz]

## 1. Kode JavaScript Sederhana:

```javascript
function hitungTotalBayar(totalBelanja, jarakKm) {
  // 1. Hitung Diskon
  let diskon = 0;
  if (totalBelanja >= 100000) {
    diskon = totalBelanja * 0.10;
    if (diskon > 20000) {
      diskon = 20000;
    }
  }

  // 2. Hitung Ongkir
  let ongkir = 0;
  if (jarakKm > 3) {
    let kelebihanKm = jarakKm - 3;
    ongkir = kelebihanKm * 2500;
  }

  // 3. Total Akhir
  let totalAkhir = totalBelanja - diskon + ongkir;
  return totalAkhir;
}

// ===== UJI COBA 3 SKENARIO =====

// Skenario A: belanja di bawah 100rb, jarak dekat (<= 3 km)
console.log("Skenario A:", hitungTotalBayar(80000, 2));
// Diskon = 0, Ongkir = 0 → Total = 80000

// Skenario B: belanja 150rb, jarak 5 km
console.log("Skenario B:", hitungTotalBayar(150000, 5));
// Diskon = 15000, Ongkir = 5000 → Total = 140000

// Skenario C: belanja 300rb, jarak 10 km (uji batas diskon maksimal)
console.log("Skenario C:", hitungTotalBayar(300000, 10));
// Diskon = 30000 → dibatasi 20000, Ongkir = 7 × 2500 = 17500
// Total = 300000 - 20000 + 17500 = 297500

Skenario A: 80000
Skenario B: 140000
Skenario C: 297500

Verifikasi Manual (Dry Run):
Skenario	Total Belanja	Jarak	Diskon (10%, max 20rb)	Ongkir ((km-3)×2500)	Total Akhir
A	80.000	2 km	0 (belum capai 100rb)	0 (≤ 3 km)	80.000
B	150.000	5 km	15.000	5.000	140.000
C	300.000	10 km	30.000 → 20.000	17.500	297.500
Semua hasil console.log() cocok dengan perhitungan manual. 
