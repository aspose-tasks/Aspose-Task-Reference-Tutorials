---
title: Menulis dan Membaca Rumus Proyek MS di Aspose.Tasks
linktitle: Menulis dan Membaca Rumus di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Belajar menulis dan membaca rumus MS Project secara efisien dengan Aspose.Tasks untuk Java. Tingkatkan keterampilan manajemen proyek Anda.
weight: 12
url: /id/java/formulas/write-read-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menulis dan Membaca Rumus Proyek MS di Aspose.Tasks

## Perkenalan
Dalam bidang manajemen proyek, penanganan data yang efektif adalah yang terpenting. Aspose.Tasks untuk Java adalah solusi tangguh yang memfasilitasi manipulasi dan ekstraksi data dari file Microsoft Project. Salah satu fitur canggih yang ditawarkannya adalah kemampuan untuk menulis dan membaca rumus MS Project. Tutorial ini akan memandu Anda melalui proses memanfaatkan fungsi ini untuk meningkatkan tugas manajemen proyek Anda.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda.
2.  Aspose.Tasks for Java: Unduh dan instal Aspose.Tasks for Java dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Pilih IDE pilihan Anda untuk pengembangan Java.

## Mengimpor Paket
Untuk memulai, impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Langkah 1: Siapkan Direktori Data
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
```
Pada langkah ini, tentukan direktori tempat file MS Project Anda berada.
## Langkah 2: Muat File Proyek
```java
Project project = new Project(dataDir + "project.mpp");
```
Di sini, muat file MS Project ke a`Project` objek untuk manipulasi.
## Langkah 3: Tentukan Formula Khusus
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
Langkah ini melibatkan pembuatan bidang khusus dengan rumus yang menggandakan biaya tugas.
## Langkah 4: Tambahkan Tugas dan Tetapkan Biaya
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Di sini, tugas baru ditambahkan, dan biayanya ditetapkan menjadi 100.
## Langkah 5: Simpan File Proyek
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Terakhir, simpan file proyek yang dimodifikasi.

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara menulis dan membaca rumus MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat memanipulasi data proyek secara efisien untuk memenuhi kebutuhan spesifik Anda.
## FAQ
### Apakah Aspose.Tasks kompatibel dengan semua versi MS Project?
Aspose.Tasks menawarkan kompatibilitas dengan berbagai versi MS Project, memastikan fleksibilitas bagi pengguna.
### Bisakah saya mengintegrasikan Aspose.Tasks ke dalam proyek Java saya yang sudah ada?
Sangat! Aspose.Tasks menyediakan integrasi yang lancar dengan proyek Java melalui penggunaan API sederhana.
### Apakah ada batasan pada jenis rumus yang bisa saya buat?
Dengan Aspose.Tasks, Anda memiliki fleksibilitas luas dalam menyusun formula khusus yang disesuaikan dengan kebutuhan proyek Anda.
### Apakah Aspose.Tasks mendukung penerapan multi-platform?
Ya, Aspose.Tasks mendukung penerapan di berbagai platform, sehingga meningkatkan keserbagunaannya.
### Bagaimana saya bisa mendapatkan dukungan teknis untuk Aspose.Tasks?
 Untuk bantuan teknis dan dukungan komunitas, kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
