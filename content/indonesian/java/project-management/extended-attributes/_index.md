---
title: Menangani Atribut yang Diperluas di Proyek Aspose.Tasks
linktitle: Menangani Atribut yang Diperluas di Proyek Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menangani atribut yang diperluas di proyek Aspose.Tasks menggunakan Java secara efisien. Panduan langkah demi langkah untuk manajemen proyek yang efektif.
type: docs
weight: 13
url: /id/java/project-management/extended-attributes/
---
## Perkenalan
Mengelola atribut yang diperluas dalam manajemen proyek sangat penting untuk menyesuaikan dan meningkatkan data proyek. Aspose.Tasks untuk Java menyediakan alat canggih untuk menangani atribut yang diperluas dalam file MS Project secara efisien. Tutorial ini akan memandu Anda melalui proses langkah demi langkah, memastikan Anda memahami setiap konsep secara menyeluruh.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan dasar tentang pemrograman Java.
2. JDK (Java Development Kit) diinstal pada sistem Anda.
3. Aspose.Tasks untuk perpustakaan Java diunduh dan disiapkan di proyek Java Anda.
## Paket Impor
Pertama, mari impor paket yang diperlukan untuk memulai:
```java
import java.util.Date;
import com.aspose.tasks.*;
```
## Langkah 1: Tentukan Direktori Data
```java
String dataDir = "Your Data Directory";
```
 Pastikan untuk mengganti`"Your Data Directory"` dengan jalur ke direktori data proyek Anda.
## Langkah 2: Muat File Proyek
```java
Project prj = new Project(dataDir + "project5.mpp");
```
 Baris ini memuat file proyek bernama`"project5.mpp"`.
## Langkah 3: Akses Definisi Atribut yang Diperluas
```java
ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();
```
Di sini, kami mengambil kumpulan definisi atribut yang diperluas dari proyek.
## Langkah 4: Buat Definisi Atribut yang Diperluas
```java
ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
```
 Segmen kode ini membuat definisi atribut yang diperluas untuk tugas, menentukan jenis bidang khusus sebagai`Start` dan nama atribut sebagai`"Start 7"`.
## Langkah 5: Tambahkan Definisi ke Proyek
```java
prj.getExtendedAttributes().add(attributeDefinition);
eads.add(attributeDefinition);
```
Kami menambahkan definisi atribut diperluas yang baru dibuat ke proyek dan kumpulan definisi atribut.
## Langkah 6: Akses Tugas dan Atribut yang Diperluas
```java
Task tsk = prj.getRootTask().getChildren().getById(1);
ExtendedAttributeCollection eas = tsk.getExtendedAttributes();
```
Di sini, kami mengambil tugas dari proyek dan atribut tambahan terkait.
## Langkah 7: Buat Instans Atribut yang Diperluas
```java
ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();
```
Langkah ini membuat instance atribut yang diperluas berdasarkan definisi atribut yang telah ditentukan sebelumnya.
## Langkah 8: Tetapkan Nilai Atribut
```java
Date date = new Date();
ea.setDateValue(date);
```
Kami menetapkan nilai atribut yang diperluas, dalam hal ini, nilai tanggal.
## Langkah 9: Tambahkan Atribut ke Tugas
```java
eas.add(ea);
```
Terakhir, kami menambahkan atribut extended ke tugas tersebut.
## Langkah 10: Simpan Proyek
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
Baris ini menyimpan proyek yang dimodifikasi dengan atribut extended yang ditambahkan ke file XML.
## Kesimpulan
Dalam tutorial ini, Anda mempelajari cara menangani atribut yang diperluas di proyek Aspose.Tasks menggunakan Java. Dengan mengikuti langkah-langkah ini, Anda dapat mengelola data proyek kustom secara efisien, sehingga meningkatkan kemampuan manajemen proyek Anda.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?
J: Ya, Aspose.Tasks mendukung berbagai bahasa pemrograman termasuk Java, .NET, dan C++.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
J: Ya, Anda dapat mengunduh uji coba gratis dari situs Aspose.Tasks.
### T: Dapatkah saya menyesuaikan jenis atribut yang diperluas?
J: Tentu saja, Aspose.Tasks memungkinkan Anda menentukan jenis atribut tambahan khusus yang disesuaikan dengan kebutuhan proyek Anda.
### T: Bagaimana cara mengakses dokumentasi Aspose.Tasks?
 J: Anda dapat menemukan dokumentasi lengkap di situs web Aspose.Tasks[dokumentasi](https://reference.aspose.com/tasks/java/).
### T: Apakah dukungan teknis tersedia untuk pengguna Aspose.Tasks?
 A: Ya, Anda dapat mengakses dukungan teknis melalui forum Aspose.Tasks[situs web](https://forum.aspose.com/c/tasks/15).