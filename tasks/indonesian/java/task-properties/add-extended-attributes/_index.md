---
title: Tambahkan Atribut yang Diperluas ke Tugas di Aspose.Tasks
linktitle: Tambahkan Atribut yang Diperluas ke Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi kekuatan Aspose.Tasks Java dalam menyesuaikan file Microsoft Project dengan atribut yang diperluas. Tingkatkan kemampuan manajemen proyek Anda dengan mudah.
weight: 11
url: /id/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Atribut yang Diperluas ke Tugas di Aspose.Tasks

## Perkenalan
Meningkatkan kemampuan manajemen proyek Anda sangat penting untuk pelacakan tugas dan manajemen sumber daya yang efisien. Aspose.Tasks untuk Java memberikan solusi ampuh bagi pengembang Java untuk memanipulasi file Microsoft Project dengan lancar. Dalam tutorial ini, kita akan mempelajari cara menambahkan atribut yang diperluas ke tugas menggunakan Aspose.Tasks untuk Java, memungkinkan Anda menyesuaikan dan mengatur data proyek sesuai dengan kebutuhan spesifik Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
-  Aspose.Tasks untuk perpustakaan Java diinstal. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/tasks/java/).
- Lingkungan Pengembangan Terpadu Java (IDE) diinstal pada sistem Anda.
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk mengakses fungsi Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah:
## 1. Menambahkan Atribut Teks Biasa
1. Setel jalur direktori dokumen:
```java
String dataDir = "Your Document Directory";
```
2. Buat proyek baru:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Buat Definisi Atribut yang Diperluas dari tipe Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Tambahkan definisi ke koleksi Atribut yang Diperluas proyek:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Tambahkan tugas ke proyek:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Buat Atribut yang Diperluas dari Definisi Atribut:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Tetapkan nilai pada Atribut Diperluas yang dihasilkan:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Tambahkan Atribut yang Diperluas ke tugas:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Simpan proyek:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Menambahkan Atribut Teks dengan Opsi Pencarian
Ikuti langkah yang sama seperti di atas, ganti Text1 dengan Text2 dan sesuaikan nilai pencarian.
## 3. Menambahkan Atribut Durasi dengan Opsi Pencarian
Ikuti langkah yang sama seperti di atas, ganti Text1 dengan Duration2 dan sesuaikan nilai pencarian.
## Kesimpulan
Dengan mengikuti panduan langkah demi langkah ini, Anda telah mempelajari cara memanfaatkan Aspose.Tasks untuk Java guna menambahkan atribut tambahan ke tugas di file Microsoft Project Anda. Penyesuaian ini memungkinkan Anda menyesuaikan pendekatan manajemen proyek, sehingga meningkatkan fleksibilitas dan efisiensi.
## Pertanyaan yang Sering Diajukan
### T: Dapatkah saya menggunakan Aspose.Tasks untuk Java dengan pustaka Java lainnya?
J: Ya, Aspose.Tasks untuk Java dapat diintegrasikan dengan lancar ke dalam proyek Java Anda, dan berfungsi baik dengan pustaka Java lainnya.
### T: Apakah Aspose.Tasks untuk Java cocok untuk aplikasi manajemen proyek skala besar?
J: Tentu saja, Aspose.Tasks untuk Java dirancang untuk menangani proyek dengan berbagai ukuran, termasuk aplikasi berskala besar.
### T: Apakah ada pertimbangan lisensi untuk menggunakan Aspose.Tasks untuk Java dalam proyek komersial?
 J: Ya, pastikan untuk meninjau informasi perizinan yang disediakan di[Situs web Aspose.Tasks](https://purchase.aspose.com/buy).
### T: Bagaimana saya bisa mendapatkan dukungan atau bantuan dengan Aspose.Tasks untuk Java?
 J: Kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi komunitas.
### T: Dapatkah saya mencoba Aspose.Tasks untuk Java sebelum membeli?
 A: Ya, Anda dapat mengakses versi uji coba gratis[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
