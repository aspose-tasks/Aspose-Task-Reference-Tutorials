---
date: 2025-12-21
description: Pelajari cara menyimpan proyek sebagai templat, mengekspor MPP ke CSV,
  dan mengonversi MPP ke teks menggunakan Aspose.Tasks untuk Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Simpan Proyek sebagai Template, CSV, dan Teks dengan Aspose.Tasks untuk Java
url: /id/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Simpan Proyek sebagai Template, CSV, dan Teks dengan Aspise.Tasks

## Perkenalan
Dalam tutorial ini, Anda akan menemukan **cara menyimpan proyek sebagai template** dan juga cara mengekspor file Microsoft Project (MPP) Anda ke format CSV dan teks biasa menggunakan pustaka Aspose.Tasks untuk Java. Apakah Anda perlu membuat template proyek yang dapat digunakan kembali, menghasilkan laporan CSV untuk analitik, atau menghasilkan ekstrak teks sederhana untuk integrasi, langkah‑langkah ini akan memandu Anda melalui proses dengan cepat dan efisien.

## Jawaban Cepat
- ** meminta saya mengekspor MPP ke CSV?** Ya – gunakan `project.save(..., SaveFileFormat.CSV)`.
- **Bagaimana cara mengekspor teks?** Simpan dengan `SaveFileFormat.TEXT`.
- **Apa yang dilakukan “save project as template”?** Itu membuat file `.mpt` yang menghapus nilai aktual dan baseline, siap untuk digunakan kembali.
- **Apakah saya membutuhkan lisensi?** Versi percobaan tersedia; lisensi komersial diperlukan untuk produksi.
- **Versi Java apa yang diperlukan?** Java8+ didukung.

## Apa itu “simpan proyek sebagai templat”?
Menyimpan proyek sebagai template (`.mpt`) menangkap struktur, hierarki tugas, dan pengugasan sumber daya sambil menghapus tanggal mulai/selesai aktual serta data baseline. Hal ini menjadikan template ideal untuk menggunakan kembali tata letak proyek standar pada banyak proyek baru.

## Mengapa menggunakan Aspose.Tasks untuk Java?
Aspose.Tasks memungkinkan Anda memanipulasi file Microsoft Project tanpa harus menginstal Microsoft Project itu sendiri. Ia mendukung **cara mengekspor MPP**, **cara mengekspor teks**, dan **mengonversi MPP ke CSV**, semuanya dari kode Java murni, yang sempurna untuk otomatisasi sisi server, pipeline CI, atau utilitas desktop.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. Java Development Kit (JDK) 8 atau yang lebih tinggi terpasang.
2. Pustaka Aspose.Tugas untuk Java ditambahkan ke proyek Anda. Unduh dari [di sini](https://releases.aspose.com/tasks/java/).
3. Familiaritas dasar dengan sintaks Java serta pengaturan proyek Maven/Gradle.

## Impor Paket
Pertama, impor kelas yang diperlukan dalam file sumber Java Anda:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Simpan Proyek sebagai CSV (Ekspor MPP ke CSV)
Mengekspor file MPP ke CSV berguna untuk analisis data di Excel atau alat BI.

### Langkah 1: Muat Proyek
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Langkah 2: Simpan sebagai CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Simpan Proyek sebagai Teks (Cara Mengekspor Teks)
Jika Anda membutuhkan representasi teks biasa dari tugas, sumber daya, atau penugasan, simpan proyek sebagai file teks.

### Langkah 1: Muat Proyek
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Langkah 2: Simpan sebagai Teks
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Simpan Proyek sebagai Templat (Buat Templat Proyek Java)
Membuat template yang dapat digunakan kembali menghapus tanggal aktual dan baseline, meninggalkan kerangka bersih untuk proyek baru.

### Langkah 1: Muat Proyek
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Langkah 2: Tetapkan Opsi Templat
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Langkah 3: Simpan sebagai Templat
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Masalah & Tip Umum
- **File Tidak Ditemukan:** Pastikan jalur ke `YourProject.mpp` benar atau gunakan jalur absolut.
- **Pengecualian Lisensi:** Tanpa lisensi yang valid, pustaka berjalan dalam mode evaluasi dan dapat menambahkan watermark. Terapkan lisensi Anda di awal kode (`License License = New License(); License.setLicense("Aspose.Tasks.Java.lic");`).
- **Proyek Besar:** Untuk file MPP yang sangat besar, pertimbangkan peningkatan ukuran heap JVM (`-Xmx2g`) untuk menghindari `OutOfMemoryError`.

## Kesimpulan
Kami telah membahas **cara menyimpan proyek sebagai template**, serta cara **mengekspor MPP ke CSV** dan **mengonversi MPP ke teks** menggunakan Aspose.Tasks untuk Java. Kemampuan ini memungkinkan Anda mengotomatisasi penanganan data proyek, menghasilkan template yang dapat digunakan kembali, dan mengintegrasikan informasi proyek ke sistem lain—semuanya tanpa perlu menginstal Microsoft Project.

## FAQ
### T: Bisakah Aspose.Tasks for Java menangani file proyek yang kompleks?
J: Tentu saja! Aspose.Tasks untuk Java dapat menangani proyek dengan berbagai tingkat kerumitan dengan mudah, menyediakan pemahaman komprehensif untuk format file Microsoft Project.

### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
A: Ya, Anda dapat memperoleh versi percobaan gratis Aspose.Tasks untuk Java dari [here](https://releases.aspose.com/).

### T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk Java?
A: Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan mengenai Aspose.Tasks untuk Java.

### T: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?
A: Ya, Anda dapat membeli lisensi sementara dari [here](https://purchase.aspose.com/temporary-license/), yang memungkinkan Anda memberikan potensi penuh pustaka ini.

### T: Apakah Aspose.Tasks untuk Java kompatibel dengan sistem operasi yang berbeda?
A: Ya, Aspose.Tasks untuk Java kompatibel dengan berbagai sistem operasi, termasuk Windows, macOS, dan Linux.

---

**Terakhir Diperbarui:** 21-12-2025
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (terbaru)
**Penulis:** Beranggapan  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
