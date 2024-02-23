---
title: Simpan File Proyek MS sebagai Templat dengan Aspose.Tasks
linktitle: Simpan Opsi Templat untuk Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara menyimpan file Microsoft Project sebagai templat menggunakan Aspose.Tasks untuk .NET. Sesuaikan pengaturan templat untuk manajemen proyek yang efisien.
type: docs
weight: 18
url: /id/net/saving-options/save-template-options/
---
## Perkenalan
Dalam tutorial ini, kita akan memandu proses menyimpan templat menggunakan Aspose.Tasks untuk .NET. Templat berguna untuk menstandardisasi struktur dan pengaturan proyek untuk penggunaan di masa mendatang. Kami akan mendemonstrasikan cara menyimpan proyek sebagai templat, sambil menyesuaikan propertinya.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Tasks untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Pengetahuan tentang Pemrograman C#: Pengetahuan dasar pemrograman C# diperlukan untuk memahami dan mengimplementasikan cuplikan kode yang disediakan.
3. File Microsoft Project: Siapkan file Microsoft Project (format MPP) yang ingin Anda simpan sebagai templat.

## Impor Namespace
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Langkah 1: Muat Proyek
Pertama, kita perlu memuat file Microsoft Project (.mpp) yang ingin kita simpan sebagai template.
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Langkah 2: Dapatkan Info File Proyek
Ambil informasi tentang file proyek yang dimuat, seperti formatnya.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Langkah 3: Konfigurasikan Opsi Simpan Template
Buat opsi penyimpanan template dan konfigurasikan propertinya sesuai dengan kebutuhan Anda. Opsi ini memungkinkan Anda menyesuaikan data apa yang harus dihapus dari templat.
```csharp
var options = new SaveTemplateOptions
{
	// Hapus semua biaya tetap dari template proyek
	RemoveFixedCosts = true,
	// Hapus semua nilai sebenarnya dari templat proyek
	RemoveActualValues = true,
	// Hapus tarif sumber daya dari templat proyek
	RemoveResourceRates = true,
	// Hapus semua nilai dasar dari templat proyek
	RemoveBaselineValues = true
};
```
## Langkah 4: Simpan Proyek sebagai Templat
Simpan proyek sebagai templat dengan opsi yang ditentukan.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Langkah 5: Dapatkan Info File Templat
Ambil informasi tentang file templat yang disimpan, seperti formatnya.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Selamat! Anda telah berhasil menyimpan templat menggunakan Aspose.Tasks untuk .NET, menyesuaikan propertinya sesuai kebutuhan.

## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara menyimpan file Microsoft Project sebagai templat menggunakan Aspose.Tasks untuk .NET. Templat sangat berharga untuk menstandardisasi struktur dan pengaturan proyek, menyederhanakan pembuatan proyek di masa depan.
## FAQ
### T: Bisakah saya menyesuaikan data mana yang akan dihapus dari template?
J: Ya, Anda dapat mengonfigurasi Opsi Simpan Templat untuk menghapus data tertentu seperti biaya tetap, nilai aktual, tarif sumber daya, dan nilai dasar.
### T: Apakah Aspose.Tasks untuk .NET kompatibel dengan semua versi Microsoft Project?
J: Aspose.Tasks untuk .NET menyediakan kompatibilitas luas dengan berbagai versi Microsoft Project, memastikan integrasi dan fungsionalitas yang lancar.
### T: Bisakah saya menerapkan template ke proyek yang sudah ada?
A: Ya, Anda dapat menerapkan template ke proyek yang sudah ada dengan memuat file template dan menggabungkannya dengan proyek Anda saat ini sesuai kebutuhan.
### T: Apakah Aspose.Tasks untuk .NET mendukung pengembangan lintas platform?
J: Aspose.Tasks untuk .NET terutama dirancang untuk aplikasi kerangka .NET yang berjalan pada platform Windows.
### T: Apakah dukungan teknis tersedia untuk Aspose.Tasks untuk .NET?
 J: Ya, Anda dapat mencari bantuan teknis dan bimbingan dari komunitas Aspose.Tasks.[forum](https://forum.aspose.com/c/tasks/15) atau hubungi tim dukungan mereka secara langsung.