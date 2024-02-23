---
title: Definisi Penanganan Kode Garis Besar Proyek MS di Aspose.Tasks
linktitle: Menangani Definisi Kode Garis Besar di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menangani definisi kode kerangka Proyek MS menggunakan Aspose.Tasks untuk .NET, sehingga memberdayakan aplikasi manajemen proyek Anda.
type: docs
weight: 12
url: /id/net/outline-code-page-settings/outline-code-definitions/
---
## Perkenalan
Microsoft Project adalah alat yang ampuh untuk mengelola proyek, dan Aspose.Tasks untuk .NET menyediakan dukungan komprehensif untuk memanipulasi file proyek secara terprogram. Salah satu aspek penting dari manajemen proyek adalah pengorganisasian tugas menggunakan kode garis besar. Dalam tutorial ini, kita akan mempelajari cara menangani definisi kode kerangka Proyek MS menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mendalami penerapannya, pastikan Anda memiliki prasyarat berikut:
### 1. Instalasi Aspose.Tasks untuk .NET
 Pastikan Anda telah menginstal Aspose.Tasks untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
### 2. Pemahaman Dasar C# dan .NET Framework
Biasakan diri Anda dengan bahasa pemrograman C# dan kerangka .NET karena tutorial ini memerlukan pengetahuan C# tingkat menengah.
### 3. Lingkungan Pengembangan Terpadu (IDE)
Miliki IDE seperti Visual Studio yang terinstal di sistem Anda untuk coding dan debugging.
## Impor Namespace
Sebelum kita mulai membuat kode, mari impor namespace yang diperlukan agar berfungsi dengan Aspose.Tasks untuk .NET.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk pemahaman yang jelas.
## Langkah 1: Muat File Proyek
Pertama, kita perlu memuat file MS Project ke dalam aplikasi kita.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Langkah 2: Buat Definisi Kode Garis Besar
Sekarang, mari buat definisi kode kerangka baru.
```csharp
var outline = new OutlineCodeDefinition();
```
## Langkah 3: Tetapkan Nomor dan Nama Bidang
Tetapkan nomor bidang dan nama untuk kode kerangka.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## Langkah 4: Atur GUID dan Properti Lainnya
Atur GUID dan properti lain dari kode kerangka.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## Langkah 5: Tambahkan Masker Garis Besar
Tambahkan masker kerangka ke kode kerangka.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## Langkah 6: Atur Properti Lainnya
Tetapkan properti tambahan dari kode kerangka.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## Langkah 7: Tambahkan Nilai Garis Besar
Terakhir, mari tambahkan nilai outline ke kode outline.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menangani definisi kode kerangka Proyek MS menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat secara efisien memanipulasi kode kerangka dalam file proyek Anda secara terprogram.
## FAQ
### Q1: Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan versi file MS Project yang berbeda?
J: Ya, Aspose.Tasks untuk .NET mendukung berbagai versi file MS Project, termasuk format MPP dan XML.
### Q2: Apakah Aspose.Tasks untuk .NET kompatibel dengan .NET Core?
J: Ya, Aspose.Tasks untuk .NET kompatibel dengan .NET Core, memungkinkan Anda mengembangkan aplikasi lintas platform.
### Q3: Bisakah saya memanipulasi penetapan sumber daya menggunakan Aspose.Tasks untuk .NET?
J: Ya, Aspose.Tasks untuk .NET menyediakan fitur ekstensif untuk memanipulasi penetapan sumber daya, termasuk menambah, memperbarui, dan menghapus penetapan.
### Q4: Apakah Aspose.Tasks untuk .NET mendukung pembacaan bidang khusus dari file MS Project?
J: Tentu saja, Aspose.Tasks untuk .NET mendukung pembacaan dan penulisan bidang khusus, termasuk kode kerangka, dari file MS Project.
### Q5: Apakah ada forum komunitas untuk Aspose.Tasks untuk .NET?
 A: Ya, Anda dapat bergabung dengan forum komunitas Aspose.Tasks untuk .NET[Di Sini](https://forum.aspose.com/c/tasks/15) untuk bertanya, berbagi pengetahuan, dan berkolaborasi dengan pengembang lain.