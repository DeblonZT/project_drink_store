## 👥 Nama Kelompok
Proyek ini dikembangkan oleh **Three Wish**:

* **[Ardhika Damar Bachtiar]**
* **[Hizqil Faza Ramadhan]**
* **[Kirana Uzhaima Putri]**

---

## ⚙️ Mekanisme Database Trigger
Kami menerapkan dua trigger utama pada database untuk memastikan integritas data dan otomatisasi stok:

### 1. Trigger Pengurangan Stok (Setelah Transaksi Lunas)
Trigger ini memastikan bahwa stok bahan baku berkurang secara otomatis ketika pesanan pelanggan telah dibayar.

**Logika:**
1. **Deteksi:** Trigger memantau perubahan status (event) pada tabel `Transaksi`.
2. **Identifikasi:** Sistem membaca `Detail_Transaksi` untuk mengetahui produk apa saja yang dibeli.
3. **Analisis Resep:** Sistem memeriksa tabel `Resep` untuk melihat daftar bahan baku yang dibutuhkan oleh produk tersebut.
4. **Eksekusi:** Sistem melakukan `UPDATE` pada kolom `stok` di tabel `Bahan Baku` berdasarkan jumlah yang dibutuhkan dikalikan dengan kuantitas pembelian.

### 2. Trigger Validasi Stok Habis (Peringatan)
Trigger ini berfungsi sebagai validasi *real-time* untuk mencegah transaksi diproses jika bahan baku tidak mencukupi (pencegahan *overselling*).

**Logika:**
1. **Pengecekan:** Sebelum pelanggan melakukan "Checkout", sistem (via trigger atau stored procedure) membandingkan `stok` di `Bahan Baku` dengan `jumlah_dibutuhkan` di tabel `Resep`.
2. **Validasi:** Jika `stok < jumlah_dibutuhkan`, sistem akan menolak transaksi.
3. **Peringatan:** Sistem memberikan pesan error: *"Maaf, stok bahan untuk minuman ini sedang habis"*.
