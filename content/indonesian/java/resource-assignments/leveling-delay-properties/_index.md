---
title: Menangani Properti Penundaan Leveling di Aspose.Tasks
linktitle: Menangani Properti Penundaan Leveling untuk Penetapan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menangani properti penundaan leveling untuk penetapan sumber daya di Aspose.Tasks untuk Java dengan tutorial komprehensif ini.
type: docs
weight: 17
url: /id/java/resource-assignments/leveling-delay-properties/
---
## Perkenalan
Dalam tutorial ini, kita akan memandu proses penanganan properti penundaan leveling untuk penetapan sumber daya di Aspose.Tasks untuk Java. Aspose.Tasks adalah perpustakaan Java yang kuat yang memungkinkan Anda bekerja dengan file Microsoft Project tanpa memerlukan Microsoft Project untuk diinstal pada sistem Anda.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal Java JDK di sistem Anda. Anda dapat mengunduh dan menginstalnya dari[situs web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks untuk Perpustakaan Java: Unduh perpustakaan Aspose.Tasks untuk Java dari[Unduh Halaman](https://releases.aspose.com/tasks/java/).

## Paket Impor
Pertama, impor paket yang diperlukan ke proyek Java Anda untuk menggunakan fungsionalitas Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Langkah 1: Buat Objek Proyek
 Buat contoh a`Project` obyek:
```java
Project prj = new Project();
```
## Langkah 2: Buat Tugas
Tambahkan tugas ke proyek:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Langkah 3: Tetapkan Tanggal dan Durasi Mulai Tugas
Tetapkan tanggal mulai dan durasi tugas:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Langkah 4: Tambahkan Sumber Daya
Tambahkan sumber daya ke proyek:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Langkah 5: Buat Penugasan Sumber Daya
Buat penetapan sumber daya untuk tugas dan sumber daya:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Langkah 6: Atur Penundaan Leveling
Tetapkan penundaan leveling untuk tugas:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Langkah 7: Tampilkan Hasil
Cetak penundaan leveling dan informasi relevan lainnya:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menangani properti penundaan leveling untuk penetapan sumber daya di Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat mengelola penetapan sumber daya di proyek Java Anda secara efisien.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Tasks dengan pustaka Java lainnya?

J: Ya, Aspose.Tasks dapat diintegrasikan dengan perpustakaan Java lainnya untuk meningkatkan kemampuan manajemen proyek.

### T: Apakah Aspose.Tasks kompatibel dengan versi file Microsoft Project yang berbeda?

J: Ya, Aspose.Tasks mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.

### T: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks?

 J: Anda dapat menemukan dukungan dan sumber daya di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).

### T: Dapatkah saya mencoba Aspose.Tasks sebelum membeli?

 J: Ya, Anda bisa mendapatkan uji coba gratis Aspose.Tasks dari[halaman rilis](https://releases.aspose.com/).

### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?

 J: Anda dapat meminta lisensi sementara dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.