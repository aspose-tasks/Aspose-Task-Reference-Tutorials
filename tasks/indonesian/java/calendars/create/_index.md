---
date: 2026-08-03
description: Pelajari cara membuat kalender ms project, menambahkan kalender ke proyek,
  dan menyimpan proyek sebagai XML menggunakan Aspose.Tasks untuk Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Tambahkan Kalender ke Proyek menggunakan Aspose.Tasks
og_description: Buat kalender ms project secara programatis menggunakan Aspose.Tasks
  untuk Java. Tambahkan kalender, sesuaikan jadwal, dan ekspor ke XML dalam hitungan
  menit.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Buat kalender ms project dengan Aspose.Tasks untuk Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Buat kalender ms project dengan Aspose.Tasks untuk Java
url: /id/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat kalender ms project dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam alur kerja manajemen proyek modern, kemampuan untuk **create ms project calendar** secara programatik dapat menghemat jam pengeditan manual. Aspose.Tasks untuk Java memberikan API yang bersih dan type‑safe untuk memanipulasi file Microsoft Project tanpa pernah membuka klien desktop. Pada tutorial ini Anda akan belajar cara menambahkan kalender, cara membuat kalender MS Project, dan cara menyimpan proyek sebagai XML—semua dengan hanya beberapa baris kode Java.

## Jawaban Cepat
- **Apa arti “create ms project calendar”?**  
  Artinya memasukkan definisi waktu kerja baru (kalender) ke dalam file Microsoft Project melalui kode.  
- **Perpustakaan mana yang menangani ini?**  
  Aspose.Tasks untuk Java menyediakan kelas `Calendar` dan kontainer `Project` untuk mengelola kalender.  
- **Apakah saya memerlukan lisensi?**  
  Lisensi evaluasi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk penggunaan produksi.  
- **Bisakah saya menyimpan file sebagai XML?**  
  Ya—gunakan `SaveFileFormat.Xml` untuk mengekspor proyek sebagai file XML.  
- **Apa prasyaratnya?**  
  Java JDK 8+ dan JAR Aspose.Tasks untuk Java di classpath Anda.

## Apa itu create ms project calendar?
Membuat kalender MS Project berarti secara programatik menambahkan definisi kalender baru ke file Proyek, menentukan hari kerja, pengecualian, dan jam kerja harian, lalu menetapkan kalender tersebut ke tugas, sumber daya, atau seluruh proyek sehingga perhitungan jadwal menghormati waktu kerja yang telah didefinisikan.

## Mengapa menggunakan Aspose.Tasks untuk Java untuk menambahkan kalender ke proyek?
Anda harus menggunakan Aspose.Tasks untuk Java karena menyediakan API type‑safe lengkap yang berfungsi tanpa Microsoft Project terpasang, mendukung semua versi Project utama (2007‑2021, mencakup lebih dari 5 rilis), dan dapat mengekspor ke XML, MPP, dan **10+** format lain, memungkinkan pembuatan kalender massal secara otomatis di server mana pun.

## Prasyarat
- **Java Development Kit (JDK) 8 atau lebih baru** terpasang dan dikonfigurasi.  
- **Aspose.Tasks untuk Java** library – unduh dari [situs resmi](https://releases.aspose.com/tasks/java/) dan tambahkan JAR ke classpath proyek Anda.  
- IDE atau alat build (Maven/Gradle) pilihan Anda.

## Panduan langkah‑demi‑langkah

### Langkah 1: impor paket Aspose.Tasks yang diperlukan
Pertama, bawa kelas Aspose.Tasks ke dalam ruang lingkup sehingga Anda dapat bekerja dengan proyek dan kalender.

```java
import com.aspose.tasks.*;
```

### Langkah 2: atur jalur direktori data
Tentukan di mana file proyek yang dihasilkan akan ditulis. Ganti placeholder dengan jalur absolut atau relatif di mesin Anda.

```java
String dataDir = "Your Data Directory";
```

### Langkah 3: buat instance Project baru
`Project` adalah kelas inti yang mewakili file Microsoft Project dalam memori.

```java
Project prj = new Project();
```

### Langkah 4: definisikan kalender yang ingin Anda tambahkan
`Calendar` mendefinisikan jadwal dengan hari kerja, pengecualian, dan jam kerja untuk sebuah proyek.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Tip pro:** Setelah menambahkan kalender, Anda dapat menyesuaikan hari kerja dengan `cal1.getWeekDays().add(...)` dan mengatur jam kerja harian menggunakan `cal1.getBaseCalendar().setWorkingTime(...)`.

### Langkah 5: simpan proyek (simpan proyek sebagai XML)
`SaveFileFormat.Xml` memberi tahu Aspose.Tasks untuk menulis proyek dalam format XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Langkah 6: tampilkan pesan selesai
Beritahu pengguna bahwa operasi selesai dengan sukses.

```java
System.out.println("Process completed Successfully");
```

Dengan mengikuti enam langkah singkat ini, Anda telah berhasil **menambahkan kalender ke proyek** dan menyimpan hasilnya sebagai file XML.

## Masalah umum dan solusi

| Masalah | Alasan | Solusi |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Objek Project tidak diinisialisasi dengan benar. | Pastikan `new Project()` dipanggil sebelum mengakses kalender. |
| **File tidak ditemukan saat menyimpan** | `dataDir` mengarah ke folder yang tidak ada. | Buat direktori terlebih dahulu atau gunakan jalur absolut. |
| **Nama kalender muncul sebagai “no info”** | Nama placeholder digunakan dalam contoh. | Ganti dengan nama yang bermakna yang mencerminkan jadwal (mis., “Kalender Libur AS”). |
| **XML yang disimpan tidak dapat dibuka di MS Project** | Menggunakan versi Aspose.Tasks yang usang. | Perbarui ke rilis Aspose.Tasks untuk Java terbaru. |

## Pertanyaan yang sering diajukan

**T: Bisakah Aspose.Tasks menangani kalender kompleks dengan banyak pengecualian?**  
J: Ya – setelah menambahkan kalender Anda dapat mendefinisikan pengecualian, jam kerja, dan hari non‑kerja menggunakan kelas `WeekDay` dan `Exception`.

**T: Apakah memungkinkan untuk menetapkan kalender baru ke tugas tertentu?**  
J: Tentu saja. Dapatkan tugas melalui `prj.getRootTask().getChildren().add("Task Name")` dan setel `task.set(Tsk.CALENDAR, cal3);`.

**T: Apakah perpustakaan mendukung penyimpanan dalam format lain seperti MPP?**  
J: Ya. Ganti `SaveFileFormat.Xml` dengan `SaveFileFormat.Mpp` atau `SaveFileFormat.P6` sesuai kebutuhan; Aspose.Tasks mendukung **12** format output.

**T: Apakah saya memerlukan lisensi untuk build pengembangan?**  
J: Lisensi evaluasi sementara cukup untuk pengujian; lisensi penuh diperlukan untuk penyebaran produksi.

**T: Di mana saya dapat mendapatkan bantuan jika mengalami masalah?**  
J: Forum komunitas Aspose.Tasks adalah sumber daya yang sangat baik: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Terakhir Diperbarui:** 2026-08-03  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Mendefinisikan Hari Minggu dalam Kalender MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Cara Mengatur Kalender Proyek Java dengan Aspose.Tasks](/tasks/java/calendars/properties/)
- [Buat Pengecualian Kalender Kustom dengan Aspose.Tasks untuk Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}