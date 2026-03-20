---
date: 2025-12-17
description: Pelajari cara menyimpan proyek sebagai gambar dan mengubah resolusi gambar
  di Java menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah ini menunjukkan
  cara merender data MS Project dengan format 24bppRgb.
linktitle: Save Project as Image – 24bppRgb Format
second_title: Aspose.Tasks Java API
title: Simpan Proyek sebagai Gambar – Format 24bppRgb dengan Aspose.Tasks
url: /id/java/project-file-operations/render-data-format-24bppRgb/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan Proyek sebagai Gambar – Format 24bppRgb dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan belajar cara **menyimpan proyek sebagai gambar** menggunakan format piksel 24bppRgb dengan Aspose.Tasks untuk Java. Merender data MS Project ke dalam gambar sangat berguna ketika Anda perlu berbagi snapshot visual dari jadwal, menyisipkan timeline dalam laporan, atau menghasilkan thumbnail untuk portal proyek. Kami juga akan menunjukkan cara **mengubah resolusi gambar java** untuk memenuhi kebutuhan kualitas Anda.

## Jawaban Cepat
- **Apakah saya dapat merender proyek ke gambar?** Ya, Aspose.Tasks memungkinkan Anda menyimpan proyek sebagai TIFF, PNG, JPEG, dll.  
- **Format piksel mana yang memberikan kedalaman warna terbaik?** `Format24bppRgb` menyediakan gambar true‑color (24‑bit).  
- **Bagaimana cara menyesuaikan resolusi gambar?** Gunakan `setHorizontalResolution` dan `setVerticalResolution` pada `ImageSaveOptions`.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi komersial diperlukan untuk penggunaan non‑evaluasi.  
- **Apakah ini kompatibel dengan semua versi Java?** Berfungsi dengan Java 8 dan yang lebih baru.

## Apa itu “simpan proyek sebagai gambar”?
Menyimpan proyek sebagai gambar mengonversi representasi visual dari file Microsoft Project (`.mpp`) ke dalam format raster (misalnya, TIFF). File yang dihasilkan dapat ditampilkan di browser, disisipkan ke dalam dokumen, atau dicetak tanpa memerlukan aplikasi Project asli.

## Mengapa menggunakan format 24bppRgb?
Format piksel 24bppRgb menyimpan setiap piksel dengan 8 bit untuk merah, hijau, dan biru, menghasilkan kualitas true‑color tanpa saluran alfa. Ini ideal untuk laporan dengan kejelasan tinggi di mana akurasi warna penting, sambil menjaga ukuran file tetap wajar dibandingkan format 32‑bit.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

1. **Java Development Kit (JDK)** – JDK 8 atau yang lebih baru terpasang di mesin Anda.  
2. **Aspose.Tasks for Java** – Unduh dan instal dari [here](https://releases.aspose.com/tasks/java/).  
3. **Pengetahuan dasar Java** – Familiaritas dengan sintaks Java dan penyiapan proyek akan membantu Anda mengikuti potongan kode.

## Impor Paket
Pertama, impor kelas Aspose.Tasks yang diperlukan ke dalam proyek Java Anda:

```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Tentukan Direktori Data
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Ganti `"Your Data Directory"` dengan path absolut tempat file `.mpp` Anda berada.

### Langkah 2: Muat File Proyek
```java
Project project = new Project(dataDir + "project.mpp");
```
Baris ini membaca file Microsoft Project (`project.mpp`) dan membuat objek `Project` yang dapat dimanipulasi oleh Aspose.Tasks.

### Langkah 3: Konfigurasikan Opsi Penyimpanan Gambar
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
Di sini kami mengatur format output menjadi TIFF, menentukan resolusi **72 dpi** (Anda dapat mengubah nilai ini sesuai kebutuhan – inilah tempat Anda **mengubah resolusi gambar java**), dan memilih format piksel 24bppRgb untuk output true‑color.

### Langkah 4: Simpan Data Proyek sebagai Gambar
```java
project.save(dataDir + "resFile.tif", options);
```
Metode `save` menulis gambar yang dirender ke `resFile.tif` menggunakan opsi yang telah ditentukan di atas.

## Masalah Umum dan Solusinya
| Masalah | Penyebab | Solusi |
|-------|--------|-----|
| **Output gambar kosong** | Tampilan proyek mungkin kosong. | Panggil `project.setDefaultView(ViewType.Gantt);` sebelum menyimpan. |
| **Gambar beresolusi rendah** | Resolusi diatur terlalu rendah. | Tingkatkan `setHorizontalResolution` dan `setVerticalResolution` (misalnya, 150 dpi). |
| **Format piksel tidak didukung** | Menggunakan versi Aspose.Tasks yang lebih lama. | Tingkatkan ke rilis Aspose.Tasks for Java terbaru. |

## Kesimpulan
Anda kini tahu cara **menyimpan proyek sebagai gambar** dengan format 24bppRgb dan menyesuaikan resolusi menggunakan Aspose.Tasks untuk Java. Pendekatan ini memungkinkan Anda menghasilkan representasi visual yang jelas dan akurat warna dari jadwal proyek untuk dibagikan, dilaporkan, atau diarsipkan.

## FAQ
### Q: Apakah saya dapat merender data proyek dalam format gambar lain?
A: Ya, Aspose.Tasks mendukung merender data proyek ke berbagai format gambar seperti PNG, JPEG, BMP, dll.  
### Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi MS Project?
A: Ya, Aspose.Tasks mendukung banyak versi MS Project termasuk 2003, 2007, 2010, 2013, dan 2016.  
### Q: Bisakah saya menyesuaikan resolusi dan format piksel gambar yang dirender?
A: Ya, Anda dapat menyesuaikan resolusi dan format piksel sesuai kebutuhan menggunakan Aspose.Tasks.  
### Q: Apakah Aspose.Tasks memerlukan lisensi untuk penggunaan komersial?
A: Ya, Anda perlu membeli lisensi untuk penggunaan komersial Aspose.Tasks. Anda dapat memperoleh lisensi sementara untuk tujuan pengujian dari [here](https://purchase.aspose.com/temporary-license/).  
### Q: Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks?
A: Anda dapat mendapatkan dukungan untuk Aspose.Tasks melalui [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Terakhir Diperbarui:** 2025-12-17  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}