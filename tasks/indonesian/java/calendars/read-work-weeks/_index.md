---
date: 2026-02-05
description: Pelajari cara membaca workweeks Java dari kalender Microsoft Project
  menggunakan Aspose.Tasks. Ikuti panduan langkah demi langkah dengan contoh kode
  lengkap.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Membaca Minggu Kerja Java dari Kalender MS Project dengan Aspose.Tasks
url: /id/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Workweeks Java dari Kalender MS Project Aspose.Tasks

## Introduction
Dalam tutorial ini Anda akan **mempelajari cara membaca workweeks Java** dari kalender Microsoft Project menggunakan pustaka Aspose.Tasks. Baik Anda sedang membangun alat pelaporan, menyinkronkan jadwal, atau mengotomatiskan ekstraksi data proyek, kemampuan untuk mengakses definisi work‑week secara programatik menghemat banyak jam kerja manual. Kami akan memandu Anda melalui penyiapan yang diperlukan, menunjukkan kode tepat untuk mengambil detail work‑week, dan menjelaskan setiap langkah sehingga Anda dapat menyesuaikan solusi ini untuk proyek Anda sendiri.

## Quick Answers
- **Apa arti “read workweeks java”?** Ini merujuk pada mengekstrak definisi work‑week dari file Project menggunakan kode Java.  
- **Pustaka apa yang dibutuhkan?** Aspose.Tasks for Java (tersedia versi percobaan gratis).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Versi percobaan dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Format file apa yang didukung?** Baik file *.mpp* maupun file Project XML dapat diproses.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit setelah pustaka terpasang.

## How to Read Workweeks Java from a Microsoft Project Calendar
Membaca work weeks dalam Java berarti menggunakan API Aspose.Tasks untuk mengakses `WorkWeekCollection` dari objek kalender di dalam file Microsoft Project. Setiap `WorkWeek` berisi tanggal mulai/berakhir serta definisi waktu kerja harian yang menentukan bagaimana sumber daya dijadwalkan.

## Why read workweeks Java from a Microsoft Project calendar?
- **Automasi:** Menghilangkan penyalinan manual data jadwal.  
- **Integrasi:** Menyalurkan informasi work‑week ke sistem ERP, HR, atau laporan khusus.  
- **Konsistensi:** Memastikan semua alat hilir menghormati aturan kalender yang sama yang didefinisikan dalam file Project.

## Prerequisites
Sebelum kita masuk ke kode, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru terpasang.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari situs resmi: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Sebuah **file Project contoh** (`ReadWorkWeeksInformation.mpp`) yang ditempatkan di folder yang diketahui.

## Import Packages
Pertama, impor kelas‑kelas yang diperlukan untuk berinteraksi dengan kalender dan work weeks:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Step 1: Set Up Your Data Directory
Tentukan folder yang berisi file `.mpp`. Ganti placeholder dengan jalur sebenarnya di mesin Anda:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Create a Project Instance and Access the Calendar
Buat objek `Project`, pilih kalender yang diinginkan (berdasarkan UID), dan dapatkan `WorkWeekCollection`‑nya:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Jika Anda tidak yakin dengan UID kalender, Anda dapat melakukan iterasi melalui `project.getCalendars()` dan mencetak nama serta UID setiap kalender.

## Step 3: Iterate Through Work Weeks
Lakukan loop pada setiap `WorkWeek` untuk menampilkan nama, tanggal mulai/berakhir, dan waktu kerja harian:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**What you’ll see:** Konsol akan mencetak label setiap work‑week (misalnya, “Standard”), rentang tanggal efektifnya, dan Anda dapat menelusuri jam kerja tepat untuk setiap hari.

## Common Issues and Solutions
| Masalah | Alasan | Solusi |
|---------|--------|--------|
| `NullPointerException` ketika mengakses `calendar` | UID salah atau kalender tidak ada | Verifikasi UID dengan `project.getCalendars().size()` dan daftar kalender yang tersedia terlebih dahulu. |
| Tidak ada output untuk work weeks | Kalender yang dipilih tidak memiliki work weeks khusus (menggunakan default) | Gunakan kalender default (`project.getDefaultCalendar()`) atau buat work week secara programatik. |
| Format tanggal terlihat aneh | `System.out.println` menggunakan format default `java.util.Date` | Terapkan `SimpleDateFormat` untuk memformat tanggal sesuai kebutuhan. |

## Frequently Asked Questions

**Q: Bisakah saya memodifikasi informasi work weeks menggunakan Aspose.Tasks for Java?**  
A: Ya. API menyediakan metode seperti `addWorkWeek()`, `removeWorkWeek()`, dan setter properti untuk mengubah nama, tanggal, serta waktu kerja.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?**  
A: Tentu saja. Ia mendukung file MPP mulai dari Project 98 hingga versi terbaru, serta file Project XML.

**Q: Dapatkah saya mengintegrasikan Aspose.Tasks dengan kerangka kerja Java lainnya?**  
A: Ya. Pustaka ini murni Java, sehingga dapat digunakan bersama Spring, Jakarta EE, atau kerangka kerja apa pun.

**Q: Apakah ada versi percobaan untuk Aspose.Tasks?**  
A: Ya, Anda dapat mengunduh percobaan gratis selama 30 hari dari situs resmi: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?**  
A: Forum komunitas Aspose adalah tempat terbaik: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Anda kini telah menguasai **cara membaca workweeks Java** menggunakan Aspose.Tasks. Dengan mengikuti langkah‑langkah di atas, Anda dapat secara programatik mengambil definisi work‑week dari kalender MS Project mana pun, mengintegrasikan data tersebut ke dalam aplikasi Anda, dan mengotomatiskan alur kerja yang terkait dengan jadwal. Jangan ragu untuk bereksperimen dengan membuat atau memperbarui work weeks—Aspose.Tasks membuatnya sangat mudah.

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}