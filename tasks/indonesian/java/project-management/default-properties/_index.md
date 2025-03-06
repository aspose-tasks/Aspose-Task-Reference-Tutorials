---
title: Kelola Properti Proyek MS secara Efisien di Aspose.Tasks
linktitle: Kelola Properti Proyek Default di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengelola properti MS Project default menggunakan Aspose.Tasks untuk Java. Sederhanakan alur kerja manajemen proyek Anda dengan mudah.
weight: 11
url: /id/java/project-management/default-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola Properti Proyek MS secara Efisien di Aspose.Tasks

## Perkenalan
Apakah Anda ingin menyederhanakan proses manajemen proyek Anda dengan Aspose.Tasks untuk Java? Mengelola properti default di file Microsoft Project dapat meningkatkan efisiensi secara signifikan. Dalam tutorial ini, kita akan memandu petunjuk langkah demi langkah tentang cara mengelola properti default MS Project menggunakan Aspose.Tasks.
## Prasyarat
Sebelum kita mempelajari tutorialnya, pastikan Anda memiliki prasyarat berikut:
### 1. Kit Pengembangan Java (JDK)
   - Pastikan JDK terinstal di sistem Anda.
   -  Anda dapat mengunduhnya dari[Di Sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tugas untuk Perpustakaan Java
   - Unduh dan sertakan perpustakaan Aspose.Tasks untuk Java dalam proyek Anda.
   -  Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/tasks/java/).
## Paket Impor
Pertama, impor paket yang diperlukan ke file Java Anda:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Mari kita bagi prosesnya menjadi langkah-langkah yang dapat dikelola:
## Langkah 1: Muat File Proyek
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Langkah 2: Tampilkan Properti Default
```java
// Tampilkan properti default
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Langkah 3: Tetapkan Properti Default
```java
// Tetapkan properti default
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## Langkah 4: Simpan Proyek ke Format XML
```java
// Simpan proyek ke format XML
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Langkah 5: Tampilkan Hasil
```java
// Tampilkan hasil konversi.
System.out.println("Process completed Successfully");
```
Dengan mengikuti langkah-langkah ini, Anda dapat mengelola properti MS Project default secara efisien menggunakan Aspose.Tasks untuk Java.
## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara mengelola properti MS Project default menggunakan Aspose.Tasks untuk Java. Dengan memanfaatkan teknik ini, Anda dapat mengoptimalkan alur kerja manajemen proyek, meningkatkan produktivitas dan organisasi.
## FAQ
### Q1: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?
A1: Ya, Aspose.Tasks mendukung berbagai bahasa pemrograman seperti .NET, Python, dan Java.
### Q2: Apakah Aspose.Tasks cocok untuk penggunaan pribadi dan perusahaan?
A2: Tentu saja! Baik Anda mengelola proyek pribadi kecil atau inisiatif perusahaan skala besar, Aspose.Tasks melayani semuanya.
### Q3: Apakah Aspose.Tasks menawarkan dukungan pelanggan?
A3: Ya, Anda dapat menemukan bantuan dan dukungan komunitas di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
### Q4: Bisakah saya mencoba Aspose.Tasks sebelum membeli?
 A4: Tentu saja! Anda dapat memanfaatkan uji coba gratis dari[situs web](https://releases.aspose.com/).
### Q5: Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks?
 A5: Anda bisa mendapatkan lisensi sementara dari[halaman pembelian](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
