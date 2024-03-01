---
title: Menguasai Properti Tugas di Aspose.Tasks
linktitle: Membaca dan Menulis Properti Umum Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi kekuatan Aspose.Tasks untuk Java dalam mengelola properti tugas dengan mudah. Membaca dan menulis dengan mudah menggunakan panduan langkah demi langkah kami.
type: docs
weight: 26
url: /id/java/task-properties/read-write-general-properties/
---
## Perkenalan
Buka potensi penuh manajemen tugas di Java dengan Aspose.Tasks. Dalam panduan komprehensif ini, kita akan mempelajari membaca dan menulis properti umum tugas menggunakan Aspose.Tasks untuk Java. Baik Anda seorang pengembang berpengalaman atau pemula, tutorial ini akan membekali Anda dengan keterampilan untuk memanipulasi properti tugas dengan mudah.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Tasks untuk perpustakaan Java diunduh dan disiapkan. Anda dapat menemukan tautan unduhan[Di Sini](https://releases.aspose.com/tasks/java/).
- Editor kode seperti IntelliJ IDEA atau Eclipse.
## Paket Impor
Untuk memulai, impor paket yang diperlukan dalam proyek Java Anda. Langkah ini memastikan bahwa Anda memiliki akses ke fungsi Aspose.Tasks. Berikut cuplikan untuk memandu Anda:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Membaca Sifat Umum Tugas
## Langkah 1: Buat Tugas
Mulailah dengan membuat tugas di proyek Anda. Ini melibatkan pengaturan nama tugas, tanggal mulai, dan detail relevan lainnya. Berikut ini contohnya:
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## Langkah 2: Baca Properti Tugas
Sekarang setelah Anda membuat tugas, mari ambil dan tampilkan properti umumnya. Cuplikan kode berikut dapat melakukan hal ini:
```java
// Membaca Sifat Umum Tugas
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## Menulis Sifat Umum Tugas
## Langkah 3: Muat Proyek dan Buat Kolektor
 Untuk menulis properti umum, muat proyek yang ada dan siapkan a`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## Langkah 4: Parsing dan Tampilkan Properti
Terakhir, parsing tugas yang dikumpulkan dan tampilkan propertinya:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
Selamat! Anda telah berhasil membaca dan menulis properti umum tugas menggunakan Aspose.Tasks untuk Java.
## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi langkah-langkah mendasar untuk memanipulasi properti tugas secara lancar dengan Aspose.Tasks untuk Java. Dengan menguasai teknik-teknik ini, Anda dapat meningkatkan keterampilan pengembangan Java dan menyederhanakan manajemen tugas dalam proyek Anda.
## FAQ
### Apakah Aspose.Tasks kompatibel dengan Java 11?
Ya, Aspose.Tasks kompatibel dengan Java 11 dan versi yang lebih baru.
### Bisakah saya menggunakan Aspose.Tasks untuk proyek komersial?
 Sangat! Aspose.Tasks adalah alat yang ampuh untuk proyek pribadi dan komersial. Mengunjungi[Di Sini](https://purchase.aspose.com/buy) untuk mengeksplorasi opsi lisensi.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk tujuan pengujian?
 Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk pengujian dan evaluasi.
### Di mana saya dapat menemukan dukungan komunitas untuk Aspose.Tasks?
 Bergabunglah dengan diskusi komunitas di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk bantuan dan kerjasama.
### Apakah ada contoh proyek yang tersedia untuk referensi?
 Jelajahi bagian contoh dokumentasi[Di Sini](https://reference.aspose.com/tasks/java/) untuk contoh proyek dan cuplikan kode.