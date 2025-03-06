---
title: Buat Dasar Tugas Proyek MS di Aspose.Tasks
linktitle: Membuat Dasar Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara membuat dasar tugas Microsoft Project di Java menggunakan Aspose.Tasks, pustaka canggih untuk mengelola data proyek dengan mudah.
weight: 11
url: /id/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Dasar Tugas Proyek MS di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari proses pembuatan dasar tugas Microsoft Project menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah pustaka Java canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project tanpa memerlukan instalasi Microsoft Project. Dengan Aspose.Tasks, Anda dapat dengan mudah memanipulasi data proyek, termasuk tugas, sumber daya, dan kalender, untuk menyederhanakan tugas manajemen proyek.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Aspose.Tasks untuk Java memerlukan JDK diinstal pada sistem Anda. Anda dapat mengunduh dan menginstal JDK dari situs web Oracle.
2.  Aspose.Tasks untuk Perpustakaan Java: Unduh perpustakaan Aspose.Tasks untuk Java dari[tautan unduhan](https://releases.aspose.com/tasks/java/) asalkan.

## Paket Impor
Untuk mulai bekerja dengan Aspose.Tasks di proyek Java Anda, impor paket yang diperlukan:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Langkah 1: Buat Objek Proyek
```java
Project project = new Project();
```
 Pertama, buat yang baru`Project` obyek. Objek ini mewakili file Microsoft Project yang akan Anda kerjakan.
## Langkah 2: Tambahkan Tugas ke Proyek
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Menggunakan`getRootTask()` metode, akses tugas root proyek dan kemudian tambahkan tugas baru ke dalamnya menggunakan`add()` metode. Berikan nama untuk tugas di dalam tanda kurung.
## Langkah 3: Tetapkan Dasar untuk Tugas Tertentu
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Untuk menetapkan garis dasar tugas tertentu, buatlah daftar tugas (`myList` dalam hal ini) dan isi dengan tugas-tugas yang ingin Anda tetapkan garis dasarnya. Kemudian, gunakan`setBaseline()` metode, menentukan tipe dasar dan daftar tugas.
## Langkah 4: Tetapkan Garis Dasar untuk Keseluruhan Proyek
```java
project.setBaseline(BaselineType.Baseline);
```
 Alternatifnya, Anda dapat menetapkan garis dasar untuk keseluruhan proyek hanya dengan memanggil`setBaseline()` metode dengan tipe dasar yang ditentukan.

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara membuat dasar tugas Microsoft Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat mengelola data proyek secara efisien dan menyederhanakan tugas manajemen proyek dengan mudah.
## FAQ
### Bisakah saya menggunakan Aspose.Tasks untuk Java tanpa menginstal Microsoft Project?
Ya, Aspose.Tasks untuk Java memungkinkan Anda bekerja dengan file Microsoft Project tanpa memerlukan Microsoft Project untuk diinstal di sistem Anda.
### Apakah Aspose.Tasks untuk Java kompatibel dengan versi Microsoft Project yang berbeda?
Ya, Aspose.Tasks untuk Java mendukung berbagai versi Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.
### Bisakah saya memanipulasi sumber daya proyek menggunakan Aspose.Tasks untuk Java?
Tentu saja, Aspose.Tasks untuk Java menyediakan fitur canggih untuk memanipulasi sumber daya proyek, termasuk menambah, memperbarui, dan menghapus sumber daya sesuai kebutuhan.
### Apakah Aspose.Tasks untuk Java mendukung pengaturan dependensi tugas?
Ya, Anda dapat mengatur dependensi tugas dengan mudah menggunakan Aspose.Tasks untuk Java, sehingga memungkinkan Anda menetapkan urutan tugas dalam proyek Anda.
### Apakah dukungan teknis tersedia untuk Aspose.Tasks untuk Java?
 Ya, Anda dapat mengakses dukungan teknis untuk Aspose.Tasks untuk Java melalui[forum dukungan](https://forum.aspose.com/c/tasks/15), tempat Anda dapat mengajukan pertanyaan dan mencari bantuan dari komunitas dan staf pendukung Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
