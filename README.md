# Simulasi Workflow Front-End di Git & GitHub

## 🎯 Tujuan

Dokumen ini mensimulasikan workflow pengembangan Front-End menggunakan Git dan GitHub.
Tujuannya agar tim memahami alur `feature branch → pull request → develop branch` tanpa harus praktik di repo asli.

## 🧱 Struktur Branch

```
main
└── develop
      └── fe-develop
            ├── fe-feature/header
            ├── fe-feature/footer
            └── fe-feature/page
      └── be-develop
```

Keterangan:

* `main` → versi paling stabil (dipakai buat rilis).
* `fe-develop` → tempat penggabungan semua fitur FE sebelum masuk ke main.
* `fe-feature/...` → tempat kerja masing-masing anggota FE untuk fitur tertentu.

---

## 🧩 Simulasi Workflow

### 1. Clone repository

```bash
git clone https://github.com/team/project.git
cd project
```

### 2. Checkout ke branch develop FE

```bash
git checkout fe-develop
```

### 3. Buat branch baru untuk fitur

```bash
git checkout -b fe-feature/header
```

### 4. Edit file dan commit perubahan

```bash
# lakukan perubahan
git add .
git commit -m "Add header layout and navbar interaction"
```

### 5. Push branch ke GitHub

```bash
git push origin fe-feature/header
```

### 6. Buat Pull Request (PR)

* Buka repository di GitHub
* Akan muncul notifikasi “Compare & Pull Request”
* Target PR: **base = fe-develop**, **compare = fe-feature/header**
* Tambahkan deskripsi singkat perubahan
* Klik **Create Pull Request**

### 7. Review & Merge

* Teman satu tim (atau kamu sendiri) bisa review PR tersebut
* Jika sudah oke → klik **Merge Pull Request**
* Hapus branch lokal kalau sudah tidak dipakai:

```bash
git branch -d fe-feature/header
```

### 8. Update branch develop di lokal

```bash
git checkout fe-develop
git pull origin fe-develop
```

---

## 🧠 Catatan

* Jika perlu perbaikan di PR, tinggal commit lagi di branch fitur dan push ulang.
* Biasakan update branch `fe-develop` sebelum membuat branch fitur baru untuk menghindari konflik.

---

📘 Dengan mengikuti simulasi ini, tim Front-End bisa memahami alur kerja Git yang profesional dan efisien sebelum diterapkan di proyek nyata.
