---
title: Menyimpan File Proyek MS dalam berbagai Format di Aspose.Tasks
linktitle: Menyimpan File dalam Berbagai Format di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menyimpan file MS Project dalam berbagai format menggunakan Aspose.Tasks untuk .NET. Langkah mudah untuk manajemen proyek yang efisien.
type: docs
weight: 17
url: /id/net/rate-recurring-tasks/save-file-formats/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menyimpan file Microsoft Project dalam berbagai format menggunakan Aspose.Tasks untuk .NET. Aspose.Tasks adalah API canggih yang memungkinkan pengembang memanipulasi dan mengelola file proyek secara terprogram.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET, seperti Visual Studio.
3. Pemahaman Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.

## Impor Namespace
Pastikan untuk mengimpor namespace yang diperlukan di awal file C# Anda:
```csharp

using Aspose.Tasks.Saving;
```
## Langkah 1: Buat Objek Proyek
Pertama, buat objek Proyek dan muat file Microsoft Project Anda.
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Langkah 2: Simpan Proyek dalam Format CSV
Sekarang, mari simpan proyek dalam format CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Langkah 3: Jelajahi Format Lain
 Aspose.Tasks mendukung berbagai format untuk menyimpan file proyek, seperti XML, PDF, XLSX, dan lainnya. Anda dapat menjelajahi format ini hanya dengan mengubah`SaveFileFormat` parameter di`Save` metode.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menyimpan file Microsoft Project dalam berbagai format menggunakan Aspose.Tasks untuk .NET.

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menyimpan file MS Project dalam format berbeda menggunakan Aspose.Tasks untuk .NET. Aspose.Tasks menyederhanakan proses manipulasi file proyek secara terprogram, menawarkan fleksibilitas dan efisiensi kepada pengembang.
## FAQ
### T: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?
J: Aspose.Tasks mendukung format Microsoft Project 2003 XML, Microsoft Project 2007 MPP, dan Microsoft Project 2010 MPP.
### T: Dapatkah saya mencoba Aspose.Tasks sebelum membeli?
 J: Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
J: Anda bisa mendapatkan dukungan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### T: Apakah lisensi sementara tersedia untuk Aspose.Tasks?
 J: Ya, lisensi sementara tersedia untuk tujuan evaluasi. Anda bisa mendapatkannya[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Berapa harga Aspose.Tasks?
 A: Informasi harga dapat ditemukan di halaman pembelian Aspose.Tasks[Di Sini](https://purchase.aspose.com/buy).