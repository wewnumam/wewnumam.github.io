---
title: "Agate MVC Case Study"
date: 2025-05-05T20:31:09+07:00
draft: false
---

## 1. 📖 Pendahuluan

Unity telah menjadi salah satu game engine terpopuler. Namun, pola berbasis komponen bawaan Unity sering kali berujung pada:

* 🔄 **Penggandengan kode (tight coupling)**
* 🗃️ **Pengelolaan data persisten yang kurang terstruktur**
* 🕹️ **Penyalahgunaan Singleton pattern**

Untuk mengatasi hal ini, studi kasus “City of Philosophy” memanfaatkan **Model‑View‑Controller (MVC)** via **Agate MVC Framework**, memisahkan data, logika, dan tampilan secara jelas.

---

## 2. 🎯 Tujuan & Manfaat

* **Tujuan**

  1. Mengimplementasikan MVC di Unity menggunakan Agate MVC.
  2. Mengevaluasi kualitas kode dan arsitektur game “City of Philosophy”.
* **Manfaat**

  * **Akademik**: Referensi praktik MVC di pengembangan game.
  * **Mahasiswa**: Peningkatan kesiapan dan kompetensi pemrograman game.
  * **Industri**: Produk game lebih **modular**, **skalabel**, dan **mudah dipelihara**.

---

## 3. 🔍 Tantangan Umum

* **Data persisten** sulit dikelola antar-scene
* **Singleton overuse** menghambat fleksibilitas dan pengujian
* **Code coupling** mempersulit pemeliharaan & pengembangan fitur baru

---

## 4. 💡 Solusi Arsitektur MVC

* **Model**
  – Menyimpan & mengelola data
* **View**
  – Menampilkan UI & menerima input
* **Controller**
  – Menghubungkan Model & View, menangani logika

> “Dengan MVC, perubahan UI tidak merusak logika, dan vice versa.”

---

## 5. 📦 Agate MVC Framework

Fitur utama:

* 🗂️ **Layered Architecture** (Global vs Scene‑specific modules)
* 🔌 **Dependency Injection (DI)**
* 📣 **Publish‑Subscribe (Pub‑Sub)**
* ⚙️ **Boot System & Scene Launcher**

Membantu memecah kode menjadi modul-modul yang mandiri dan mudah diuji.

---

## 6. 🕹️ Studi Kasus: “City of Philosophy”

### 6.1. Alur Game

1. **Splash Screen**: Logo & versi game
2. **Main Menu**: Navigasi Play / Quiz
3. **Cutscene**: Narasi cerita
4. **Level Selection**: Pilih level & preview
5. **Gameplay**: Shooter + puzzle + collect
6. **Quiz**: Pertanyaan pengetahuan

### 6.2. Struktur Model

| Jenis Model   | Nama Model       | Fungsi Singkat                                |
| ------------- | ---------------- | --------------------------------------------- |
| **Persisten** | LevelData        | Koleksi level & progres unlock                |
|               | CollectibleData  | Data item & koleksi                           |
|               | QuestData        | Daftar misi & progres                         |
|               | GameSettings     | Volume, vibrasi, tutorial                     |
| **Sementara** | CutscenePlayer   | Aset dialog & progres cutscene                |
| (per scene)   | LevelSelection…  | Aset level terpilih                           |
|               | Mission, Health… | Logika gameplay (nyawa, musuh, puzzle, timer) |
|               | QuizPlayer       | Soal & skor kuis                              |

### 6.3. Struktur Controller

| Jenis Controller | Nama Controller                       | Tanggung Jawab                     |
| ---------------- | ------------------------------------- | ---------------------------------- |
| **Persisten**    | LevelData, QuestData…                 | Menyimpan & memproses data global  |
| **Sementara**    | MainMenu, GamePause, PlayerCharacter… | Mengatur UI lokal & event gameplay |

---

## 7. 🧪 Metodologi Pengembangan

Mengikuti **Game Development Life Cycle (GDLC)**:

1. **Inisiasi**: Konsep & target audiens
2. **Pra-Produksi**: GDD, mockup UI, prototipe dasar & struktur
3. **Produksi**: Integrasi aset & kode, optimalisasi
4. **Testing**:

   * **Black‑Box** (fungsi sesuai spesifikasi)
   * **Unit Testing** (≥ 80% code coverage)
   * **Static Code Analysis** (SonarQube, Code Metrics)
5. **Beta**: Playtesting terbuka/tertutup & survei
6. **Release**: Peluncuran & rencana pemeliharaan

---

## 8. 📊 Hasil Evaluasi

* **SonarQube & Code Metrics**: Kualitas kode **tinggi**, technical debt **rendah**
* **Unit Testing Coverage**: Mencapai **≥ 80%**
* **Survei (n = 6)**:

  * 91,7% menilai **struktur kode sangat baik**
  * 66,7% menyatakan **kemudahan pemeliharaan & pengembangan**

---

## 9. ✨ Kesimpulan

Penerapan **MVC** dengan **Agate MVC Framework** pada game “City of Philosophy” berhasil:

* 🏗️ **Membangun struktur kode terorganisir**
* 🔄 **Memudahkan iterasi & pengujian**
* 📈 **Mendukung skala game lebih besar**

> **Rekomendasi**: Adopsi pendekatan ini untuk proyek Unity lainnya guna meningkatkan **modularitas**, **skalabilitas**, dan **efisiensi pengembangan**!