---
title: Konversi Proyek MS ke SVG di Java
linktitle: Simpan Sebagai SVG di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menyimpan file Microsoft Project sebagai SVG di Java menggunakan perpustakaan Aspose.Tasks. Panduan langkah demi langkah dengan contoh kode.
weight: 18
url: /id/java/project-file-operations/save-as-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konversi Proyek MS ke SVG di Java

## Perkenalan
Aspose.Tasks untuk Java adalah perpustakaan yang kuat untuk bekerja dengan file manajemen proyek, memungkinkan pengembang memanipulasi data proyek, melakukan berbagai operasi, dan menghasilkan laporan secara efisien. Dalam tutorial ini, kita akan mempelajari cara menyimpan proyek sebagai SVG menggunakan Aspose.Tasks untuk Java. SVG (Scalable Vector Graphics) adalah format yang banyak digunakan untuk menampilkan grafik vektor di web, memberikan skalabilitas dan rendering berkualitas tinggi.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
### Lingkungan Pengembangan Jawa
Pastikan Anda telah menginstal Java Development Kit (JDK) di sistem Anda. Anda dapat mengunduh dan menginstal JDK dari situs web Oracle.
### Aspose.Tugas untuk Perpustakaan Java
 Unduh dan instal perpustakaan Aspose.Tasks untuk Java dari situs web. Anda dapat menemukan tautan unduhan di dokumentasi yang disediakan[Di Sini](https://releases.aspose.com/tasks/java/).

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan dalam program Java Anda agar dapat bekerja dengan fungsi Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Sekarang mari kita bagi contoh yang diberikan menjadi beberapa langkah:
## Langkah 2: Tentukan Direktori Data
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"`dengan jalur ke direktori tempat file proyek Anda berada.
## Langkah 3: Muat File Proyek
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Langkah ini memuat file proyek bernama "HomeMovePlan.mpp" dari direktori data yang ditentukan.
## Langkah 4: Simpan sebagai SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Langkah ini menyimpan proyek yang dimuat sebagai format SVG dengan nama "project5.svg" di direktori data yang ditentukan.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menyimpan proyek sebagai SVG menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat mengonversi file proyek ke format SVG secara efisien, memungkinkan integrasi tanpa batas dengan aplikasi berbasis web atau alat visualisasi.
## FAQ
### Apakah Aspose.Tasks untuk Java kompatibel dengan semua versi file Microsoft Project?
Ya, Aspose.Tasks untuk Java mendukung berbagai versi file Microsoft Project, termasuk format MPP, MPT, dan XML.
### Bisakah saya menyesuaikan tampilan keluaran SVG?
Ya, Anda dapat menyesuaikan tampilan keluaran SVG dengan menyesuaikan parameter seperti font, warna, dan konfigurasi tata letak.
### Apakah Aspose.Tasks untuk Java memerlukan lisensi untuk penggunaan komersial?
 Ya, lisensi yang valid diperlukan untuk penggunaan komersial Aspose.Tasks untuk Java. Anda dapat memperoleh lisensi dari situs web[Di Sini](https://purchase.aspose.com/temporary-license/).
### Bisakah saya mencoba Aspose.Tasks untuk Java sebelum membeli?
 Ya, Anda dapat meminta uji coba gratis Aspose.Tasks untuk Java dari situs web[Di Sini](https://purchase.aspose.com/buy) untuk mengevaluasi fitur dan kemampuannya.
### Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk Java?
 Anda bisa mendapatkan dukungan untuk Aspose.Tasks untuk Java dengan mengunjungi forum[Di Sini](https://forum.aspose.com/c/tasks/15), tempat Anda dapat bertanya dan berinteraksi dengan komunitas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
