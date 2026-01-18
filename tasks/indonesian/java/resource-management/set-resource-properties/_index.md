---
date: 2026-01-18
description: Pelajari cara mengatur tarif standar dan properti sumber daya lainnya
  di MS Project menggunakan Aspose.Tasks untuk Java, termasuk cara menambahkan sumber
  daya MS Project dan mengelola sumber daya secara efisien.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengatur Tarif Standar untuk Sumber Daya di Aspose.Tasks
url: /id/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menetapkan Tarif Standar untuk Sumber Daya di Aspose.Tasks

## Pendahuluan
Jika Anda membangun aplikasi Java yang perlu berinteraksi dengan file Microsoft Project, **menetapkan tarif standar** untuk sebuah sumber daya adalah salah satu tugas yang paling umum. Dalam tutorial ini Anda akan belajar cara **menetapkan tarif standar** dan properti sumber daya lainnya menggunakan Aspose.Tasks untuk Java. Pada akhir panduan Anda akan dapat membuat objek proyek, menambahkan sumber daya ke file MS Project, dan mengelola sumber daya MS Project dengan percaya diri.

## Jawaban Cepat
- **Apa kelas utama untuk bekerja dengan file Project?** `Project`
- **Metode mana yang menambahkan sumber daya baru?** `project.getResources().add()`
- **Bagaimana cara menetapkan tarif standar?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Apakah saya memerlukan lisensi untuk produksi?** Yes, a valid Aspose.Tasks license is required.
- **Versi Java mana yang didukung?** Java 8+ (the latest JDK is recommended).

## Apa itu “set standard rate”?
Operasi *set standard rate* menetapkan biaya per jam default untuk sebuah sumber daya. Manajer proyek menggunakan nilai ini untuk menghitung biaya tenaga kerja, menghasilkan laporan biaya, dan meramalkan anggaran.

## Mengapa menetapkan tarif dengan Aspose.Tasks?
- **Tidak perlu instalasi Microsoft Project** – memanipulasi file langsung dari Java.
- **Kualitas penuh** – semua bidang sumber daya, termasuk lembur dan tarif biaya, dipertahankan.
- **Lintas‑platform** – bekerja di Windows, Linux, dan macOS.
- **Ramahan otomatisasi** – ideal untuk pemrosesan batch atau integrasi dengan pipeline CI.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki hal berikut:

### Penyiapan Lingkungan Pengembangan Java
1. **Instal JDK:** Pastikan Anda memiliki Java Development Kit (JDK) terinstal di sistem Anda. Anda dapat mengunduhnya dari [situs Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. **Penyiapan IDE:** Pilih Integrated Development Environment (IDE) seperti IntelliJ IDEA, Eclipse, atau NetBeans dan siapkan di mesin Anda.

### Instalasi Aspose.Tasks untuk Java
1. **Unduh Aspose.Tasks untuk Java:** Buka [halaman unduhan](https://releases.aspose.com/tasks/java/) dan dapatkan versi terbaru Aspose.Tasks untuk Java.
2. **Integrasikan dengan Proyek:** Masukkan pustaka Aspose.Tasks untuk Java ke dalam proyek Java Anda dengan menambahkannya sebagai dependensi.

## Impor Paket
Untuk memulai, Anda perlu mengimpor paket yang diperlukan dari Aspose.Tasks untuk Java ke dalam proyek Anda. Langkah ini memastikan Anda memiliki akses ke fungsionalitas yang dibutuhkan.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Langkah 1: Buat Objek Project
Membuat **objek proyek** adalah langkah pertama dalam setiap manipulasi MS Project. Objek ini mewakili seluruh file proyek dalam memori.

```java
Project project = new Project();
```

## Langkah 2: Tambahkan Sumber Daya (add resource ms project)
Sekarang kita akan **menambahkan sumber daya MS Project** menggunakan koleksi Resources. Nama sumber daya dapat berupa apa saja yang masuk akal untuk jadwal Anda.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Langkah 3: Atur Properti Sumber Daya (how to set rates)
Di sinilah kita **menetapkan tarif standar** dan juga mendemonstrasikan cara menetapkan tarif lembur. Tarif ini disimpan sebagai nilai `BigDecimal` untuk mempertahankan presisi.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Masalah Umum dan Solusinya
| Masalah | Mengapa Terjadi | Solusi |
|-------|----------------|-----|
| `NullPointerException` when calling `set` | Sumber daya tidak ditambahkan dengan benar. | Ensure `project.getResources().add()` returns a non‑null `Resource`. |
| Rates appear as 0 in the saved file | Menggunakan `int` alih‑alih `BigDecimal`. | Always use `BigDecimal.valueOf()` for monetary values. |
| License not found | File lisensi tidak dimuat sebelum membuat `Project`. | Load the license (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) at the start of your program. |

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda telah belajar cara **membuat objek proyek**, **menambahkan sumber daya MS Project**, dan **menetapkan tarif standar** beserta properti sumber daya lainnya. Hal ini memungkinkan Anda mengotomatisasi perhitungan biaya, menghasilkan laporan khusus, dan mengelola sumber daya MS Project sepenuhnya dari Java.

## FAQ
### Apakah Aspose.Tasks untuk Java dapat menangani file MS Project yang kompleks?
Ya, Aspose.Tasks untuk Java mampu menangani berbagai format file MS Project, termasuk yang kompleks dengan hierarki tugas yang luas.

### Apakah tersedia trial gratis untuk Aspose.Tasks untuk Java?
Ya, Anda dapat mengakses trial gratis Aspose.Tasks untuk Java dari [sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk Java?
Anda dapat mencari bantuan dan berpartisipasi dalam diskusi terkait Aspose.Tasks untuk Java di [forum dukungan](https://forum.aspose.com/c/tasks/15).

### Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Tasks untuk Java?
Anda dapat memperoleh lisensi sementara dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.

### Di mana saya dapat membeli versi berlisensi Aspose.Tasks untuk Java?
Anda dapat membeli versi berlisensi Aspose.Tasks untuk Java dari [halaman pembelian](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose