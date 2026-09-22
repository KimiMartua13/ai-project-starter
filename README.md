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
3. DB Designer (docs/schema.dbml)  +  UI/UX Designer (docs/ui_flow.md)
   ↓
4. API Designer (docs/api_contracts.md)
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
| `docs/ui_flow.md` | UI/UX Designer | Struktur halaman, user journey, interaksi, dan state tampilan. |
| `docs/api_contracts.md` | API Designer | Kontrak endpoint, method, payload JSON, status code, dan error. |
| `backend/` | Backend Agent | Source code aplikasi backend. |
| `frontend/` | Frontend Agent | Source code aplikasi frontend. |

---

## 📋 Cheatsheet Prompt (Copy-Paste ke AI)

Cukup panggil AI Anda dengan template prompt berikut di setiap tahapnya:

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
> *"Baca `AGENTS.md`. Kamu bertindak sebagai **UI/UX Designer**. Rancang alur halaman dan state interaksi di `docs/ui_flow.md` berdasarkan `docs/architecture.md` dan batasan di `AGENTS_FRONTEND.md`."*

### 5. Merancang Kontrak API (API Designer)
> *"Baca `AGENTS.md`. Kamu bertindak sebagai **API Designer**. Susun kontrak API lengkap di `docs/api_contracts.md` yang menjembatani `docs/schema.dbml` dan `docs/ui_flow.md`."*

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

## 🛡️ Matriks Isolasi Konteks (Anti-Halusinasi)

Agar AI bekerja cepat dan tidak kelebihan konteks (*context bloat*), masing-masing peran hanya membaca file yang dibutuhkan:

```
System Architect (Backend)   → architecture.md + architect_notes.md (Part A) + diskusi user
System Architect (Frontend)  → architecture.md + AGENTS_BACKEND.md + architect_notes.md (Part B) + diskusi user
DB Designer                  → architecture.md + AGENTS_BACKEND.md
UI/UX Designer               → architecture.md + AGENTS_FRONTEND.md
API Designer                 → architecture.md + schema.dbml + ui_flow.md
Backend Setup Agent          → AGENTS_BACKEND.md
Frontend Setup Agent         → AGENTS_FRONTEND.md
Backend Agent                → AGENTS_BACKEND.md + api_contracts.md + schema.dbml
Frontend Agent               → AGENTS_FRONTEND.md + api_contracts.md + ui_flow.md
```

> **Catatan Penting:** `docs/architect_notes.md` diisolasi khusus untuk SA & User. Agen hilir (DB, UI, Coder) tidak boleh membacanya agar terhindar dari bias alternatif yang sudah dibatalkan.

---

## 🤖 Strategi Pemilihan Model AI & Eskalasi

### 1. Primary Environment: Antigravity IDE (Gemini Models)

| Tahap / Peran Agen | Model Rekomendasi | Keterangan |
| :--- | :--- | :--- |
| **AI System Architect** | `Gemini 3.8 Flash High` | Butuh nalar arsitektur & sintesis kuat |
| **AI DB Designer** | `Gemini 3.8 Flash High` | Butuh akurasi relasi & normalisasi skema |
| **AI UI/UX Designer** | `Gemini 3.8 Flash High` | Butuh perancangan UX flow & state komprehensif |
| **AI API Designer** | `Gemini 3.8 Flash High` | Butuh ketelitian struktur kontrak JSON |
| **AI Backend Coder** | `Gemini 3.8 Flash Medium` *(Default)* | Eksekusi cepat, hemat token, dan akurat |
| **AI Frontend Coder** | `Gemini 3.8 Flash Medium` *(Default)* | Eksekusi cepat, hemat token, dan akurat |

**Troubleshooting & Escalation Ladder (Tangga Eskalasi):**
- Jika `Flash Medium` gagal/stuck $\rightarrow$ Naik ke `Flash High`
- Jika `Flash High` masih gagal $\rightarrow$ Naik ke `Gemini Pro`

---

### 2. Fallback Environment: Codex (Luna Models)
*(Digunakan jika limit di Antigravity IDE atau menggunakan Codex CLI)*

| Tahap / Peran Agen | Model Rekomendasi | Keterangan |
| :--- | :--- | :--- |
| **AI System Architect** | `Luna MAX` | Penalaran arsitektur level tertinggi |
| **AI DB Designer** | `Luna MAX` | Desain skema DBML presisi tinggi |
| **AI UI/UX Designer** | `Luna MAX` | Perancangan interaksi dan state |
| **AI API Designer** | `Luna MAX` | Kontrak API decoupled terstandar |
| **AI Backend Coder** | `Luna HIGH` *(Default)* | Koding backend modular cepat |
| **AI Frontend Coder** | `Luna HIGH` *(Default)* | Koding komponen frontend cepat |

**Troubleshooting & Escalation Ladder (Tangga Eskalasi):**
- Jika `Luna Medium` gagal $\rightarrow$ Naik ke `Luna High`
- Jika `Luna High` gagal $\rightarrow$ Naik ke Model tertinggi (Escalate Model)
