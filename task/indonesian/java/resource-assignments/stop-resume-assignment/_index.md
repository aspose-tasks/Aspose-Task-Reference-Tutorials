---
title: Hentikan dan Lanjutkan Penugasan Sumber Daya di Aspose.Tasks
linktitle: Hentikan dan Lanjutkan Penugasan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengelola penetapan sumber daya secara efektif di Aspose.Tasks untuk Java dengan tutorial langkah demi langkah ini.
type: docs
weight: 23
url: /id/java/resource-assignments/stop-resume-assignment/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menghentikan dan melanjutkan penetapan sumber daya menggunakan Aspose.Tasks untuk Java. Aspose.Tasks adalah Java API canggih yang memungkinkan pengembang bekerja dengan file Microsoft Project tanpa perlu menginstal Microsoft Project di sistem mereka. Kami akan membagi prosesnya menjadi langkah-langkah yang dapat dikelola agar mudah diikuti.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Tugas untuk perpustakaan Java diunduh. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
- Pemahaman dasar pemrograman Java.
## Paket Impor
Pertama, mari impor paket yang diperlukan ke proyek Java kita:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Langkah 1: Muat File Proyek
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
// Muat file proyek
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 Pada langkah ini, kami memuat file proyek ke a`Project` objek menggunakan jalur file.
## Langkah 2: Ulangi Melalui Penugasan Sumber Daya
```java
// Tentukan tanggal minimum
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterasi melalui penetapan sumber daya
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Di sini, kami menentukan tanggal minimum dan mulai mengulangi setiap penetapan sumber daya dalam proyek.
## Langkah 3: Periksa Tanggal Berhenti dan Lanjutkan
```java
    // Periksa tanggal berhenti
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Periksa tanggal resume
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
Pada langkah ini, kami memeriksa apakah tanggal berhenti dan melanjutkan setiap penetapan sumber daya sebelum tanggal minimum. Jika ya, kami mencetak "NA", jika tidak, kami mencetak tanggalnya masing-masing.
## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menghentikan dan melanjutkan penetapan sumber daya di Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah mengimplementasikan fungsi ini di proyek Java Anda.

## FAQ
### Bisakah saya menggunakan Aspose.Tasks tanpa menginstal Microsoft Project?
Ya, Aspose.Tasks memungkinkan Anda bekerja dengan file Microsoft Project tanpa perlu menginstal Microsoft Project di sistem Anda.
### Di mana saya dapat menemukan dokumentasi lainnya?
 Anda dapat menemukan dokumentasi terperinci[Di Sini](https://reference.aspose.com/tasks/java/).
### Apakah ada uji coba gratis yang tersedia?
 Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).
### Bagaimana saya bisa mendapatkan dukungan jika saya menemui masalah?
Anda bisa mendapatkan dukungan dari komunitas[Di Sini](https://forum.aspose.com/c/tasks/15).
### Bisakah saya membeli lisensi sementara?
 Ya, Anda dapat membeli lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).