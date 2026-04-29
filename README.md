# Macam-macam Trigger yang digunakan di projek ini :
### Trigger Pengurangan Stok (Setelah Transaksi Lunas)
Trigger mendeteksi adanya perubahan status di Tabel Transaksi. <br> Sistem melihat Tabel Detail Transaksi untuk mengetahui produk apa saja yang dibeli.  Sistem mengecek Tabel Resep untuk melihat bahan apa saja yang digunakan untuk produk tersebut.  Sistem secara otomatis melakukan UPDATE pada kolom stok di Tabel Bahan Baku (Inventory) berdasarkan jumlah yang dibutuhkan. 
