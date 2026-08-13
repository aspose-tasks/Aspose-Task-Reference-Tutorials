---
date: 2026-08-13
description: Pelajari cara menambahkan hari libur ke kalender, menetapkan kalender
  ke proyek, dan menyimpan file MS Project sebagai MPP menggunakan Aspose.Tasks untuk
  Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Perbarui kalender ke format MPP di Aspose.Tasks
og_description: Tambahkan hari libur ke kalender, tetapkan ke proyek, dan konversi
  jadwal ke MPP menggunakan Aspose.Tasks untuk Java. Pelajari otomatisasi langkah
  demi langkah.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Tambahkan hari libur ke kalender dan simpan sebagai MPP dengan Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Tambahkan hari libur ke kalender dan simpan sebagai MPP dengan Aspose.Tasks
url: /id/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan hari libur ke kalender dan simpan sebagai MPP dengan Aspose.Tasks

## Pendahuluan

Pada manajemen proyek modern Anda sering perlu **menambahkan hari libur ke kalender** file, membuat **kalender MS Project**, dan kemudian membagikan jadwal dalam format MPP asli. Baik Anda mengkonsolidasikan timeline dari berbagai sumber atau memigrasikan data lama, menghasilkan kalender secara programatik menghilangkan kesalahan manual dan mempercepat penyampaian. Tutorial ini memandu Anda melalui proses lengkap membuat kalender di MS Project, menyesuaikannya dengan hari libur, **menetapkan kalender ke proyek**, dan akhirnya **mengonversi proyek ke MPP** menggunakan Aspose.Tasks Java API.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menambahkan hari libur ke kalender, menetapkannya ke proyek, dan menyimpan hasilnya sebagai file MPP dengan Aspose.Tasks untuk Java.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Versi Java apa yang diperlukan?** Java 8 atau lebih tinggi (JDK 8+).  
- **Bisakah saya menyesuaikan kalender?** Ya – Anda dapat menambahkan jam kerja, pengecualian, dan hari libur.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk kalender dasar.  

## Apa itu “create calendar MS Project”?

Membuat kalender MS Project berarti mendefinisikan hari kerja, jam kerja, dan pengecualian yang mengatur penjadwalan tugas dalam file Microsoft Project. Dengan menggunakan Aspose.Tasks Anda dapat membangun kalender ini secara programatik, menetapkan hari libur, dan menyematkannya ke dalam proyek tanpa membuka UI MS Project.

## Mengapa menggunakan Aspose.Tasks untuk tugas ini?

Anda harus menggunakan Aspose.Tasks karena menyediakan kompatibilitas penuh dengan Java, tidak memerlukan Microsoft Office, dan memungkinkan Anda menghasilkan serta menyimpan file MPP asli langsung dari kode. Perpustakaan ini mendukung semua fitur kalender, berfungsi di lingkungan server apa pun, dan memproses proyek hingga 10.000 tugas dalam waktu kurang dari satu detik.

## Prasyarat

1. **Java Development Kit (JDK) 8+** – pastikan `java -version` menampilkan 1.8 atau lebih baru.  
2. **Aspose.Tasks for Java** – unduh JAR terbaru dari [situs Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, atau editor apa pun yang Anda sukai.  
4. **Pengetahuan dasar Java** – familiaritas dengan kelas, metode, dan I/O file.

## Cara menambahkan hari libur ke kalender

Untuk menambahkan hari libur, Anda membuat objek `Calendar` baru, mengambil koleksi `Exceptions`‑nya, dan menambahkan entri `DateException` untuk setiap tanggal hari libur. `DateException` mewakili satu tanggal atau rentang non‑kerja dalam kalender. Aspose.Tasks kemudian memperlakukan tanggal tersebut sebagai hari non‑kerja, memastikan tugas dijadwalkan di sekitar hari libur yang telah ditentukan.

### Langkah 1: impor paket yang diperlukan

Pertama, bawa kelas Aspose.Tasks dan utilitas Java ke dalam ruang lingkup.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Langkah 2: siapkan direktori data

Tentukan lokasi template input dan file output Anda. Ganti placeholder dengan jalur sebenarnya di mesin Anda.

```java
String dataDir = "Your Data Directory";
```

### Langkah 3: tentukan nama file input dan output

Kami akan memuat file MPP yang ada (atau proyek kosong) dan menulis hasilnya ke file baru.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Langkah 4: muat proyek dan tambahkan kalender baru

Kelas `Project` mewakili file MS Project dalam memori dan menyediakan akses ke kalender, tugas, dan sumber dayanya.

Buat instance `Project` dari file sumber dan tambahkan kalender bernama **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Langkah 5: sesuaikan kalender (opsional)

Objek `Calendar` mendefinisikan hari kerja, jam kerja, dan pengecualian untuk jadwal proyek.

Jika Anda memerlukan jam kerja khusus, hari libur, atau pengecualian, panggil metode pembantu Anda sendiri. Contoh ini menggunakan `GetTestCalendar` sebagai placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Anda dapat langsung memanipulasi `cal1.getWeekDays()` untuk mengatur jam kerja untuk setiap **hari** dalam seminggu, atau gunakan `cal1.getExceptions()` untuk **menambahkan hari libur ke kalender**.

### Langkah 6: tetapkan kalender ke proyek

Beritahu proyek untuk menggunakan kalender yang baru dibuat untuk semua perhitungan penjadwalannya.

```java
project.set(Prj.CALENDAR, cal1);
```

### Langkah 7: simpan proyek sebagai MPP

Enumerasi `SaveFileFormat` menentukan format output, dengan `Mpp` menunjukkan format Microsoft Project asli.

Sekarang **konversi proyek ke MPP** dengan menyimpannya menggunakan opsi `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Langkah 8: konfirmasi penyelesaian berhasil

Pesan konsol sederhana memberi tahu Anda bahwa proses selesai tanpa error.

```java
System.out.println("Process completed Successfully");
```

## Kasus penggunaan umum

- **Pembuatan jadwal otomatis** untuk proyek berulang (mis., sprint mingguan).  
- **Migrasi kalender CSV atau Excel lama** ke dalam file MS Project yang lengkap.  
- **Pelaporan sisi server** di mana layanan web mengembalikan file MPP sesuai permintaan.  

## Pemecahan Masalah & jebakan umum

| Masalah | Penyebab | Solusi |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` mengarah ke folder yang tidak ada | Pastikan direktori ada atau buat secara programatik. |
| Calendar not applied to tasks | Tasks still reference the default calendar | After setting `Prj.CALENDAR`, also update each task’s `Task.CALENDAR` if they were previously overridden. |
| Output file is 0 KB | Missing write permissions | Run the JVM with appropriate file system rights or choose a writable path. |

## Pertanyaan yang Sering Diajukan

**Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai versi MS Project?**  
A: Ya, Aspose.Tasks mendukung semua format file Microsoft Project dari Project 2007 hingga Project 2024, mencakup lebih dari 10 versi.

**Q: Bisakah saya menyesuaikan kalender sesuai dengan kebutuhan proyek tertentu?**  
A: Tentu saja. Anda dapat mendefinisikan hari kerja, mengatur minggu kerja khusus, menambahkan hari libur, dan bahkan membuat beberapa kalender dalam satu file proyek.

**Q: Apakah Aspose.Tasks untuk Java menawarkan dukungan untuk pemecahan masalah dan bantuan?**  
A: Ya, Anda dapat mendapatkan bantuan dari forum komunitas Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Apakah tersedia percobaan gratis untuk Aspose.Tasks untuk Java?**  
A: Ya, percobaan gratis yang berfungsi penuh tersedia [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk Aspose.Tasks untuk Java?**  
A: Lisensi sementara dapat diminta melalui situs Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

**Terakhir Diperbarui:** 2026-08-13  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Tambahkan kalender ke proyek dengan Aspose.Tasks untuk Java](/tasks/java/calendars/create/)
- [Cara Mendefinisikan Hari Kerja dalam Kalender MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Buat Pengecualian Kalender Kustom dengan Aspose.Tasks untuk Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}