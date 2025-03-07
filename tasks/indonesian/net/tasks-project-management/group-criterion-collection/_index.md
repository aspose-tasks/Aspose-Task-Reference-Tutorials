---
title: Kelola Kriteria Grup Proyek MS dengan Aspose.Tasks
linktitle: Mengelola Pengumpulan Kriteria Grup di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola kumpulan Proyek MS Kriteria Grup menggunakan Aspose.Tasks untuk .NET. Panduan langkah demi langkah untuk pengembang.
weight: 28
url: /id/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola Kriteria Grup Proyek MS dengan Aspose.Tasks

## Perkenalan
Aspose.Tasks untuk .NET adalah API canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project secara terprogram. Dalam tutorial ini, kita akan mempelajari cara mengelola kumpulan Kriteria Grup dalam MS Project menggunakan Aspose.Tasks.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Tasks untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Tasks di proyek .NET Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/net/).

2. File Proyek Microsoft: Siapkan file Microsoft Project (MPP) untuk digunakan.

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan ke kode C# Anda. Langkah ini penting untuk mengakses fungsionalitas yang disediakan oleh Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Langkah 1: Muat File Proyek

 Inisialisasi a`Project` objek dengan memuat file MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Langkah 2: Akses Kriteria Grup

Ambil grup dari proyek dan akses kriterianya.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Langkah 3: Ulangi Kriteria Grup

Ulangi setiap kriteria dalam grup dan tampilkan propertinya.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Langkah 4: Hapus Kriteria Grup

Hapus kriteria grup yang ada jika tidak hanya dapat dibaca.

```csharp
group.GroupCriteria.Clear();
```

## Langkah 5: Tambahkan Kriteria Baru

Buat kriteria grup baru dan tambahkan ke grup.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Langkah 6: Salin Kriteria ke Grup Lain

Salin kriteria dari satu kelompok ke kelompok lainnya.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara mengelola koleksi Proyek MS Kriteria Grup menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif memanipulasi kriteria grup dalam file Microsoft Project Anda secara terprogram.

## FAQ

### Q1: Apakah Aspose.Tasks kompatibel dengan semua versi Microsoft Project?

J: Ya, Aspose.Tasks mendukung file Microsoft Project berbagai versi, termasuk 2003, 2007, 2010, 2013, dan 2016.

### Q2: Bisakah saya menerapkan beberapa kriteria ke satu grup?

J: Tentu saja, Anda dapat menambahkan beberapa kriteria ke grup dengan mengulangi masing-masing kriteria dan menambahkannya sesuai kebutuhan.

### Q3: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?

 J: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/).

### Q4: Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks?

 A: Anda dapat merujuk ke dokumentasinya[Di Sini](https://reference.aspose.com/tasks/net/).

### Q5: Bagaimana saya bisa mendapatkan dukungan jika saya mengalami masalah?

 J: Jika Anda memiliki pertanyaan atau menghadapi masalah apa pun, Anda dapat mencari dukungan dari forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
