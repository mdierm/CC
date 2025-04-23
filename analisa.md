---

# Laporan Analisis Kebocoran Data Kartu Kredit  
## BIN 451249 – Bank Negara Indonesia (BNI)  
### Disusun oleh: Divisi Enterprise Risk Management (ERM)

### Pendahuluan  
Laporan ini disusun oleh **Divisi Enterprise Risk Management (ERM)** untuk melakukan analisis terhadap potensi kebocoran data kartu kredit yang berawalan **BIN 451249**, yang diterbitkan oleh **Bank Negara Indonesia (BNI)** untuk kartu **Visa Platinum Credit**. Fokus dari laporan ini adalah untuk mengidentifikasi potensi risiko terkait dengan kebocoran data kartu, serta mengevaluasi dampak yang dapat timbul terhadap organisasi, baik dari sisi finansial, operasional, maupun reputasional.

Laporan ini juga mencakup penelusuran mendalam terkait dengan insiden kebocoran data besar yang terjadi dalam **dark web** dan platform terkait, serta mengaitkan kebocoran data kartu dengan potensi penyalahgunaan yang dapat terjadi beberapa bulan setelah kebocoran.

### Metodologi Penelusuran  
Untuk melakukan analisis ini, tim ERM telah melakukan penelusuran menggunakan berbagai sumber, termasuk mesin pencari (Google/Bing), situs paste publik seperti Pastebin, forum **dark web**, serta mesin pencari **OSINT** (Open Source Intelligence) seperti **DeHashed**, **Intelligence X**, dan **Leak-Lookup**. Penelusuran ini bertujuan untuk menemukan data atau jejak nomor kartu **451249********** dan mengidentifikasi potensi kebocoran terkait.

Divisi ERM juga mengembangkan **tools khusus** yang memanfaatkan **jaringan Onion (Tor)** untuk mencari informasi terkait kebocoran data kartu kredit di **dark web**. Tools ini dirancang untuk melakukan pencarian secara lebih mendalam dengan menggabungkan **teknik dorking** untuk menemukan informasi terkait jual beli data, **carding**, dan aktivitas penipuan lainnya yang mungkin terdaftar di platform yang lebih sulit dijangkau oleh pencarian umum.

### Kejadian BidenCash dan B1ack’s Stash  
Sebelum membahas lebih lanjut mengenai kebocoran data kartu kredit, perlu dijelaskan terlebih dahulu dua kejadian besar yang melibatkan kebocoran data kartu dalam skala besar, yaitu **BidenCash** dan **B1ack’s Stash**. Kedua insiden ini memiliki relevansi karena menjadi sumber utama dari kebocoran data kartu yang dapat berisiko bagi pihak-pihak yang terlibat, termasuk **Bank Negara Indonesia (BNI)**.

#### 1. **Kebocoran Data oleh BidenCash**  
**BidenCash** adalah salah satu marketplace carding yang beroperasi di **dark web** dan dikenal karena kebocoran data kartu dalam jumlah besar.  
- **Maret 2023:** BidenCash merilis sekitar **2 juta data kartu** yang dicuri secara gratis di forum gelap sebagai promosi. Data yang bocor mencakup **PAN (Primary Account Number)**, **CVV** (Card Verification Value), dan **tanggal kedaluwarsa** kartu. Informasi ini juga mencakup identitas pemilik kartu dan sering digunakan untuk melakukan transaksi penipuan.
- **Desember 2023:** Insiden serupa terjadi, dengan **1,6 juta data kartu** yang bocor dalam bentuk **plaintext**, yang lebih rentan disalahgunakan.
- **April 2025:** BidenCash kembali merilis **910.380 data kartu** sebagai bagian dari promosi untuk menarik perhatian di pasar gelap.

Meskipun **BIN 451249** (dari BNI) tidak disebutkan secara eksplisit dalam laporan kebocoran ini, mengingat skala besar kebocoran dan distribusi data yang luas, **kemungkinan besar kartu BNI (dengan BIN 451249)** turut terdampak. Terlebih lagi, kartu dengan **BIN 451249** yang merupakan kartu **Visa Platinum Credit** dari BNI sering kali disalahgunakan dalam transaksi penipuan, mengingat data kartu tersebut dicuri melalui teknik **web skimming** atau dari platform yang kurang aman.

#### 2. **Kebocoran Data oleh B1ack’s Stash**  
**B1ack’s Stash** adalah marketplace carding lain yang sangat berbahaya dan beroperasi di **dark web**.  
- **Februari 2025:** B1ack’s Stash merilis **1 juta data kartu** sebagai bagian dari promosi. Data yang bocor mencakup **PAN**, **CVV2**, **tanggal kedaluwarsa**, serta informasi pemilik kartu yang lebih mendalam, seperti nama, alamat, tanggal lahir, email, nomor telepon, dan informasi lainnya.  
- Kebocoran ini mencakup kartu dari berbagai negara, dan meskipun tidak ada data yang teridentifikasi dari **BIN 451249 (BNI)**, sangat mungkin bahwa kartu dari **BNI** turut terdampak mengingat skala kebocoran tersebut.

#### 3. **Relevansi Insiden dengan BIN 451249**  
Berdasarkan kebocoran besar yang terjadi di **BidenCash** dan **B1ack’s Stash**, ada kemungkinan kuat bahwa kartu dengan **BIN 451249** yang diterbitkan oleh **BNI** turut terdampak oleh kebocoran tersebut, meskipun nomor kartu yang spesifik tidak dapat diidentifikasi. Hal ini menandakan bahwa **kartu dengan BIN 451249** berisiko lebih tinggi untuk digunakan dalam transaksi penipuan, mengingat keduanya merupakan platform yang dikenal karena distribusi massal data kartu curian untuk penipuan.

### Analisis Terhadap Kebocoran Data Kartu Kredit  
Divisi ERM melanjutkan dengan menganalisis potensi kebocoran data kartu kredit lebih lanjut, berdasarkan dua insiden besar yang terjadi di **BidenCash** dan **B1ack’s Stash**.

#### 1. **Kebocoran oleh B1ack’s Stash:**  
   Pada **Februari 2025**, **B1ack’s Stash** merilis **1 juta data kartu** sebagai bagian dari strategi promosi mereka. Data yang bocor meliputi informasi lengkap mengenai kartu, seperti **PAN (16 digit)**, **tanggal kedaluwarsa**, **CVV2**, serta informasi sensitif lainnya termasuk nama pemegang kartu, alamat, tanggal lahir, email, nomor telepon, bahkan **IP address dan User-Agent** yang digunakan saat transaksi.  
   Insiden ini sangat relevan karena distribusi data kartu yang bocor mencakup berbagai negara, dan meskipun nomor kartu spesifik dengan **BIN 451249 (BNI)** belum teridentifikasi dalam dump ini, ada kemungkinan besar bahwa kartu BNI turut terdampak mengingat skala kebocoran tersebut.

   **Relevansi Rentan Waktu:**  
   Insiden **B1ack’s Stash** terjadi pada **Februari 2025**, dan kartu dengan **BIN 451249** yang bocor mungkin saja digunakan dalam transaksi yang terjadi pada periode berikutnya. Korelasi ini **mungkin berasal dari insiden kebocoran tersebut**, mengingat adanya transaksi penipuan yang terdeteksi pada **April 2025** yang terjadi pada aplikasi **My XLnAxiata. Hal ini menyoroti pentingnya **rentang waktu** yang dapat terjadi antara kebocoran data dan pemanfaatannya untuk transaksi penipuan. Meskipun kebocoran terjadi beberapa bulan sebelumnya, data kartu yang bocor tetap dapat dimanfaatkan dalam waktu yang lebih lama untuk transaksi yang mencurigakan.

### Riwayat BIN 451249 dalam Forum Underground  
Dalam penelusuran lebih lanjut, **BIN 451249** tercatat sebagai salah satu **BIN cardable** yang sering muncul dalam forum carding underground. Sejak **2017**, **BIN 451249** telah dikenal di kalangan pelaku kejahatan siber sebagai BIN yang **rentan untuk disalahgunakan** dalam transaksi penipuan, terutama pada merchant yang tidak memiliki sistem deteksi penipuan yang ketat.

- **Pastebin (2017)** mencatat **BIN 451249** sebagai **BIN yang digunakan di situs e-commerce** seperti **Agoda**, yang menunjukkan bahwa sejak 2017, kartu BNI sudah dianggap **rentan terhadap carding** di beberapa situs.
- Forum carding di **dark web** juga mencatat **BIN 451249** dalam daftar **“BIN rekomendasi”**, yang menunjukkan bahwa **kartu ini sering digunakan oleh pelaku fraud** untuk melakukan transaksi penipuan.
- **BinCheck** mengonfirmasi bahwa **BIN 451249** adalah **Visa Platinum Credit** yang diterbitkan oleh **BNI**. Ini mengonfirmasi bahwa **BIN ini berasal dari Indonesia** dan sering muncul di forum carding sebagai target transaksi.

### Evaluasi Penyebab Kebocoran Data  
Dari perspektif **Enterprise Risk Management (ERM)**, kebocoran data kartu dengan **BIN 451249** dapat disebabkan oleh beberapa faktor yang berpotensi menjadi sumber kebocoran data. Beberapa kemungkinan penyebab kebocoran data ini meliputi:

1. **Malware Stealer:**  
   Malware stealer, atau perangkat lunak yang dirancang untuk mencuri data kartu dari perangkat pengguna, adalah salah satu penyebab utama kebocoran data kartu. Jenis malware ini sering kali disusupkan melalui lampiran email phishing atau situs web yang tidak aman, malware ini dapat mengumpulkan informasi sensitif seperti nomor kartu, CVV, dan tanggal kedaluwarsa yang kemudian dikirimkan ke server peretas. Kebocoran semacam ini sulit dideteksi sampai transaksi penipuan terjadi.

2. **Web Skimming (Magecart):**  
   **Web skimming** adalah teknik pencurian data yang umum terjadi di situs e-commerce yang telah terinfeksi malware berbasis JavaScript. Malware ini biasanya disisipkan pada halaman pembayaran online untuk mencuri data kartu saat nasabah melakukan transaksi. Dengan cara ini, informasi kartu yang dimasukkan oleh nasabah pada saat melakukan pembelian dapat dicuri dan disalahgunakan. Kejadian ini relevan mengingat beberapa insiden kebocoran besar, seperti yang terjadi pada **B1ack’s Stash**, diyakini berasal dari praktik web skimming.

3. **Pihak Ketiga (Third-Party Breach):**  
   Pihak ketiga yang menyimpan atau memproses data kartu, seperti **payment gateway**, **platform e-commerce**, atau penyedia layanan pembayaran lainnya, juga dapat menjadi sumber kebocoran data kartu.
   
5. **Pihak Internal (Insider Threats):**  
   Di samping ancaman dari luar, risiko dari dalam perusahaan juga harus menjadi perhatian. Individu yang memiliki akses ke data kartu, seperti karyawan di bagian keamanan atau operasional, berpotensi secara sengaja maupun tidak sengaja membocorkan informasi sensitif.

### Rekomendasi Strategis ERM  
Berdasarkan hasil analisis ini, Divisi ERM merekomendasikan langkah-langkah berikut untuk mengelola risiko kebocoran kartu kredit yang berpotensi terjadi:

1. **Pemantauan Dark Web:**  
   Meningkatkan pemantauan secara terus-menerus terhadap forum carding dan **dark web** guna mendeteksi peredaran data kartu yang melibatkan **BIN 451249**.

2. **Penguatan Keamanan Transaksi:**  
   Memastikan bahwa **3D Secure/OTP** diaktifkan untuk semua transaksi kartu yang dilakukan oleh perusahaan. Hal ini dapat membantu mencegah penyalahgunaan meskipun data kartu telah bocor.

3. **Peningkatan Kesadaran dan Pelatihan Karyawan:**  
   Meningkatkan **kesadaran karyawan** tentang bahaya web skimming dan phishing, serta cara mengenali potensi serangan yang bisa mencuri informasi.

4. **Audit dan Penilaian Keamanan Pihak Ketiga:**  
   Melakukan **audit keamanan rutin** terhadap pihak ketiga yang memproses atau menyimpan data kartu untuk memastikan bahwa mereka memenuhi standar keamanan data yang relevan, seperti **PCI DSS**.

5. **Tanggapan Insiden dan Pemulihan:**  
   Menyusun protokol insiden response yang cepat untuk **menggantikan kartu yang bocor** dan melaporkan kebocoran data kepada pihak yang berwenang.

### Kesimpulan  
**BIN 451249** telah diketahui di kalangan pelaku kejahatan kartu kredit sebagai **BIN yang rentan terhadap penyalahgunaan**. Meskipun nomor kartu yang dianalisis tidak ditemukan dalam kebocoran data secara eksplisit, temuan ini menunjukkan bahwa **kartu dengan BIN 451249** berisiko lebih tinggi terkena serangan carding dan penyalahgunaan. Oleh karena itu, sangat penting untuk **memantau peredaran data kartu secara berkelanjutan** dan memastikan langkah-langkah keamanan yang lebih ketat diterapkan untuk melindungi data kartu dari potensi kebocoran.

---
