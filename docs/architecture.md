# Kebutuhan dan Arsitektur Awal Proyek

**Status pengisian:** BELUM DIISI

Dokumen ini diisi oleh pemilik proyek sebagai masukan untuk konsultasi dengan System Architect. Tulis fakta bisnis, kebutuhan, pilihan teknis, dan batasan yang sudah diketahui. Dokumen ini tidak menggantikan `AGENTS_BACKEND.md`, `AGENTS_FRONTEND.md`, `docs/schema.dbml`, `docs/ui_flow.md`, atau `docs/api_contracts.md`.

## Cara mengisi

- Ganti setiap `[isi]` dengan jawaban proyek. Tambah atau duplikasi blok fitur, data, dan integrasi sesuai kebutuhan.
- Tulis `Perlu dibahas` untuk keputusan yang belum dibuat. Jelaskan pilihan, kekhawatiran, atau batasannya jika sudah ada. Tulis `N/A` jika suatu butir memang tidak berlaku.
- Bedakan pilihan teknis yang **wajib**, **preferensi**, dan **dilarang**. Jangan menyajikan preferensi sebagai keputusan final.
- Ubah status menjadi `SIAP KONSULTASI` setelah tujuan proyek, pengguna, fitur dan alur utama, serta batasan yang sudah diketahui terisi. Keputusan lain boleh tetap `Perlu dibahas` untuk diselesaikan bersama System Architect. Ubah status menjadi `SIAP DESAIN` hanya setelah pertanyaan yang memengaruhi desain atau implementasi terjawab dan panduan arsitektur backend/frontend sudah disepakati.
- Jangan tulis kata sandi, token, private key, atau nilai rahasia di dokumen ini. Tuliskan nama variabel atau cara penyimpanannya saja.

## 1. Identitas, tujuan, dan batas proyek

- **Nama proyek:** [isi]
- **Ringkasan produk dan masalah yang diselesaikan:** [isi]
- **Hasil yang diharapkan dan ukuran keberhasilannya:** [isi]
- **Pemilik keputusan dan pihak yang perlu menyetujui perubahan:** [isi]
- **Tahap proyek dan kondisi awalnya:** [isi]
- **Kondisi sistem, data, atau layanan yang sudah ada dan harus dipertahankan:** [isi]
- **Cakupan rilis pertama dan prioritasnya:** [isi]
- **Hal yang secara tegas di luar cakupan rilis pertama:** [isi]
- **Batasan waktu, biaya, lisensi, kebijakan organisasi, atau kewajiban lain:** [isi]
- **Kriteria proyek dianggap siap dipakai:** [isi]

## 2. Pengguna, akses, dan aturan bisnis lintas fitur

- **Kelompok pengguna dan tujuan masing-masing:** [isi]
- **Peran serta hak setiap peran untuk melihat, membuat, mengubah, menghapus, menyetujui, atau mengunduh data:** [isi]
- **Aktivitas yang boleh dilakukan tanpa masuk akun:** [isi]
- **Cara akun dibuat, diaktifkan, diubah, ditangguhkan, dan dihapus:** [isi]
- **Kebutuhan masuk akun, pemulihan akses, sesi, dan faktor keamanan tambahan:** [isi]
- **Kepemilikan serta batas akses data antar pengguna, tim, organisasi, atau pelanggan:** [isi]
- **Aturan persetujuan, perubahan status, batas waktu, dan pengecualian yang berlaku lintas fitur:** [isi]
- **Tindakan yang harus meninggalkan riwayat atau jejak audit:** [isi]
- **Istilah bisnis yang perlu digunakan konsisten di seluruh proyek:** [isi]

## 3. Kebutuhan fitur dan alur bisnis

Duplikasi blok ini untuk setiap fitur atau alur bisnis yang berbeda. Uraikan perilaku yang diinginkan; rincian layar, tabel, dan endpoint akan dirancang pada dokumen turunannya.

### Fitur: [isi nama dan identitas fitur]

- **Tujuan, nilai, dan prioritas/rilis:** [isi]
- **Aktor yang terlibat dan batas hak aksesnya:** [isi]
- **Pemicu dan prasyarat:** [isi]
- **Urutan kerja normal dari awal sampai selesai:** [isi]
- **Data yang dimasukkan, ditampilkan, diubah, atau dihasilkan:** [isi]
- **Aturan validasi bisnis dan kondisi yang menolak tindakan:** [isi]
- **Perubahan status/data dan dampaknya pada fitur lain:** [isi]
- **Pilihan pengguna, pembatalan, koreksi, dan pengulangan tindakan:** [isi]
- **Kondisi tanpa data, gagal, timeout, atau proses sebagian berhasil:** [isi]
- **Kebutuhan persetujuan, notifikasi, pekerjaan tertunda, atau proses terjadwal:** [isi]
- **Ketergantungan pada fitur, data, atau sistem lain:** [isi]
- **Hasil yang harus dapat diuji sebagai tanda fitur selesai:** [isi]

## 4. Data dan aturan penyimpanannya

Duplikasi blok ini untuk setiap konsep data bisnis. Jelaskan makna dan aturannya; desain tabel, kolom teknis, dan indeks menjadi tanggung jawab DB Designer.

### Data bisnis: [isi nama dan identitas data]

- **Arti data dan fitur yang menggunakannya:** [isi]
- **Atribut bisnis yang perlu dicatat serta mana yang wajib atau opsional:** [isi]
- **Nilai yang dibatasi, aturan keunikan, dan aturan perhitungan:** [isi]
- **Hubungan dengan data lain, jumlah hubungan, serta siapa yang memiliki data:** [isi]
- **Cara data dibuat, berubah status, diarsipkan, dan dihapus:** [isi]
- **Akibat bisnis ketika data terkait dihapus atau dipulihkan:** [isi]
- **Kebutuhan riwayat perubahan, audit, retensi, dan pemusnahan:** [isi]
- **Data pribadi/rahasia dan pembatasan aksesnya:** [isi]
- **Perkiraan jumlah data, pertumbuhan, pencarian, filter, dan laporan yang diperlukan:** [isi]

- **Aturan data yang berlaku lintas beberapa konsep data:** [isi]
- **Sumber data awal, impor, ekspor, atau migrasi yang diperlukan:** [isi]

## 5. Kebutuhan antarmuka dan pengalaman pengguna

- **Perangkat, ukuran layar, browser, dan platform yang harus didukung:** [isi]
- **Tugas utama setiap peran dan urutan pengguna menyelesaikannya:** [isi]
- **Halaman atau area yang wajib ada jika sudah menjadi keputusan:** [isi]
- **Batasan navigasi, pencarian, filter, pengurutan, dan paginasi dari sisi pengguna:** [isi]
- **Data yang perlu dilihat atau diedit pada tiap tugas utama:** [isi]
- **Kebutuhan formulir, validasi yang terlihat, konfirmasi, dan pencegahan aksi ganda:** [isi]
- **Kebutuhan unggah, unduh, pratinjau, cetak, atau visualisasi data:** [isi]
- **Perilaku yang diharapkan saat memuat, tidak ada data, berhasil, gagal, atau koneksi terputus:** [isi]
- **Kebutuhan tata letak responsif, aksesibilitas, bahasa, format tanggal/angka, dan zona waktu:** [isi]
- **Kebutuhan identitas visual, aset, desain yang sudah ada, dan batasan konten:** [isi]
- **Kebutuhan halaman publik, keterindeksan mesin pencari, atau berbagi tautan:** [isi]

## 6. Pilihan dan batasan teknis backend

- **Bahasa, runtime, framework, serta versi yang dipilih atau dipertimbangkan:** [isi]
- **Status tiap pilihan di atas (wajib/preferensi/dilarang) dan alasannya:** [isi]
- **Pengelola paket, kebijakan versi, dan batasan lisensi dependensi:** [isi]
- **Pola modul/folder, pemisahan tanggung jawab, atau aturan kode yang wajib diikuti:** [isi]
- **Strategi autentikasi, masa berlaku sesi/token, dan otorisasi:** [isi]
- **Cara frontend dan backend berkomunikasi serta batasan protokol, versi API, atau format data:** [isi]
- **Konvensi penamaan properti, penanganan kesalahan, dan format respons yang sudah diwajibkan:** [isi]
- **Kebutuhan pekerjaan latar, antrean, penjadwalan, retry, serta konsekuensi jika gagal:** [isi]
- **Kebutuhan cache, pencarian, komunikasi real time, email, dan notifikasi:** [isi]
- **Kebutuhan penyimpanan serta pemrosesan berkas pada sisi server:** [isi]
- **Paket/library wajib, preferensi, atau dilarang; sebutkan tujuan dan batasan versinya:** [isi]
- **Standar pengujian, kualitas kode, dan target kompatibilitas backend:** [isi]

## 7. Pilihan dan batasan teknis database

- **Mesin database dan versi yang dipilih atau dipertimbangkan beserta status pilihannya:** [isi]
- **Lokasi database untuk pengembangan dan produksi serta batasan penyedia layanan:** [isi]
- **Konvensi ID, primary key, foreign key, nama tabel/kolom, dan panjang pengenal jika diwajibkan:** [isi]
- **Konvensi timestamp, zona waktu, soft delete, serta kebijakan penghapusan fisik:** [isi]
- **Aturan transaksi, integritas, cascading, dan pencatatan riwayat yang diwajibkan:** [isi]
- **ORM, migrasi, seeder, dan batasan query yang dipilih atau dilarang:** [isi]
- **Target kapasitas, kinerja pencarian, serta kebutuhan indeks yang sudah diketahui:** [isi]
- **Kebutuhan cadangan, pemulihan, lokasi data, dan masa simpan:** [isi]

## 8. Pilihan dan batasan teknis frontend

- **Bahasa, framework, serta versi yang dipilih atau dipertimbangkan:** [isi]
- **Status tiap pilihan di atas (wajib/preferensi/dilarang) dan alasannya:** [isi]
- **Pengelola paket, kebijakan versi, dan batasan lisensi dependensi:** [isi]
- **Strategi rendering, routing, halaman publik, dan SEO:** [isi]
- **Library UI, cara styling, komponen, aset, dan design system:** [isi]
- **Pemisahan state lokal/server, penyimpanan sementara, dan sinkronisasi data:** [isi]
- **Konvensi formulir, validasi pada klien, serta pesan kesalahan:** [isi]
- **Konvensi klien API, alamat API, penyimpanan kredensial, dan penanganan sesi habis:** [isi]
- **Pola modul/folder, pemakaian ulang komponen, dan batasan kode yang diwajibkan:** [isi]
- **Paket/library wajib, preferensi, atau dilarang; sebutkan tujuan dan batasan versinya:** [isi]
- **Standar pengujian, kualitas kode, dan target build/browser:** [isi]

## 9. Kebutuhan API, integrasi, dan berkas

- **Konsumen API selain frontend proyek ini, jika ada:** [isi]
- **Batasan path dasar, versi, protokol, format payload, dan cara klien mengenali kesalahan:** [isi]
- **Kebutuhan pencarian, filter, pengurutan, paginasi, dan pembatasan permintaan:** [isi]
- **Kebutuhan unggah: siapa boleh mengunggah, tujuan, jenis berkas, ukuran/jumlah maksimum, validasi, lokasi dan masa simpan, serta penanganan gagal:** [isi]
- **Kebutuhan unduh: siapa boleh mengunduh, sumber isi berkas, cakupan data/filter, format, nama berkas, kondisi tanpa data, ukuran, dan masa berlaku akses:** [isi]
- **Pembuatan berkas unduhan langsung atau lewat proses tertunda, serta cara pengguna mengetahui hasilnya:** [isi]
- **Kebutuhan pratinjau atau respons khusus di luar respons JSON biasa:** [isi]
- **Kebutuhan webhook, callback, atau komunikasi antarsistem:** [isi]

Duplikasi blok ini untuk setiap layanan luar. Jika tidak ada, tulis `N/A`.

### Integrasi eksternal: [isi nama layanan]

- **Tujuan dan fitur yang bergantung padanya:** [isi]
- **Data yang dikirim/diterima serta arah perpindahannya:** [isi]
- **Cara autentikasi, pemilik akun, lingkungan uji/produksi, dan lokasi penyimpanan rahasia:** [isi]
- **Batasan layanan, biaya, rate limit, timeout, serta perilaku saat layanan gagal:** [isi]
- **Kebutuhan sinkronisasi, webhook, retry, dan pencatatan hasil:** [isi]

## 10. Server, lingkungan, dan deployment

- **Lingkungan yang diperlukan dan perbedaan konfigurasi masing-masing:** [isi]
- **Penyedia hosting/server dan model pengelolaannya:** [isi]
- **Sistem operasi server serta batasan CPU, memori, disk, dan jaringan:** [isi]
- **Penempatan frontend, backend, database, penyimpanan berkas, dan layanan pendukung:** [isi]
- **Web server/reverse proxy, process manager, atau container yang wajib/preferensi/dilarang:** [isi]
- **Domain/subdomain, HTTPS/TLS, akses jaringan, firewall, dan batasan lokasi server:** [isi]
- **Port frontend, backend, database, dan layanan lain pada tiap lingkungan:** [isi]
- **Alamat frontend, base URL API, dan origin CORS pada tiap lingkungan:** [isi]
- **Nama variabel lingkungan yang diwajibkan, kepemilikan rahasia, dan isi yang perlu dicontohkan di `.env.example`:** [isi]
- **Konfigurasi database, storage, email, cache, dan queue untuk tiap lingkungan:** [isi]
- **Cara build, rilis, migrasi database, rollback, dan CI/CD yang diinginkan:** [isi]
- **Kebutuhan proses latar, restart, penskalaan, dan batas downtime saat rilis:** [isi]

## 11. Kualitas, keamanan, dan operasi

- **Perkiraan jumlah pengguna aktif, trafik puncak, dan pertumbuhan data:** [isi]
- **Target waktu respons, kapasitas, ketersediaan, dan batas gangguan yang dapat diterima:** [isi]
- **Jenis data sensitif, kewajiban privasi, enkripsi, penghapusan, dan aturan kepatuhan yang berlaku:** [isi]
- **Ancaman atau penyalahgunaan yang perlu dicegah serta batas keamanan khusus:** [isi]
- **Kebutuhan log, metrik, alert, audit, dan siapa yang menindaklanjutinya:** [isi]
- **Frekuensi backup, target pemulihan, dan penanggung jawab pemulihan:** [isi]
- **Jenis pengujian yang diwajibkan dan kasus gagal/tepi yang paling penting:** [isi]
- **Kriteria penerimaan nonfungsional yang bisa diperiksa:** [isi]

## 12. Keputusan terbuka dan catatan pemilik proyek

- **Keputusan yang sudah final dan tidak boleh diubah tanpa persetujuan:** [isi]
- **Pilihan yang masih berupa preferensi dan trade-off yang ingin dibahas:** [isi]
- **Pertanyaan untuk System Architect, termasuk pilihan dan dampaknya bila sudah diketahui:** [isi]
- **Konflik, risiko, asumsi yang perlu diuji, dan pihak yang dapat menjawabnya:** [isi]
- **Catatan tambahan dari pemilik proyek:** [isi]
