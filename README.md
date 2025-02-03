# Rupiah Formatter & Terbilang Converter

Sebuah komponen web untuk memformat input mata uang Rupiah dan menampilkan terbilang secara otomatis.  
**Fitur**:
- Format real-time ke Rupiah (contoh: `1500000` → `Rp 1.500.000`)
- Konversi ke terbilang (contoh: `125000` → `Seratus Dua Puluh Lima Ribu Rupiah`)
- Dukungan angka desimal (Sen)
- Responsif dengan Bootstrap

## Instalasi
1. Clone repositori:
   ```bash
   git clone https://github.com/username/repo-name.git
   ```
2. Buka file `index.html` di browser.

## Cara Penggunaan
Tambahkan struktur HTML berikut:
```html
<div class="form-group">
  <label for="txtharga1">Harga Nego</label>
  <input type="text" class="form-control" id="txtharga1">
  <small id="txtharga1Terbilang" class="form-text text-muted"></small>
</div>
```

Dan sertakan script:
```javascript
// Fungsi formatRupiah() dan terbilang() dari kode
```

## Contoh Hasil
| Input           | Formatted Rupiah | Terbilang                                      |
|-----------------|------------------|-----------------------------------------------|
| `1500000`       | Rp 1.500.000     | /Satu Juta Lima Ratus Ribu Rupiah/            |
| `2500000,50`    | Rp 2.500.000,50  | /Dua Juta Lima Ratus Ribu Rupiah Lima Puluh Sen/ |
| `0,99`          | Rp 0,99          | /Nol Rupiah Sembilan Puluh Sembilan Sen/      |

## Penjelasan Teknis
### 1. Fungsi `formatRupiah()`
```javascript
function formatRupiah(angka, prefix) { ... }
```
- **Tujuan**: Memformat angka ke string Rupiah dengan separator ribuan
- **Parameter**:
  - `angka`: Nilai input (string/number)
  - `prefix`: Tambahkan `Rp` jika `true`
- **Contoh**:
  ```javascript
  formatRupiah("1500000", true); // "Rp 1.500.000"
  ```

### 2. Fungsi `terbilang()`
```javascript
function terbilang(angka) { ... }
```
- **Tujuan**: Mengonversi angka ke kata-kata dalam Bahasa Indonesia
- **Algoritma**:
  1. Pisahkan bagian integer dan desimal
  2. Proses integer dengan rekursi untuk skala besar (ribu/juta/miliar)
  3. Tambahkan "Sen" untuk bagian desimal

### 3. Event Handling
- Menggunakan event `input` untuk update real-time
- Memproses 2 field secara dinamis dengan loop

## Berkontribusi
1. Fork repositori
2. Buat branch fitur:
   ```bash
   git checkout -b fitur/namafitur
   ```
3. Commit perubahan:
   ```bash
   git commit -m "Tambahkan fitur X"
   ```
4. Push ke branch:
   ```bash
   git push origin fitur/namafitur
   ```
5. Buat Pull Request

## Lisensi
MIT License. Lihat [LICENSE](LICENSE) untuk detail.

![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.x-blue)
