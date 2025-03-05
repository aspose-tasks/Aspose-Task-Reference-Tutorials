---
title: Kelola Tugas Kritis dan Berbasis Upaya di Aspose.Tasks
linktitle: Kelola Tugas Kritis dan Berbasis Upaya di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Kelola tugas-tugas penting dan berbasis upaya dengan mudah di proyek Java Anda dengan Aspose.Tasks. Unduh perpustakaan dan tingkatkan kemampuan manajemen proyek Anda.
type: docs
weight: 14
url: /id/java/task-properties/critical-effort-driven-tasks/
---
Dalam dunia manajemen proyek yang bergerak cepat, penanganan tugas-tugas penting dan berbasis upaya secara efisien sangat penting untuk keberhasilan penyelesaian proyek. Aspose.Tasks untuk Java memberikan solusi tangguh untuk mengelola tugas-tugas ini dengan lancar. Dalam tutorial ini, kami akan memandu Anda melalui proses penggunaan Aspose.Tasks untuk Java untuk menangani tugas-tugas penting dan berbasis upaya dalam proyek Anda.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Aspose.Tugas untuk Perpustakaan Java: Unduh dan instal perpustakaan dari[Aspose.Tasks untuk dokumentasi Java](https://reference.aspose.com/tasks/java/).
- Java Development Kit (JDK): Pastikan Anda telah menginstal Java di sistem Anda.
- Lingkungan Pengembangan Terpadu (IDE): Gunakan IDE pilihan Anda untuk pengembangan Java.
- File Proyek: Siapkan file proyek dalam format XML yang akan Anda gunakan untuk demonstrasi.
## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk memanfaatkan fungsionalitas Aspose.Tasks untuk Java:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```
Sekarang, mari kita uraikan setiap langkah menjadi panduan komprehensif:
## Langkah 1: Kumpulkan Tugas Menggunakan ChildTasksCollector
 Membuat`ChildTasksCollector` contoh untuk mengumpulkan semua tugas dari tugas root menggunakan`TaskUtils.apply`. Hal ini memastikan Anda memiliki akses ke semua tugas dalam proyek.
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Buat instans ChildTasksCollector
ChildTasksCollector collector = new ChildTasksCollector();
// Kumpulkan semua tugas dari RootTask menggunakan TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Langkah 2: Ulangi Tugas yang Dikumpulkan
 Parsing semua tugas yang dikumpulkan menggunakan a`for` lingkaran. Untuk setiap tugas, tentukan apakah tugas tersebut didorong oleh upaya dan penting, dengan mencetak status masing-masing.
```java
// Parsing semua tugas yang dikumpulkan
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```
Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif mengelola tugas-tugas penting dan berbasis upaya dalam proyek Anda menggunakan Aspose.Tasks untuk Java.
## Kesimpulan
Kesimpulannya, Aspose.Tasks untuk Java memberdayakan pengembang Java untuk secara efisien mengelola tugas-tugas penting dan didorong oleh upaya dalam manajemen proyek. Dengan fitur-fiturnya yang mudah digunakan dan fungsionalitas yang tangguh, menangani skenario proyek yang kompleks menjadi sangat mudah.
## Pertanyaan yang Sering Diajukan
### T: Bisakah saya menggunakan Aspose.Tasks untuk Java di lingkungan Windows dan Linux?
Ya, Aspose.Tasks untuk Java tidak bergantung pada platform dan dapat digunakan di lingkungan Windows dan Linux.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 Ya, Anda dapat mengakses uji coba gratis Aspose.Tasks untuk Java[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk Java?
 Mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi komunitas.
### T: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 Anda dapat memperoleh lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat membeli Aspose.Tasks untuk Java?
 Anda dapat membeli Aspose.Tasks untuk Java dari[halaman pembelian](https://purchase.aspose.com/buy).