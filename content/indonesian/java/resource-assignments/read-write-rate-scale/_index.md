---
title: Skala Kecepatan Baca dan Tulis untuk Penugasan Sumber Daya di Aspose.Tasks
linktitle: Skala Kecepatan Baca dan Tulis untuk Penugasan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengelola skala tingkat penetapan sumber daya secara efektif di Aspose.Tasks untuk Java dengan tutorial komprehensif ini.
type: docs
weight: 20
url: /id/java/resource-assignments/read-write-rate-scale/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengelola skala tingkat penetapan sumber daya menggunakan Aspose.Tasks untuk Java, pustaka yang kuat untuk bekerja dengan file Microsoft Project secara terprogram. Dengan mengikuti langkah-langkah ini, Anda akan dapat secara efektif memanipulasi pengaturan skala tarif untuk penetapan sumber daya di aplikasi Java Anda.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java Development Kit (JDK) di sistem Anda.
2.  Aspose.Tasks for Java Library: Unduh dan instal perpustakaan Aspose.Tasks for Java dari[Di Sini](https://releases.aspose.com/tasks/java/).

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan untuk bekerja dengan fungsi Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Langkah 1: Siapkan proyek Anda
Mulailah dengan menyiapkan proyek Java Anda dan sertakan pustaka Aspose.Tasks dalam dependensi Anda.
## Langkah 2: Muat File Proyek
Muat file Proyek yang ingin Anda kerjakan ke dalam aplikasi Java Anda.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Langkah 3: Tambahkan Tugas
Tambahkan tugas baru ke proyek Anda.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Langkah 4: Tentukan Sumber Daya
Mendefinisikan sumber daya material dan non material dan menentukan jenisnya.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Langkah 5: Tetapkan Sumber Daya ke Tugas
Tetapkan sumber daya yang telah ditentukan sebelumnya ke tugas beserta jenis skala tarifnya.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Langkah 6: Simpan Proyek
Simpan proyek dengan penetapan sumber daya yang dimodifikasi.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Langkah 7: Ambil Penugasan Sumber Daya
Muat ulang proyek yang disimpan dan ambil penetapan sumber daya untuk memverifikasi pengaturan skala tarif.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Kesimpulan
Mengelola skala tingkat penugasan sumber daya di Aspose.Tasks untuk Java sangat penting untuk manajemen proyek yang efektif. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah memanipulasi pengaturan skala tarif untuk penetapan sumber daya di aplikasi Java Anda.
## FAQ
### Q1: Dapatkah saya menggunakan Aspose.Tasks untuk Java dengan IDE Java apa pun?
J: Ya, Aspose.Tasks untuk Java kompatibel dengan semua IDE Java utama, termasuk IntelliJ IDEA, Eclipse, dan NetBeans.
### Q2: Apakah Aspose.Tasks mendukung format file lain selain MPP?
J: Ya, Aspose.Tasks mendukung berbagai format file, termasuk MPP, XML, dan HTML.
### Q3: Apakah Aspose.Tasks cocok untuk manajemen proyek tingkat perusahaan?
J: Tentu saja, Aspose.Tasks menawarkan fitur komprehensif untuk mengelola proyek dalam skala apa pun, sehingga cocok untuk manajemen proyek tingkat perusahaan.
### Q4: Dapatkah saya menyesuaikan penetapan sumber daya lebih jauh dari skala tarif?
J: Ya, Aspose.Tasks memberikan kemampuan ekstensif untuk menyesuaikan penetapan sumber daya, termasuk penyesuaian biaya, pekerjaan, dan durasi.
### Q5: Apakah ada forum komunitas untuk dukungan Aspose.Tasks?
 J: Ya, Anda dapat menemukan dukungan dan berinteraksi dengan pengguna lain di forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).