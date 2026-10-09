--Projek UTS algoritma pemrograman(Alpro)
studi kasus 6: Sistem evaluasi persediaan barang

--Anggota kelompok 
Kevin Sebastian Liem/ NIM:32261006
Lucy Filipini Vita Katarina/NIM:32261008

Bahasa pemrograman yang dipakai:C++

1.Analisis masalah 
Progam ini dirancang untuk digunakan oleh petugas koperasi atau pengurus inventaris barang guna mengevaluasi stok barang secara cepat, akurat, dan terstruktur.

B.Tujuan progam 
Mengevaluasi stok barang di koperasi, menghitung stok akhir, menentukan status ketersediaan barang (Aman, Menipis, atau Habis), serta menghitung jumlah pemesanan kembali (restock) beserta total biaya pemesanannya.

C.Identifikasi input 
Program menerima data masukan untuk setiap barang berupa:
* Kode Barang
* Nama Barang
* Stok Awal
* Barang Masuk
* Barang Terjual
* Stok Minimum
* Harga Beli

D.Aturan dan perhitungan&proses
1. **Stok Akhir:** Dihitung dengan rumus:  
   Stok Akhir = Stok Awal + Barang Masuk - Barang Terjual
2. **Status Persediaan:**
   * Jika Stok Akhir = 0 -> Status: **Habis**
   * Jika Stok Akhir < Stok Minimum -> Status: **Menipis**
   * Jika Stok Akhir >= Stok Minimum -> Status: **Aman**
3. **Pemesanan Kembali (Restock):**
   * Jika status **Menipis** atau **Habis**, barang harus dipesan sampai stok mencapai dua kali lipat dari stok minimum:  
     Jumlah Pesan = (2 * Stok Minimum) - Stok Akhir
   * Jika status **Aman**, jumlah pesan = 0.
4. **Biaya Pemesanan:**  
   Biaya Pemesanan = Jumlah Pesan * Harga Beli

   E.kondisi perulangan
   Program memproses data beberapa barang secara berulang (menggunakan looping) tanpa menggunakan array (sesuai batasan proyek) sampai petugas memilih untuk mengakhiri proses.

   F.Validasi input tidak valid
   * Menolak nilai negatif pada input stok, barang masuk, barang terjual, stok minimum, atau harga beli.
* Menolak jumlah barang terjual yang melebihi total ketersediaan stok (Stok Awal + Barang Masuk) agar program tidak mengalami kesalahan sistem.


## 2. Tabel Input - Process - Output (IPO)

| Input | Process (Proses & Perhitungan) | Output (Keluaran) |
| :--- | :--- | :--- |
| • Kode Barang<br>• Nama Barang<br>• Stok Awal<br>• Barang Masuk<br>• Barang Terjual<br>• Stok Minimum<br>• Harga Beli | 1. Validasi input agar tidak negatif dan penjualan tidak melebihi stok tersedia.<br>2. Hitung Stok Akhir = Stok Awal + Barang Masuk - Barang Terjual.<br>3. Tentukan status barang (Aman / Menipis / Habis) menggunakan percabangan.<br>4. Hitung jumlah unit pesanan (Restock) jika status Menipis / Habis.<br>5. Hitung biaya pemesanan (Jumlah Pesan * Harga Beli).<br>6. Akumulasi data untuk rekapitulasi akhir. | • Rincian stok akhir barang<br>• Status persediaan barang<br>• Jumlah unit yang harus dipesan<br>• Total biaya pemesanan<br>• Rekapitulasi keseluruhan (jumlah barang aman/menipis/habis, total unit terjual, total unit dipesan, total biaya, & penjualan tertinggi) |