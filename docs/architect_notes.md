# architect_notes.md

<!--
INTERNAL WORKING DOCUMENT FOR SYSTEM ARCHITECT & USER.

STRICT BOUNDARY:
Downstream agents (DB Designer, UI/UX Designer, API Designer, Backend Agent, Frontend Agent)
MUST NOT read this file. It contains exploratory debates, architectural trade-offs,
and rejected options that will cause confusion and hallucinations if loaded into downstream context.
-->

## Purpose

This document serves as the long-term memory, working scratchpad, and Architecture Decision Record (ADR)
for the System Architect and User.

It is strictly divided into two distinct domains to prevent cross-domain confusion:
- **Part A: Backend Architecture**
- **Part B: Frontend Architecture**

---

# PART A: BACKEND ARCHITECTURE

## A1. Backend Debate & Active Working Notes
<!--
Catatan mentah diskusi, eksplorasi stack, dependensi, dan ide arsitektur backend selama sesi debat.
-->

## A2. Backend Architecture Decision Records (ADR Log)
<!--
Keputusan final backend yang disepakati bersama User:

### [ADR-B01] Judul Keputusan Backend
- **Status**: Decided
- **Context**: Kebutuhan/masalah apa yang mendasari keputusan ini?
- **Decision**: Pilihan stack / library / pattern / port yang disepakati.
- **Rationale**: Mengapa opsi ini yang dipilih?
- **Folder Blueprint**: Rencana pola folder modular backend.
-->

## A3. Backend Rejected Alternatives
<!--
Opsi backend yang sempat dipertimbangkan tapi DITOLAK (agar SA tidak menyarankan ulang):
- **Opsi Ditolak**: [Nama Library / Pola]
  - **Alasan Penolakan**: [Alasan User & SA menolak]
-->

## A4. Backend Pending Questions & Open Issues
<!--
Hal-hal teknis backend yang masih menggantung atau butuh klarifikasi lebih lanjut.
-->

---

# PART B: FRONTEND ARCHITECTURE

## B1. Frontend Debate & Active Working Notes
<!--
Catatan mentah diskusi, eksplorasi UI stack, state management, router, dan library selama sesi debat.
-->

## B2. Frontend Architecture Decision Records (ADR Log)
<!--
Keputusan final frontend yang disepakati bersama User:

### [ADR-F01] Judul Keputusan Frontend
- **Status**: Decided
- **Context**: Kebutuhan tampilan / UX / performa yang mendasari keputusan ini?
- **Decision**: Pilihan UI framework / styling / state / port yang disepakati.
- **Rationale**: Mengapa opsi ini yang dipilih?
- **Folder Blueprint**: Rencana pola folder modular frontend (feature-based).
-->

## B3. Frontend Rejected Alternatives
<!--
Opsi frontend yang sempat dipertimbangkan tapi DITOLAK (agar SA tidak menyarankan ulang):
- **Opsi Ditolak**: [Nama Library / Framework / Styling]
  - **Alasan Penolakan**: [Alasan User & SA menolak]
-->

## B4. Frontend Pending Questions & Open Issues
<!--
Hal-hal teknis frontend yang masih menggantung atau butuh klarifikasi lebih lanjut.
-->
