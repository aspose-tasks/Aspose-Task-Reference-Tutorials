---
title: Kelola Koleksi Atribut Proyek MS di Aspose.Tasks
linktitle: Mengelola Koleksi Atribut yang Diperluas di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola atribut tambahan MS Project secara efisien menggunakan Aspose.Tasks untuk .NET. Memanipulasi atribut tugas secara lancar dengan panduan langkah demi langkah.
type: docs
weight: 12
url: /id/net/tasks-project-management/extended-attribute-collection/
---
## Perkenalan
Apakah Anda ingin mengelola atribut tambahan MS Project secara efisien menggunakan Aspose.Tasks untuk .NET? Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah. Ayo selami!
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Visual Studio: Instal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[Di Sini](https://releases.aspose.com/tasks/net/).
3. Pengetahuan Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.

## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke dalam proyek Anda:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Langkah 1: Muat File Proyek
Pertama, muat file MS Project menggunakan cuplikan kode berikut:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Langkah 2: Akses Tugas dan Atribut yang Diperluas
Akses tugas tertentu dan atribut tambahannya:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Langkah 3: Hapus Atribut yang Diperluas
Hapus atribut tambahan yang ada jika diperlukan:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Langkah 4: Buat Definisi Atribut yang Diperluas
Buat definisi untuk atribut baru yang diperluas:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Langkah 5: Ulangi Atribut Tugas yang Diperluas
Ulangi atribut tugas yang diperluas:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Langkah 6: Tambahkan Atribut yang Diperluas
Tambahkan atribut baru yang diperluas ke tugas:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Langkah 7: Bekerja dengan Atribut yang Diperluas
Lakukan operasi pada atribut yang diperluas sesuai kebutuhan.
## Langkah 8: Hapus Atribut yang Diperluas
Hapus atribut yang diperluas berdasarkan indeks atau kondisional:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Langkah 9: Salin Atribut ke Tugas Lain
Salin atribut ke tugas lain dalam proyek yang sama atau berbeda:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Kesimpulan
Mengelola koleksi atribut MS Project yang diperluas menjadi lancar dengan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat menangani atribut yang diperluas secara efisien, sehingga meningkatkan kemampuan manajemen proyek Anda.
## FAQ
### T: Dapatkah saya memanipulasi atribut yang diperluas di beberapa proyek?
J: Ya, Anda dapat menyalin atribut yang diperluas antar tugas di proyek berbeda menggunakan Aspose.Tasks untuk .NET.
### T: Apakah ada batasan jumlah atribut yang diperluas per tugas?
J: Aspose.Tasks untuk .NET tidak menerapkan batasan bawaan pada jumlah atribut yang diperluas per tugas.
### T: Dapatkah saya membuat kolom atribut khusus yang diperluas?
J: Tentu saja! Aspose.Tasks untuk .NET memungkinkan Anda menentukan bidang atribut tambahan khusus yang disesuaikan dengan kebutuhan proyek Anda.
### T: Apakah Aspose.Tasks untuk .NET mendukung membaca dan menulis ke file MS Project dari berbagai versi?
J: Ya, Aspose.Tasks untuk .NET mendukung format file MS Project di berbagai versi.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk .NET?
 J: Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).