---
title: Mendukung Fungsi Evaluasi dalam Rumus Aspose.Tugas
linktitle: Mendukung Fungsi Evaluasi dalam Rumus Aspose.Tugas
second_title: Aspose.Tugas Java API
description: Pelajari cara mendukung evaluasi fungsi MS Project dalam rumus Aspose.Tasks menggunakan Java. Tingkatkan produktivitas Anda dengan Aspose.Tasks.
weight: 10
url: /id/java/formulas/evaluation-functions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mendukung Fungsi Evaluasi dalam Rumus Aspose.Tugas


## Perkenalan
Aspose.Tasks untuk Java adalah perpustakaan canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram. Salah satu fitur utamanya adalah kemampuan untuk mendukung evaluasi fungsi MS Project dalam rumus Aspose.Tasks. Kemampuan ini memungkinkan pengguna untuk melakukan penghitungan dan analisis kompleks secara langsung dalam aplikasi Java mereka.
## Prasyarat
Sebelum mulai mengintegrasikan fungsi MS Project ke dalam rumus Aspose.Tasks, pastikan Anda memiliki hal berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java di sistem Anda bersama dengan IDE yang kompatibel untuk pengembangan Java seperti IntelliJ IDEA atau Eclipse.
2.  Aspose.Tasks for Java Library: Unduh dan sertakan perpustakaan Aspose.Tasks for Java dalam proyek Java Anda. Anda dapat mengunduhnya dari[Aspose.Tasks untuk halaman unduh Java](https://releases.aspose.com/tasks/java/).
## Paket Impor
Untuk memulai, impor paket yang diperlukan di kelas Java Anda untuk memanfaatkan fungsi Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## Langkah 1: Buat Objek Proyek Baru
 Pertama, buat yang baru`Project`objek untuk dikerjakan:
```java
Project project = new Project();
```
Ini menginisialisasi proyek kosong baru.
## Langkah 2: Tentukan Atribut yang Diperluas untuk Tugas
Selanjutnya, tentukan atribut yang diperluas untuk tugas. Atribut ini akan menyimpan data khusus yang terkait dengan tugas:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 Di sini, kami membuat atribut tipe yang diperluas`Number` dengan nama "Sine" untuk tugas.
## Langkah 3: Tambahkan Atribut yang Diperluas ke Proyek
Tambahkan definisi atribut yang diperluas ke daftar atribut yang diperluas proyek:
```java
project.getExtendedAttributes().add(attr);
```
Ini menambahkan atribut khusus ke proyek.
## Langkah 4: Buat Tugas Baru
Sekarang, mari buat tugas baru di dalam proyek:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Ini menambahkan tugas baru bernama "Tugas" ke proyek.
## Langkah 5: Kaitkan Atribut yang Diperluas dengan Tugas
Kaitkan atribut diperluas yang dibuat sebelumnya dengan tugas:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
Ini mengaitkan atribut yang diperluas "Sine" dengan tugas.

## Kesimpulan
Kesimpulannya, mengintegrasikan fungsi MS Project ke dalam rumus Aspose.Tasks di Java adalah proses yang mudah. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat secara efektif memanfaatkan kemampuan kuat Aspose.Tasks untuk Java untuk memanipulasi dan menganalisis file Microsoft Project secara terprogram.
## FAQ
### T: Dapatkah Aspose.Tasks untuk Java menangani rumus MS Project yang kompleks?
J: Ya, Aspose.Tasks untuk Java mendukung evaluasi berbagai fungsi MS Project, memungkinkan penghitungan kompleks dalam aplikasi Java.
### T: Apakah Aspose.Tasks untuk Java kompatibel dengan versi file Microsoft Project yang berbeda?
J: Ya, Aspose.Tasks untuk Java mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.
### T: Dapatkah saya mencoba Aspose.Tasks untuk Java sebelum membeli?
 J: Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis untuk Java dari situs web[Di Sini](https://purchase.aspose.com/buy).
### T: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks untuk Java?
J: Anda bisa mendapatkan dukungan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### T: Apakah ada lisensi sementara yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda bisa mendapatkan lisensi sementara untuk tujuan pengujian dari situs web Aspose[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
