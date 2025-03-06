---
title: Kelola Biaya Tugas di Aspose.Tasks
linktitle: Kelola Biaya Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengelola biaya tugas di aplikasi Java menggunakan Aspose.Tasks. Ikuti panduan langkah demi langkah kami untuk manajemen biaya proyek yang efektif.
type: docs
weight: 21
url: /id/java/task-properties/manage-task-cost/
---
## Perkenalan
Selamat datang di dunia Aspose.Tasks untuk Java, perpustakaan canggih yang memungkinkan Anda mengelola biaya tugas dengan lancar dalam aplikasi Java Anda. Dalam panduan langkah demi langkah ini, kita akan mempelajari cara memanfaatkan Aspose.Tasks secara efektif untuk menangani biaya tugas, memastikan manajemen proyek yang efisien.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Lingkungan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di sistem Anda.
2. Perpustakaan Aspose.Tasks: Unduh dan instal perpustakaan Aspose.Tasks untuk Java. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/tasks/java/).
## Paket Impor
Setelah Anda menyiapkan lingkungan dan menginstal pustaka Aspose.Tasks, Anda perlu mengimpor paket yang diperlukan ke proyek Java Anda. Sertakan baris berikut dalam kode Anda:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Impor kelas Aspose.Tasks
```
Sekarang, mari kita bagi contoh ini menjadi beberapa langkah untuk mengelola biaya tugas secara efektif.
## Langkah 1: Siapkan Proyek Anda
```java
// Tetapkan jalur ke direktori dokumen Anda
String dataDir = "Your Document Directory";
// Buat proyek baru
Project project = new Project();
```
## Langkah 2: Tambahkan Tugas Baru
```java
// Tambahkan tugas baru ke tugas root
Task task = project.getRootTask().getChildren().add("Task");
```
## Langkah 3: Tetapkan Biaya Tugas
```java
// Tetapkan biaya tugas menjadi 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```
## Langkah 4: Ambil Informasi Tugas
```java
// Ambil dan cetak informasi tugas
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Ambil dan cetak informasi biaya tingkat proyek
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```
Ulangi langkah-langkah ini untuk mengelola biaya tugas secara efektif di aplikasi Aspose.Tasks for Java Anda.
## Kesimpulan
Kesimpulannya, menguasai manajemen biaya tugas sangat penting untuk keberhasilan pelaksanaan proyek. Aspose.Tasks untuk Java memberikan solusi tangguh, memungkinkan pengembang menangani biaya dengan tepat.
## FAQ
### T: Di mana saya dapat menemukan dokumentasi Aspose.Tasks untuk Java?
 J: Anda dapat mengakses dokumentasinya[Di Sini](https://reference.aspose.com/tasks/java/).
### T: Bagaimana cara mengunduh perpustakaan Aspose.Tasks untuk Java?
 J: Unduh perpustakaannya[Di Sini](https://releases.aspose.com/tasks/java/).
### T: Di mana saya dapat membeli Aspose.Tasks untuk Java?
 J: Anda bisa membelinya[Di Sini](https://purchase.aspose.com/buy).
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 A: Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat mencari dukungan untuk Aspose.Tasks untuk Java?
 J: Kunjungi forum dukungan[Di Sini](https://forum.aspose.com/c/tasks/15).