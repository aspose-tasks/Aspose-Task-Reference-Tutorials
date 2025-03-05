---
title: Simpan Sebagai PDF di Aspose.Tasks
linktitle: Simpan Sebagai PDF di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengonversi file proyek ke PDF menggunakan Aspose.Tasks untuk Java. Langkah sederhana untuk konversi yang efisien.
type: docs
weight: 17
url: /id/java/project-file-operations/save-as-pdf/
---
## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses menyimpan proyek sebagai PDF menggunakan Aspose.Tasks untuk Java. Dengan Aspose.Tasks, Anda dapat secara efisien mengonversi file proyek Anda ke format PDF, memastikan kompatibilitas dan kemudahan berbagi. Mari selami langkah-langkahnya:
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Tasks untuk Java Library: Unduh dan instal perpustakaan Aspose.Tasks. Anda dapat menemukan tautan unduhan[Di Sini](https://releases.aspose.com/tasks/java/).
3. File Proyek: Siapkan file proyek (misalnya, HomeMovePlan.mpp) yang ingin Anda konversi ke PDF.

## Paket Impor
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Langkah 1: Baca File Proyek Masukan
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Pastikan Anda menggantinya`"Your Data Directory"` dengan jalur ke direktori data Anda yang berisi file proyek.
## Langkah 2: Simpan Proyek sebagai PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Cuplikan kode ini menyimpan proyek sebagai file PDF dengan nama "Project5.pdf".
## Langkah 3: Menyesuaikan Konten dengan Ukuran Sel
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Di sini, kami menetapkan opsi untuk menyimpan PDF, termasuk penyesuaian konten, skala waktu, dan format presentasi.
## Langkah 4: Sembunyikan Legenda
```java
o.setLegendOnEachPage(false);
```
Langkah ini menyembunyikan legenda di setiap halaman PDF.
## Langkah 5: Simpan Proyek dengan Opsi Terapan
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Terakhir, kode ini menyimpan proyek dengan opsi yang diterapkan ke file PDF.

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menggunakan Aspose.Tasks untuk Java untuk menyimpan proyek sebagai PDF. Dengan mengikuti langkah-langkah sederhana ini, Anda dapat mengonversi file proyek secara efisien agar mudah dibagikan dan didistribusikan.
## FAQ
### T: Apakah Aspose.Tasks kompatibel dengan semua versi Java?
A: Ya, Aspose.Tasks mendukung versi Java mulai dari JDK 6 ke atas.
### T: Dapatkah saya menyesuaikan tampilan keluaran PDF?
J: Tentu saja! Aspose.Tasks menyediakan berbagai opsi untuk menyesuaikan keluaran PDF sesuai dengan kebutuhan Anda.
### T: Apakah Aspose.Tasks mendukung format file lain untuk konversi?
J: Ya, Aspose.Tasks mendukung berbagai format file, termasuk MPP, XML, XLSX, dan banyak lagi.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?
 J: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
 A: Untuk dukungan dan bantuan, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).