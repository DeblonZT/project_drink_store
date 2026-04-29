# Macam-macam Trigger yang digunakan di projek ini :
### 1. Trigger Pengurangan Stok (Setelah Transaksi Lunas)
Logikanya :
<br>1. Trigger mendeteksi adanya perubahan status di Tabel Transaksi. <br>2.  Sistem melihat Tabel Detail Transaksi untuk mengetahui produk apa saja yang dibeli.<br>3.  Sistem mengecek Tabel Resep untuk melihat bahan apa saja yang digunakan untuk produk tersebut.<br>4.  Sistem secara otomatis melakukan UPDATE pada kolom stok di Tabel Bahan Baku (Inventory) berdasarkan jumlah yang dibutuhkan. 
<br>
### 2. Trigger Validasi Stok Habis (Peringatan)
Logikanya :
<br>1. Sebelum pelanggan melakukan "Checkout", trigger (atau stored procedure) melakukan pengecekan ke Tabel Bahan Baku.<br>2.  Jika stok < jumlah_dibutuhkan di resep, sistem akan menolak transaksi dan memberikan pesan: "Maaf, stok bahan untuk minuman ini sedang habis".
