# 🚀 AI Project Starter

Framework template dan protokol orkestrasi untuk pengembangan software modern berbasis **AI Agent (Spec-Driven Development)**.

Dirancang untuk mencegah **halusinasi AI**, **context bloat**, dan **kode berantakan** dengan menerapkan pemisahan peran (*role isolation*) dan prinsip *Single Source of Truth (SSOT)*.

---

## 🧭 Alur Kerja Pengembangan (Pipeline)

```text
1. User Architecture (docs/architecture.md)
   ↓
2. System Architect (docs/architect_notes.md → AGENTS_BACKEND.md & AGENTS_FRONTEND.md)
   ↓
3. DB Designer (docs/schema.dbml)  +  UI/UX Designer (docs/ui_flow.md: DRAFT → review User → FINAL)
   ↓
4. API Designer (docs/api_contracts.md; hanya setelah UI flow FINAL)
   ↓
5. Setup / Installation (backend/ & frontend/)
   ↓
6. Implementation (Backend Agent & Frontend Agent)
```

---

## 📂 Struktur File & Dokumen

| File / Direktori | Pemilik (Owner) | Fungsi |
| :--- | :--- | :--- |
| `AGENTS.md` | Master Rule | Konstitusi dan aturan batasan bagi setiap peran AI agent. |
| `docs/architecture.md` | **User (Anda)** | Konsep bisnis, kebutuhan klien, stack pilihan, dan ide mentah. |
| `docs/architect_notes.md` | **System Architect & User** | Catatan debat, keputusan ADR, opsi yang ditolak (*private*). |
| `AGENTS_BACKEND.md` | System Architect | Panduan implementasi backend (stack, folder, port, `.env`). |
| `AGENTS_FRONTEND.md` | System Architect | Panduan implementasi frontend (stack, UI library, port, `.env`). |
| `docs/schema.dbml` | DB Designer | Skema database, entitas, primary/foreign keys, dan relasi. |
| `docs/ui_flow.md` | UI/UX Designer | Satu file untuk draft dan hasil final: menu per peran, route, user journey, interaksi, dan state tampilan. API menunggu status FINAL yang disetujui User. |
| `docs/api_contracts.md` | API Designer | Kontrak endpoint, method, payload JSON, status code, dan error. |
| `docs/features.md` | **Feature Agent & User** | Papan pelacakan fitur tambahan/CR (Sedang Dikerjakan & Selesai). |
| `.agents/skills/spec-consistency-review/SKILL.md` | Reviewer spesifikasi | Prosedur pemeriksaan konsistensi spec sebelum checkpoint desain selesai; tunduk pada batas konteks di `AGENTS.md`. |
| `backend/` | Backend Agent | Source code aplikasi backend. |
| `frontend/` | Frontend Agent | Source code aplikasi frontend. |

---

## 📋 Cheatsheet Prompt (Copy-Paste ke AI)

Cukup panggil AI Anda dengan template prompt berikut di setiap tahapnya:

Mulai chat baru saat berganti peran agar konteks dan izin baca dari tugas sebelumnya tidak terbawa. Minta agen mengikuti daftar bacaan perannya di `AGENTS.md` Bagian 3 dan 15, lalu menyebutkan dokumen spesifikasi yang benar-benar dipakai saat menyerahkan hasil.

Skill `spec-consistency-review` tersedia dari `.agents/skills/` setelah template di-clone. API Designer dan Feature Agent menjalankannya sebelum checkpoint desain selesai. Untuk memanggilnya secara eksplisit, gunakan `/spec-consistency-review` di Antigravity atau `$spec-consistency-review` di Codex. Skill ini hanya melaporkan temuan dan tidak menambah izin baca atau mengubah file.

### 1. Sesi 1: Debat Backend & Generate AGENTS_BACKEND.md (Chat 1)
- **Mulai Debat Backend:**
  > *"Baca `AGENTS.md`. Kamu bertindak sebagai **System Architect**. Mari kita bahas arsitektur **BACKEND** saja dulu berdasarkan `docs/architecture.md`. Catat semua kesepakatan dan pertimbangan kita di `docs/architect_notes.md` Bagian A (Backend)."*
- **Kompilasi ke File:**
  > *"Debat backend selesai. Tolong baca kembali `docs/architect_notes.md` Bagian A, lalu buatkan instruksi implementasi final yang rapi di `AGENTS_BACKEND.md`."*

---

### 2. Sesi 2: Debat Frontend & Generate AGENTS_FRONTEND.md (Buka Chat Baru / Chat 2)
*(Membuka chat baru membuat AI bebas dari kebisingan debat backend, cukup membaca `AGENTS_BACKEND.md` yang sudah bersih & matang)*
- **Mulai Debat Frontend:**
  > *"Baca `AGENTS.md`. Kamu bertindak sebagai **System Architect**. Sekarang mari kita bahas arsitektur **FRONTEND** berdasarkan `docs/architecture.md` dan gunakan `AGENTS_BACKEND.md` yang sudah final sebagai acuan port & auth. Catat kesepakatan kita di `docs/architect_notes.md` Bagian B (Frontend)."*
- **Kompilasi ke File:**
  > *"Debat frontend selesai. Tolong baca kembali `docs/architect_notes.md` Bagian B, lalu buatkan instruksi implementasi final yang rapi di `AGENTS_FRONTEND.md`."*

### 3. Merancang Database (DB Designer)
> *"Baca `AGENTS.md`. Kamu bertindak sebagai **DB Designer**. Rancang skema database di `docs/schema.dbml` berdasarkan `docs/architecture.md` dan konvensi di `AGENTS_BACKEND.md`."*

### 4. Merancang Tampilan & Alur (UI/UX Designer)

- **Buat draft yang tersimpan di file:**
  > *"Baca `AGENTS.md`. Kamu bertindak sebagai **UI/UX Designer**. Berdasarkan `docs/architecture.md` dan `AGENTS_FRONTEND.md`, tulis draft menu per peran, hierarki, route, alur pengguna, state interaksi, dan kebutuhan data halaman di `docs/ui_flow.md`. Tandai status `DRAFT` dan persetujuan `BELUM ADA`. Bedakan kebutuhan User dari usulan UI/UX, sebutkan pertanyaan yang belum terjawab, lalu ringkas bagian yang perlu saya tinjau. Jangan tandai FINAL."*

- **Revisi setelah meninjau draft:**
  > *"Sebagai UI/UX Designer, perbaiki draft di `docs/ui_flow.md` berdasarkan masukan saya berikut: [isi masukan]. Pertahankan status DRAFT dan tunjukkan bagian yang berubah serta pertanyaan yang masih terbuka."*

- **Finalisasi hanya setelah Anda benar-benar menyetujui versi draft saat ini:**
  > *"Saya sudah meninjau dan menyetujui draft `docs/ui_flow.md` saat ini. Sebagai UI/UX Designer, pastikan tidak ada pertanyaan atau placeholder yang belum selesai, catat tanggal dan cakupan persetujuan saya di file, lalu ubah statusnya menjadi FINAL."*

Draft tetap tersimpan di `docs/ui_flow.md` meski chat berganti. Bila Anda belum setuju, revisi file yang sama dan biarkan statusnya DRAFT. Perubahan material oleh UI/UX Designer setelah FINAL harus kembali melalui review User; perubahan fitur saat aplikasi sudah berjalan mengikuti protokol Feature Agent.

### 5. Merancang Kontrak API (API Designer)
> *"Baca `AGENTS.md`. Kamu bertindak sebagai **API Designer**. Pastikan `docs/ui_flow.md` berstatus FINAL dan persetujuan User untuk versi saat ini tercatat. Jika belum, berhenti dan laporkan bahwa review UI/UX belum selesai. Jika sudah, susun kontrak API lengkap di `docs/api_contracts.md` berdasarkan `docs/architecture.md`, keputusan backend di `AGENTS_BACKEND.md`, skema di `docs/schema.dbml`, dan kebutuhan layar di `docs/ui_flow.md`."*

### 6. Inisialisasi Proyek & Pembuatan Folder Fisik (Installation Phase)
*(Disarankan dipisah jadi 2 request agar terminal stabil dan tidak timeout)*

#### 6a. Backend Setup
> *"Baca `AGENTS.md` Bagian 10. Kamu bertindak sebagai **Backend Setup Agent**. Inisialisasi framework di `backend/`, buat seluruh struktur folder fisik (`mkdir`) sesuai pohon folder di `AGENTS_BACKEND.md`, install package yang terdaftar, dan siapkan file `backend/.env.example`."*

#### 6b. Frontend Setup
> *"Baca `AGENTS.md` Bagian 10. Kamu bertindak sebagai **Frontend Setup Agent**. Inisialisasi framework di `frontend/`, buat seluruh struktur folder fisik (`mkdir`) sesuai pohon folder di `AGENTS_FRONTEND.md`, install package yang terdaftar, dan siapkan file `frontend/.env.example`."*

### 7. Implementasi Koding (Backend & Frontend)
> *"Baca `AGENTS.md`. Kamu bertindak sebagai **Backend Implementation Agent**. Implementasikan endpoint [Nama Fitur] sesuai kontrak di `docs/api_contracts.md` dan skema di `docs/schema.dbml`."*
>
> *"Baca `AGENTS.md`. Kamu bertindak sebagai **Frontend Implementation Agent**. Implementasikan komponen dan halaman [Nama Fitur] sesuai `docs/ui_flow.md` dan konsumsi data dari `docs/api_contracts.md`."*

---

### 8. Penambahan Fitur Baru / Change Request dari Klien (Feature Agent)
*(Dipakai setelah aplikasi sudah berjalan untuk menangani revisi atau fitur tambahan dari klien)*

- **Skenario A: Masukkan Ide/Permintaan ke Antrean Task Saja (Tanpa Desain Dulu)**
  > *"Baca `AGENTS.md` Bagian 13. Kamu bertindak sebagai **Feature Agent**. Klien meminta fitur tambahan berikut: '[Salin pesan dari klien]'. Tolong catat ke `docs/features.md` di bagian Sedang Dikerjakan, tapi jangan buat desain spec dulu."*

- **Skenario B: Mulai Rancang Revisi Spec (Two-Turn Anti-Halu)**
  > *"Baca `AGENTS.md` Bagian 13. Kamu bertindak sebagai **Feature Agent**. Tolong buatkan draft revisi spec untuk [FEAT-XX]. Sebutkan definisi DB, API, dan UI yang akan berubah serta keputusan yang masih kurang jelas. Tampilkan draft di chat dulu agar saya konfirmasi sebelum kamu menulis ke file."*
  *(Setelah draft disetujui, Feature Agent mengubah hanya definisi terkait di spec yang berlaku, mencatat keputusan di `docs/features.md`, memeriksa diff dan konsistensi DB/API/UI, lalu mencentang `[x] 1. Desain Spec Selesai` jika semua pemeriksaan lulus.)*

- **Skenario C: Koding Fitur (Panggil Backend & Frontend Dev)**
  > *"Baca `AGENTS.md`. Kamu bertindak sebagai **Backend Agent**. Implementasikan endpoint untuk [FEAT-XX] sesuai kontrak terkini di `docs/api_contracts.md`."*
  > *"Baca `AGENTS.md`. Kamu bertindak sebagai **Frontend Agent**. Implementasikan tampilan dan koneksi data untuk [FEAT-XX] sesuai alur terkini di `docs/ui_flow.md`."*

- **Skenario D: Tandai Fitur Selesai & Pindahkan Task**
  > *"Baca `AGENTS.md` Bagian 13. Kamu bertindak sebagai **Feature Agent**. Implementasi koding untuk [FEAT-XX] sudah selesai dan diverifikasi. Tolong centang checklist nomor 2 dan pindahkan blok fitur ini ke bagian Fitur Selesai di `docs/features.md`."*

---

## 🛡️ Matriks Isolasi Konteks (Anti-Halusinasi)

Agar AI bekerja cepat dan tidak kelebihan konteks (*context bloat*), masing-masing peran hanya membaca file yang dibutuhkan:

```
System Architect (Backend)   → architecture.md + architect_notes.md (Part A) + diskusi user
System Architect (Frontend)  → architecture.md + AGENTS_BACKEND.md + architect_notes.md (Part B) + diskusi user
DB Designer                  → architecture.md + AGENTS_BACKEND.md
UI/UX Designer               → architecture.md + AGENTS_FRONTEND.md
API Designer                 → architecture.md + AGENTS_BACKEND.md + schema.dbml + ui_flow.md
Backend Setup Agent          → AGENTS_BACKEND.md
Frontend Setup Agent         → AGENTS_FRONTEND.md
Backend Agent                → AGENTS_BACKEND.md + api_contracts.md + schema.dbml
Frontend Agent               → AGENTS_FRONTEND.md + api_contracts.md + ui_flow.md
Feature Agent                → features.md + AGENTS_BACKEND.md + AGENTS_FRONTEND.md + (schema.dbml / ui_flow.md / api_contracts.md)
```

> **Catatan Penting:** `docs/architect_notes.md` diisolasi khusus untuk SA & User. Agen hilir (DB, UI, Coder, Feature Agent) tidak boleh membacanya agar terhindar dari bias alternatif yang sudah dibatalkan.

---

## 🤖 Pilihan Model per Agent

Rekomendasi berikut adalah **panduan pemilihan**, bukan aturan yang mengubah tanggung jawab atau izin baca/tulis di `AGENTS.md`. Penilaian dibuat pada **24 September 2026** dari tugas setiap peran di repo ini dan dokumentasi resmi model. Ketersediaan model dan batas pemakaian dapat berubah; periksa pemilih model pada akun Anda sebelum memulai proyek baru.

- **Minimum:** pilihan terendah yang masih layak ketika spesifikasi sudah jelas dan tugas dibatasi dengan baik. Untuk pekerjaan yang luas, gunakan kolom Recommendation.
- **Recommendation:** pilihan awal untuk pekerjaan normal; pertimbangan utama adalah kualitas hasil dibanding waktu dan penggunaan model.
- **Safety:** naikkan ke pilihan ini untuk spesifikasi yang saling bertentangan, aturan bisnis rumit, perubahan lintas banyak dokumen, atau kesalahan yang akan merambat ke tahap berikutnya. Ini menambah ruang penalaran, bukan jaminan bebas halusinasi.

### Google Antigravity — Gemini

| Agent | Minimum | Recommendation | Safety |
| :--- | :--- | :--- | :--- |
| System Architect — backend | Gemini 3.7 Flash · Medium | **Gemini 3.8 Flash · Medium** | Gemini 3.8 Flash · High |
| System Architect — frontend | Gemini 3.7 Flash · Medium | **Gemini 3.8 Flash · Medium** | Gemini 3.8 Flash · High |
| DB Designer | Gemini 3.7 Flash · Medium | **Gemini 3.8 Flash · Medium** | Gemini 3.8 Flash · High |
| UI/UX Designer | Gemini 3.6 Flash · Medium | **Gemini 3.8 Flash · Medium** | Gemini 3.8 Flash · High |
| API Designer | Gemini 3.7 Flash · Medium | **Gemini 3.8 Flash · Medium** | Gemini 3.8 Flash · High |
| Installation Agent — backend | Gemini 3.6 Flash · Medium | **Gemini 3.7 Flash · Medium** | Gemini 3.8 Flash · Medium |
| Installation Agent — frontend | Gemini 3.6 Flash · Medium | **Gemini 3.7 Flash · Medium** | Gemini 3.8 Flash · Medium |
| Backend Implementation Agent | Gemini 3.7 Flash · Medium | **Gemini 3.8 Flash · Medium** | Gemini 3.8 Flash · High |
| Frontend Implementation Agent | Gemini 3.7 Flash · Medium | **Gemini 3.8 Flash · Medium** | Gemini 3.8 Flash · High |
| Feature Agent | Gemini 3.7 Flash · Medium | **Gemini 3.8 Flash · Medium** | Gemini 3.8 Flash · High |

Gemini 3.8 Flash Medium cocok sebagai titik awal untuk coding dan alur agent. Gunakan High ketika perlu menimbang banyak aturan sekaligus atau menelusuri konflik. Gemini 3.7 Flash dapat menjadi pilihan untuk pekerjaan yang lebih terarah; 3.6 Flash cukup untuk setup yang mengikuti panduan arsitektur final. Tingkat High bisa memakai lebih banyak waktu dan token. **Jangan gunakan Gemini Pro sebagai jalur eskalasi dalam template ini.** Rujukan: [model yang tersedia di Antigravity](https://www.antigravity.google/docs/models/), [pilihan model dan effort di Antigravity](https://www.antigravity.google/docs/cli/headless/), dan [panduan Gemini 3.8 Flash](https://ai.google.dev/gemini-api/docs/latest-model).

### Codex — GPT

| Agent | Minimum | Recommendation | Safety |
| :--- | :--- | :--- | :--- |
| System Architect — backend | GPT-6 Sol · Medium | **GPT-6 Sol · High** | GPT-6 Astra · Medium |
| System Architect — frontend | GPT-6 Sol · Medium | **GPT-6 Sol · High** | GPT-6 Astra · Medium |
| DB Designer | GPT-6 Sol · Medium | **GPT-6 Sol · High** | GPT-6 Astra · Medium |
| UI/UX Designer | GPT-6 Sol · Low | **GPT-6 Sol · Medium** | GPT-6 Sol · High |
| API Designer | GPT-6 Sol · Medium | **GPT-6 Sol · High** | GPT-6 Astra · High |
| Installation Agent — backend | GPT-6 Luna · Medium | **GPT-6 Sol · Low** | GPT-6 Sol · Medium |
| Installation Agent — frontend | GPT-6 Luna · Medium | **GPT-6 Sol · Low** | GPT-6 Sol · Medium |
| Backend Implementation Agent | GPT-6 Sol · Low | **GPT-6 Sol · Medium** | GPT-6 Sol · High |
| Frontend Implementation Agent | GPT-6 Sol · Low | **GPT-6 Sol · Medium** | GPT-6 Sol · High |
| Feature Agent | GPT-6 Sol · Medium | **GPT-6 Sol · High** | GPT-6 Astra · Medium |

Sol adalah pilihan utama Codex untuk coding serta pekerjaan yang membutuhkan penilaian. Luna cocok untuk setup rutin yang spesifikasinya sudah final, tetapi bukan pilihan awal untuk keputusan arsitektur, skema, atau kontrak API. Astra disimpan untuk persoalan desain paling rumit agar biaya dan waktu tetap sebanding dengan dampak tugas. Tingkat `xhigh` atau `max` tidak perlu menjadi default; coba hanya jika hasil pada tugas nyata menunjukkan manfaat dibanding `medium` atau `high`. Rujukan: [OpenAI Docs tentang pemilihan model](https://developers.openai.com/api/docs/guides/model-selection), [Codex untuk pembuatan kode](https://developers.openai.com/api/docs/guides/code-generation), dan [tingkat reasoning OpenAI](https://developers.openai.com/api/docs/guides/reasoning).

### Cara memakai pilihan ini

1. Mulai dari **Recommendation** untuk satu tugas/peran dan periksa hasil terhadap sumber kebenaran serta *Definition of Done* di `AGENTS.md`.
2. Jika tugas hanya setup yang sudah diputuskan atau perubahan kode kecil dengan kontrak lengkap, **Minimum** dapat dipakai. Feature Agent yang **hanya mengantrekan permintaan** juga cukup memakai Gemini 3.6 Flash Medium atau GPT-6 Luna Medium; pilihan tabel Feature Agent berlaku untuk revisi spesifikasi.
3. Jika ditemukan konflik atau keputusan penting yang belum dijawab, **berhenti dan minta keputusan User** sesuai Zero-Assumption Protocol. Ganti model ke **Safety** jika setelah kejelasan diperoleh tugasnya tetap sulit; model lebih kuat tidak boleh mengarang keputusan yang belum ada.
4. Untuk API Designer dan Feature Agent, jalankan `spec-consistency-review` sebelum menandai desain selesai. Skill ini adalah **pemeriksaan**, bukan agent tambahan atau pengganti persetujuan keputusan. Untuk pemeriksaan rumit, gunakan Gemini 3.8 Flash High atau GPT-6 Sol High; naikkan ke GPT-6 Astra Medium jika konflik masih sulit dianalisis.

Harga API dan kuota aplikasi adalah hal berbeda. Pada harga pengantar API Google hingga akhir 2026, Gemini 3.6, 3.7, dan 3.8 Flash mempunyai tarif token dasar yang sama, tetapi total token suatu tugas dapat berbeda. Pilihan di atas tidak mengasumsikan biaya Antigravity atau Codex sama dengan tagihan API. Lihat [harga Gemini API](https://ai.google.dev/gemini-api/docs/pricing) dan [harga OpenAI API](https://developers.openai.com/api/docs/pricing) jika memakai API secara langsung.
