---
title: Mengelola Koleksi Properti Proyek Kustom di Aspose.Tasks
linktitle: Mengelola Koleksi Properti Proyek Kustom di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola properti proyek kustom secara efektif di Aspose.Tasks untuk .NET, sehingga meningkatkan pengalaman manajemen proyek Anda.
weight: 24
url: /id/net/calendar-scheduling/custom-project-property-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mengelola Koleksi Properti Proyek Kustom di Aspose.Tasks

## Perkenalan

Apakah Anda siap untuk meningkatkan pengalaman manajemen proyek Anda dengan Aspose.Tasks untuk .NET? Mengelola properti proyek khusus adalah aspek penting dalam manajemen proyek, memungkinkan Anda menambahkan metadata spesifik yang disesuaikan dengan kebutuhan proyek Anda. Dalam tutorial ini, kita akan mendalami bagaimana Anda dapat bekerja secara efektif dengan kumpulan properti proyek kustom menggunakan Aspose.Tasks untuk .NET.

## Prasyarat

Sebelum melanjutkan, pastikan Anda telah menyiapkan prasyarat berikut:

1. Lingkungan Visual Studio: Instal Visual Studio di sistem Anda.
2.  Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
3. Pengetahuan Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.

## Impor Namespace

Mulailah dengan mengimpor namespace yang diperlukan agar berfungsi dengan Aspose.Tasks untuk .NET:

```csharp
using Aspose.Tasks;
using System;


```

Mari kita pecahkan kode contoh menjadi beberapa langkah untuk pemahaman yang komprehensif:

## Langkah 1: Inisialisasi Proyek

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

Langkah ini menginisialisasi proyek baru menggunakan Aspose.Tasks.

## Langkah 2: Periksa Kesiapan Koleksi Properti Kustom

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

Kode ini memeriksa apakah kumpulan properti khusus bersifat hanya-baca.

## Langkah 3: Tambahkan Properti Kustom

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

Di sini, kami menambahkan properti khusus ke proyek, mendukung tipe Boolean, DateTime, Double, dan String.

## Langkah 4: Akses Properti Kustom

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

Perulangan ini memungkinkan kita melakukan iterasi melalui properti khusus dan menampilkan tipe, nama, dan nilainya.

## Langkah 5: Ambil Nilai Properti Khusus

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

Kode ini mengambil nilai properti khusus tertentu bernama "Nama Khusus".

## Langkah 6: Ulangi Nama Properti Kustom

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

Di sini, kami mengulangi nama properti khusus dan menampilkannya.

## Langkah 7: Hapus atau Hapus Properti Kustom

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

Anda dapat menghapus properti khusus tertentu berdasarkan namanya atau menghapus seluruh koleksi.

## Kesimpulan

Menguasai koleksi properti proyek kustom di Aspose.Tasks untuk .NET memberdayakan Anda untuk mengelola metadata proyek secara efisien. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah mengintegrasikan properti khusus ke dalam alur kerja manajemen proyek Anda, sehingga meningkatkan organisasi dan efisiensi.

## FAQ

### Q1: Bisakah saya menambahkan properti khusus tipe data apa pun ke proyek saya menggunakan Aspose.Tasks untuk .NET?

A1: Ya, Anda dapat menambahkan properti khusus yang mendukung tipe Boolean, DateTime, Double, dan String.

### Q2: Apakah mungkin untuk mengulangi nama properti khusus di Aspose.Tasks untuk .NET?

 A2: Tentu saja, Anda dapat mengulangi nama properti khusus menggunakan`Names` Properti.

### Q3: Bagaimana cara menghapus properti khusus tertentu dari proyek saya?

 A3: Anda dapat menghapus properti khusus berdasarkan namanya menggunakan`Remove` metode.

### Q4: Apakah Aspose.Tasks untuk .NET menyediakan dukungan untuk lisensi sementara?

A4: Ya, Anda bisa mendapatkan lisensi sementara dari situs Aspose untuk tujuan evaluasi.

### Q5: Di mana saya dapat menemukan dukungan atau bantuan lebih lanjut mengenai Aspose.Tasks untuk .NET?

 A5: Anda dapat mengunjungi forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15) untuk pertanyaan atau bantuan apa pun.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
