# AI Skills & Persona Collection

**Creator: Grownie Studio**

Kumpulan **skill** dan **persona** untuk berbagai **AI agent** dan **AI chat** — mulai dari OpenCode, Claude Code, Cursor, Windsurf, GitHub Copilot, Codex, Gemini CLI, hingga ChatGPT, Claude, Gemini, Copilot, dan aplikasi chat lain di **browser, desktop, maupun mobile**.

Setiap skill membawa identitas, standar kerja, checklist, dan format deliverable yang konsisten, sehingga AI dapat bekerja seperti spesialis di bidangnya — bukan sekadar menjawab secara generik. Isinya berupa Markdown yang **portabel**: dapat dipakai sebagai skill file, rules proyek, system prompt, custom instructions, project knowledge, atau Gem tergantung platform yang Anda gunakan.

Repositori ini cocok dipakai sebagai:

- **Lapisan keahlian** untuk AI coding agent sehari-hari (backend, frontend, mobile, database, DevOps).
- **Standar tim** untuk review kode, arsitektur, dan handoff desain.
- **Persona siap pakai** untuk AI chat di browser, desktop, atau aplikasi.
- **Referensi prompt** yang bisa disesuaikan dengan konvensi proyek masing-masing.
- **Titik awal** bagi creator yang ingin membangun koleksi skill sendiri.

---

## Daftar Isi

- [Informasi Proyek](#informasi-proyek)
- [Untuk Creator: Informasi yang Dibutuhkan](#untuk-creator-informasi-yang-dibutuhkan)
- [Quick Start](#quick-start)
- [Prasyarat](#prasyarat)
- [Daftar Skill](#daftar-skill)
- [Struktur Direktori](#struktur-direktori)
- [Anatomi Skill](#anatomi-skill)
- [Cara Kerja Skill](#cara-kerja-skill)
- [Portabilitas & Platform](#portabilitas--platform)
- [Adaptasi ke Platform Lain](#adaptasi-ke-platform-lain)
- [Panduan Menulis Deskripsi](#panduan-menulis-deskripsi)
- [Alur Kerja Authoring](#alur-kerja-authoring)
- [Testing & Validasi](#testing--validasi)
- [Detail Skill](#detail-skill)
  - [backend-architect](#backend-architect)
  - [code-reviewer](#code-reviewer)
  - [database-optimizer](#database-optimizer)
  - [devops-automator](#devops-automator)
  - [flutter](#flutter)
  - [frontend-dev](#frontend-dev)
  - [laravel-dev](#laravel-dev)
  - [ui-designer](#ui-designer)
  - [ux-architect](#ux-architect)
  - [ux-researcher](#ux-researcher)
- [Compatibility Matrix](#compatibility-matrix)
- [Instalasi](#instalasi)
- [Cara Menggunakan](#cara-menggunakan)
- [Kustomisasi](#kustomisasi)
- [Versioning & Changelog](#versioning--changelog)
- [Keamanan & Privasi](#keamanan--privasi)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)
- [Praktik Terbaik](#praktik-terbaik)
- [Kontribusi](#kontribusi)
- [Roadmap](#roadmap)
- [Support & Kontak](#support--kontak)
- [Lisensi & Kredit](#lisensi--kredit)

---

## Informasi Proyek

| Field | Nilai |
| --- | --- |
| **Nama koleksi** | AI Skills & Persona Collection |
| **Creator** | Grownie Studio |
| **Versi** | 1.1.0 |
| **Status** | Active / Stable |
| **Terakhir diperbarui** | 10 November 2026 |
| **Jumlah skill** | 10 |
| **Format inti** | `SKILL.md` + YAML frontmatter; dapat diadaptasi ke rules file, system prompt, atau project knowledge |
| **Lokasi global (OpenCode)** | `~/.config/opencode/skills/<nama-skill>/` |
| **Lokasi per proyek (OpenCode)** | `.opencode/skills/<nama-skill>/` |
| **Bahasa instruksi** | Inggris (isi skill), dokumentasi ini Bahasa Indonesia |
| **Target platform** | macOS, Linux, Windows, browser, desktop, mobile |
| **Kompatibilitas** | AI coding agent dan AI chat yang menerima instruksi/persona |
| **Lisensi** | MIT (dapat diganti sesuai kebutuhan) |
| **Maintainer** | Grownie Studio |

---

## Untuk Creator: Informasi yang Dibutuhkan

Bagian ini menjawab pertanyaan: **informasi apa saja yang harus disiapkan sebelum membuat skill?**

### Checklist informasi wajib

| # | Informasi | Pertanyaan kunci | Contoh |
| --- | --- | --- | --- |
| 1 | **Tujuan skill** | Skill ini membuat agent mampu melakukan apa, dari awal sampai akhir? | "Melakukan review PR secara terstruktur" |
| 2 | **Audiens** | Siapa penggunanya? Pemula, engineer senior, atau tim tertentu? | "Engineer yang sudah familiar dengan TypeScript" |
| 3 | **Trigger** | Frasa, konteks, atau tugas seperti apa yang harus memicu skill? | "review PR", "audit kode", "cek security" |
| 4 | **Anti-trigger** | Kapan skill **tidak** boleh dipakai? | "Jangan dipakai untuk menulis kode baru dari nol" |
| 5 | **Input** | Apa yang diberikan pengguna? | Diff PR, path folder, link issue |
| 6 | **Output** | Deliverable seperti apa yang diharapkan? | Daftar temuan + prioritas + saran perbaikan |
| 7 | **Workflow** | Langkah wajib apa yang harus dipertahankan urutannya? | Baca diff → klasifikasi temuan → beri rekomendasi |
| 8 | **Tools/dependensi** | Tool, MCP, CLI, atau akses apa yang dibutuhkan? | Git, GitHub CLI, akses repo |
| 9 | **Batasan** | Apa yang tidak boleh dilakukan? | "Jangan mengubah file tanpa persetujuan" |
| 10 | **Quality bar** | Kriteria output dianggap berhasil? | "Semua temuan punya alasan dan contoh perbaikan" |
| 11 | **Contoh** | Contoh prompt dan contoh output ideal | 3–5 contoh prompt nyata |
| 12 | **Edge case** | Situasi sulit yang perlu ditangani? | Repo kosong, diff sangat besar, file binary |
| 13 | **Referensi** | Dokumen, standar, atau contoh yang jadi acuan | Panduan internal, dokumentasi framework |
| 14 | **Testing plan** | Bagaimana kualitas skill diuji? | Kumpulan prompt uji + penilaian manual |
| 15 | **Owner & versi** | Siapa penanggung jawab dan bagaimana versinya? | Grownie Studio, semantic versioning |
| 16 | **Target platform** | Di mana skill akan dipakai? | OpenCode, Cursor, ChatGPT, Claude, Gemini, mobile |
| 17 | **Format distribusi** | Bagaimana skill dibagikan? | `SKILL.md`, rules file, system prompt, project knowledge |

### Template brief skill

Gunakan template ini saat mengajukan skill baru:

```markdown
# Skill Brief

## Identitas
- Nama skill      :
- Creator         :
- Versi           :
- Status          : draft | review | stable

## Tujuan
- Masalah yang diselesaikan :
- Kemampuan yang diberikan  :
- Bukan untuk              :

## Penggunaan
- Trigger utama   :
- Anti-trigger    :
- Contoh prompt   : 1. ...
                    2. ...
                    3. ...

## Input & Output
- Input           :
- Output wajib    :
- Format output   :

## Workflow
1. ...
2. ...
3. ...

## Batasan
- ...

## Tools & Dependensi
- ...

## Quality Bar
- ...

## Testing
- Prompt uji      :
- Kriteria lulus :
- Metode evaluasi :

## Referensi
- ...
```

### Informasi yang sebaiknya **tidak** dimasukkan

- Kredensial, API key, token, atau password.
- Data pribadi pengguna atau data pelanggan.
- Informasi internal yang bersifat rahasia.
- Instruksi yang bergantung pada path absolut mesin tertentu.

---

## Quick Start

Pilih jalur sesuai platform Anda:

### A. AI coding agent dengan dukungan skill (OpenCode, Claude Code, dll.)

1. **Pastikan skill tersedia** di salah satu lokasi:

   ```text
   ~/.config/opencode/skills/<nama-skill>/SKILL.md   # global (OpenCode)
   .opencode/skills/<nama-skill>/SKILL.md            # per proyek (OpenCode)
   ```

2. **Buka agent** di proyek Anda.

3. **Panggil skill** secara eksplisit:

   ```text
   Gunakan skill code-reviewer untuk me-review perubahan di folder src/.
   ```

   Atau biarkan terpicu otomatis dengan menjelaskan tugas secara natural.

4. **Tinjau hasil** dan berikan koreksi. Skill akan mengikuti persona dan format deliverable yang sudah ditentukan.

### B. AI coding agent berbasis rules file (Cursor, Windsurf, Copilot, Codex, Gemini CLI)

1. Salin isi `SKILL.md` ke file aturan yang dikenali platform (mis. `.cursor/rules/`, `.windsurfrules`, `.github/copilot-instructions.md`, `AGENTS.md`, `GEMINI.md`).
2. Sesuaikan bagian depan agar ringkas dan spesifik untuk proyek.
3. Minta agent mengikuti persona tersebut pada tugas terkait.

Detail per platform ada di [Adaptasi ke Platform Lain](#adaptasi-ke-platform-lain).

### C. AI chat (ChatGPT, Claude, Gemini, Copilot, dll.)

1. Buka `SKILL.md` yang ingin dipakai.
2. Salin bagian persona dan aturan inti ke **Custom Instructions**, **Projects**, **Gems**, **Spaces**, atau system prompt.
3. Jika platform mendukung upload file, lampirkan `SKILL.md` sebagai knowledge.
4. Mulai percakapan dengan menyebut peran yang diinginkan, misalnya:

   ```text
   Kamu adalah Code Reviewer. Ikuti aturan pada dokumen yang saya lampirkan.
   ```

5. Untuk pemakaian berulang di mobile, simpan persona di custom instructions atau project agar tidak perlu menempel ulang.

---

## Prasyarat

| Kebutuhan | Keterangan |
| --- | --- |
| AI agent / AI chat | Platform yang menerima instruksi, system prompt, atau rules |
| File system (opsional) | Diperlukan untuk pemakaian skill berbasis file |
| Editor/terminal (opsional) | Untuk menyalin dan menyesuaikan file |
| Git (opsional) | Untuk versioning koleksi skill |
| Tool tambahan | Tergantung skill (mis. Git, Docker, database client) |

Tidak ada dependensi runtime khusus: skill hanyalah teks Markdown. Tool eksternal hanya dibutuhkan jika isi skill memang merujuk ke tool tersebut, dan hanya berfungsi pada platform yang memberi akses tool.

---

## Daftar Skill

Semua skill di bawah ini bersifat portabel. Yang berbeda antar platform hanyalah cara pemasangan dan pemicuannya — isi persona dan aturannya tetap sama.

| Skill | Fokus Utama | Cocok Untuk |
| --- | --- | --- |
| `backend-architect` | Arsitektur sistem, API, database, keamanan, observability | Perancangan service, microservices, skema data skala besar |
| `code-reviewer` | Review kode: correctness, security, maintainability, performance | Pull request, audit kode, mentoring |
| `database-optimizer` | Query plan, indexing, schema, connection pooling | PostgreSQL/MySQL/Supabase/PlanetScale yang lambat atau akan scale |
| `devops-automator` | IaC, CI/CD, container, monitoring, cost optimization | Setup pipeline, deployment, infrastruktur cloud |
| `flutter` | Mobile native & cross-platform | Aplikasi iOS/Android, offline-first, integrasi perangkat |
| `frontend-dev` | Web app modern, performa, aksesibilitas | React/Vue/Angular/Svelte, design system, PWA |
| `laravel-dev` | Laravel, Livewire, FluxUI, UI premium | Website Laravel dengan tampilan kelas atas |
| `ui-designer` | Design system, komponen, visual hierarchy | Pembuatan UI konsisten, dark mode, handoff desain |
| `ux-architect` | Fondasi CSS, layout, information architecture | Menjembatani spesifikasi produk dan implementasi |
| `ux-researcher` | Riset pengguna, usability testing, persona | Validasi desain, riset perilaku, rekomendasi berbasis data |

---

## Struktur Direktori

Struktur ini adalah **format sumber** koleksi. Untuk platform lain, isi `SKILL.md` disalin ke rules file atau system prompt sesuai kebutuhan.

```text
skills/
├── README.md
├── backend-architect/
│   └── SKILL.md
├── code-reviewer/
│   └── SKILL.md
├── database-optimizer/
│   └── SKILL.md
├── devops-automator/
│   └── SKILL.md
├── flutter/
│   └── SKILL.md
├── frontend-dev/
│   └── SKILL.md
├── laravel-dev/
│   └── SKILL.md
├── ui-designer/
│   └── SKILL.md
├── ux-architect/
│   └── SKILL.md
└── ux-researcher/
    └── SKILL.md
```

Setiap folder berisi satu `SKILL.md`. Nama folder **wajib** sama dengan field `name` pada frontmatter.

### Struktur skill yang lebih besar

Untuk skill yang kompleks, gunakan struktur berikut:

```text
skill-name/
├── SKILL.md          # wajib: workflow utama + ringkasan
├── references/       # dokumen detail yang dibaca saat dibutuhkan
│   ├── guide.md
│   └── schemas.md
├── scripts/          # kode deterministik untuk tugas berulang
│   └── validate.sh
├── assets/           # template, ikon, font
│   └── template.html
└── evals/            # kumpulan prompt dan kriteria uji
    └── evals.json
```

Prinsipnya: **isi utama tetap ringkas**, detail dipindahkan ke file pendukung dan dirujuk dari `SKILL.md`.

---

## Anatomi Skill

### Frontmatter

```yaml
---
name: nama-skill
description: Apa yang dilakukan skill dan kapan harus dipakai.
---
```

| Field | Wajib | Aturan |
| --- | --- | --- |
| `name` | Ya* | Kebab-case, 1–64 karakter, regex `^[a-z0-9]+(-[a-z0-9]+)*$`, harus sama dengan nama folder |
| `description` | Ya* | Menjelaskan **apa** dan **kapan**; ini mekanisme trigger utama |
| `compatibility` | Tidak | Tool atau dependensi yang dibutuhkan |
| `metadata` | Tidak | Informasi tambahan (versi, owner, tag) |

\* Wajib pada platform skill-aware. Untuk rules file atau system prompt, frontmatter dapat dihilangkan dan isinya disesuaikan.

### Isi `SKILL.md`

Urutan yang disarankan:

1. **Judul** dan satu paragraf ringkas tentang peran skill.
2. **Identitas & memori** — persona, gaya kerja, pengalaman.
3. **Core mission** — kemampuan utama yang harus dijalankan.
4. **Critical rules** — aturan yang tidak boleh dilanggar.
5. **Deliverables** — format output yang diharapkan.
6. **Workflow** — langkah kerja yang harus diikuti.
7. **Communication style** — nada dan cara penyampaian.
8. **Success metrics** — ukuran keberhasilan.

### Progressive disclosure

Platform skill-aware (seperti OpenCode dan Claude Code) umumnya memuat skill secara bertahap:

1. **Metadata** (`name` + `description`) — selalu tersedia, ±100 kata.
2. **Isi `SKILL.md`** — dimuat saat skill terpicu; idealnya di bawah 500 baris.
3. **Bundled resources** — dibaca hanya saat dibutuhkan.

Konsekuensinya:

- Taruh informasi paling penting di bagian atas.
- Jangan menaruh seluruh dokumentasi di `SKILL.md`.
- Beri petunjuk jelas kapan file referensi harus dibaca.
- Untuk AI chat, terapkan prinsip yang sama: kirim hanya bagian yang relevan agar konteks tidak penuh.

---

## Cara Kerja Skill

Skill pada dasarnya adalah **instruksi berperan**: persona + aturan + workflow + format output. Cara memuatnya berbeda-beda tergantung platform:

1. **Skill-aware agent** (OpenCode, Claude Code) — metadata dan isi `SKILL.md` dimuat oleh agent; skill dapat terpicu otomatis berdasarkan `description`.
2. **Rules-based agent** (Cursor, Windsurf, Copilot, Codex, Gemini CLI) — aturan dibaca dari file konfigurasi proyek; perilaku mengikuti mekanisme platform.
3. **AI chat** (ChatGPT, Claude, Gemini, Copilot, dll.) — persona dipilih atau ditempel manual melalui custom instructions, project, gem, space, atau system prompt. Tidak ada trigger otomatis.

Yang perlu dipahami:

- Skill **tidak** dijalankan seperti fungsi; ia menjadi instruksi tambahan bagi AI.
- Pada platform dengan trigger otomatis, `description` menentukan pemilihan skill.
- Pada AI chat, Anda yang memilih persona; konsistensi bergantung pada instruksi yang tersimpan.
- Tugas sederhana yang bisa diselesaikan AI tanpa skill mungkin tidak memicu skill, meskipun deskripsinya cocok.
- Instruksi yang membutuhkan file, terminal, atau tool hanya berfungsi di platform yang memberi akses tersebut.

Contoh frontmatter (untuk platform yang mendukung):

```yaml
---
name: code-reviewer
description: Expert code reviewer who provides constructive, actionable feedback focused on correctness, maintainability, security, and performance — not style preferences.
---
```

---

## Portabilitas & Platform

### Tingkat portabilitas

| Lapisan | Portabilitas | Catatan |
| --- | --- | --- |
| Isi persona, aturan, workflow | **Tinggi** | Teks Markdown murni, dapat dipindahkan ke platform apa pun |
| Frontmatter (`name`, `description`) | **Sedang** | Dipakai platform skill-aware; platform lain mengabaikannya |
| Trigger otomatis | **Rendah** | Bergantung mekanisme platform |
| Instruksi khusus tool | **Rendah** | Hanya berlaku jika tool tersedia |

### Matriks platform

| Platform | Jenis | Cara memakai | Trigger otomatis | Catatan |
| --- | --- | --- | --- | --- |
| **OpenCode** | Coding agent (CLI/desktop) | `~/.config/opencode/skills/` atau `.opencode/skills/` | Ya | Format asli koleksi ini |
| **Claude Code** | Coding agent | Skill directory atau `CLAUDE.md` | Ya (skill) / aturan proyek | Ringkas bila memakai `CLAUDE.md` |
| **Cursor** | IDE agent | `.cursor/rules/*.mdc` | Ya (rule matching) | Satu persona per rule |
| **Windsurf** | IDE agent | `.windsurf/rules/` atau `.windsurfrules` | Ya | Perhatikan batas ukuran file |
| **GitHub Copilot** | IDE + chat | `.github/copilot-instructions.md` | Sebagian | Fokus pada aturan proyek |
| **Codex CLI** | Coding agent | `AGENTS.md` | Ya | Instruksi ringkas dan tegas |
| **Gemini CLI** | Coding agent | `GEMINI.md` | Ya | Pola mirip `AGENTS.md` |
| **ChatGPT** (browser/desktop/app) | AI chat | Custom Instructions, Projects, GPTs | Tidak | Pilih/paste persona; upload file bila perlu |
| **Claude** (browser/desktop/app) | AI chat | Projects, custom instructions, Styles | Tidak | Gunakan project knowledge |
| **Gemini** (browser/app) | AI chat | Gems, saved info | Tidak | Ringkas untuk batas konteks |
| **Copilot Chat** | AI chat | Custom instructions | Sebagian | Terikat ekosistem Microsoft |
| **Perplexity / chat lain** | AI chat | Spaces, custom instructions | Tidak | Utamakan aturan inti |

### Rekomendasi per jenis platform

- **Coding agent skill-aware** — simpan `SKILL.md` utuh; biarkan mekanisme skill memilih.
- **Coding agent berbasis rules** — ekstrak bagian terpenting ke rules file; jaga tetap ringkas (±200–300 baris).
- **Chat desktop/browser** — simpan versi ringkas di custom instructions: persona, 5–8 aturan inti, dan format output.
- **Chat mobile** — gunakan versi paling ringkas; simpan di project/gem agar persisten.

### Batasan lintas platform

- AI chat tanpa tool tidak dapat membaca repository atau menjalankan perintah.
- Trigger otomatis umumnya tidak tersedia di AI chat.
- Ukuran context window berbeda-beda; skill panjang mungkin perlu diringkas.
- Dukungan Markdown, tabel, dan kode berbeda antar antarmuka.
- Sebagian platform menyimpan memori antar-percakapan, sebagian tidak.

---

## Adaptasi ke Platform Lain

Prinsipnya: **pertahankan persona, aturan kritis, dan format output; sesuaikan cara pemasangannya.**

### 1. OpenCode

Gunakan format asli koleksi ini:

```text
~/.config/opencode/skills/<nama-skill>/SKILL.md
.opencode/skills/<nama-skill>/SKILL.md
```

Tidak perlu diubah. Lihat [Instalasi](#instalasi).

### 2. Claude Code

Gunakan skill directory jika didukung, atau ringkas ke `CLAUDE.md` di root proyek:

```markdown
# CLAUDE.md

## Persona: Code Reviewer

Kamu adalah reviewer kode senior. Fokus pada correctness, security,
maintainability, dan performance.

### Aturan wajib
- Tandai temuan sebagai Blocker, Suggestion, atau Nit.
- Setiap temuan harus punya alasan dan saran perbaikan.
- Jangan mengubah file tanpa persetujuan.

### Format output
1. Ringkasan
2. Blocker
3. Suggestion
4. Nit
```

### 3. Cursor

Buat rule di `.cursor/rules/code-reviewer.mdc`:

```markdown
---
description: Aturan review kode untuk proyek ini
globs: ["**/*.ts", "**/*.tsx"]
alwaysApply: false
---

Kamu adalah Code Reviewer. Fokus pada correctness, security,
maintainability, dan performance.

- Tandai temuan sebagai Blocker / Suggestion / Nit.
- Sertakan alasan dan contoh perbaikan.
- Jangan mengubah kode tanpa persetujuan.
```

### 4. Windsurf

Buat `.windsurf/rules/code-reviewer.md` atau tambahkan ke `.windsurfrules`:

```markdown
# Code Reviewer

Kamu adalah reviewer kode senior. Fokus pada correctness, security,
maintainability, dan performance.

- Blocker: bug, risiko keamanan, kehilangan data.
- Suggestion: perbaikan desain atau performa.
- Nit: gaya penulisan opsional.
```

### 5. GitHub Copilot

Tambahkan ke `.github/copilot-instructions.md`:

```markdown
# Instruksi Proyek

Saat diminta review kode, gunakan persona Code Reviewer:
- Fokus pada correctness, security, maintainability, performance.
- Kelompokkan temuan: Blocker, Suggestion, Nit.
- Sertakan alasan dan saran perbaikan.
```

### 6. Codex CLI / Gemini CLI

Gunakan `AGENTS.md` (Codex) atau `GEMINI.md` (Gemini CLI) di root proyek:

```markdown
# AGENTS.md

## Code Review
- Gunakan persona Code Reviewer.
- Fokus: correctness, security, maintainability, performance.
- Format: Ringkasan → Blocker → Suggestion → Nit.
- Jangan mengubah kode tanpa persetujuan.
```

### 7. ChatGPT (browser, desktop, aplikasi)

Pilih salah satu:

- **Custom Instructions** — untuk persona yang dipakai sehari-hari.
- **Projects** — untuk persona + file referensi per proyek.
- **GPTs** — jika ingin persona yang dapat dibagikan.

Template ringkas untuk Custom Instructions:

```text
Kamu adalah Code Reviewer senior. Saat saya meminta review kode:
1. Fokus pada correctness, security, maintainability, dan performance.
2. Kelompokkan temuan menjadi Blocker, Suggestion, dan Nit.
3. Sertakan alasan dan contoh perbaikan.
4. Jangan mengubah kode tanpa persetujuan saya.
```

### 8. Claude (browser, desktop, aplikasi)

- Gunakan **Projects** dan lampirkan `SKILL.md` sebagai project knowledge.
- Atau tempel ringkasan persona ke custom instructions.
- Untuk pemakaian di aplikasi mobile, simpan persona di project yang sama.

### 9. Gemini (browser, aplikasi)

- Gunakan **Gems** untuk persona yang dipakai berulang.
- Atau simpan aturan inti di saved info/custom instructions.
- Ringkas instruksi karena batas konteks dapat berbeda antar-varian.

### 10. Platform chat lain

Gunakan template system prompt berikut:

```text
Kamu adalah <nama persona>, seorang spesialis <bidang>.

Tugas:
- <kemampuan utama 1>
- <kemampuan utama 2>

Aturan wajib:
- <aturan 1>
- <aturan 2>
- <batasan>

Format output:
1. <bagian 1>
2. <bagian 2>

Jika informasi kurang, tanyakan terlebih dahulu.
```

### Tips adaptasi

1. **Pertahankan aturan kritis** — bagian yang paling menentukan kualitas.
2. **Buang referensi tool yang tidak tersedia** di platform tujuan.
3. **Ringkas contoh kode** agar tidak menghabiskan konteks.
4. **Sesuaikan bahasa output** jika pengguna tidak nyaman dengan Inggris.
5. **Uji dengan 3 prompt nyata** sebelum dipakai sehari-hari.
6. **Simpan versi** agar mudah dibandingkan dan diperbarui.

---

## Panduan Menulis Deskripsi

`description` adalah bagian paling penting untuk distribusi skill. Formula yang disarankan:

```text
[Peran/keahlian] + [kemampuan utama] + [konteks trigger] + [batasan/anti-trigger]
```

### Contoh baik

```yaml
description: Expert database specialist focusing on schema design, query optimization, indexing strategies, and performance tuning for PostgreSQL, MySQL, and modern databases like Supabase and PlanetScale. Use whenever the user mentions slow queries, EXPLAIN plans, indexes, N+1 problems, or database migrations.
```

Mengapa baik:

- Menyebut teknologi spesifik.
- Menyebut gejala/tugas yang memicu skill.
- Cukup panjang untuk membedakan dari skill lain.

### Contoh kurang baik

```yaml
description: Helps with databases.
```

Mengapa kurang baik:

- Terlalu umum, mudah bentrok dengan skill lain.
- Tidak menjelaskan kapan harus dipakai.
- Tidak memberi sinyal teknologi atau tugas.

### Tips trigger

- Sertakan **kata kunci** yang benar-benar dipakai pengguna.
- Sertakan **sinonim** (mis. "PR", "pull request", "code review").
- Sebut **gejala** untuk skill debugging (mis. "lambat", "timeout", "memory leak").
- Tambahkan **anti-trigger** jika skill mudah salah picu.
- Uji dengan prompt nyata, bukan hanya membayangkan.

---

## Alur Kerja Authoring

### 1. Riset & intent

- Tentukan masalah yang ingin diselesaikan.
- Tentukan **platform target**: agent skill-aware, rules-based agent, atau AI chat.
- Kumpulkan contoh nyata: prompt, input, output.
- Identifikasi workflow yang harus dipertahankan.
- Tentukan batas: apa yang **bukan** tanggung jawab skill.

### 2. Draft

- Tulis `SKILL.md` dengan struktur yang konsisten.
- Buat `description` yang spesifik.
- Tambahkan 3–5 contoh prompt.
- Tentukan format deliverable.
- Siapkan versi ringkas untuk platform dengan konteks terbatas.

### 3. Uji

- Jalankan prompt uji dengan dan tanpa skill.
- Bandingkan kualitas, konsistensi, dan relevansi.
- Catat kegagalan dan perbaiki instruksi.
- Uji juga prompt yang **tidak** boleh memicu skill.
- Uji di platform target yang sebenarnya (browser, desktop, mobile, atau CLI).

### 4. Review

- Minta review dari pengguna lain atau anggota tim.
- Periksa kejelasan, panjang, dan potensi konflik antar-skill.
- Pastikan tidak ada data sensitif.

### 5. Publikasi

- Letakkan di lokasi global, per proyek, atau simpan di platform chat.
- Sertakan petunjuk pemasangan untuk platform target.
- Perbarui README dan changelog.
- Tandai versi.

### 6. Maintenance

- Tinjau saat stack atau standar berubah.
- Perbaiki deskripsi jika trigger meleset.
- Arsipkan skill yang tidak lagi relevan.

---

## Testing & Validasi

### Test prompt set

Siapkan minimal tiga kategori:

| Kategori | Tujuan | Contoh |
| --- | --- | --- |
| **Should trigger** | Memastikan skill terpicu | "Review PR ini" |
| **Should not trigger** | Memastikan tidak salah picu | "Buat commit message" |
| **Edge case** | Menguji ketahanan | Repo kosong, diff 10k baris, file binary |

### Kriteria kualitas

- **Relevan** — output sesuai tugas, tidak melebar.
- **Konsisten** — format dan nada stabil antar-run.
- **Actionable** — rekomendasi bisa langsung dijalankan.
- **Jujur** — tidak mengarang temuan atau data.
- **Aman** — tidak membocorkan rahasia atau menjalankan perintah berbahaya.

### Trigger test

Uji `description` secara terpisah dari isi skill:

1. Buat 10–20 prompt yang seharusnya memicu skill.
2. Buat 10–20 prompt yang seharusnya tidak memicu.
3. Jalankan beberapa kali per prompt untuk melihat konsistensi.
4. Hitung tingkat pemicuan yang benar.
5. Perbaiki deskripsi jika ada false positive/negative.

### Regression test

Setiap kali mengubah skill:

- Jalankan ulang prompt uji utama.
- Bandingkan output dengan versi sebelumnya.
- Pastikan perubahan tidak merusak perilaku yang sudah baik.

### Uji lintas platform

Karena skill dapat dipakai di banyak platform, uji setidaknya pada dua jenis:

| Platform | Yang diuji |
| --- | --- |
| Agent skill-aware | Trigger otomatis, akses tool, konsistensi format |
| Rules-based agent | Kepatuhan terhadap aturan proyek |
| AI chat desktop/browser | Pemahaman persona, kualitas jawaban tanpa tool |
| AI chat mobile | Keringkasan, keterbacaan, dan stabilitas format |

Catat perbedaan hasil agar ekspektasi pengguna sesuai dengan platform yang dipakai.

---

## Detail Skill

### backend-architect

**Peran:** Senior backend architect untuk sistem yang skalabel, aman, dan andal.

**Cakupan:**

- Pemilihan arsitektur: monolith, modular monolith, microservices, atau serverless berdasarkan ukuran tim dan kebutuhan scaling.
- Desain skema data, index, ETL, dan persistence layer berperforma tinggi.
- API architecture: versioning, kontrak, dokumentasi, event-driven system.
- Reliability: error handling, circuit breaker, timeout budget, retry dengan backoff, idempotency, bulkhead, rate limit, dead-letter queue.
- Keamanan: autentikasi, otorisasi, kontrol akses, kepatuhan standar.
- Observability dan strategi caching.

**Contoh prompt:**

```text
Rancang arsitektur backend untuk marketplace dengan 500k user aktif.
Fokus pada pembagian service, skema database, dan strategi scaling.
```

**Deliverable umum:** diagram arsitektur high-level, dekomposisi service, desain database, spesifikasi API, dan rencana observability.

---

### code-reviewer

**Peran:** Reviewer kode yang konstruktif, berfokus pada hal yang berdampak.

**Cakupan:**

- Correctness, security, maintainability, performance, dan testing.
- Checklist review dengan prioritas: **Blocker** (wajib diperbaiki), **Suggestion** (sebaiknya diperbaiki), **Nit** (opsional).
- Format komentar review yang menjelaskan *apa*, *mengapa*, dan *saran perbaikan*.
- Gaya komunikasi yang mendidik, bukan menghakimi.

**Contoh prompt:**

```text
Review PR ini. Tandai blocker, suggestion, dan nit.
Jelaskan alasan setiap temuan dan berikan contoh perbaikannya.
```

**Deliverable umum:** daftar temuan terprioritas, penjelasan risiko, dan rekomendasi perbaikan yang dapat langsung dieksekusi.

---

### database-optimizer

**Peran:** Spesialis performa database yang berpikir dalam query plan dan index.

**Cakupan:**

- PostgreSQL sebagai domain utama; MySQL, Supabase, dan PlanetScale.
- `EXPLAIN ANALYZE` dan interpretasi query plan.
- Strategi indexing: B-tree, GiST, GIN, partial index, composite index.
- Desain skema: normalisasi vs denormalisasi.
- Deteksi dan perbaikan N+1 query.
- Connection pooling: PgBouncer, Supabase pooler.
- Migrasi dan deployment tanpa downtime.

**Contoh prompt:**

```text
Query laporan penjualan ini lambat. Analisis query plan-nya,
usulkan index yang tepat, dan tulis ulang query-nya.
```

**Deliverable umum:** skema teroptimasi, query yang sudah diperbaiki, rekomendasi index, dan catatan migrasi.

---

### devops-automator

**Peran:** DevOps engineer untuk otomasi infrastruktur dan operasi cloud.

**Cakupan:**

- Infrastructure as Code: Terraform, CloudFormation, CDK.
- CI/CD: GitHub Actions, GitLab CI, Jenkins.
- Container dan orkestrasi: Docker, Kubernetes, service mesh.
- Deployment tanpa downtime: blue-green, canary, rolling.
- Monitoring dan observability: Prometheus, Grafana, Datadog, log aggregation, distributed tracing.
- Security scanning, compliance automation, dan cost optimization.

**Contoh prompt:**

```text
Buat pipeline CI/CD untuk aplikasi Node.js ke Kubernetes
dengan canary deployment, automated rollback, dan monitoring.
```

**Deliverable umum:** arsitektur pipeline, template IaC, konfigurasi monitoring/alerting, dan runbook operasional.

---

### flutter

**Peran:** Mobile app builder untuk iOS, Android, dan cross-platform.

**Cakupan:**

- Native iOS: Swift, SwiftUI.
- Native Android: Kotlin, Jetpack Compose.
- Cross-platform: Flutter, React Native.
- Offline-first architecture dan sinkronisasi data.
- Optimasi performa: startup time, memori, baterai, animasi.
- Integrasi perangkat: biometrik, kamera/AR, geolokasi, push notification, in-app purchase.

**Contoh prompt:**

```text
Bangun aplikasi mobile offline-first dengan Flutter.
Sertakan strategi sinkronisasi, struktur navigasi, dan optimasi performa.
```

**Deliverable umum:** strategi platform, contoh komponen per platform, rencana integrasi, dan checklist pengujian/deployment.

---

### frontend-dev

**Peran:** Frontend developer untuk aplikasi web modern yang cepat dan aksesibel.

**Cakupan:**

- Framework: React, Vue, Angular, Svelte.
- Implementasi UI presisi dengan CSS modern.
- Design system dan component library.
- Optimasi Core Web Vitals, code splitting, lazy loading.
- Progressive Web App (PWA) dan kemampuan offline.
- Aksesibilitas dan desain mobile-first.
- Pengujian unit/integration dan integrasi CI/CD.

**Contoh prompt:**

```text
Implementasikan halaman dashboard dengan React + TypeScript.
Perhatikan Core Web Vitals, aksesibilitas, dan responsive design.
```

**Deliverable umum:** komponen siap pakai, catatan optimasi performa, implementasi aksesibilitas, dan strategi pengujian.

---

### laravel-dev

**Peran:** Senior full-stack developer untuk pengalaman web premium dengan Laravel.

**Cakupan:**

- Laravel dan Livewire.
- FluxUI: penggunaan seluruh komponen sesuai dokumentasi resmi.
- Alpine.js (sudah termasuk dalam Livewire).
- CSS lanjutan: glassmorphism, organic shapes, animasi premium.
- Three.js untuk pengalaman imersif bila relevan.
- Wajib: toggle tema **light / dark / system**.
- Standar kualitas: animasi 60fps dan performa load di bawah 1,5 detik.

**Contoh prompt:**

```text
Buat landing page Laravel + Livewire + FluxUI bernuansa premium.
Sertakan theme toggle, micro-interaction, dan animasi yang halus.
```

**Deliverable umum:** komponen Livewire, markup FluxUI, pola CSS premium, dan catatan QA performa/animasi.

---

### ui-designer

**Peran:** UI designer untuk design system dan antarmuka yang konsisten.

**Cakupan:**

- Design token dan component library.
- Visual hierarchy: tipografi, warna, spacing.
- Responsive design dan breakpoint strategy.
- Dark mode dan sistem tema.
- Aksesibilitas minimal WCAG AA.
- Dokumentasi komponen dan handoff ke developer.
- Design QA untuk memastikan akurasi implementasi.

**Contoh prompt:**

```text
Buat design system untuk aplikasi SaaS: token warna, tipografi,
spacing, komponen dasar, dan panduan penggunaannya.
```

**Deliverable umum:** fondasi desain (warna, tipografi, spacing), spesifikasi komponen, aturan responsif, dan panduan aksesibilitas.

---

### ux-architect

**Peran:** Arsitek teknis dan UX yang menyiapkan fondasi siap-implementasi.

**Cakupan:**

- Fondasi CSS: variabel, spacing scale, hierarki tipografi.
- Layout framework dengan Grid/Flexbox.
- Component architecture dan konvensi penamaan.
- Information architecture dan content hierarchy.
- Interaction pattern serta pertimbangan aksesibilitas.
- Toggle tema light/dark/system sebagai default.
- Menjembatani task dari PM dengan kebutuhan implementasi developer.

**Contoh prompt:**

```text
Siapkan fondasi teknis untuk website company profile:
struktur CSS, layout grid, information architecture, dan prioritas implementasi.
```

**Deliverable umum:** arsitektur CSS, spesifikasi layout, struktur UX, dan implementation guide untuk developer.

---

### ux-researcher

**Peran:** Peneliti UX yang menghubungkan kebutuhan pengguna dengan keputusan desain.

**Cakupan:**

- Riset kualitatif dan kuantitatif.
- User persona berbasis data dan pola perilaku.
- User journey mapping untuk menemukan pain point.
- Usability testing dan analisis perilaku.
- A/B testing dan analisis statistik.
- Riset aksesibilitas dan desain inklusif.
- Repositori riset untuk knowledge institusional.

**Contoh prompt:**

```text
Susun rencana usability testing untuk fitur checkout baru.
Sertakan profil partisipan, skenario tugas, dan metrik keberhasilan.
```

**Deliverable umum:** ringkasan riset, persona, journey map, temuan usability, dan rekomendasi berprioritas.

---

## Compatibility Matrix

Matrix ini menunjukkan stack dan tool yang **dirujuk** oleh setiap skill. Skill tetap dapat dipakai di AI chat tanpa tool tersebut; sertakan konteks yang relevan secara manual.

| Skill | Stack / Tools yang Dirujuk | Catatan |
| --- | --- | --- |
| `backend-architect` | Cloud, API, database, message broker | Tidak terikat satu vendor |
| `code-reviewer` | Git, platform PR | Bisa dipakai untuk diff lokal maupun PR |
| `database-optimizer` | PostgreSQL, MySQL, Supabase, PlanetScale, PgBouncer | Fokus utama PostgreSQL |
| `devops-automator` | Terraform, CloudFormation, CDK, Docker, Kubernetes, GitHub Actions, GitLab CI, Jenkins, Prometheus, Grafana, Datadog | Pilih subset sesuai proyek |
| `flutter` | Swift/SwiftUI, Kotlin/Compose, Flutter, React Native | Native dan cross-platform |
| `frontend-dev` | React, Vue, Angular, Svelte, TypeScript, CSS | Termasuk PWA dan aksesibilitas |
| `laravel-dev` | Laravel, Livewire, FluxUI, Alpine.js, Three.js | FluxUI memerlukan akses dokumentasi resmi |
| `ui-designer` | Design token, komponen, WCAG AA | Tidak terikat tool desain tertentu |
| `ux-architect` | CSS, Grid, Flexbox, HTML | Berfokus pada fondasi implementasi |
| `ux-researcher` | Metode riset kualitatif/kuantitatif | Bisa tanpa tool khusus |

---

## Instalasi

Cara instalasi bergantung pada platform. Bagian ini fokus pada **OpenCode**; untuk Cursor, Windsurf, Copilot, Codex, Gemini CLI, dan AI chat, lihat [Adaptasi ke Platform Lain](#adaptasi-ke-platform-lain).

### OpenCode — global (semua proyek)

Skill sudah berada di lokasi global berikut:

```text
~/.config/opencode/skills/<nama-skill>/SKILL.md
```

OpenCode akan mendeteksinya otomatis.

### OpenCode — per proyek

Salin skill yang dibutuhkan ke dalam proyek:

```bash
mkdir -p .opencode/skills
cp -R ~/.config/opencode/skills/code-reviewer .opencode/skills/
```

Struktur akhirnya:

```text
<project>/.opencode/skills/code-reviewer/SKILL.md
```

### Verifikasi

Pastikan setiap folder memiliki `SKILL.md` dan field `name` sesuai nama folder:

```bash
for f in ~/.config/opencode/skills/*/SKILL.md; do
  echo "== $f"
  sed -n '1,5p' "$f"
done
```

### Menghapus skill

```bash
rm -rf ~/.config/opencode/skills/<nama-skill>
```

Hapus hanya folder skill; jangan menghapus direktori `skills/` secara keseluruhan.

---

## Cara Menggunakan

Cara pemakaian berbeda menurut platform. Pada agent skill-aware, skill bisa terpicu otomatis. Pada rules-based agent, aturan mengikuti file konfigurasi proyek. Pada AI chat, persona dipilih atau ditempel manual.

### 1. Pemicuan otomatis (agent skill-aware)

Cukup jelaskan tugas secara natural. Jika cocok dengan `description`, agent akan memakai skill terkait.

```text
Tolong review perubahan di folder src/ dan tandai risiko keamanannya.
```

### 2. Pemicuan eksplisit

Sebut nama skill agar agent langsung memuatnya.

```text
Gunakan skill database-optimizer untuk menganalisis query lambat berikut.
```

### 3. Kombinasi beberapa skill

Skill bisa dipakai berurutan dalam satu alur kerja, misalnya:

```text
1. ux-researcher  → validasi kebutuhan pengguna
2. ux-architect   → susun fondasi layout dan CSS
3. ui-designer    → rancang design system
4. frontend-dev   → implementasikan UI
5. code-reviewer  → review hasil implementasi
```

### 4. Alur backend

```text
1. backend-architect  → rancang arsitektur dan API
2. database-optimizer → desain skema dan index
3. devops-automator   → siapkan pipeline dan deployment
4. code-reviewer      → review implementasi
```

### 5. Pemakaian di AI chat (browser, desktop, aplikasi)

1. Simpan persona di **Custom Instructions**, **Projects**, **Gems**, atau **Spaces**.
2. Lampirkan `SKILL.md` jika platform mendukung upload file.
3. Awali percakapan dengan konteks tugas dan hasil yang diharapkan.

Contoh:

```text
Gunakan persona Database Optimizer.
Query berikut lambat pada PostgreSQL 16. Analisis query plan-nya,
usulkan index, dan tulis ulang query-nya.
```

Karena AI chat umumnya tidak memiliki akses ke repository atau database, sertakan potongan yang relevan (query, skema, `EXPLAIN`) langsung di percakapan.

---

## Kustomisasi

Skill adalah file Markdown biasa, sehingga mudah disesuaikan.

**Yang aman diubah:**

- Menambah konvensi tim (nama branch, format commit, aturan review).
- Menyesuaikan stack (misalnya mengganti framework favorit).
- Menambahkan contoh kode atau checklist khusus proyek.
- Menajamkan `description` agar lebih mudah terpicu pada konteks tertentu.
- Menambah bagian deliverable sesuai kebutuhan organisasi.

**Yang perlu dijaga:**

- Field `name` harus tetap sama dengan nama folder.
- `description` harus tetap menjelaskan **apa** dan **kapan** skill dipakai.
- Jangan menghapus bagian peran/identitas jika ingin perilaku persona tetap konsisten.
- Jaga ukuran `SKILL.md` tetap ringkas; pindahkan detail besar ke file referensi terpisah.

Contoh penyesuaian:

```yaml
---
name: code-reviewer
description: Expert code reviewer for the Acme team. Use for every pull request, focusing on correctness, security, maintainability, and performance. Enforces Acme's TypeScript and testing conventions.
---
```

### Fork untuk organisasi

Jika ingin memakai koleksi ini sebagai basis internal:

1. Salin seluruh folder skill yang relevan.
2. Ganti bagian identitas dan aturan dengan konvensi organisasi.
3. Sesuaikan `description` dengan istilah internal.
4. Dokumentasikan perubahan di changelog internal.
5. Tetapkan owner dan jadwal review.

---

## Versioning & Changelog

Koleksi ini menggunakan [Semantic Versioning](https://semver.org/):

- **MAJOR** — perubahan yang mengubah perilaku atau menghapus skill.
- **MINOR** — penambahan skill atau kemampuan baru.
- **PATCH** — perbaikan instruksi, typo, atau dokumentasi.

### Changelog

| Versi | Tanggal | Perubahan |
| --- | --- | --- |
| 1.1.0 | 10 Nov 2026 | Memperluas lingkup ke semua AI agent dan AI chat (browser, desktop, aplikasi); menambah matriks platform dan panduan adaptasi |
| 1.0.0 | 10 Nov 2026 | Rilis awal: 10 skill, README lengkap, panduan creator |

### Format changelog yang disarankan

```markdown
## [1.1.0] - YYYY-MM-DD

### Added
- Skill baru: ...

### Changed
- Deskripsi `code-reviewer` diperjelas untuk trigger PR.

### Fixed
- Typo pada `database-optimizer`.

### Removed
- Skill yang tidak lagi relevan.
```

---

## Keamanan & Privasi

Skill adalah instruksi, bukan kode yang otomatis dieksekusi. Meskipun demikian, tetap perhatikan hal berikut:

- **Jangan menyimpan rahasia** di `SKILL.md` atau file pendukung.
- **Review script** di folder `scripts/` sebelum menjalankannya.
- **Batasi izin** tool yang diberikan ke agent.
- **Waspadai prompt injection** dari file atau halaman web yang dibaca agent.
- **Jangan kirim data sensitif** ke layanan eksternal tanpa persetujuan.
- **Gunakan prinsip least privilege** untuk akses repository dan cloud.
- **Audit perubahan skill** seperti Anda mengaudit kode.

Jika skill merujuk ke layanan pihak ketiga, pastikan kebijakan privasi layanan tersebut sesuai dengan kebutuhan organisasi.

---

## Troubleshooting

| Gejala | Kemungkinan Penyebab | Solusi |
| --- | --- | --- |
| Skill tidak terpicu | Di agent: deskripsi terlalu sempit. Di chat: tidak ada trigger otomatis | Perluas `description`, atau pilih/tempel persona secara manual |
| Skill terpicu terlalu sering | Deskripsi terlalu umum | Tambahkan batasan dan anti-trigger |
| Dua skill saling bentrok | Cakupan saling tumpang tindih | Perjelas batas tanggung jawab masing-masing |
| Skill tidak muncul di agent | Lokasi folder salah | Pastikan berada di `skills/<nama>/SKILL.md` atau rules file yang benar |
| Nama skill tidak dikenali | `name` tidak sama dengan nama folder | Samakan keduanya |
| Frontmatter error | YAML tidak valid | Periksa tanda kutip, indentasi, dan pemisah `---` |
| Instruksi diabaikan | Teks terlalu panjang, konteks penuh, atau tidak terstruktur | Ringkas, prioritaskan aturan penting di atas |
| Output tidak konsisten | Instruksi ambigu | Tambahkan format deliverable dan contoh |
| Perubahan tidak terbaca | Cache sesi/aplikasi | Mulai sesi baru atau restart aplikasi |
| Skill lambat | Terlalu banyak file referensi | Kurangi ukuran atau pecah menjadi beberapa skill |
| Skill jalan di proyek yang salah | Instalasi global | Pindahkan ke rules/skill per proyek |
| Persona "lupa" aturan di chat | Instruksi tidak tersimpan atau percakapan terlalu panjang | Simpan di custom instructions/project/gem; ulangi aturan inti |
| Instruksi tool tidak berjalan di chat | Platform tidak memberi akses tool | Sertakan data manual atau gunakan AI agent |
| Tabel/format rusak di aplikasi chat | Rendering antarmuka terbatas | Minta output dalam bentuk list atau teks biasa |
| Konteks terpotong | Skill terlalu panjang untuk batas platform | Gunakan versi ringkas atau bagi per bagian |

### Debug cepat

1. Periksa `SKILL.md` dan frontmatter (untuk platform berbasis file).
2. Pastikan nama folder = `name`.
3. Uji dengan prompt eksplisit: "Gunakan skill `<nama>` untuk ...".
4. Untuk AI chat, pastikan persona tersimpan dan aturan inti berada di awal instruksi.
5. Jika masih gagal, mulai sesi baru atau restart aplikasi.
6. Periksa log atau pesan error dari platform yang dipakai.

---

## FAQ

**Apakah harus memakai semua skill?**
Tidak. Pasang hanya skill yang relevan dengan pekerjaan Anda.

**Bisakah satu proyek memakai skill berbeda dari proyek lain?**
Bisa. Gunakan skill/rules per proyek, misalnya `.opencode/skills/`, `.cursor/rules/`, atau `AGENTS.md` sesuai platform.

**Bisakah skill dipakai di luar OpenCode?**
Bisa. Isi skill berupa Markdown yang dapat diadaptasi menjadi `CLAUDE.md`, `.cursor/rules/`, `.windsurfrules`, `.github/copilot-instructions.md`, `AGENTS.md`, `GEMINI.md`, system prompt, custom instructions, project knowledge, atau Gem. Lihat [Adaptasi ke Platform Lain](#adaptasi-ke-platform-lain).

**Bagaimana memakai skill di ChatGPT, Claude, atau Gemini?**
Tempel ringkasan persona ke Custom Instructions, Projects, Gems, atau Spaces. Jika platform mendukung upload file, lampirkan `SKILL.md` sebagai referensi.

**Apakah skill mengubah kode secara otomatis?**
Tidak. Skill memberi instruksi dan panduan. Pada AI agent dengan akses tool, eksekusi tetap mengikuti izin dan keputusan agent. Pada AI chat, skill hanya memengaruhi jawaban.

**Apakah skill aman untuk data sensitif?**
Skill tidak mengirim data dengan sendirinya, tetapi AI dapat memproses data yang Anda berikan. Ikuti kebijakan keamanan organisasi dan hindari menempelkan rahasia ke layanan pihak ketiga.

**Bisakah beberapa skill digabung?**
Bisa, tetapi jaga agar setiap skill tetap punya tanggung jawab yang jelas. Untuk AI chat, gabungkan beberapa persona hanya jika aturannya tidak bertentangan.

**Apakah perlu restart setelah mengubah skill?**
Sering kali perlu, terutama jika sesi atau aplikasi sudah memuat versi lama.

**Bagaimana mengukur kualitas skill?**
Gunakan prompt uji, bandingkan output dengan dan tanpa skill, dan minta review pengguna.

**Apakah skill bisa berbahasa Indonesia?**
Bisa. Dokumentasi ini berbahasa Indonesia, sedangkan isi skill menggunakan Inggris agar konsisten dengan istilah teknis. Anda dapat menerjemahkan isinya jika diinginkan.

**Bagaimana cara menghapus skill?**
Hapus folder skill dari direktori (atau hapus dari custom instructions/project di AI chat), lalu mulai sesi baru.

**Apakah skill ini terikat pada satu model atau vendor?**
Tidak. Skill dapat dipakai dengan model dan platform yang berbeda, meskipun kualitas output, panjang konteks, dan dukungan tool dapat berbeda.

---

## Praktik Terbaik

- **Satu skill, satu tanggung jawab.** Hindari menggabungkan disiplin yang sangat berbeda dalam satu skill.
- **Tulis deskripsi yang spesifik.** Sertakan teknologi, jenis tugas, dan sinonim yang mungkin dipakai pengguna.
- **Beri contoh prompt.** Contoh membuat perilaku skill lebih mudah diprediksi.
- **Prioritaskan deliverable.** Sebutkan output yang diharapkan agar agent tidak berhenti di analisis.
- **Jaga `SKILL.md` tetap ringkas.** Pindahkan detail ke file referensi.
- **Uji sebelum publikasi.** Jalankan prompt nyata dan bandingkan hasilnya.
- **Dokumentasikan perubahan.** Gunakan changelog dan versioning.
- **Tinjau ulang secara berkala.** Perbarui skill ketika stack atau standar tim berubah.
- **Hindari duplikasi.** Jika dua skill mirip, gabungkan atau perjelas batasnya.
- **Uji di proyek nyata.** Skill yang baik adalah yang menghasilkan perubahan yang bisa langsung dipakai.

---

## Kontribusi

Kontribusi terbuka untuk perbaikan dokumentasi, penambahan skill, atau penyempurnaan instruksi.

### Alur kontribusi

1. **Fork** atau buat branch baru.
2. **Buat perubahan** pada skill atau dokumentasi.
3. **Uji** dengan prompt nyata.
4. **Perbarui** README dan changelog jika perlu.
5. **Ajukan pull request** dengan deskripsi yang jelas.

### Konvensi branch

```text
feat/nama-skill-baru
fix/deskripsi-code-reviewer
docs/perbarui-readme
chore/bersihkan-format
```

### Konvensi commit

Gunakan [Conventional Commits](https://www.conventionalcommits.org/):

```text
feat(skills): tambah skill api-designer
fix(code-reviewer): perjelas kriteria blocker
docs(readme): tambah panduan testing
chore: rapikan struktur folder
```

### Checklist pull request

- [ ] Nama folder sama dengan `name` di frontmatter.
- [ ] `description` menjelaskan apa dan kapan.
- [ ] Ada minimal 3 contoh prompt.
- [ ] Deliverable dan batasan jelas.
- [ ] Tidak ada data sensitif.
- [ ] Sudah diuji dengan prompt nyata.
- [ ] README/changelog diperbarui bila perlu.

### Kriteria review

- Kejelasan tujuan dan trigger.
- Konsistensi gaya dengan skill lain.
- Keringkasan dan struktur.
- Tidak ada tumpang tindih yang membingungkan.
- Manfaat nyata bagi pengguna.

---

## Roadmap

- [x] Rilis awal 10 skill spesialis.
- [x] Dokumentasi creator dan panduan authoring.
- [x] Dukungan lintas platform (agent + AI chat).
- [ ] Template `SKILL.md` yang dapat disalin.
- [ ] Template rules untuk Cursor, Windsurf, Copilot, Codex, dan Gemini CLI.
- [ ] Paket prompt ringkas untuk ChatGPT, Claude, dan Gemini.
- [ ] Kumpulan prompt uji standar untuk semua skill.
- [ ] Skrip validasi frontmatter otomatis.
- [ ] Contoh integrasi CI untuk validasi skill.
- [ ] Terjemahan dokumentasi ke Bahasa Inggris.
- [ ] Katalog skill tambahan (mobile, data, security).

---

## Support & Kontak

| Kebutuhan | Saluran |
| --- | --- |
| Pertanyaan umum | Buka issue di repositori |
| Bug atau perilaku tak terduga | Laporkan dengan langkah reproduksi |
| Permintaan skill baru | Gunakan template brief skill |
| Kontribusi | Ajukan pull request |
| Kontak creator | Grownie Studio |

Saat melaporkan masalah, sertakan:

- Nama skill dan versi.
- Platform yang dipakai (OpenCode, Claude Code, Cursor, ChatGPT, Claude, Gemini, dll.).
- Mode penggunaan (browser, desktop, aplikasi mobile, atau CLI).
- Prompt yang digunakan.
- Output yang diharapkan vs aktual.
- Lingkungan (OS, versi platform/aplikasi, model).

---

## Lisensi & Kredit

**Creator:** Grownie Studio

Koleksi ini disusun sebagai dokumentasi dan alat bantu kerja untuk berbagai **AI agent** dan **AI chat** — termasuk OpenCode, Claude Code, Cursor, Windsurf, GitHub Copilot, Codex, Gemini CLI, ChatGPT, Claude, Gemini, dan platform lain di browser, desktop, maupun aplikasi. Lisensi default: **MIT** — Anda bebas menggunakan, memodifikasi, dan mendistribusikan dengan tetap menyertakan atribusi kepada creator. Ganti lisensi ini jika kebutuhan organisasi Anda berbeda.

Jika Anda menambahkan skill baru, pertahankan struktur, gaya penulisan, dan tingkat detail yang sama agar seluruh koleksi tetap konsisten.

---

<p align="center">
  Dibuat dan dikelola oleh <strong>Grownie Studio</strong>
</p>
