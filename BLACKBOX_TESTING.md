# Blackbox Testing Report: Restaurant POS System 🧪

Dokumen ini merangkum hasil pengujian fungsional (Blackbox Testing) untuk memastikan seluruh fitur berjalan sesuai spesifikasi tanpa kegagalan.

## 1. Modul Autentikasi & Keamanan
| ID | Fitur | Langkah Pengujian | Hasil yang Diharapkan | Status |
|:---|:---|:---|:---|:---:|
| TC-AUTH-01 | Login Owner | Input email & password valid owner | Masuk ke Dashboard Admin | ✅ PASS |
| TC-AUTH-02 | Login Staff | Input email & password valid staff | Masuk ke Dashboard Pesanan | ✅ PASS |
| TC-AUTH-03 | Login Invalid | Input email/password salah | Muncul pesan error "Login Gagal" | ✅ PASS |
| TC-AUTH-04 | Proteksi Route | Akses dashboard tanpa login | Dialihkan (redirect) ke halaman Login | ✅ PASS |

## 2. Modul Menu & Katalog (Owner)
| ID | Fitur | Langkah Pengujian | Hasil yang Diharapkan | Status |
|:---|:---|:---|:---|:---:|
| TC-MENU-01 | Tambah Menu | Isi Form Menu + Upload Foto | Menu baru muncul di daftar & katalog | ✅ PASS |
| TC-MENU-02 | Edit Menu | Ubah harga atau status ketersediaan | Data terupdate secara real-time | ✅ PASS |
| TC-MENU-03 | Hapus Menu | Klik hapus pada salah satu item | Item hilang dari database & UI | ✅ PASS |

## 3. Modul Pemesanan (Customer)
| ID | Fitur | Langkah Pengujian | Hasil yang Diharapkan | Status |
|:---|:---|:---|:---|:---:|
| TC-ORD-01 | Scan QR | Akses URL dengan parameter meja | Nomor meja terdeteksi otomatis | ✅ PASS |
| TC-ORD-02 | Tambah Keranjang | Pilih beberapa menu & kuantitas | Keranjang menghitung total harga | ✅ PASS |
| TC-ORD-03 | Checkout | Klik tombol Pesan / Order | Pesanan muncul di Dashboard Staff | ✅ PASS |

## 4. Modul Pembayaran (Midtrans)
| ID | Fitur | Langkah Pengujian | Hasil yang Diharapkan | Status |
|:---|:---|:---|:---|:---:|
| TC-PAY-01 | Generate Snap | Klik "Bayar" pada pesanan | Muncul popup/Snap UI Midtrans | ✅ PASS |
| TC-PAY-02 | Pembayaran QRIS | Scan & bayar via simulator | Status berubah jadi "Paid" otomatis | ✅ PASS |
| TC-PAY-03 | Webhook Sync | Pembayaran sukses di Midtrans | Database update status tanpa refresh | ✅ PASS |

## 5. Modul Dashboard & Laporan (Owner)
| ID | Fitur | Langkah Pengujian | Hasil yang Diharapkan | Status |
|:---|:---|:---|:---|:---:|
| TC-REP-01 | Sinkronisasi Tgl | Buat pesanan di pagi hari/malam | Data masuk ke tanggal yang benar | ✅ PASS |
| TC-REP-02 | Grafik Penjualan | Filter laporan harian/mingguan | Grafik menampilkan data yang akurat | ✅ PASS |
| TC-REP-03 | Ringkasan Jam | Lihat detail penjualan hari ini | Muncul statistik per jam | ✅ PASS |

## 6. Manajemen Staff
| ID | Fitur | Langkah Pengujian | Hasil yang Diharapkan | Status |
|:---|:---|:---|:---|:---:|
| TC-STF-01 | Registrasi Staff | Owner mendaftarkan email staff | Akun berhasil dibuat & bisa login | ✅ PASS |
| TC-STF-02 | Update Order | Staff mengubah status ke 'Ready' | Customer melihat update status | ✅ PASS |

---
**Kesimpulan Pengujian:**  
Seluruh fitur utama telah diuji dengan metode input-output (Blackbox) dan dinyatakan **100% Berhasil (Passed)**. Sistem siap digunakan untuk lingkungan Produksi.
