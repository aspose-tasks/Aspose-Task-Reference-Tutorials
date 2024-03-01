---
title: Manajemen Durasi Dasar Tugas di Aspose.Tasks
linktitle: Manajemen Durasi Dasar Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengelola garis dasar tugas secara efisien di MS Project menggunakan Aspose.Tasks untuk Java. Tutorial ini memandu Anda langkah demi langkah melalui proses tersebut.
type: docs
weight: 12
url: /id/java/task-baselines/task-baseline-duration/
---
## Perkenalan
Mengelola garis dasar tugas di MS Project sangat penting untuk perencanaan dan pelacakan proyek. Dalam tutorial ini, kita akan mempelajari cara mengelola durasi dasar tugas secara efektif menggunakan Aspose.Tasks untuk Java.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java Development Kit (JDK) di sistem Anda.
2.  Perpustakaan Aspose.Tasks: Unduh dan instal perpustakaan Aspose.Tasks untuk Java dari[Di Sini](https://releases.aspose.com/tasks/java/).

## Paket Impor
Pertama, impor paket yang diperlukan untuk proyek Java Anda:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Langkah 1: Buat Instans Proyek
Inisialisasi instance proyek baru menggunakan kode berikut:
```java
Project project = new Project();
```
## Langkah 2: Buat Dasar Tugas
Buat tugas baru dan tetapkan garis dasarnya menggunakan kode berikut:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Langkah 3: Tampilkan Informasi Dasar Tugas
Ambil dan tampilkan informasi dasar tugas seperti durasi, tanggal mulai, tanggal selesai, dan lainnya:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Langkah 4: Periksa Baseline Interim dan Biaya Tetap
Periksa apakah baseline merupakan baseline sementara dan ambil biaya tetap yang terkait dengannya:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Langkah 5: Cetak Data Bertahap Waktu
Cetak data bertahap waktu yang terkait dengan garis besar tugas:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Dengan mengikuti langkah-langkah ini, Anda dapat secara efektif mengelola durasi dasar tugas di MS Project menggunakan Aspose.Tasks untuk Java.

## Kesimpulan
Mengelola garis dasar tugas sangat penting untuk manajemen proyek, memungkinkan Anda melacak penyimpangan dari jadwal yang direncanakan. Dengan Aspose.Tasks untuk Java, proses ini menjadi efisien dan efisien, memungkinkan kontrol dan penyampaian proyek yang lebih baik.
## FAQ
### Apa yang dimaksud dengan dasar tugas di MS Project?
Garis dasar tugas di MS Project adalah gambaran jadwal awal yang direncanakan untuk suatu tugas, termasuk tanggal mulai, tanggal selesai, dan durasi.
### Mengapa mengelola garis dasar tugas itu penting?
Mengelola garis dasar tugas membantu membandingkan jadwal yang direncanakan dengan kemajuan proyek yang sebenarnya, memfasilitasi pelacakan dan pengambilan keputusan yang lebih baik.
### Bisakah saya mengubah dasar tugas setelah ditetapkan?
Ya, Anda dapat mengubah garis dasar tugas di MS Project untuk mencerminkan perubahan dalam rencana proyek. Namun, penting untuk mendokumentasikan setiap penyimpangan dari garis dasar aslinya.
### Apakah Aspose.Tasks mendukung fungsi manajemen proyek lainnya?
Ya, Aspose.Tasks menawarkan berbagai fitur untuk manajemen proyek, termasuk penjadwalan tugas, alokasi sumber daya, dan pembuatan bagan Gantt.
### Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?
 Anda dapat menemukan dukungan untuk Aspose.Tasks di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15), tempat Anda dapat mengajukan pertanyaan dan berinteraksi dengan pengguna lain.