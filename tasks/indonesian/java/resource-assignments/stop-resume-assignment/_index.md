---
date: 2026-01-10
description: Pelajari cara menghentikan penugasan, mengelola penugasan sumber daya,
  dan melihat contoh penugasan sumber daya di Aspose.Tasks untuk Java dengan tutorial
  langkah demi langkah ini.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menghentikan Penugasan dan Melanjutkan Penugasan Sumber Daya di Aspose.Tasks
url: /id/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menghentikan Penugasan dan Melanjutkan Penugasan Sumber Daya di Aspose.Tasks

## Introduction
Dalam tutorial ini, **Anda akan menemukan cara menghentikan penugasan** dan kemudian melanjutkannya menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah API Java yang kuat yang memungkinkan Anda membaca file proyek dalam format Java, memanipulasi data Microsoft Project, dan mengelola penugasan sumber daya tanpa harus menginstal Microsoft Project. Kami akan membahas setiap langkah, menjelaskan mengapa setiap baris penting, dan memberikan tip praktis yang dapat Anda terapkan pada proyek dunia nyata.

## Quick Answers
- **Apa arti “stop assignment”?** Itu menandai penugasan sumber daya sebagai tidak aktif sementara mulai dari tanggal berhenti tertentu.  
- **Apakah saya dapat melanjutkan penugasan yang sama nanti?** Ya, dengan menetapkan tanggal melanjutkan pada penugasan yang sama.  
- **Apakah saya memerlukan Microsoft Project untuk menggunakan API ini?** Tidak, Aspose.Tasks berfungsi secara independen dari Microsoft Project.  
- **Versi Java apa yang diperlukan?** Java 8 atau yang lebih tinggi disarankan.  
- **Di mana saya dapat mengunduh perpustakaan?** Dari halaman unduhan resmi Aspose.Tasks Java.

## What is “how to stop assignment” in the context of Aspose.Tasks?
Menghentikan penugasan memberi tahu penjadwal untuk mengabaikan pekerjaan yang dialokasikan ke sumber daya setelah **tanggal berhenti** hingga **tanggal melanjutkan** (jika ada). Ini berguna untuk menangani cuti, downtime peralatan, atau periode apa pun ketika sumber daya tidak dianggap aktif.

## Why use Aspose.Tasks to manage resource assignments?
- **Tidak perlu Microsoft Project** – bekerja langsung dengan file .mpp.  
- **Kontrol penuh atas tanggal** – Anda dapat memeriksa tanggal berhenti, tanggal melanjutkan, dan menyesuaikannya secara programatik.  
- **Cross‑platform** – berjalan pada sistem operasi apa pun yang mendukung Java.  
- **API kaya** – menyediakan *contoh penugasan sumber daya* yang dapat Anda kembangkan untuk pelaporan khusus.

## Prerequisites
Before we begin, make sure you have:

- Java Development Kit (JDK) terpasang di sistem Anda.  
- Aspose.Tasks for Java library downloaded. You can download it from [here](https://releases.aspose.com/tasks/java/).  
- Pemahaman dasar tentang pemrograman Java.  

## Import Packages
First, let's import the necessary packages into our Java project:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Step 1: Load the Project File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Di sini kami **membaca file proyek Java** format (`.mpp`) dan membuat objek `Project` yang memberi kami akses ke semua data proyek, termasuk penugasan sumber daya.

## Step 2: Iterate Through Resource Assignments
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Kami menetapkan **tanggal minimum** untuk menyaring tanggal placeholder dan kemudian melakukan iterasi melalui setiap penugasan. Ini adalah pola *contoh penugasan sumber daya* yang umum digunakan ketika Anda perlu memeriksa atau memodifikasi penugasan.

## Step 3: Check Stop and Resume Dates
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

Pada blok ini kami **memeriksa tanggal berhenti** dan **memeriksa tanggal melanjutkan** untuk setiap penugasan. Jika tanggal tersebut sebelum `minDate` kami, kami menganggapnya tidak diatur (`"NA"`); jika tidak, kami mencetak tanggal sebenarnya. Logika ini penting untuk **mengelola penugasan sumber daya** dengan benar.

## Common Issues and Solutions
- **Tanggal null** – `ra.get(Asn.STOP)` may return `null`. Guard against it by adding a null check before calling `.before(minDate)`.  
- **Path file tidak tepat** – Ensure `dataDir` ends with a path separator (`/` or `\\`) appropriate for your OS.  
- **Versi tidak cocok** – Use the latest Aspose.Tasks for Java version to avoid missing enum values.

## FAQ's
### Can I use Aspose.Tasks without Microsoft Project installed?
Ya, Aspose.Tasks memungkinkan Anda bekerja dengan file Microsoft Project tanpa perlu menginstal Microsoft Project di sistem Anda.

### Where can I find more documentation?
Anda dapat menemukan dokumentasi detail [here](https://reference.aspose.com/tasks/java/).

### Is there a free trial available?
Ya, Anda dapat mendapatkan percobaan gratis [here](https://releases.aspose.com/).

### How can I get support if I encounter any issues?
Anda dapat mendapatkan dukungan dari komunitas [here](https://forum.aspose.com/c/tasks/15).

### Can I purchase a temporary license?
Ya, Anda dapat membeli lisensi sementara [here](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: How do I programmatically set a stop date for an assignment?**  
A: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.

**T: Bagaimana cara saya secara programatik menetapkan tanggal berhenti untuk sebuah penugasan?**  
**J:** Gunakan `ra.set(Asn.STOP, yourDateObject);` dimana `yourDateObject` adalah `java.util.Date`.

**Q: What happens if the resume date is earlier than the stop date?**  
A: The API does not enforce chronological order; however, the scheduler will treat the assignment as active only after the later of the two dates, so you should validate dates yourself.

**T: Apa yang terjadi jika tanggal melanjutkan lebih awal daripada tanggal berhenti?**  
**J:** API tidak memaksa urutan kronologis; namun, penjadwal akan menganggap penugasan aktif hanya setelah tanggal yang lebih akhir di antara keduanya, jadi Anda harus memvalidasi tanggal secara manual.

**Q: Can I filter assignments to only those that have a stop date set?**  
A: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP) != null`.

**T: Bisakah saya memfilter penugasan hanya yang memiliki tanggal berhenti yang diatur?**  
**J:** Ya, iterasi melalui `prj.getResourceAssignments()` dan periksa `ra.get(Asn.STOP) != null`.

**Q: Is it possible to remove a stop date once set?**  
A: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save the project.

**T: Apakah memungkinkan menghapus tanggal berhenti setelah diatur?**  
**J:** Atur tanggal berhenti menjadi `null` dengan `ra.set(Asn.STOP, null);` lalu simpan proyek.

**Q: Does Aspose.Tasks support other date‑related fields like start, finish, or actual start?**  
A: Absolutely. The `Asn` enum provides constants for all assignment fields, such as `Asn.START`, `Asn.FINISH`, etc.

**T: Apakah Aspose.Tasks mendukung bidang terkait tanggal lain seperti start, finish, atau actual start?**  
**J:** Tentu saja. Enum `Asn` menyediakan konstanta untuk semua bidang penugasan, seperti `Asn.START`, `Asn.FINISH`, dll.

## Conclusion
Dengan mengikuti langkah‑langkah ini Anda kini mengetahui **cara menghentikan penugasan**, memeriksa tanggal berhenti/melanjutkan, dan melanjutkan penugasan bila diperlukan. Kemampuan ini memungkinkan Anda **mengelola penugasan sumber daya** dengan lebih tepat, terutama dalam skenario seperti cuti sumber daya atau downtime peralatan. Jangan ragu untuk memperluas contoh ini untuk memperbarui tanggal, menghasilkan laporan, atau mengintegrasikannya dengan logika penjadwalan Anda sendiri.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}