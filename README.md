# 🏨 GoTell — Smart Hotel Management System

<div align="center">

<img src="assets/gotell-banner.svg" alt="GoTell Smart Hotel Management System Banner" width="100%"/>

<br/><br/>

![C++](https://img.shields.io/badge/Language-C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Console App](https://img.shields.io/badge/Type-Console%20App-orange?style=for-the-badge)
![Role Based](https://img.shields.io/badge/Login-Role%20Based-0ea5e9?style=for-the-badge)
![Windows](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Status](https://img.shields.io/badge/Status-Development-success?style=for-the-badge)

</div>

GoTell adalah aplikasi manajemen hotel berbasis **console/CLI** yang dibuat menggunakan **C++**. Program ini mensimulasikan operasional hotel dengan tiga role utama, yaitu **Manager**, **Resepsionis**, dan **Housekeeping**.

Program sudah dilengkapi dengan **login berbasis role**, **menu interaktif menggunakan tombol panah**, **check-in/check-out tamu**, **layanan tambahan**, **struk transaksi**, **simulasi pembayaran QRIS**, **dashboard manager**, **laporan pendapatan**, **statistik okupansi**, serta **pengelolaan status kamar oleh housekeeping**.

> Catatan penting: versi kode ini **tidak memakai file `.txt` atau database**. Semua data disimpan di memori selama program berjalan. Jika program ditutup lalu dijalankan ulang, data akan kembali ke data default dari kode.

---

## 📌 Daftar Isi

- [Tentang Proyek](#-tentang-proyek)
- [Fitur Utama](#-fitur-utama)
- [Tampilan Program](#-tampilan-program)
- [Konsep C++ yang Digunakan](#-konsep-c-yang-digunakan)
- [Struktur Data yang Di-set di Program](#-struktur-data-yang-di-set-di-program)
- [Alur Program](#-alur-program)
- [Cara Menjalankan](#-cara-menjalankan)
- [Library yang Digunakan](#-library-yang-digunakan)
- [Rumus Perhitungan](#-rumus-perhitungan)
- [Catatan Batasan Program](#-catatan-batasan-program)
- [Pembagian Tugas Tim](#-pembagian-tugas-tim-7-anggota)
- [Lisensi](#-lisensi)

---

## 📖 Tentang Proyek

GoTell dibuat sebagai studi kasus penerapan konsep dasar pemrograman C++ dalam bentuk aplikasi sederhana yang menyerupai sistem hotel. Program ini berfokus pada pengelolaan kamar, tamu, layanan, transaksi, pembayaran, laporan, dan status kamar.

Tampilan program dibuat lebih interaktif dengan beberapa elemen berikut:

- Banner ASCII art **GoTell**
- Warna teks menggunakan ANSI escape code
- Menu berbentuk kotak
- Navigasi menggunakan tombol **panah atas**, **panah bawah**, dan **Enter**
- Animasi loading sederhana
- Struk transaksi berbasis teks
- Simulasi tampilan QRIS menggunakan karakter/simbol
- Banner penutup saat program selesai

---

## ✨ Fitur Utama

### 👔 Manager

| No | Fitur | Keterangan |
|----|-------|------------|
| 1 | Dashboard Utama | Menampilkan total pendapatan, transaksi selesai, tingkat okupansi, dan status kamar |
| 2 | Lihat Semua Kamar | Menampilkan seluruh kamar beserta tipe, lantai, harga, dan status |
| 3 | Lihat Transaksi Aktif | Menampilkan transaksi yang masih berstatus aktif |
| 4 | Laporan Pendapatan | Menampilkan total pendapatan kamar, layanan, dan grand total |
| 5 | Statistik Okupansi | Menampilkan okupansi per tipe kamar dan total booking |
| 6 | Logout | Keluar dari akun manager dan kembali ke menu awal |

### 🧾 Resepsionis

| No | Fitur | Keterangan |
|----|-------|------------|
| 1 | Check-in Tamu | Memilih kamar kosong, input data tamu, membuat transaksi aktif |
| 2 | Tambah Layanan ke Tamu | Menambahkan layanan tambahan ke transaksi aktif |
| 3 | Check-out Tamu | Menampilkan struk, memilih pembayaran Tunai/QRIS, menyelesaikan transaksi |
| 4 | Lihat Semua Kamar | Melihat status semua kamar |
| 5 | Lihat Transaksi Aktif | Melihat transaksi yang sedang berjalan |
| 6 | Logout | Keluar dari akun resepsionis dan kembali ke menu awal |

### 🧹 Housekeeping

| No | Fitur | Keterangan |
|----|-------|------------|
| 1 | Lihat Semua Status Kamar | Menampilkan seluruh kamar dan statusnya |
| 2 | Selesaikan Pembersihan Kamar | Mengubah kamar dari `Dibersihkan` menjadi `Kosong` |
| 3 | Set Kamar ke Maintenance | Mengubah kamar menjadi `Maintenance` jika tidak sedang terisi |
| 4 | Selesaikan Maintenance | Mengubah kamar dari `Maintenance` menjadi `Dibersihkan` |
| 5 | Logout | Keluar dari akun housekeeping dan kembali ke menu awal |

### 🔐 Validasi Input

Program sudah menambahkan validasi agar input tidak mudah menyebabkan error:

- Nama tamu hanya boleh huruf dan spasi
- Nomor KTP wajib **16 digit angka**
- Nomor HP wajib angka, panjang **9–13 digit**, dan diawali `08` atau `62`
- Input angka tidak menerima teks seperti `1a`, `abc`, atau nilai kosong
- Nomor kamar harus benar-benar ada dan berstatus `Kosong` saat check-in
- Login dibatasi maksimal **3 kali percobaan**
- Jika input berakhir tidak normal, program akan dihentikan dengan pesan error

---

## 🖼️ Tampilan Program

Bagian ini dapat diisi dengan screenshot asli hasil running program. Karena kode ini berbasis console, screenshot sebaiknya diambil langsung dari terminal/Command Prompt.

Contoh struktur folder aset yang disarankan:

```text
assets/
│
├── gotell-banner.svg
├── screenshot-menu-awal.png
├── screenshot-login.png
├── screenshot-dashboard-manager.png
├── screenshot-menu-resepsionis.png
├── screenshot-checkin.png
├── screenshot-struk-qris.png
├── screenshot-menu-housekeeping.png
└── screenshot-penutup.png
```

### 🔐 Menu Awal & Login

<div align="center">
  <img src="assets/screenshot-menu-awal.png" alt="Menu Awal GoTell" width="80%"/>
  <br/><br/>
  <img src="assets/screenshot-login.png" alt="Login GoTell" width="80%"/>
</div>

### 👔 Dashboard Manager

<div align="center">
  <img src="assets/screenshot-dashboard-manager.png" alt="Dashboard Manager GoTell" width="80%"/>
</div>

### 🧾 Menu Resepsionis & Check-in

<div align="center">
  <img src="assets/screenshot-menu-resepsionis.png" alt="Menu Resepsionis GoTell" width="80%"/>
  <br/><br/>
  <img src="assets/screenshot-checkin.png" alt="Check-in GoTell" width="80%"/>
</div>

### 💳 Struk & Simulasi QRIS

<div align="center">
  <img src="assets/screenshot-struk-qris.png" alt="Struk dan QRIS GoTell" width="80%"/>
</div>

### 🧹 Menu Housekeeping

<div align="center">
  <img src="assets/screenshot-menu-housekeeping.png" alt="Menu Housekeeping GoTell" width="80%"/>
</div>

---

## 🧠 Konsep C++ yang Digunakan

| Konsep | Penerapan dalam Program |
|--------|--------------------------|
| `struct` | Membuat model data `Kamar`, `Tamu`, `Layanan`, `Transaksi`, dan `User` |
| `vector` | Menyimpan data dinamis seperti `daftarKamar`, `daftarUser`, `daftarTamu`, `daftarLayanan`, dan `daftarTransaksi` |
| Fungsi | Hampir seluruh proses dipisahkan menjadi fungsi agar kode lebih rapi dan modular |
| Pointer | Fungsi pencarian seperti `cariKamar()` dan `cariTransaksiAktif()` mengembalikan alamat data agar data asli bisa langsung diubah |
| Looping | Digunakan untuk menampilkan data, mencari data, validasi input, dan menjalankan menu |
| Percabangan | Mengatur pilihan menu, role user, validasi status kamar, dan metode pembayaran |
| String processing | Digunakan untuk validasi nama, KTP, nomor HP, format rupiah, dan format tanggal |
| ANSI escape code | Digunakan untuk memberi warna pada output console |
| Array sederhana | Masih digunakan untuk pilihan menu dan daftar tipe kamar, sedangkan data utama memakai `vector` |

---

## 🗂 Struktur Data yang Di-set di Program

Semua data awal dibuat langsung dari kode melalui fungsi `inisialisasiDataAwal()`. Fungsi ini akan membersihkan data lama lalu mengisi kembali data default kamar, user, layanan, dan transaksi kosong.

### 🛏️ Daftar Kamar Default

Total kamar default: **14 kamar**

| Nomor | Tipe | Lantai | Kapasitas | Harga/Malam |
|-------|------|--------|-----------|-------------|
| 101 | Standard | 1 | 2 orang | Rp 450.000 |
| 102 | Standard | 1 | 2 orang | Rp 450.000 |
| 103 | Standard | 1 | 2 orang | Rp 450.000 |
| 104 | Standard | 1 | 3 orang | Rp 550.000 |
| 105 | Standard | 1 | 2 orang | Rp 450.000 |
| 201 | Deluxe | 2 | 2 orang | Rp 750.000 |
| 202 | Deluxe | 2 | 2 orang | Rp 750.000 |
| 203 | Deluxe | 2 | 3 orang | Rp 950.000 |
| 204 | Deluxe | 2 | 2 orang | Rp 850.000 |
| 301 | Suite | 3 | 4 orang | Rp 1.500.000 |
| 302 | Suite | 3 | 4 orang | Rp 1.500.000 |
| 303 | Suite | 3 | 2 orang | Rp 1.800.000 |
| 401 | Presidential | 4 | 6 orang | Rp 5.000.000 |
| 402 | Presidential | 4 | 4 orang | Rp 4.500.000 |

### 👤 Daftar Akun Default

Total akun default: **5 user**

| Username | Password | Nama | Role |
|----------|----------|------|------|
| `manager` | `manager123` | Iqbal ganteng | Manager |
| `resep1` | `resep123` | Adji | Resepsionis |
| `resep2` | `resep456` | zhyla | Resepsionis |
| `hk1` | `hk123` | Nurra | Housekeeping |
| `hk2` | `hk456` | Wira | Housekeeping |

### 🛎️ Daftar Layanan Default

Total layanan default: **10 layanan**

| ID | Nama Layanan | Harga |
|----|--------------|-------|
| `FB-01` | Sarapan Pagi (Buffet) | Rp 85.000 |
| `FB-02` | Room Service 24 Jam | Rp 50.000 |
| `FB-03` | Makan Malam Romantis | Rp 350.000 |
| `SP-01` | Pijat Tradisional | Rp 250.000 |
| `SP-02` | Spa Pasangan | Rp 750.000 |
| `LN-01` | Laundry Express | Rp 50.000 |
| `TR-01` | Antar Jemput Bandara | Rp 200.000 |
| `TR-02` | City Tour Setengah Hari | Rp 350.000 |
| `EN-01` | Karaoke 1 Jam | Rp 150.000 |
| `BS-01` | Sewa Meeting Room | Rp 500.000 |

### 🚪 Status Kamar

Status kamar yang digunakan dalam program:

| Status | Arti |
|--------|------|
| `Kosong` | Kamar tersedia dan bisa dipilih saat check-in |
| `Terisi` | Kamar sedang ditempati tamu |
| `Dipesan` | Status disiapkan di program, tetapi belum ada fitur reservasi pada versi ini |
| `Dibersihkan` | Kamar sudah check-out dan menunggu dibersihkan housekeeping |
| `Maintenance` | Kamar sedang dalam perbaikan |

---

## 🔄 Alur Program

```text
Mulai
  │
  ▼
Set encoding console ke UTF-8
  │
  ▼
Inisialisasi data awal dari kode
  │
  ▼
Tampilkan menu awal
  │
  ├── Login
  │     │
  │     ▼
  │   Input username dan password
  │     │
  │     ├── Gagal 3 kali → kembali ke menu awal
  │     │
  │     └── Berhasil
  │           │
  │           ▼
  │        Cek role user
  │           │
  │           ├── Manager       → Menu Manager
  │           ├── Resepsionis   → Menu Resepsionis
  │           └── Housekeeping  → Menu Housekeeping
  │
  │        Setelah logout
  │           │
  │           ▼
  │        Kembali ke menu awal
  │
  └── Keluar
        │
        ▼
     Tampilkan banner penutup
        │
        ▼
      Selesai
```

### Alur Check-in

```text
Check-in
  │
  ├── Cek batas transaksi
  ├── Tampilkan kamar kosong
  ├── Input nomor kamar
  ├── Validasi kamar harus ada dan statusnya Kosong
  ├── Input nama tamu
  ├── Input KTP 16 digit
  ├── Input nomor HP
  ├── Input lama menginap
  ├── Tambah data tamu jika belum pernah ada
  ├── Buat transaksi aktif
  ├── Ubah status kamar menjadi Terisi
  └── Tampilkan pesan check-in berhasil
```

### Alur Check-out

```text
Check-out
  │
  ├── Input nomor kamar
  ├── Cari transaksi aktif
  ├── Tampilkan struk
  ├── Pilih metode bayar
  │     ├── Tunai
  │     └── QRIS → tampilkan simulasi QRIS
  ├── Ubah transaksi menjadi Selesai
  ├── Ubah kamar menjadi Dibersihkan
  ├── Tambahkan total belanja tamu
  └── Tampilkan struk akhir
```

### Alur Housekeeping

```text
Kamar selesai check-out
  │
  ▼
Status kamar menjadi Dibersihkan
  │
  ▼
Housekeeping memilih "Selesaikan Pembersihan Kamar"
  │
  ▼
Status kamar berubah menjadi Kosong
```

---

## 🚀 Cara Menjalankan

Program ini paling aman dijalankan di **Windows**, karena memakai:

- `<conio.h>` untuk membaca tombol panah dan Enter
- `system("cls")` untuk membersihkan layar
- `system("chcp 65001 > nul")` untuk mengaktifkan karakter UTF-8 di console

### 1. Compile dengan MinGW/g++

Jika nama file masih seperti file yang dikirim:

```bash
g++ -std=c++17 "Pasted code(72).cpp" -o GoTell.exe
```

Jika file sudah diubah namanya menjadi `GoTell.cpp`:

```bash
g++ -std=c++17 GoTell.cpp -o GoTell.exe
```

### 2. Jalankan program

```bash
GoTell.exe
```

> Untuk Linux/Mac, program perlu disesuaikan terlebih dahulu karena `<conio.h>` dan `system("cls")` bersifat khusus Windows.

---

## 📚 Library yang Digunakan

| Library | Fungsi dalam Program | Status |
|---------|----------------------|--------|
| `<iostream>` | Input dan output utama seperti `cin`, `cout`, dan `getline` | Wajib |
| `<iomanip>` | Merapikan tabel dan angka dengan `setw`, `setfill`, `fixed`, `setprecision` | Wajib |
| `<string>` | Menggunakan tipe data `string` dan `to_string` | Wajib |
| `<ctime>` | Mengambil tanggal sekarang untuk dashboard manager | Dipakai |
| `<sstream>` | Membuat format tanggal dengan `ostringstream` | Dipakai |
| `<cstdlib>` | Menjalankan `system("cls")`, `system("chcp 65001 > nul")`, dan `exit(0)` | Dipakai |
| `<thread>` | Membuat animasi loading | Dipakai |
| `<chrono>` | Mengatur jeda waktu animasi loading | Dipakai |
| `<conio.h>` | Mengambil input tombol tanpa Enter memakai `getch()` | Wajib untuk Windows |
| `<vector>` | Menyimpan data utama secara dinamis tanpa array fixed-size | Wajib |

---

## 🧮 Rumus Perhitungan

### Total Pembayaran

```text
biaya kamar = harga kamar per malam × lama menginap
subtotal = biaya kamar + total layanan
pajak = subtotal × 11%
service charge = subtotal × 5%
grand total = subtotal + pajak + service charge
```

Dalam kode, pajak disimpan pada konstanta:

```cpp
const double PAJAK = 0.11;
const double SERVICE_CHARGE = 0.05;
```

### Okupansi Kamar

```text
okupansi = jumlah kamar berstatus Terisi / total kamar × 100%
```

Contoh:

```text
Jika total kamar = 14
Kamar terisi = 3

okupansi = 3 / 14 × 100%
okupansi = 21,4%
```

### Progress Bar Okupansi

Progress bar dibuat dengan lebar 30 karakter.

```text
jumlah blok terisi = persen okupansi × lebar bar / 100
```

Kode juga melakukan pembulatan:

```cpp
int isi = (int)((persen * lebarBar / 100.0) + 0.5);
```

Artinya, jika hasilnya pecahan, jumlah blok akan dibulatkan ke angka terdekat. Jika okupansi lebih dari 0% tetapi hasil blok masih 0, program tetap menampilkan minimal 1 blok agar terlihat ada isi.

---

## ⚠️ Catatan Batasan Program

Versi kode ini sengaja dibuat tanpa file `.txt`, sehingga beberapa hal berikut perlu diperhatikan:

- Data hanya tersimpan selama program masih berjalan.
- Jika program ditutup, data kamar, tamu, layanan, transaksi, dan ID transaksi kembali ke default.
- Program belum memiliki fitur penyimpanan permanen.
- Program belum memiliki fitur reservasi kamar.
- Program belum memiliki fitur pembatalan reservasi.
- Program belum memiliki fitur upgrade/pindah kamar.
- Program belum memiliki fitur mini bar terpisah.
- Program belum memiliki fitur rating/feedback pelanggan.
- Program belum memiliki fitur cetak ulang struk.
- QRIS yang ditampilkan hanya simulasi simbol di console, bukan QRIS asli yang bisa discan untuk pembayaran nyata.
- Status `Dipesan` sudah dikenali di tampilan status, tetapi belum ada proses menu yang mengubah kamar menjadi `Dipesan`.

---

## 👥 Pembagian Tugas Tim (7 Anggota)

Pembagian tugas berikut disesuaikan dengan fungsi yang benar-benar ada pada kode saat ini. Jumlah akun login di program adalah **5 akun**, sedangkan pembagian tugas tetap dibuat untuk **7 anggota tim**.

| # | Anggota | Modul / Tanggung Jawab | Fungsi/Bagian Terkait |
|---|---------|--------------------------|-------------------------|
| 1 | **Iqbal — Project Lead & Core System** | Menyusun pondasi utama program, model data, konstanta global, alur utama, inisialisasi data, dan penghubung antar-role. | `struct Kamar`, `struct Tamu`, `struct Layanan`, `struct Transaksi`, `struct User`, `vector daftarKamar`, `vector daftarUser`, `vector daftarTamu`, `vector daftarLayanan`, `vector daftarTransaksi`, `inisialisasiDataAwal()`, `menuAwal()`, `main()` |
| 2 | **Zhyla — Input Validation & Utility** | Membuat fungsi input aman, validasi nama/KTP/nomor HP/angka, format rupiah, format tanggal, dan ID transaksi. | `cekEOF()`, `trimTeks()`, `bacaTeks()`, `bacaTeksPanjang()`, `semuaAngka()`, `bacaKTP()`, `namaValid()`, `bacaNamaTamu()`, `formatHPValid()`, `bacaNoHP()`, `bacaAngka()`, `formatRupiah()`, `tanggalSekarang()`, `buatID()` |
| 3 | **Adji — UI Console & Navigasi Interaktif** | Membuat tampilan banner, garis/judul, menu kotak, navigasi tombol panah, animasi loading, dan tampilan penutup. | `clearScreen()`, `bacaTombolArah()`, `kotakMenu()`, `hitungLebarKotak()`, `pilihMenuKotak()`, `tungguTombol()`, `animasiLoading()`, `garis()`, `judul()`, `tampilkanBanner()`, `tampilkanPenutup()` |
| 4 | **Nurra — Data Master & Pencarian Pointer** | Mengelola data default kamar, user, layanan, serta fungsi pencarian yang mengembalikan pointer ke data asli. | `tambahKamar()`, `inisialisasiKamarDefault()`, `tambahKamarDefaultJikaBelumAda()`, `pastikanKamarDefaultLengkap()`, `tambahUser()`, `inisialisasiUser()`, `tambahLayanan()`, `inisialisasiLayanan()`, `cariKamar()`, `cariUser()`, `cariTamuByKTP()`, `cariLayanan()`, `cariTransaksiAktif()`, `ambilOrTambahTamu()` |
| 5 | **Wira — Modul Resepsionis & Transaksi** | Mengelola check-in, tambah layanan, check-out, perhitungan total, struk, pembayaran Tunai/QRIS, dan menu resepsionis. | `hitungTotalAkhir()`, `tampilkanKamarTersedia()`, `tampilkanLayanan()`, `cetakStruk()`, `tampilkanLogoQRIS()`, `tampilkanDataQRIS()`, `tampilkanQRISSimbol()`, `tampilkanHeaderQRIS()`, `bacaKamarKosong()`, `prosesCheckIn()`, `prosesTambahLayanan()`, `pilihMetodeBayar()`, `prosesCheckOut()`, `menuResepsionis()` |
| 6 | **Sultan — Modul Housekeeping & Status Kamar** | Mengelola alur pembersihan kamar, maintenance, serta tampilan status kamar. | `warnaStatusKamar()`, `tampilkanSemuaKamar()`, `prosesBersihkanKamar()`, `prosesSetMaintenance()`, `prosesSelesaiMaintenance()`, `menuHousekeeping()` |
| 7 | **Isam — Modul Manager, Dashboard & Statistik** | Membuat dashboard manager, transaksi aktif, laporan pendapatan, statistik okupansi, dan perhitungan ringkasan operasional hotel. | `tampilkanTransaksiAktif()`, `tampilkanBarOkupansi()`, `hitungKamarStatus()`, `hitungTransaksiSelesai()`, `hitungPendapatanSelesai()`, `tampilkanDashboard()`, `tampilkanLaporanPendapatan()`, `tampilkanOkupansi()`, `menuManager()` |

> Saran kerja tim: setiap anggota dapat membuat branch sesuai modulnya, misalnya `feature/resepsionis`, `feature/housekeeping`, `feature/manager`, lalu digabungkan ke branch utama setelah direview.

---

## 📄 Lisensi

Proyek ini dibuat untuk keperluan tugas dan pembelajaran. Bebas digunakan serta dimodifikasi untuk kebutuhan edukasi.

<div align="center">

**GoTell : Smart Hotel Management System**  
Made with ❤️ using C++

</div>
