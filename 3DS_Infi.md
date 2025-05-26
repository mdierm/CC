# 🛡️ Laporan Ringkas Analisis Keamanan

**Topik:** Evaluasi Proses Otentikasi OTP dalam Implementasi 3D Secure oleh Infinitium
**Fokus:** Kerentanan terkait pengiriman OTP tanpa validasi CVV dan potensi eksploitasi melalui rekayasa sosial dan spam OTP

---

## 1. 📌 **Deskripsi Temuan**

### 1.1. **Kondisi Sistem Saat Ini**

* Sistem Infinitium sebagai ACS (Access Control Server) mengirimkan OTP ke nomor telepon yang terdaftar pada kartu kredit meskipun:

  * CVV yang dimasukkan salah,
  * Transaksi tidak pernah benar-benar dimulai oleh pemilik kartu.
* Halaman 3D Secure dapat diakses dan diulang berkali-kali oleh pengguna (atau penyerang) untuk:

  * Mengisi ulang kombinasi nomor kartu dan CVV.
  * Menghasilkan OTP baru tanpa pembatasan.
* OTP berlaku selama 5 menit dan dikirim setiap kali form diulang, tanpa validasi transaksional yang kuat.

### 1.2. **Pola Penyalahgunaan**

* Penyerang dengan data kartu (tanpa CVV) dapat memicu pengiriman OTP ke korban.
* Penyerang kemudian menelepon korban, berpura-pura sebagai pihak bank/merchant, dan meminta OTP.
* Jika korban memberikan OTP, penyerang dapat melanjutkan percobaan dengan brute-force CVV untuk menyelesaikan transaksi.

---

## 2. 🚨 **Risiko Keamanan**

| Risiko                            | Penjelasan                                                                                                                                             |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Abuse OTP**                     | Penyerang dapat memicu pengiriman OTP tanpa batas, menyebabkan spam dan confusi korban.                                                                |
| **Rekayasa Sosial**               | OTP digunakan sebagai umpan dalam serangan phising melalui telepon.                                                                                    |
| **CVV Enumeration (Brute-force)** | Sistem memungkinkan penyerang mencoba berbagai kombinasi CVV tanpa diblokir.                                                                           |
| **Transaksi Berbahaya**           | Jika korban membocorkan OTP, transaksi berpotensi berhasil dengan CVV yang valid ditebak.                                                              |
| **Kelemahan Protokol**            | Sistem menyimpang dari arsitektur EMV 3DS dengan memperlakukan OTP sebagai independent token, tidak dikaitkan ketat dengan session dan transaction ID. |

---

## 3. 📘 **Analisis Terhadap Best Practices**

| Aspek                              | Standar Best Practice (EMVCo / PCI DSS)                                 | Implementasi Saat Ini                             |
| ---------------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------- |
| **Validasi CVV sebelum OTP**       | ❌ Tidak disarankan (berisiko leak informasi)                            | ✅ Dilewati, sesuai                                |
| **Pengiriman OTP**                 | ✅ Hanya setelah validitas minimal terverifikasi & dilindungi rate-limit | ❌ Dapat diulang tanpa batas                       |
| **Keterkaitan OTP dengan session** | ✅ OTP terikat ke transaksi spesifik                                     | ❌ OTP dapat dikirim ulang tanpa session locking   |
| **Mitigasi Social Engineering**    | ✅ Berikan konteks OTP, edukasi pengguna, alert sistem                   | ❌ Tidak ada tampilan informasi transaksi pada OTP |
| **Rate Limiting / Anti-abuse**     | ✅ Penting untuk mencegah brute-force dan spam                           | ❌ Tidak diterapkan atau tidak efektif             |

---

## 4. 🧩 **Rekomendasi Perbaikan**

| Rekomendasi                              | Penjelasan                                                                               |
| ---------------------------------------- | ---------------------------------------------------------------------------------------- |
| 🔒 **Rate Limiting OTP**                 | Batasi OTP maksimum 3 kali per 15 menit per kartu atau nomor.                            |
| 🔗 **Bind OTP ke Session & Transaction** | OTP hanya valid untuk 1 transaksi dan 1 sesi browser.                                    |
| 🧠 **Contextual OTP Message**            | Tambahkan informasi seperti “Transaksi di Merchant A senilai Rp XXX”.                    |
| 🧪 **RBA (Risk-Based Authentication)**   | Gunakan device fingerprint, IP, behavior untuk menentukan apakah OTP dikirim atau tidak. |
| 🧱 **ReCAPTCHA / Anti-bot**              | Tambahkan tantangan CAPTCHA jika sistem mendeteksi pola mencurigakan.                    |
| 📉 **Monitoring Abuse Pattern**          | Buat sistem deteksi dini untuk flow OTP tidak normal.                                    |
| 📚 **Edukasi Pengguna**                  | Kirim notifikasi edukatif tentang penipuan OTP jika terjadi permintaan OTP mendadak.     |

---

## 5. 📝 **Kesimpulan**

Walau pengiriman OTP tanpa validasi CVV terdengar lemah di permukaan, pendekatan ini **sesuai dengan desain standar EMV 3D Secure** untuk mencegah **enumerasi dan kebocoran informasi kartu**. Namun, **kelemahan aktual terletak pada kurangnya proteksi terhadap abuse** dan rekayasa sosial, khususnya:

* Tidak adanya rate limiting.
* Tidak adanya binding OTP terhadap sesi spesifik.
* Tidak adanya proteksi terhadap spam OTP.
* Tidak adanya edukasi atau kontekstualisasi kepada pemilik kartu.

Tanpa mitigasi yang tepat, sistem saat ini **berpotensi dimanfaatkan untuk mencuri OTP dari korban melalui social engineering**, dan oleh karena itu **perlu segera dilakukan perbaikan pada flow pengiriman OTP dan verifikasi 3DS.**

---
