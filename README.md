# Macam-macam Trigger yang digunakan di projek ini :
### Trigger Pengurangan Stok (Setelah Transaksi Lunas)
1. Trigger mendeteksi adanya perubahan status di Tabel Transaksi. <br>2.  Sistem melihat Tabel Detail Transaksi untuk mengetahui produk apa saja yang dibeli.<br>3.  Sistem mengecek Tabel Resep untuk melihat bahan apa saja yang digunakan untuk produk tersebut.<br>4.  Sistem secara otomatis melakukan UPDATE pada kolom stok di Tabel Bahan Baku (Inventory) berdasarkan jumlah yang dibutuhkan. 
