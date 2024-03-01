---
title: Menguasai Hitungan Skala Waktu Proyek MS di Aspose.Tasks
linktitle: Tetapkan Jumlah Skala Waktu di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengelola penghitungan skala waktu secara efektif di MS Project menggunakan Aspose.Tasks untuk Java. Optimalkan visualisasi dan manajemen proyek dengan mudah.
type: docs
weight: 22
url: /id/java/project-file-operations/set-time-scale-count/
---
## Perkenalan
Mengelola penghitungan skala waktu di MS Project dapat memengaruhi visualisasi dan manajemen proyek secara signifikan. Dengan Aspose.Tasks untuk Java, API canggih untuk menangani tugas manajemen proyek secara terprogram, Anda dapat memanipulasi penghitungan skala waktu secara efisien untuk menyesuaikan tampilan proyek dengan kebutuhan spesifik Anda.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java Development Kit (JDK) di sistem Anda.
2.  Aspose.Tasks untuk Perpustakaan Java: Unduh dan instal perpustakaan Aspose.Tasks untuk Java. Anda bisa mendapatkannya dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Pengetahuan Dasar Pemrograman Java: Keakraban dengan bahasa pemrograman Java akan bermanfaat.

## Paket Impor
Impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Langkah 1: Tetapkan Direktori Data
Tentukan jalur ke direktori data tempat file proyek Anda akan disimpan:
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur ke direktori data Anda.
## Langkah 2: Buat Instans Proyek
 Buat instance yang baru`Project` obyek:
```java
Project project = new Project();
```
Ini menciptakan objek proyek baru.
## Langkah 3: Konfigurasikan Tampilan Gantt Chart
 Membuat`GanttChartView` objek untuk mengonfigurasi tampilan bagan Gantt:
```java
GanttChartView view = new GanttChartView();
```
## Langkah 4: Tetapkan Jumlah Skala Waktu untuk Tingkat Bawah
Tetapkan visibilitas hitungan dan tick untuk tingkat skala waktu terbawah:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Ini menentukan jumlah interval dan apakah akan menampilkan tanda centang untuk tingkat terbawah.
## Langkah 5: Tetapkan Jumlah Skala Waktu untuk Tingkat Menengah
Demikian pula, konfigurasikan tingkat skala waktu menengah:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Langkah 6: Tambahkan Tampilan ke Proyek
Tambahkan tampilan yang dikonfigurasi ke proyek:
```java
project.getViews().add(view);
```
Ini menambahkan tampilan yang disesuaikan ke proyek.
## Langkah 7: Tambahkan Data Uji ke Proyek
Tambahkan beberapa data pengujian ke proyek untuk demonstrasi:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Ini menciptakan dua tugas dengan durasi tertentu.
## Langkah 8: Simpan Proyek sebagai PDF
Simpan proyek sebagai file PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Ini menyimpan proyek dengan konfigurasi yang diterapkan ke file PDF.

## Kesimpulan
Mengelola jumlah skala waktu secara efektif di MS Project menggunakan Aspose.Tasks untuk Java memberdayakan Anda untuk menyesuaikan tampilan proyek untuk visualisasi dan manajemen yang lebih baik.
## FAQ
### T: Bisakah Aspose.Tasks for Java menangani file proyek berskala besar?
J: Ya, Aspose.Tasks for Java mampu menangani file proyek berskala besar secara efisien.
### T: Apakah Aspose.Tasks untuk Java kompatibel dengan IDE Java yang berbeda?
J: Ya, Aspose.Tasks untuk Java bekerja secara lancar dengan Java Integrated Development Environment (IDE) yang populer seperti Eclipse dan IntelliJ IDEA.
### T: Bisakah saya mengkustomisasi tampilan bagan Gantt menggunakan Aspose.Tasks untuk Java?
J: Tentu saja, Aspose.Tasks untuk Java menyediakan kemampuan ekstensif untuk menyesuaikan tampilan bagan Gantt sesuai kebutuhan Anda.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
 A: Ya, Anda bisa mendapatkan versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk Java?
 J: Anda dapat menemukan dukungan dan bantuan di forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).