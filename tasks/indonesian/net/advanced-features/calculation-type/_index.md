---
date: 2026-03-24
description: Pelajari cara mengatur perhitungan di Aspose.Tasks untuk .NET, dengan
  contoh menghitung nilai ringkasan, mendefinisikan rumus perhitungan, dan mengonfigurasi
  ringkasan rollup.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cara Mengatur Jenis Perhitungan di Aspose.Tasks
url: /id/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengatur Tipe Perhitungan di Aspose.Tasks

## Pendahuluan

Jika Anda perlu **mengatur perhitungan** aturan untuk tugas dan baris ringkasan dalam file Microsoft Project, tutorial ini menunjukkan cara melakukannya menggunakan Aspose.Tasks untuk .NET. Kami akan menelusuri contoh **tipe perhitungan** lengkap, mendemonstrasikan cara **menghitung nilai ringkasan**, dan menjelaskan cara **mendefinisikan formula perhitungan** serta **mengonfigurasi ringkasan rollup** untuk atribut ekstended. Pada akhir tutorial, Anda akan dapat menambahkan tugas ke proyek, mengatur logika perhitungan khusus, dan mengendalikan perilaku roll‑up dengan percaya diri.

## Jawaban Cepat
- **Apa tujuan utama?** Untuk mengontrol bagaimana nilai tugas dan ringkasan dihitung dalam file Project.  
- **Kelas API mana yang digunakan?** `ExtendedAttributeDefinition` bersama dengan `CalculationType` dan `SummaryRowsCalculationType`.  
- **Apakah saya dapat menggunakan formula?** Ya – atur `CalculationType = CalculationType.Formula` dan berikan string formula.  
- **Bagaimana cara roll‑up nilai ringkasan?** Gunakan `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` dan tentukan `RollupType` seperti `Average`.  
- **Apakah saya memerlukan lisensi?** Lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.

## Apa itu Tipe Perhitungan dan cara mengatur perhitungan?

`CalculationType` memberi tahu Aspose.Tasks bagaimana menghitung nilai atribut ekstended. Anda dapat memilih nilai statis, formula, atau membiarkan perpustakaan melakukan roll‑up nilai dari tugas anak. Mengatur perhitungan dengan benar sangat penting ketika Anda ingin proyek mencerminkan aturan bisnis khusus tanpa pembaruan manual.

## Mengapa menggunakan tipe perhitungan untuk menghitung nilai ringkasan?

Ketika sebuah proyek berisi tugas ringkasan, Anda sering memerlukan baris ringkasan menampilkan data teragregasi (misalnya, total biaya, rata‑rata durasi). Dengan mengonfigurasi **menghitung nilai ringkasan** melalui `SummaryRowsCalculationType` dan `RollupType`, Aspose.Tasks dapat secara otomatis menjaga agregat tersebut tetap sinkron saat Anda memodifikasi tugas individu.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

1. Pengetahuan dasar tentang C# dan kerangka kerja .NET.  
2. Visual Studio (versi terbaru apa pun) terpasang di mesin Anda.  
3. Perpustakaan Aspose.Tasks untuk .NET terinstal – Anda dapat mengunduhnya dari [sini](https://releases.aspose.com/tasks/net/).  
4. Akses ke dokumentasi resmi Aspose.Tasks untuk .NET sebagai referensi, tersedia [sini](https://reference.aspose.com/tasks/net/).

## Impor Namespace

Sebelum menyelam ke contoh, pastikan untuk mengimpor namespace yang diperlukan:

```csharp
using Aspose.Tasks;
using System;
```

## Langkah 1: Buat Proyek Baru

Pertama, kami membuat objek `Project` kosong yang akan menampung tugas dan atribut khusus kami.

```csharp
var project = new Project();
```

## Langkah 2: Tambahkan Tugas ke Proyek

Sekarang kami **menambahkan data tugas proyek** dengan membuat tugas sederhana, mengatur tanggal mulai, dan memberinya durasi satu hari.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Langkah 3: Tentukan Tipe Perhitungan untuk Atribut Ekstended (Contoh Formula)

Di sini kami membuat definisi atribut ekstended yang nilainya dihitung dari sebuah formula. Ini mendemonstrasikan **contoh tipe perhitungan** dan menunjukkan cara **mendefinisikan formula perhitungan**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Langkah 4: Tentukan Tipe Perhitungan untuk Baris Ringkasan (Konfigurasi Ringkasan Rollup)

Selanjutnya, kami membuat definisi atribut ekstended lain yang memberi tahu Aspose.Tasks untuk **mengonfigurasi ringkasan rollup** menggunakan tipe roll‑up *Average*. Ini adalah cara tipikal untuk **menghitung nilai ringkasan** untuk biaya, pekerjaan, atau bidang khusus.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Masalah Umum & Pemecahan Masalah

| Gejala | Penyebab Kemungkinan | Solusi |
|--------|----------------------|--------|
| Formula mengembalikan `null` | Referensi bidang yang salah dalam formula | Verifikasi nama bidang di dalam kurung siku (misalnya, `[Start]` bukan `[stARt]`). |
| Baris ringkasan menampilkan 0 | `SummaryRowsCalculationType` tidak diatur atau `RollupType` salah | Pastikan `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` dan pilih `RollupType` yang sesuai. |
| Proyek gagal dimuat setelah menambahkan atribut | Ketidaksesuaian antara definisi atribut dan penggunaan tugas | Tambahkan definisi atribut **sebelum** Anda menetapkannya ke tugas apa pun. |

## Kesimpulan

Dalam tutorial ini, kami telah membahas **cara mengatur perhitungan** aturan di Aspose.Tasks untuk .NET, mulai dari membuat tugas sederhana hingga mendefinisikan tipe perhitungan berbasis formula dan roll‑up. Dengan menguasai pengaturan ini, Anda memperoleh kontrol detail atas **menghitung nilai ringkasan**, memungkinkan analitik proyek yang lebih kaya tanpa pekerjaan spreadsheet manual.

## FAQ

### Q1: Apa itu Tipe Perhitungan di Aspose.Tasks?

A1: Tipe Perhitungan di Aspose.Tasks menentukan bagaimana nilai dihitung untuk tugas dan tugas ringkasan dalam sebuah proyek, menawarkan opsi seperti Formula dan Rollup.

### Q2: Bagaimana cara mengatur Tipe Perhitungan untuk Atribut Ekstended?

A2: Anda dapat mengatur Tipe Perhitungan untuk Atribut Ekstended dengan mendefinisikan properti `CalculationType`‑nya sesuai.

### Q3: Bisakah saya menyesuaikan Tipe Perhitungan untuk baris ringkasan dalam proyek?

A3: Ya, Aspose.Tasks memungkinkan Anda menentukan Tipe Perhitungan untuk baris ringkasan, sehingga Anda dapat menyesuaikan perhitungan nilai sesuai kebutuhan.

### Q4: Apakah ada tipe Rollup yang berbeda tersedia untuk perhitungan tugas ringkasan?

A4: Ya, Aspose.Tasks menyediakan berbagai Tipe Rollup seperti Average, Sum, dan Count untuk menghitung nilai tugas ringkasan.

### Q5: Di mana saya dapat menemukan lebih banyak sumber daya tentang Aspose.Tasks untuk .NET?

A5: Anda dapat menjelajahi dokumentasi dan forum dukungan komunitas yang tersedia di [Aspose.Tasks untuk .NET](https://reference.aspose.com/tasks/net/) untuk panduan komprehensif dan bantuan.

---

**Terakhir Diperbarui:** 2026-03-24  
**Diuji Dengan:** Aspose.Tasks for .NET (rilis terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}