---
title: Tentukan Versi Proyek MS dengan Aspose.Tasks
linktitle: Tentukan Versi Proyek dengan Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menentukan versi file MS Project secara terprogram menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah dengan contoh kode.
type: docs
weight: 12
url: /id/java/project-management/determine-version/
---
## Perkenalan
Tutorial ini akan memandu Anda dalam menggunakan Aspose.Tasks untuk Java untuk menentukan versi file MS Project langkah demi langkah. Aspose.Tasks adalah API Java yang kuat yang memungkinkan pengembang memanipulasi file Microsoft Project tanpa memerlukan instalasi Microsoft Project.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  File JAR Aspose.Tasks untuk Java: Unduh pustaka Aspose.Tasks untuk Java dari[situs web](https://releases.aspose.com/tasks/java/) dan menambahkannya ke proyek Java Anda.
3. File Proyek MS: Siapkan file Proyek MS (format XML) untuk pengujian.

## Paket Impor
Sebelum mendalami kodenya, mari impor paket yang diperlukan:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Langkah 1: Siapkan Proyek
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan path ke direktori yang berisi file MS Project Anda.
## Langkah 2: Muat Proyek
```java
Project project = new Project(dataDir + "input.xml");
```
 Mengganti`"input.xml"` dengan nama file MS Project Anda.
## Langkah 3: Tentukan Versi Proyek
```java
//Tampilkan properti versi proyek
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Cuplikan kode ini mengambil dan mencetak versi dan tanggal terakhir penyimpanan file MS Project.
## Langkah 4: Tampilkan Hasil
```java
//Tampilkan hasil konversi.
System.out.println("Process completed Successfully");
```
Baris ini menunjukkan selesainya proses.

## Kesimpulan
Dalam tutorial ini, Anda mempelajari cara menentukan versi file MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti panduan langkah demi langkah, Anda dapat bekerja secara efisien dengan file MS Project di aplikasi Java Anda tanpa kerumitan.

## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?
J: Ya, Aspose.Tasks mendukung berbagai bahasa pemrograman termasuk .NET, Java, dan C++.
### T: Apakah Aspose.Tasks cocok untuk proyek skala besar?
J: Tentu saja, Aspose.Tasks dirancang untuk menangani proyek dengan ukuran berapa pun dengan mudah.
### T: Dapatkah saya menyesuaikan data proyek menggunakan Aspose.Tasks?
J: Ya, Anda dapat memanipulasi data proyek, mengubah tugas, sumber daya, dan banyak lagi menggunakan Aspose.Tasks.
### T: Apakah Aspose.Tasks memerlukan instalasi Microsoft Project?
J: Tidak, Aspose.Tasks bekerja secara independen dan tidak memerlukan instalasi Microsoft Project.
### T: Apakah dukungan teknis tersedia untuk Aspose.Tasks?
 A: Ya, Anda bisa mendapatkan dukungan teknis dari forum Aspose.Tasks di[Di Sini](https://forum.aspose.com/c/tasks/15).