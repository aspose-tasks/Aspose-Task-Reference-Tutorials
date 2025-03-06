---
title: Kelola Nilai Garis Besar Proyek MS dengan Aspose.Tasks
linktitle: Kumpulan Nilai Garis Besar di Aspose.Tugas
second_title: Aspose.Tugas .NET API
description: Pelajari cara mengelola nilai kerangka dalam file Microsoft Project menggunakan Aspose.Tasks untuk .NET. Tutorial langkah demi langkah dengan contoh kode.
weight: 17
url: /id/net/outline-code-page-settings/outline-value-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kelola Nilai Garis Besar Proyek MS dengan Aspose.Tasks

## Perkenalan
Aspose.Tasks untuk .NET menyediakan serangkaian fitur komprehensif untuk berinteraksi dengan file Microsoft Project. Salah satu fitur tersebut adalah kemampuan untuk mengelola nilai garis besar dalam suatu proyek. Dalam tutorial ini, kita akan mempelajari cara mengumpulkan dan memanipulasi nilai kerangka menggunakan Aspose.Tasks untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1.  Aspose.Tasks untuk .NET: Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/tasks/net/).
2. Lingkungan Pengembangan: Pastikan Anda menginstal IDE yang sesuai, seperti Visual Studio.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat.
## Impor Namespace
Dalam file kode C# Anda, impor namespace yang diperlukan untuk mengakses kelas dan metode Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Mari kita bagi contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Muat File Proyek
 Pertama, inisialisasi a`Project` objek dengan memuat file Microsoft Project yang ada:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Langkah 2: Hapus Nilai Garis Besar yang Ada
Selanjutnya, hapus semua nilai garis besar yang ada dari proyek:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Langkah 3: Tentukan Kode Garis Besar Baru
Sekarang, tentukan kode kerangka baru dengan deskripsi dan nilai:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Langkah 4: Perbarui Nilai Garis Besar
Perbarui nilai kode kerangka:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Langkah 5: Ulangi Nilai Garis Besar
Ulangi nilai kerangka dan cetak detailnya:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Langkah 6: Memanipulasi Nilai Garis Besar
Lakukan operasi seperti menghapus, menyisipkan, dan menyalin nilai kerangka sesuai kebutuhan:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Kesimpulan
Dalam tutorial ini, kita mempelajari cara bekerja dengan nilai kerangka dalam file Microsoft Project menggunakan Aspose.Tasks untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat mengelola nilai garis besar secara efisien dalam proyek Anda, sehingga memungkinkan kontrol dan fleksibilitas yang lebih besar.
## FAQ
### T: Dapatkah saya memanipulasi beberapa kode outline secara bersamaan?
J: Ya, Anda dapat menentukan dan memanipulasi beberapa kode kerangka dalam suatu proyek menggunakan Aspose.Tasks.
### T: Apakah Aspose.Tasks kompatibel dengan versi file Microsoft Project yang berbeda?
J: Ya, Aspose.Tasks mendukung berbagai versi file Microsoft Project, termasuk format MPP dan XML.
### T: Bagaimana cara menangani kesalahan saat bekerja dengan nilai outline?
J: Anda dapat menerapkan mekanisme penanganan kesalahan seperti blok coba-tangkap untuk mengelola pengecualian dengan baik.
### T: Bisakah saya mengkustomisasi tampilan nilai outline di proyek saya?
J: Ya, Aspose.Tasks menyediakan API ekstensif untuk menyesuaikan tampilan dan perilaku nilai kerangka sesuai dengan kebutuhan Anda.
### T: Di mana saya dapat menemukan sumber daya tambahan dan dukungan untuk Aspose.Tasks?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan komunitas dan menjelajahi[dokumentasi](https://reference.aspose.com/tasks/net/) untuk informasi mendetail tentang API dan fitur.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
