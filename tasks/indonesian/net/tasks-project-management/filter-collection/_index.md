---
title: Kelola Filter Proyek MS secara Efisien dengan Aspose.Tasks
linktitle: Mengelola Koleksi Filter di Aspose.Tasks
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola koleksi MS Project filter secara efektif menggunakan Aspose.Tasks untuk .NET.
weight: 17
url: /id/net/tasks-project-management/filter-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola Filter Proyek MS secara Efisien dengan Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengelola koleksi filter MS Project secara efektif menggunakan Aspose.Tasks untuk .NET. Mengelola filter sangat penting untuk mengatur dan menganalisis data proyek secara efisien. Aspose.Tasks menyediakan fungsionalitas yang kuat untuk menangani filter tugas dan sumber daya dengan lancar.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Instalasi Aspose.Tasks untuk .NET: Unduh dan instal Aspose.Tasks untuk .NET dari[tautan unduhan](https://releases.aspose.com/tasks/net/).
2. Akses ke Lingkungan Pengembangan .NET: Pastikan Anda memiliki lingkungan pengembangan .NET yang disiapkan untuk bekerja dengan Aspose.Tasks.

## Impor Namespace
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Langkah 1: Muat File Proyek
```csharp
// Jalur ke direktori dokumen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## Langkah 2: Ulangi Filter Tugas
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## Langkah 3: Ulangi Filter Sumber Daya
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## Langkah 4: Hapus dan Salin Filter
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Hapus filter proyek lain
otherProject.TaskFilters.Clear();
// Salin filter ke proyek lain
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## Langkah 5: Tambahkan Filter Tugas Khusus
```csharp
// Tambahkan filter tugas khusus
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## Langkah 6: Hapus Semua Filter
```csharp
// Hapus semua filter
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
Dengan mengikuti langkah-langkah ini, Anda dapat mengelola koleksi filter MS Project secara efisien menggunakan Aspose.Tasks untuk .NET.

## Kesimpulan
Mengelola filter secara efektif dalam koleksi MS Project sangat penting untuk mengatur dan menganalisis data proyek. Aspose.Tasks untuk .NET menyediakan fungsionalitas komprehensif untuk menangani filter tugas dan sumber daya dengan lancar, memberdayakan pengembang untuk menyederhanakan tugas manajemen proyek secara efisien.
## FAQ
### T: Dapatkah Aspose.Tasks menangani struktur proyek yang kompleks?
J: Aspose.Tasks menawarkan fitur canggih untuk menangani berbagai struktur proyek, termasuk yang kompleks, sehingga memastikan kemampuan manajemen proyek yang komprehensif.
### T: Apakah Aspose.Tasks kompatibel dengan versi file MS Project yang berbeda?
J: Ya, Aspose.Tasks mendukung berbagai format file MS Project, memastikan kompatibilitas di berbagai versi.
### T: Dapatkah saya menyesuaikan filter sesuai dengan kebutuhan proyek tertentu?
J: Tentu saja! Aspose.Tasks memungkinkan pengembang membuat filter khusus yang disesuaikan dengan kebutuhan proyek unik, sehingga meningkatkan fleksibilitas dan efisiensi.
### T: Apakah Aspose.Tasks menyediakan dokumentasi dan sumber daya dukungan?
J: Ya, Aspose.Tasks menawarkan dokumentasi ekstensif, tutorial, dan forum dukungan khusus untuk membantu pengembang di setiap langkah implementasi proyek mereka.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks?
J: Ya, pengembang dapat mengakses Aspose.Tasks versi uji coba gratis untuk menjelajahi fitur-fiturnya sebelum membuat keputusan pembelian.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
