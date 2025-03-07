---
title: Mengelola Koleksi Proyek di Aspose.Tasks
linktitle: Mengelola Koleksi Grup di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola koleksi MS Project secara efisien menggunakan Aspose.Tasks untuk .NET. Ikuti panduan langkah demi langkah kami.
weight: 26
url: /id/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengelola Koleksi Proyek di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan menjelajahi cara mengelola koleksi grup MS Project menggunakan Aspose.Tasks untuk .NET. Mengelola koleksi grup sangat penting untuk mengatur dan memanipulasi tugas dan sumber daya secara efisien dalam proyek Anda.
## Prasyarat
Sebelum melanjutkan tutorial ini, pastikan Anda memiliki prasyarat berikut:
1.  Aspose.Tasks untuk .NET Library: Unduh dan instal perpustakaan Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
2. Pengetahuan Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C# karena tutorial ini melibatkan pengkodean dalam C#.
3. Lingkungan Pengembangan: Siapkan lingkungan pengembangan seperti Visual Studio atau IDE lain yang mendukung pengembangan .NET.

## Impor Namespace
Pertama, mari impor namespace yang diperlukan agar berfungsi dengan fungsi Aspose.Tasks dalam kode C# kita.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Langkah 1: Muat Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Langkah ini melibatkan memuat file MS Project ke objek proyek Aspose.Tasks, memungkinkan kita untuk melakukan operasi padanya.
## Langkah 2: Ulangi Kelompok Tugas
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Di sini, kami mengulangi grup tugas dalam proyek, mencetak detail seperti indeks, nama, dan visibilitas di menu untuk setiap grup.
## Langkah 3: Ulangi Grup Sumber Daya
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Demikian pula, langkah ini mengulangi grup sumber daya, menampilkan indeks, nama, dan visibilitasnya di menu.
## Langkah 4: Hapus dan Salin Grup ke Proyek Lain
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Hapus grup proyek lain
otherProject.TaskGroups.Clear();
// Salin grup ke proyek lain
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Di sini, kami menghapus grup dari proyek lain dan kemudian menyalin grup dari proyek asli ke proyek tersebut.
## Langkah 5: Tambahkan Grup Tugas Kustom
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
Pada langkah ini, kita membuat grup tugas kustom dan menambahkannya ke proyek lain jika belum ada.
## Langkah 6: Hapus Semua Grup
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Terakhir, kami menghapus semua grup dari proyek lainnya.

## Kesimpulan
Mengelola koleksi proyek MS grup di Aspose.Tasks untuk .NET sangat penting untuk mengatur dan memanipulasi data proyek secara efisien. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat secara efektif menangani tugas dan kelompok sumber daya dalam proyek Anda, sehingga meningkatkan manajemen proyek secara keseluruhan.
## FAQ
### Apakah Aspose.Tasks for .NET kompatibel dengan semua versi MS Project?
Aspose.Tasks untuk .NET mendukung berbagai versi Microsoft Project, termasuk 2003, 2007, 2010, 2013, 2016, dan 2019.
### Bisakah saya mengkustomisasi properti grup menggunakan Aspose.Tasks untuk .NET?
Ya, Anda dapat menyesuaikan properti grup seperti nama dan visibilitas menggunakan Aspose.Tasks untuk .NET.
### Apakah Aspose.Tasks untuk .NET menawarkan kompatibilitas lintas platform?
Aspose.Tasks untuk .NET terutama menargetkan kerangka .NET, tetapi dapat digunakan dalam skenario lintas platform dengan .NET Core dan .NET Standard.
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET?
 Anda bisa mendapatkan dukungan untuk Aspose.Tasks untuk .NET melalui[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
### Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?
 Ya, Anda dapat mengunduh Aspose.Tasks versi uji coba gratis untuk .NET dari[situs web](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
