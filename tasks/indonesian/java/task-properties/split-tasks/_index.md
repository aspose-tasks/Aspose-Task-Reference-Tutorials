---
title: Pisahkan Tugas di Aspose.Tasks
linktitle: Pisahkan Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Kuasai manajemen tugas di Java dengan Aspose.Tasks! Pelajari cara membagi tugas secara efisien untuk jadwal proyek yang optimal. Unduh sekarang!
weight: 29
url: /id/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pisahkan Tugas di Aspose.Tasks

## Perkenalan
Apakah Anda kesulitan dengan manajemen tugas di proyek Java Anda? Aspose.Tasks untuk Java memberikan solusi canggih untuk membagi tugas secara efisien, meningkatkan kemampuan manajemen proyek. Dalam tutorial ini, kami akan memandu Anda melalui proses pemisahan tugas menggunakan Aspose.Tasks untuk Java, membantu Anda mengoptimalkan jadwal proyek dan alokasi sumber daya.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada mesin Anda.
-  Aspose.Tasks untuk perpustakaan Java diunduh dan ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari[Aspose.Tasks untuk dokumentasi Java](https://reference.aspose.com/tasks/java/).
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Langkah 1: Buat Proyek Baru
Mulailah dengan membuat proyek baru menggunakan perpustakaan Aspose.Tasks:
```java
// Buat proyek baru
Project splitTaskProject = new Project();
```
## Langkah 2: Tetapkan Kalender Proyek
Tetapkan pengaturan kalender proyek untuk menetapkan garis waktu:
```java
// Dapatkan kalender standar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Tetapkan pengaturan kalender proyek
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (lanjutkan dengan contoh)
```
## Langkah 3: Tambahkan Tugas Root
Tambahkan tugas root ke proyek Anda:
```java
// Tugas akar
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Langkah 4: Tambahkan Tugas Baru untuk Dibagi
Tambahkan tugas baru ke proyek Anda yang ingin Anda bagi:
```java
// Tambahkan tugas baru
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Langkah 5: Buat Penugasan Sumber Daya
Buat penetapan sumber daya baru untuk tugas tersebut:
```java
// Buat penetapan sumber daya baru
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Langkah 6: Hasilkan Data Berfase Waktu
Menghasilkan data bertahap penugasan sumber daya:
```java
// Menghasilkan data fase waktu penetapan sumber daya
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Langkah 7: Bagi Tugas
Bagi tugas menjadi beberapa bagian:
```java
// Bagi tugas menjadi 3 bagian
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (lanjutkan dengan contoh)
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara membagi tugas menggunakan Aspose.Tasks untuk Java. Pustaka yang kuat ini menyederhanakan manajemen tugas dalam proyek Java, memberikan solusi efisien untuk mengoptimalkan jadwal proyek dan alokasi sumber daya.
## Pertanyaan yang Sering Diajukan
### Bisakah saya membagi tugas dengan durasi berbeda?
Ya, Anda dapat menyesuaikan durasi tugas sesuai dengan kebutuhan proyek Anda.
### Apakah Aspose.Tasks for Java kompatibel dengan semua versi Java?
Aspose.Tasks untuk Java dirancang untuk bekerja secara lancar dengan berbagai versi Java, memastikan kompatibilitas.
### Bisakah saya menggunakan Aspose.Tasks untuk Java secara gratis?
Aspose.Tasks untuk Java menawarkan uji coba gratis, memungkinkan Anda menjelajahi fitur-fiturnya sebelum melakukan pembelian.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk Java?
 Mengunjungi[Aspose.Tasks untuk forum dukungan Java](https://forum.aspose.com/c/tasks/15) untuk mendapatkan bantuan dan berhubungan dengan masyarakat.
### Apakah saya memerlukan lisensi sementara untuk Aspose.Tasks untuk Java?
 Anda dapat memperoleh lisensi sementara dari[Link ini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
