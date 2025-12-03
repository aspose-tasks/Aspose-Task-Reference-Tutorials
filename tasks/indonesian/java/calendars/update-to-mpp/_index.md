---
date: 2025-12-03
description: Pelajari cara membuat kalender MS Project, mengonversi proyek ke MPP,
  dan menyimpan proyek MPP dengan mudah menggunakan Aspose.Tasks untuk Java.
language: id
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Buat Kalender MS Project dan Simpan sebagai MPP dengan Aspose.Tasks
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Kalender MS Project dan Simpan sebagai MPP dengan Aspose.Tasks

## Introduction

Dalam manajemen proyek modern Anda sering perlu **membuat file kalender MS Project** dan kemudian membagikannya dalam format MPP asli. Baik Anda mengkonsolidasikan jadwal dari berbagai sumber atau memigrasikan data warisan, kemampuan menghasilkan kalender secara programatik menghemat waktu dan menghilangkan kesalahan manual. Tutorial ini memandu Anda melalui proses lengkap membuat kalender di MS Project, menyesuaikannya, dan akhirnya **mengonversi proyek ke MPP** menggunakan Aspose.Tasks Java API.

## Quick Answers
- **Apa yang dibahas tutorial ini?** Membuat kalender di MS Project dan menyimpannya sebagai file MPP dengan Aspose.Tasks untuk Java.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi Java apa yang diperlukan?** Java 8 atau lebih tinggi (JDK 8+).  
- **Bisakah saya menyesuaikan kalender?** Ya – Anda dapat menambahkan jam kerja, pengecualian, dan hari libur.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk kalender dasar.

## What is “create calendar MS Project”?

Membuat kalender MS Project berarti mendefinisikan secara programatik hari kerja, jam kerja, dan pengecualian yang mengatur penjadwalan tugas dalam file Microsoft Project. Dengan menggunakan Aspose.Tasks Anda dapat membangun, memodifikasi, dan menyimpan kalender ini tanpa pernah membuka UI Microsoft Project.

## Why use Aspose.Tasks for this task?

- **Kompatibilitas .NET/Java penuh** – berfungsi di platform apa pun yang mendukung Java.  
- **Tidak memerlukan instalasi COM atau Office** – ideal untuk otomatisasi sisi server.  
- **API kaya** – mendukung setiap properti kalender, termasuk minggu kerja khusus dan hari libur.  
- **Output MPP langsung** – Anda dapat **menyimpan proyek MPP** tanpa konversi perantara.

## Prerequisites

1. **Java Development Kit (JDK) 8+** – pastikan `java -version` menampilkan 1.8 atau lebih baru.  
2. **Aspose.Tasks untuk Java** – unduh JAR terbaru dari [situs Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, atau editor apa pun yang Anda sukai.  
4. **Pengetahuan dasar Java** – familiar dengan kelas, metode, dan I/O file.

## Step‑by‑Step Guide

### Step 1: Import Required Packages

First, bring the Aspose.Tasks classes and Java utilities into scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Step 2: Set Up the Data Directory

Define where your input template and output files will live. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Define Input and Output File Names

We’ll load an existing MPP file (or a blank project) and write the result to a new file.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Step 4: Load the Project and Add a New Calendar

Create a `Project` instance from the source file and add a calendar named **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Step 5: Customize the Calendar (Optional)

If you need specific working times, holidays, or exceptions, call your own helper method. The sample uses `GetTestCalendar` as a placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set working hours for each day of the week.

### Step 6: Assign the Calendar to the Project

Tell the project to use the newly created calendar for all its scheduling calculations.

```java
project.set(Prj.CALENDAR, cal1);
```

### Step 7: Save the Project as MPP

Now **convert project to MPP** by saving it with the `SaveFileFormat.Mpp` option.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Step 8: Confirm Successful Completion

A simple console message lets you know the process finished without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Use Cases

- **Pembuatan jadwal otomatis** untuk proyek berulang (mis., sprint mingguan).  
- **Migrasi kalender CSV atau Excel lama** ke file MS Project yang lengkap.  
- **Pelaporan sisi server** di mana layanan web mengembalikan file MPP sesuai permintaan.  

## Troubleshooting & Common Pitfalls

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| `NullPointerException` pada `project.save` | `dataDir` mengarah ke folder yang tidak ada | Pastikan direktori ada atau buat secara programatis. |
| Kalender tidak diterapkan pada tugas | Tugas masih merujuk ke kalender default | Setelah mengatur `Prj.CALENDAR`, juga perbarui setiap `Task.CALENDAR` jika sebelumnya telah ditimpa. |
| File output berukuran 0 KB | Tidak ada izin menulis | Jalankan JVM dengan hak akses sistem file yang sesuai atau pilih jalur yang dapat ditulisi. |

## Frequently Asked Questions

**T: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi MS Project?**  
J: Ya, Aspose.Tasks untuk Java mendukung berbagai versi MS Project, mulai dari Project 2007 hingga rilis terbaru, memastikan kompatibilitas yang mulus.

**T: Bisakah saya menyesuaikan kalender sesuai kebutuhan proyek tertentu?**  
J: Tentu saja. Anda dapat menentukan hari kerja, mengatur minggu kerja khusus, menambahkan hari libur, dan bahkan membuat beberapa kalender dalam satu file proyek.

**T: Apakah Aspose.Tasks untuk Java menyediakan dukungan untuk pemecahan masalah dan bantuan?**  
J: Ya, Anda dapat mendapatkan bantuan dari forum komunitas Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15).

**T: Apakah tersedia percobaan gratis untuk Aspose.Tasks untuk Java?**  
J: Ya, percobaan gratis yang berfungsi penuh tersedia [di sini](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?**  
J: Lisensi sementara dapat diminta melalui situs Aspose [di sini](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}