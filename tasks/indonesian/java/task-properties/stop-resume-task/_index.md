---
title: Hentikan dan Lanjutkan Tugas di Aspose.Tasks
linktitle: Hentikan dan Lanjutkan Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi kecanggihan Aspose.Tasks untuk Java dengan panduan langkah demi langkah kami dalam menghentikan dan melanjutkan tugas. Tingkatkan manajemen proyek dengan lancar!
weight: 30
url: /id/java/task-properties/stop-resume-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hentikan dan Lanjutkan Tugas di Aspose.Tasks

## Perkenalan
Dalam bidang pengembangan Java, mengelola tugas secara efisien merupakan aspek penting dalam pelaksanaan proyek. Aspose.Tasks untuk Java memberikan solusi tangguh untuk menangani tugas dengan fitur-fitur canggihnya. Dalam tutorial ini, kita akan mempelajari satu fungsi spesifik - menghentikan dan melanjutkan tugas. Dengan mengikuti panduan langkah demi langkah ini, Anda akan dapat mengintegrasikan fitur ini dengan lancar ke dalam proyek Java Anda.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar pemrograman Java.
- Menginstal Java Development Kit (JDK) di sistem Anda.
- Aspose.Tasks untuk perpustakaan Java diunduh dan ditambahkan ke proyek Anda. Anda bisa mendapatkannya dari[Di Sini](https://releases.aspose.com/tasks/java/).
## Paket Impor
Untuk memulai prosesnya, pastikan untuk mengimpor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## Langkah 1: Inisialisasi
 Mulailah dengan menginisialisasi proyek Anda dan membuat`ChildTasksCollector` misalnya untuk mengumpulkan semua tugas.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Langkah 2: Tetapkan Tanggal Minimum
Tentukan tanggal minimum untuk memfilter tugas yang perlu dihentikan atau dilanjutkan.
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## Langkah 3: Hentikan dan Lanjutkan Tugas
Ulangi tugas, periksa dan cetak tanggal berhenti dan melanjutkan.
```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```
Ulangi langkah-langkah ini di proyek Java Anda untuk mengintegrasikan fungsionalitas berhenti dan melanjutkan dengan lancar menggunakan Aspose.Tasks untuk Java.
## Kesimpulan
Dalam tutorial ini, kita menjelajahi proses menghentikan dan melanjutkan tugas menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat meningkatkan kemampuan manajemen proyek dan menyederhanakan pelaksanaan tugas.
## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Tasks untuk Java cocok untuk proyek skala besar?
Sangat! Aspose.Tasks untuk Java dirancang untuk menangani proyek dengan berbagai ukuran, memastikan efisiensi dan keandalan.
### Bisakah saya menyesuaikan tanggal untuk menghentikan dan melanjutkan tugas?
Ya, contoh yang diberikan memungkinkan fleksibilitas dalam menetapkan tanggal minimum sesuai dengan kebutuhan proyek Anda.
### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks untuk Java?
 Mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi komunitas.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 Ya, Anda dapat mengakses[uji coba gratis](https://releases.aspose.com/) untuk menjelajahi fitur sebelum melakukan pembelian.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
