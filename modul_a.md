PROGRAM ModulA_EvaluasiPersediaan
DEKLARASI
    string kodeBarang, namaBarang, status
    int stokAwal, barangMasuk, barangTerjual, stokAkhir, stokMinimum, jumlahPesan
    float hargaBeli, biayaPesan

DESKRIPSI
    // Input data utama barang
    READ(kodeBarang)
    READ(namaBarang)
    READ(stokAwal)
    READ(barangMasuk)
    
    // Validasi input tidak boleh negatif
    IF (stokAwal < 0 OR barangMasuk < 0) THEN
        WRITE("Error: Stok atau barang masuk tidak boleh bernilai negatif!")
    ELSE
        READ(barangTerjual)
        
        // Validasi penjualan tidak boleh melebihi ketersediaan stok
        IF (barangTerjual > (stokAwal + barangMasuk)) THEN
            WRITE("Error: Penjualan tidak boleh melebihi total stok yang tersedia!")
        ELSE
            // Proses perhitungan stok akhir
            stokAkhir <- (stokAwal + barangMasuk) - barangTerjual
            
            READ(stokMinimum)
            READ(hargaBeli)
            
            // Penentuan Status Persediaan Barang
            IF (stokAkhir == 0) THEN
                status <- "Habis"
                jumlahPesan <- (2 * stokMinimum) - stokAkhir
            ELSE IF (stokAkhir < stokMinimum) THEN
                status <- "Menipis"
                jumlahPesan <- (2 * stokMinimum) - stokAkhir
            ELSE
                status <- "Aman"
                jumlahPesan <- 0
            ENDIF
            
            // Hitung Biaya Pemesanan
            biayaPesan <- jumlahPesan * hargaBeli
            
            // Output Hasil Modul A
            WRITE("--- RINCIAN MODUL A ---")
            WRITE("Kode Barang: ", kodeBarang)
            WRITE("Nama Barang: ", namaBarang)
            WRITE("Stok Akhir: ", stokAkhir)
            WRITE("Status Persediaan: ", status)
            WRITE("Jumlah Barang yang Harus Dipesan: ", jumlahPesan)
            WRITE("Total Biaya Pemesanan: Rp", biayaPesan)
        ENDIF
    ENDIF
ENDPROGRAM