### Nama: Mahfuz Fauzi
### NIM: 312410412

## Jawab Soal UTS

### Struktur Data yang Digunakan:
Barang:

Setiap barang akan memiliki nama, harga, dan jumlah yang ditambahkan ke keranjang.

Keranjang:

Keranjang akan berisi daftar barang yang dipilih oleh pelanggan beserta jumlah dan harga setiap barang.

Struk:

Struk akan berisi daftar barang yang dibeli beserta harga dan total harga setelah diskon (jika ada).

### Code Python

class Barang:
    def __init__(self, nama, harga):
        self.nama = nama
        self.harga = harga

class Keranjang:
    def __init__(self):
        self.items = []  # Menyimpan barang dan jumlah yang dibeli
    
    def tambah_barang(self, barang, jumlah):
        # Mencari apakah barang sudah ada dalam keranjang
        for item in self.items:
            if item['barang'] == barang:
                item['jumlah'] += jumlah  # Menambah jumlah barang yang sudah ada
                return
        # Jika barang belum ada, tambah barang baru ke dalam keranjang
        self.items.append({'barang': barang, 'jumlah': jumlah})
    
    def total_harga(self):
        total = 0
        for item in self.items:
            total += item['barang'].harga * item['jumlah']
        return total
    
    def tampilkan_daftar_barang(self):
        print("Daftar Barang di Keranjang:")
        for item in self.items:
            print(f"{item['barang'].nama} (x{item['jumlah']}) - Rp{item['barang'].harga * item['jumlah']}")

    def cetak_struk(self):
        print("\n==== Struk Pembelian ====")
        for item in self.items:
            print(f"{item['barang'].nama} (x{item['jumlah']}) - Rp{item['barang'].harga * item['jumlah']}")
        print(f"Total Harga: Rp{self.total_harga()}")
        print("===========================")


# Contoh penggunaan program kasir

# Daftar barang yang tersedia
barang1 = Barang("Sabun Mandi", 15000)
barang2 = Barang("Shampo", 25000)
barang3 = Barang("Pasta Gigi", 12000)

# Membuat keranjang belanja
keranjang = Keranjang()

# Menambahkan barang ke keranjang
keranjang.tambah_barang(barang1, 2)  # 2 Sabun Mandi
keranjang.tambah_barang(barang2, 1)  # 1 Shampo
keranjang.tambah_barang(barang3, 3)  # 3 Pasta Gigi

# Menampilkan daftar barang yang ada di keranjang
keranjang.tampilkan_daftar_barang()

# Menghitung total harga
total = keranjang.total_harga()
print(f"Total Harga: Rp{total}")

# Mencetak struk
keranjang.cetak_struk()

