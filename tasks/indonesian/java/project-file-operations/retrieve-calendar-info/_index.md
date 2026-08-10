---
date: 2026-03-27
description: Pelajari cara menggunakan Aspose dan Aspose.Tasks untuk mengekstrak detail
  kalender proyek dari file Microsoft Project menggunakan Java. Panduan langkah demi
  langkah dengan contoh kode.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menggunakan Aspose.Tasks untuk Mengambil Info Kalender MS Project
url: /id/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggunakan Aspose.Tasks untuk Mengambil Info Kalender MS Project

## Introduction
Dalam tutorial ini, **Anda akan menemukan cara menggunakan Aspose.Tasks** untuk secara programatis mengambil informasi kalender dari file Microsoft Project. Mengakses data kalender seperti hari kerja, jam kerja, dan pengecualian sangat penting ketika Anda perlu **mengekstrak kalender proyek** untuk pelaporan, integrasi, atau logika penjadwalan khusus. Mari kita jalani prosesnya langkah demi langkah, dan Anda akan melihat **cara menggunakan Aspose** untuk menarik data ini dari file *.mpp*.

## Quick Answers
- **Perpustakaan apa yang digunakan tutorial ini?** Aspose.Tasks for Java.  
- **Kata kunci utama apa yang dibahas?** *how to use aspose*.  
- **Apa yang dapat Anda ekstrak?** Kalender proyek, termasuk hari kerja dan jam kerja.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Java 8 atau lebih tinggi.

## What is Aspose.Tasks and Why Use It?
Aspose.Tasks adalah API Java yang kuat yang memungkinkan pengembang membaca, menulis, dan memanipulasi file Microsoft Project tanpa memerlukan Microsoft Project itu sendiri. Dengan menggunakan Aspose.Tasks Anda dapat **mengekstrak informasi kalender**, mengotomatiskan perhitungan jadwal, dan mengintegrasikan data proyek dengan sistem perusahaan lain—semua dari kode Java murni.

## Why extract project calendar information?
Kalender proyek mengatur tanggal tugas, alokasi sumber daya, dan perhitungan timeline keseluruhan. Dengan mengekstrak data ini Anda dapat:
- Membuat laporan khusus yang mencerminkan jadwal kerja sebenarnya.  
- Sinkronkan timeline Microsoft Project dengan sistem eksternal (ERP, BI, dll.).  
- Lakukan analisis what‑if dengan memodifikasi pengaturan kalender secara programatis.  
- **Ekstrak data kalender MS Project** untuk migrasi ke alat perencanaan lain.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki:

- Pengetahuan dasar pemrograman Java.  
- Java Development Kit (JDK) terinstal di sistem Anda.  
- Perpustakaan Aspose.Tasks for Java. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/tasks/java/).

## Import Packages
Pertama, impor kelas Aspose.Tasks yang diperlukan ke dalam proyek Java Anda.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Step 1: Set Data Directory
Tentukan folder yang berisi file *.mpp* Anda.

```java
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan path absolut ke folder tempat **project.mpp** berada.

## Step 2: Define Time Units
Buat konstanta yang membantu mengonversi representasi waktu internal menjadi jam yang dapat dibaca manusia.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Nilai-nilai ini diekspresikan dalam mikrodetik, yang merupakan cara Aspose.Tasks menyimpan waktu secara internal.

## Step 3: Create Project Instance
Muat file Microsoft Project ke dalam objek `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Konstruktor `Project` mem-parsing file *.mpp* dan membuat semua data proyek, termasuk kalender, dapat diakses melalui API.

## Step 4: Retrieve Calendars Information
Dapatkan koleksi kalender yang didefinisikan dalam proyek.

```java
CalendarCollection alCals = project.getCalendars();
```

Sebuah proyek dapat berisi banyak kalender (standar, sumber daya, dan kalender khusus). Koleksi ini memberi Anda akses ke masing‑masingnya.

## Step 5: Iterate Through Calendars
Loop melalui setiap kalender, tampilkan UID, nama, dan hari kerja beserta jam kerja yang bersesuaian.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Loop dalam memeriksa setiap objek `WeekDay`. Jika hari tersebut ditandai sebagai hari kerja, ia mencetak tipe hari (Monday, Tuesday, …) bersama dengan jam kerja yang dihitung.

## Step 6: Display Completion Message
Berikan sinyal bahwa proses ekstraksi telah selesai.

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Tidak ada kalender yang dikembalikan** | File proyek mungkin tidak berisi kalender khusus apa pun. | Verifikasi bahwa *.mpp* benar‑benar mendefinisikan kalender atau buka di Microsoft Project untuk memastikan. |
| **Jam kerja tidak tepat** | Konstanta konversi waktu tidak cocok untuk versi Project yang berbeda. | Sesuaikan `OneSec`, `OneMin`, `OneHour` jika Anda menggunakan versi Aspose.Tasks yang lebih baru yang mengubah satuan waktu internal. |
| **`NullPointerException` pada `cal.getName()`** | Beberapa objek kalender mungkin bernilai null. | Tambahkan pengecekan null sebelum mengakses properti (sudah ditunjukkan). |

## Frequently Asked Questions

**Q: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
A: Ya, Aspose.Tasks mendukung banyak platform dan bahasa pemrograman, termasuk .NET, C++, Python, dan Java.

**Q: Apakah ada versi percobaan gratis untuk Aspose.Tasks?**  
A: Ya, Anda dapat mengunduh versi percobaan gratis dari [here](https://releases.aspose.com/).

**Q: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks?**  
A: Anda dapat mendapatkan dukungan dari forum komunitas Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Bisakah saya membeli lisensi sementara untuk Aspose.Tasks?**  
A: Ya, lisensi sementara tersedia untuk dibeli [here](https://purchase.aspose.com/temporary-license/).

**Q: Di mana saya dapat menemukan dokumentasi detail untuk Aspose.Tasks?**  
A: Anda dapat merujuk ke dokumentasi [here](https://reference.aspose.com/tasks/java/).

## Conclusion
Dengan mengikuti langkah‑langkah ini, **Anda kini tahu cara menggunakan Aspose.Tasks untuk mengekstrak kalender proyek** dari file MS Project menggunakan Java. Anda dapat mengintegrasikan logika ini ke dalam aplikasi yang lebih besar, mengotomatiskan pelaporan, atau menyinkronkan jadwal dengan sistem perusahaan lain. Ingat, menguasai **cara menggunakan aspose** membuka pintu ke banyak skenario otomatisasi manajemen proyek tingkat lanjut.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}