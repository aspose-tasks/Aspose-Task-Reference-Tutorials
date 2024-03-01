---
title: Simpan Data Proyek MS ke Excel di Aspose.Tasks
linktitle: Simpan Data ke Excel di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menyimpan data Microsoft Project ke file Excel menggunakan Aspose.Tasks untuk Java. Integrasi yang mudah untuk pengembang Java.
type: docs
weight: 19
url: /id/java/project-file-operations/save-data-to-excel/
---
## Perkenalan
Aspose.Tasks untuk Java adalah perpustakaan canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram. Dalam tutorial ini, kami akan memandu Anda melalui proses menyimpan data dari file Proyek ke file Excel langkah demi langkah.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda. Anda dapat mengunduh dan menginstal JDK versi terbaru dari situs web Oracle.
2.  Aspose.Tasks untuk Perpustakaan Java: Unduh perpustakaan Aspose.Tasks untuk Java dari[tautan unduhan](https://releases.aspose.com/tasks/java/) dan sertakan dalam proyek Java Anda.

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan dalam kode Java Anda untuk bekerja dengan Aspose.Tasks.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Mari kita bagi contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Tentukan Jalur Direktori Data
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"`dengan jalur ke direktori data Anda tempat file Proyek berada.
## Langkah 2: Muat File Proyek
```java
Project project = new Project(dataDir + "project5.mpp");
```
Baris kode ini memuat file Proyek bernama "project5.mpp" dari direktori data yang ditentukan.
## Langkah 3: Simpan Proyek sebagai XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Di sini, itu`save` metode ini digunakan untuk menyimpan file Proyek yang dimuat sebagai file Excel dengan nama "project1.xlsx" di direktori data yang sama. Kami menentukan`SaveFileFormat.Xlsx` parameter untuk menyimpannya dalam format XLSX.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menyimpan data dari file Microsoft Project ke file Excel menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat mengintegrasikan fungsi ini dengan lancar ke dalam aplikasi Java Anda.
## FAQ
### Bisakah saya menggunakan Aspose.Tasks untuk Java untuk memanipulasi data proyek secara terprogram?
Ya, Aspose.Tasks untuk Java menyediakan fitur ekstensif untuk memanipulasi data proyek, termasuk membaca, menulis, dan memodifikasi file proyek.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis untuk Java dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks untuk Java?
Anda dapat menemukan dokumentasi Aspose.Tasks untuk Java[Di Sini](https://reference.aspose.com/tasks/java/).
### Bagaimana saya bisa mendapatkan dukungan untuk masalah atau pertanyaan apa pun yang terkait dengan Aspose.Tasks untuk Java?
 Anda bisa mendapatkan dukungan dengan mengunjungi forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### Bisakah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?
 Ya, Anda dapat membeli lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).