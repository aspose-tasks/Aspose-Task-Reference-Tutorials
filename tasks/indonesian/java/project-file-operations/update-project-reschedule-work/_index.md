---
title: Perbarui & Jadwalkan Ulang Proyek MS di Aspose.Tasks
linktitle: Perbarui Proyek dan Jadwalkan Ulang Pekerjaan yang Belum Selesai di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara memperbarui dan menjadwal ulang file MS Project secara terprogram menggunakan Aspose.Tasks untuk Java.
weight: 23
url: /id/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Perbarui & Jadwalkan Ulang Proyek MS di Aspose.Tasks

## Perkenalan
Microsoft Project adalah perangkat lunak manajemen proyek yang banyak digunakan yang memungkinkan pengguna mengelola tugas, sumber daya, dan jadwal secara efisien. Aspose.Tasks untuk Java menyediakan serangkaian API yang kuat untuk memanipulasi file Microsoft Project secara terprogram. Dalam tutorial ini, kita akan mempelajari cara memperbarui file MS Project dan menjadwal ulang pekerjaan yang belum selesai menggunakan Aspose.Tasks untuk Java.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Aspose.Tugas untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Pemahaman dasar bahasa pemrograman Java.

## Paket Impor
Pertama, impor paket yang diperlukan dalam kode Java Anda:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Langkah 1: Siapkan Proyek
Inisialisasi objek Proyek baru dan tentukan tugas di dalamnya beserta durasi dan ketergantungannya.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Tentukan tugas dan durasinya
// ...
// Tentukan dependensi tugas
// ...
// Simpan status proyek awal
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Langkah 2: Perbarui Pekerjaan Proyek
Perbarui pekerjaan proyek untuk menandainya selesai hingga tanggal tertentu.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Simpan proyek yang diperbarui
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Langkah 3: Jadwalkan Ulang Pekerjaan yang Belum Selesai
Jadwalkan ulang pekerjaan yang belum selesai untuk dimulai setelah tanggal yang ditentukan.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Simpan proyek yang dijadwalkan ulang
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara memperbarui file MS Project dan menjadwal ulang pekerjaan yang belum selesai menggunakan Aspose.Tasks untuk Java. Hal ini sangat berguna dalam skenario di mana jadwal proyek memerlukan penyesuaian berdasarkan kemajuan atau perubahan prioritas.

## FAQ
### T: Dapatkah Aspose.Tasks untuk Java menangani struktur proyek yang kompleks?
J: Ya, Aspose.Tasks untuk Java menyediakan API yang kuat untuk mengelola tugas, dependensi, sumber daya, dan elemen proyek lainnya secara efisien.
### T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
 A: Ya, Anda bisa mendapatkan uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks untuk Java?
 A: Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun.
### T: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?
 J: Ya, lisensi sementara tersedia untuk dibeli[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks untuk Java?
 A: Anda dapat merujuk ke dokumentasinya[Di Sini](https://reference.aspose.com/tasks/java/) untuk panduan komprehensif dan referensi API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
