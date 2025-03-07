---
title: Konversikan Proyek MS Sebagai JPEG di Aspose.Tasks
linktitle: Simpan Proyek Sebagai JPEG di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mudah mengonversi file Microsoft Project ke gambar JPEG menggunakan Aspose.Tasks untuk Java. Tingkatkan produktivitas Anda.
weight: 20
url: /id/java/project-file-operations/save-as-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversikan Proyek MS Sebagai JPEG di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menyimpan file Microsoft Project sebagai gambar JPEG menggunakan Aspose.Tasks untuk Java. Hal ini khususnya berguna untuk berbagi visualisasi proyek atau mengintegrasikan data proyek ke dalam laporan atau presentasi.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda. Anda dapat mengunduh dan menginstal versi terbaru dari[situs web Jawa](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks for Java: Unduh dan atur Aspose.Tasks for Java dengan mengikuti instruksi yang disediakan di[dokumentasi](https://reference.aspose.com/tasks/java/).

## Paket Impor
Pertama, impor paket yang diperlukan ke file Java Anda:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Langkah 1: Tentukan Direktori Data
Tetapkan jalur ke direktori data tempat file MS Project Anda berada.
```java
String dataDir = "Your Data Directory";
```
## Langkah 2: Muat File Proyek MS
Muat file MS Project menggunakan Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Langkah 3: Konfigurasikan Kualitas JPEG (Opsional)
 Jika Anda ingin mengatur kualitas JPEG, Anda dapat mengaturnya menggunakan`ImageSaveOptions` kelas. Kualitasnya berkisar dari 0 hingga 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Atur kualitas JPEG ke 50
```
## Langkah 4: Simpan Proyek sebagai JPEG
Simpan file MS Project sebagai gambar JPEG.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menyimpan file Microsoft Project sebagai gambar JPEG menggunakan Aspose.Tasks untuk Java. Fitur ini memungkinkan kemudahan berbagi dan integrasi data proyek ke dalam berbagai dokumen dan presentasi.
## FAQ
### Q: Bisakah saya mengatur kualitas gambar JPEG?
 A: Ya, Anda dapat mengatur kualitasnya menggunakan`setJpegQuality()` metode, dengan rentang dari 0 hingga 100.
### T: Bagaimana jika saya tidak menentukan kualitas JPEG?
J: Jika Anda tidak menentukan kualitasnya, kualitas default akan digunakan.
### T: Apakah Aspose.Tasks untuk Java gratis digunakan?
 J: Aspose.Tasks untuk Java adalah perpustakaan komersial, namun Anda dapat menjelajahi fitur-fiturnya dengan uji coba gratis. Mengunjungi[halaman uji coba gratis](https://releases.aspose.com/) untuk informasi lebih lanjut.
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk Java?
J: Anda bisa mendapatkan dukungan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### T: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks?
 J: Ya, Anda dapat membeli lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
