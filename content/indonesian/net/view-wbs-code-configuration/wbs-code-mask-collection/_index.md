---
title: Menguasai Masker Kode WBS dengan Aspose.Tasks untuk .NET
linktitle: Kumpulan Masker Kode WBS di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Tingkatkan manajemen proyek dengan Aspose.Tasks untuk .NET. Pelajari cara membuat, mengelola, dan mentransfer Masker Kode WBS dengan mudah dalam tutorial komprehensif ini.
type: docs
weight: 15
url: /id/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Perkenalan
Dalam dunia manajemen proyek yang dinamis, pengorganisasian tugas secara efisien sangatlah penting. Aspose.Tasks untuk .NET memberikan solusi ampuh untuk mengelola kode struktur rincian kerja proyek (WBS) dengan mudah. Dalam tutorial ini, kita akan mempelajari Kumpulan Masker Kode WBS, menjelajahi cara mengimplementasikan dan memanipulasinya menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita memulai perjalanan coding ini, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan tentang bahasa pemrograman C#.
-  Aspose.Tasks untuk .NET diinstal di lingkungan pengembangan Anda. Jika tidak, unduh[Di Sini](https://releases.aspose.com/tasks/net/).
- Editor kode seperti Visual Studio untuk pengalaman pengkodean yang lancar.
## Impor Namespace
Untuk memulai, mari impor namespace yang diperlukan:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Inisialisasi Definisi Proyek dan Kode WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Tentukan Masker Kode WBS
Hapus semua masker kode yang ada dan tambahkan yang baru:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Menampilkan Informasi Kode Masker
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Tambahkan Tugas ke Proyek
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Ambil Informasi Tugas
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Memanipulasi Masker Kode
Hapus masker kode dan pastikan sudah dihapus:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Salin Kode Masker ke Proyek Lain
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Tampilkan Masker Kode di Proyek Lain
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Tambahkan Tugas ke Proyek Lain
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Tampilkan Kode WBS di Proyek Lain
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Kesimpulan
Dengan Aspose.Tasks untuk .NET, mengelola kode WBS menjadi tugas yang mudah. Tutorial ini mencakup pembuatan, manipulasi, dan transfer Masker Kode WBS, memberi Anda panduan komprehensif untuk meningkatkan pengalaman manajemen proyek Anda.
## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks untuk .NET dengan bahasa pemrograman lain?
J: Aspose.Tasks terutama mendukung bahasa .NET, namun Anda dapat menjelajahi opsi interoperabilitas dengan bahasa lain.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?
 A: Ya, Anda dapat mendownload versi trialnya[Di Sini](https://releases.aspose.com/).
### T: Bagaimana cara mencari bantuan atau melaporkan masalah dengan Aspose.Tasks untuk .NET?
 J: Kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi.
### T: Apa tujuan kode WBS dalam manajemen proyek?
J: Kode WBS membantu mengatur dan menyusun tugas proyek secara hierarki, memberikan pendekatan sistematis terhadap perencanaan proyek.
### T: Dapatkah saya menyesuaikan format kode WBS di Aspose.Tasks untuk .NET?
J: Tentu saja, Anda memiliki kendali penuh atas format dan struktur kode WBS menggunakan Aspose.Tasks untuk .NET.