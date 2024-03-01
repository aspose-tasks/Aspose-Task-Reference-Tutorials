---
title: Cetak Halaman untuk Memisahkan Gambar di Aspose.Tasks
linktitle: Cetak Halaman untuk Memisahkan Gambar di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mencetak halaman untuk memisahkan gambar di Aspose.Tasks untuk Java. Tingkatkan visualisasi proyek dengan panduan langkah demi langkah ini.
type: docs
weight: 22
url: /id/java/project-management/print-pages/
---
## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses pencetakan halaman untuk memisahkan gambar menggunakan Aspose.Tasks untuk Java. Fungsionalitas ini bisa sangat berguna ketika Anda perlu memvisualisasikan tata letak proyek atau tugas penting secara terpisah.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari[Di Sini](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks untuk Perpustakaan Java: Unduh dan sertakan perpustakaan Aspose.Tasks untuk Java dalam proyek Anda. Anda bisa mendapatkannya dari[Di Sini](https://releases.aspose.com/tasks/java/).

## Paket Impor
Pastikan untuk mengimpor paket yang diperlukan di awal file Java Anda:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Langkah 1: Muat Data Proyek
Pertama, muat data proyek dari file MPP Anda:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Langkah 2: Atur Opsi Penyimpanan Gambar
Tentukan pilihan untuk menyimpan gambar, termasuk tanggal mulai, tanggal akhir, tugas penting, legenda, dan garis kisi:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Langkah 3: Sesuaikan Garis Kisi
Sesuaikan garis kisi untuk gambar, tentukan jenis, warna, dan pola:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Langkah 4: Simpan Gambar
Simpan tata letak proyek sebagai gambar, baik sebagai file tunggal maupun file terpisah:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Kesimpulan
Dalam tutorial ini, kami telah mendemonstrasikan cara mencetak halaman untuk memisahkan gambar menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat memvisualisasikan tata letak proyek dan tugas penting secara efisien sesuai dengan kebutuhan Anda.
## FAQ
### T: Dapatkah saya menyesuaikan format gambar saat menyimpan tata letak proyek?
 A: Ya, Aspose.Tasks for Java mendukung berbagai format gambar seperti PNG, JPEG, BMP, dll. Anda dapat menentukan format yang diinginkan di bagian`ImageSaveOptions` kelas.
### T: Apakah Aspose.Tasks untuk Java kompatibel dengan lingkungan pengembangan Java yang berbeda?
J: Ya, Aspose.Tasks untuk Java kompatibel dengan sebagian besar lingkungan pengembangan Java, termasuk Eclipse, IntelliJ IDEA, dan NetBeans.
### T: Dapatkah saya mengintegrasikan Aspose.Tasks untuk Java ke dalam proyek Maven atau Gradle saya?
J: Ya, Anda dapat dengan mudah mengintegrasikan Aspose.Tasks untuk Java ke dalam proyek Maven atau Gradle Anda dengan menambahkan ketergantungan yang sesuai pada proyek Anda.`pom.xml` atau`build.gradle` mengajukan.
### T: Apakah Aspose.Tasks untuk Java mendukung ekspor data proyek ke format lain selain gambar?
J: Ya, Aspose.Tasks untuk Java mendukung ekspor data proyek ke berbagai format seperti PDF, HTML, XLSX, dll., memberikan fleksibilitas dalam visualisasi dan pelaporan data.
### T: Apakah ada dukungan komunitas yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat menemukan dukungan komunitas, mengajukan pertanyaan, dan berinteraksi dengan pengguna lain di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).