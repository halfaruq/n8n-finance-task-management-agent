# 🤖 AI WhatsApp Personal Assistant (n8n + WAHA + Gemini)

Bot WhatsApp cerdas serba bisa yang ditenagai oleh **AI (Google Gemini)**, **n8n**, dan **WAHA (WhatsApp HTTP API)**. Bot ini berfungsi sebagai asisten pribadi yang dapat mencatat pengeluaran/pemasukan keuangan dan mengelola tugas kuliah/kerja secara otomatis ke **Google Sheets**, lengkap dengan fitur notifikasi pengingat otomatis (H-1 Deadline).

---

## ✨ Fitur Utama

- **💬 Natural Language Processing (AI Agent):** Tidak perlu menghafal format kaku. Cukup chat dengan bahasa santai (contoh: *"Bro, catat pengeluaran 15rb buat makan"* atau *"/tugas Makalah SPIDI deadline besok jam 23:59"*), AI akan mengekstrak datanya secara otomatis.
- **💰 Finance Tracker (`/finance`):** Mencatat arus kas (pemasukan & pengeluaran) dan mengecek sisa saldo langsung dari WhatsApp. Data tersimpan rapi di Google Sheets.
- **📋 Task Management (`/tugas`):** 
  - Mencatat daftar tugas beserta tanggal deadline.
  - Mengecek tugas apa saja yang belum selesai.
  - Menandai tugas yang sudah selesai (*Mark as Done*).
- **⏰ H-1 Auto-Reminder:** Bot akan otomatis mengirimkan pesan pengingat ke WhatsApp kamu jika ada tugas yang deadlinenya tersisa $\le$ 24 jam (menggunakan *Schedule Trigger/Cron*).

---

## 🛠️ Tech Stack

- **[n8n](https://n8n.io/):** Workflow Automation Tool (Visual Node-Based).
- **[WAHA](https://waha.devlike.pro/):** WhatsApp HTTP API (berbasis WhatsApp Web.js) untuk mengirim/menerima pesan.
- **[Google Sheets API](https://developers.google.com/sheets/api):** Sebagai *database* pencatatan tugas dan keuangan.
- **[Google Gemini API](https://aistudio.google.com/):** Otak AI Agent (menggunakan model `gemini-1.5-flash` / `gemini-2.5-flash`).
- **[Docker](https://www.docker.com/):** (Opsional/Sangat Disarankan) Untuk menjalankan n8n dan WAHA secara lokal/server.

---

## 🚀 Prasyarat Instalasi

Sebelum memulai, pastikan kamu sudah memiliki:
1. Docker & Docker Compose terinstal di mesin/PC kamu.
2. Akun Google Cloud Console untuk mendapatkan kredensial **Google Sheets API** (Service Account/OAuth).
3. API Key dari **Google AI Studio (Gemini)**.
4. Akun WhatsApp aktif yang akan digunakan sebagai nomor bot.

---

## ⚙️ Panduan Instalasi & Penggunaan

### 1. Clone Repositori
```bash
git clone [https://github.com/halfaruq/n8n-finance-agent.git](https://github.com/halfaruq/n8n-finance-agent.git)
cd n8n-finance-agent
