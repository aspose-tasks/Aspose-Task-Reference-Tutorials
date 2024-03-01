---
title: Hasilkan Data Fase Waktu di Aspose.Tasks
linktitle: Hasilkan Data Bertahap Waktu untuk Penugasan Sumber Daya di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menghasilkan data bertahap waktu untuk penetapan sumber daya menggunakan Aspose.Tasks untuk Java. Tingkatkan efisiensi manajemen proyek dengan panduan komprehensif ini.
type: docs
weight: 24
url: /id/java/resource-assignments/timephased-data-generation/
---
## Perkenalan
Dalam tutorial ini, kita akan memandu proses pembuatan data bertahap waktu untuk penetapan sumber daya menggunakan Aspose.Tasks untuk Java. Data bertahap memberikan wawasan berharga tentang bagaimana sumber daya dialokasikan dari waktu ke waktu dalam suatu proyek, membantu manajer proyek membuat keputusan yang tepat.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduh dan menginstal JDK dari[Di Sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Tasks untuk Perpustakaan Java: Anda harus memiliki perpustakaan Aspose.Tasks untuk Java. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/tasks/java/).

## Paket Impor
Pertama, mari impor paket yang diperlukan untuk bekerja dengan Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Langkah 1: Baca File MPP Sumber
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
// Baca file MPP sumber
Project project = new Project(dataDir + "project.mpp");
```
## Langkah 2: Dapatkan Penugasan Tugas dan Sumber Daya
```java
// Dapatkan tugas pertama Proyek
Task task = project.getRootTask().getChildren().getById(1);
// Dapatkan penetapan sumber daya pertama proyek
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Langkah 3: Hasilkan Data Berfase Waktu dengan Kontur Datar
```java
// Kontur datar adalah kontur default
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Langkah 4: Ubah Kontur menjadi Turtle
```java
// Ubah kontur menjadi Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Langkah 5: Ubah Kontur menjadi BackLoaded
```java
// Ubah kontur menjadi BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Langkah 6: Ubah Kontur menjadi FrontLoaded
```java
// Ubah kontur menjadi FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Langkah 7: Ubah Kontur menjadi Lonceng
```java
// Ubah kontur menjadi Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Langkah 8: Ubah Kontur ke EarlyPeak
```java
// Ubah kontur menjadi EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Langkah 9: Ubah Kontur menjadi LatePeak
```java
// Ubah kontur menjadi LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Langkah 10: Ubah Kontur menjadi DoublePeak
```java
// Ubah kontur menjadi DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Kesimpulan
Dalam tutorial ini, kami telah membahas cara menghasilkan data bertahap waktu untuk penetapan sumber daya menggunakan Aspose.Tasks untuk Java. Memahami kontur kerja yang berbeda dapat membantu manajer proyek secara efektif mengelola alokasi sumber daya dan penjadwalan dalam proyek mereka.
## FAQ
### Bisakah saya menggunakan Aspose.Tasks dengan perpustakaan Java lainnya?
Ya, Aspose.Tasks dapat diintegrasikan dengan perpustakaan Java lainnya untuk meningkatkan kemampuan manajemen proyek.
### Apakah Aspose.Tasks cocok untuk proyek perusahaan skala besar?
Tentu saja, Aspose.Tasks dirancang untuk menangani proyek dari semua ukuran, termasuk proyek perusahaan skala besar.
### Apakah Aspose.Tasks menyediakan dukungan untuk format file proyek yang berbeda?
Ya, Aspose.Tasks mendukung berbagai format file proyek, termasuk MPP, XML, dan MPX.
### Bisakah saya menyesuaikan kontur kerja sesuai dengan kebutuhan proyek saya?
Ya, Aspose.Tasks memungkinkan pengguna menentukan kontur kerja khusus agar sesuai dengan kebutuhan proyek spesifik mereka.
### Apakah ada forum komunitas di mana saya bisa mendapatkan bantuan dengan Aspose.Tasks?
 Ya, Anda dapat mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi.