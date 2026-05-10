# Panduan Penjelasan Kode: Website Burjo Sahabat

File README ini dibuat untuk membantu kamu menjelaskan alur dan fungsi-fungsi kode pada video presentasi/responsi kamu.

## 📁 Struktur Folder & File

Project ini terdiri dari file-file berikut:
1. **`index.html`**: Halaman utama. Berisi struktur dasar website, daftar menu (card), form pesanan, dan logika JavaScript untuk menghitung pesanan.
2. **`style.css`**: File khusus untuk mendesain tampilan web (warna, tata letak menggunakan Flexbox, ukuran font, dll) agar lebih menarik.
3. **`detail-magelangan.html`, `detail-mie-goreng.html`, `detail-omelet.html`**: Halaman-halaman spesifik yang menampilkan informasi lebih detail tentang masing-masing menu (komposisi, kalori, harga).
4. **Folder `images/`**: Tempat menyimpan aset foto makanan.

---

## 💻 Bedah Kode: `index.html`

File ini adalah jantung dari aplikasi web pemesanan sederhana ini. Terdapat 3 bagian utama:

### 1. Struktur HTML (Tampilan Rangka)
* Menggunakan elemen semantik dasar seperti `<h1>` s/d `<h3>` untuk judul, dan `<p>` untuk paragraf.
* Menggunakan tag **`<mark>`** untuk memberikan efek *highlight* (stabilo) kuning pada teks penting.
* **Flexbox Container (`<div class="card-container">`)**: Bagian ini membungkus 3 menu makanan. Dengan bantuan CSS (`display: flex;`), ketiga menu ini bisa berjejer rapi ke samping secara otomatis.

### 2. Form Pemesanan & Interaksi
* Terdapat tombol **`-`** dan **`+`** pada setiap menu. Tombol ini memiliki atribut `onclick="..."` yang akan memanggil fungsi JavaScript saat ditekan.
* Terdapat input teks (`<input type="text" id="namaPemesan">`) agar pembeli bisa memasukkan nama mereka.

### 3. Logika JavaScript (Alur Program)
Bagian `<script>` di bawah `index.html` adalah otak dari interaksi web ini. Berikut adalah penjelasan fungsi-fungsinya:

* **`tambah(id)`**
  * **Fungsi:** Menambah jumlah porsi menu.
  * **Alur:** Saat tombol `+` ditekan, fungsi ini mengambil elemen berdasarkan `id` (misal `qty1`), membaca angka yang ada, dan menambahkannya dengan `1`.

* **`kurang(id)`**
  * **Fungsi:** Mengurangi jumlah porsi menu.
  * **Alur:** Mirip dengan fungsi tambah, namun di sini terdapat **validasi penting**: `if (val > 0)`. Validasi ini memastikan bahwa pesanan hanya bisa dikurangi jika jumlahnya lebih dari 0. Ini mencegah pesanan bernilai negatif (minus).

* **`pesanSekarang()`**
  * **Fungsi:** Memproses pesanan saat tombol "Pesan Sekarang" diklik.
  * **Alur:**
    1. **Pengambilan Data:** Mengambil nama dari input teks dan jumlah masing-masing pesanan.
    2. **Validasi Nama:** Mengecek apakah input nama kosong menggunakan `.trim() === ''`. Jika kosong, akan muncul peringatan (*alert*) dan proses berhenti.
    3. **Validasi Menu:** Mengecek apakah pengguna belum memilih menu sama sekali (semua kuantitas = 0). Jika ya, muncul peringatan dan proses berhenti.
    4. **Membuat Struk:** Jika semua validasi lolos, program akan merangkai teks/string berisi nama dan menu apa saja yang jumlah porsinya lebih dari 0.
    5. **Tampilan Output:** Menampilkan teks struk tersebut dalam bentuk pop-up (*alert*) di browser.

---

## 🎨 Bedah Kode: Halaman Detail (`detail-*.html`)

Halaman-halaman detail dirancang sederhana untuk memberikan informasi ekstra. Beberapa hal teknis yang bisa dijelaskan:
* **Tag `<s>`**: Digunakan untuk mencoret teks (strikethrough) pada teks "Harga lama".
* **Tag `<sup>` (Superscript)**: Digunakan untuk menulis teks kecil agak ke atas, contoh: 250<sup>gram</sup>.
* **Tag `<sub>` (Subscript)**: Digunakan untuk menulis teks kecil agak ke bawah, contoh: kkal<sub>per porsi</sub>.
* Tombol "Kembali" dibuat menggunakan tag tautan `<a>` biasa yang diberi desain *button* melalu CSS (`class="btn-back"`), dan mengarah kembali ke `index.html`.

---

## 🎥 Tips Presentasi Video
1. Buka file `index.html` di dalam text editor (seperti VS Code) berdampingan (split screen) dengan *web browser*.
2. Praktekkan menekan tombol `+`, lalu tunjukkan di kode JavaScript bagian mana yang bekerja (fungsi `tambah()`).
3. Praktekkan klik "Pesan Sekarang" dengan kondisi nama kosong untuk menunjukkan bahwa fitur validasi di fungsi `pesanSekarang()` berfungsi dengan baik.
4. Jangan lupa arahkan kursor ke komentar `//` yang sudah ditambahkan di kode untuk mempermudah ingatan kamu saat presentasi.
