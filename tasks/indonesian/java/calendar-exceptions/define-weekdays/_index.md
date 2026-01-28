---
date: 2026-01-28
description: Pelajari cara membuat kalender proyek Aspose, menentukan hari kerja untuk
  pengecualian kalender, dan mengelola jadwal hari non‑kerja menggunakan Aspose.Tasks
  untuk Java.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Buat Kalender Proyek Aspose – Tentukan Hari Kerja untuk Pengecualian Kalender
url: /id/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Kalender Proyek Aspose – Tentukan Hari Kerja untuk Pengecualian Kalender

### Introduction
Ketika Anda perlu **create project calendar aspose**, Anda harus dapat memodelkan hari kerja non‑standar seperti hari libur, shift khusus, atau penutupan sementara. Aspose.Tasks untuk Java memberi Anda kontrol penuh atas definisi kalender, memungkinkan Anda menambahkan pengecualian yang mencerminkan jadwal dunia nyata. Dalam tutorial ini kami akan memandu Anda langkah demi langkah untuk mendefinisikan hari kerja untuk pengecualian kalender, sehingga timeline proyek Anda tetap akurat dan dapat diandalkan. Pada akhir tutorial Anda juga akan melihat bagaimana hal ini masuk ke dalam strategi **non‑working days schedule** yang lebih luas untuk proyek perusahaan mana pun.

## Quick Answers
- **Apa arti “create project calendar aspose”?**  
  Ini merujuk pada penggunaan Aspose.Tasks untuk membuat objek kalender khusus yang mengatur penjadwalan tugas.
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?**  
  Versi trial gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.
- **IDE mana yang didukung?**  
  IntelliJ IDEA, Eclipse, NetBeans, atau IDE apa pun yang mendukung Java 8+.
- **Bisakah saya menambahkan beberapa pengecualian ke kalender yang sama?**  
  Ya – Anda dapat menambahkan sebanyak yang diperlukan objek `CalendarException`.
- **Format file apa yang dapat saya simpan proyek?**  
  XML, MPP, dan beberapa format lain yang didukung oleh Aspose.Tasks.

## What is a Project Calendar in Aspose.Tasks?
**Project calendar** mendefinisikan hari kerja dan jam kerja untuk sebuah proyek. Kalender ini memengaruhi tanggal mulai/selesai tugas, alokasi sumber daya, dan perhitungan jadwal secara keseluruhan. Dengan menyesuaikan kalender, Anda memastikan jadwal menghormati kendala dunia nyata seperti libur perusahaan atau kebijakan kerja akhir pekan.

## Why define weekdays for calendar exceptions?
- **Timeline yang akurat:** Tugas tidak akan dijadwalkan pada hari yang ditandai sebagai non‑working.
- **Perencanaan sumber daya:** Sumber daya hanya dialokasikan pada hari kerja yang sah.
- **Kepatuhan:** Menyelaraskan jadwal proyek dengan kebijakan organisasi atau hari libur resmi.

## Non‑working Days Schedule with Calendar Exceptions
Saat Anda memelihara **non‑working days schedule**, biasanya Anda memiliki daftar utama libur, jendela pemeliharaan, atau periode blackout lainnya. Menambahkan tanggal‑tanggal tersebut sebagai objek `CalendarException` menjamin setiap perhitungan—baik analisis jalur kritis maupun leveling sumber daya—secara otomatis menghormati kendala tersebut. Pendekatan ini menghilangkan penyesuaian tanggal manual dan mengurangi risiko penyimpangan jadwal.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru.  
2. **Aspose.Tasks for Java** – unduh dari halaman resmi [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, atau editor Java‑compatible lainnya.  

## How to create project calendar aspose – Define weekdays for calendar exceptions

### Step‑by‑Step Guide

### Step 1: Import Required Packages
We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for date handling.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Step 2: Define the Data Directory
Specify where the generated project file will be saved.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Create a Project Instance
Instantiate a new `Project` object – this is the container for all project data, including calendars.

```java
Project project = new Project();
```

### Step 4: Define a Calendar
Add a custom calendar to the project. This calendar will hold our exceptions.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Step 5: Define Weekdays Exception
Create a `CalendarException` that marks a range of days (e.g., the last week of December) as non‑working.  
The example sets the exception from **24 Dec 2009** to **31 Dec 2009**, disables work for those days, and treats the exception as a daily type.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Step 6: Save the Project
Persist the project, including the custom calendar and its exception, to an XML file.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Exception dates not applied** | Pastikan `setEnteredByOccurrences(false)` dan nilai `FromDate/ToDate` sudah benar. |
| **Saved file is empty** | Verifikasi bahwa `dataDir` mengarah ke folder yang dapat ditulisi dan nama file berakhiran `.xml`. |
| **Calendar not reflected in task scheduling** | Tetapkan kalender ke tugas atau sumber daya menggunakan `task.setCalendar(cal)` atau `resource.setCalendar(cal)`. |

## Frequently Asked Questions

**Q: Can I define multiple exceptions for different weekdays within the same calendar?**  
A: Ya. Tambahkan objek `CalendarException` tambahan ke `cal.getExceptions()` untuk setiap periode atau aturan yang berbeda.

**Q: Is Aspose.Tasks for Java compatible with different Java IDEs?**  
A: Tentu saja. Library ini bekerja dengan IntelliJ IDEA, Eclipse, NetBeans, dan IDE apa pun yang mendukung proyek Java standar.

**Q: Can I customize exception types other than daily exceptions?**  
A: Ya. Gunakan `CalendarExceptionType.Weekly`, `Monthly`, atau `Yearly` sesuai kebutuhan penjadwalan Anda.

**Q: How can I handle exceptions dynamically based on project requirements?**  
A: Bangun objek pengecualian secara programatis—misalnya, baca tanggal libur dari basis data atau file konfigurasi dan buat instance `CalendarException` dalam loop.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Ya, Anda dapat mengunduh trial gratis dari [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Conclusion
Dengan mengikuti langkah‑langkah ini Anda kini tahu cara **create project calendar aspose** dan mendefinisikan pengecualian hari kerja yang secara akurat mencerminkan hari libur atau periode non‑working khusus. Konfigurasi kalender yang tepat sangat penting untuk jadwal yang realistis, alokasi sumber daya, dan keberhasilan proyek secara keseluruhan. Jelajahi lebih lanjut dengan mengaitkan kalender khusus ke tugas atau sumber daya serta bereksperimen dengan tipe pengecualian lain untuk membangun **non‑working days schedule** yang komprehensif bagi proyek apa pun.

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}