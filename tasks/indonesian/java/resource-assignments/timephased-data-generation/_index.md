---
date: 2026-01-10
description: Pelajari cara mengubah kontur dan menghasilkan data berwaktu untuk penugasan
  sumber daya menggunakan Aspose.Tasks untuk Java, meningkatkan efisiensi manajemen
  proyek.
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengubah Kontur di Aspose.Tasks untuk Data Berfase Waktu
url: /id/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengubah Kontur di Aspose.Tasks untuk Data Berwaktu

## Introduction
Dalam tutorial ini, Anda akan menemukan **cara mengubah kontur** untuk penugasan sumber daya dan menghasilkan data berwaktu menggunakan Aspose.Tasks untuk Java. Data berwaktu mengungkapkan distribusi pekerjaan sepanjang garis waktu proyek, memungkinkan Anda menyesuaikan jadwal, menyeimbangkan beban kerja, dan membuat keputusan berbasis data.

## Quick Answers
- **Apa itu kontur?** Kontur kerja mendefinisikan bagaimana upaya dibagi sepanjang durasi tugas (mis., Flat, Turtle, Bell).  
- **Mengapa mengubah kontur?** Untuk mencerminkan pola kerja realistis seperti penambahan beban di awal atau di akhir.  
- **Pustaka apa yang diperlukan?** Aspose.Tasks untuk Java (versi terbaru apa pun).  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya melihat hasilnya di konsol?** Contoh mencetak tanggal mulai dan nilai untuk setiap segmen berwaktu.

## What is “how to change contour”?
Mengubah kontur berarti memperbarui properti `WORK_CONTOUR` dari `ResourceAssignment`. Aspose.Tasks mendukung beberapa kontur bawaan (Flat, Turtle, Bell, dll.) yang memengaruhi bagaimana pekerjaan dialokasikan seiring waktu.

## Why use Aspose.Tasks to generate timephased data?
- **Pelaporan akurat:** Mengekspor distribusi kerja yang tepat untuk alat pelaporan.  
- **Perencanaan skenario:** Menguji berbagai kontur tanpa mengubah jadwal asli.  
- **Otomasi:** Mengintegrasikan ke dalam pipeline CI untuk memvalidasi kesehatan proyek secara otomatis.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduh dan menginstal JDK dari [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java Library: Anda perlu memiliki pustaka Aspose.Tasks untuk Java. Anda dapat mengunduhnya dari [website](https://releases.aspose.com/tasks/java/).

## Import Packages
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
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Langkah 2: Dapatkan Tugas dan Penugasan Sumber Daya
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Cara Mengubah Kontur – Flat (Default)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Masalah Umum & Tips
- **Kontur tidak diperbarui?** Pastikan Anda memanggil `firstRA.set(Asn.WORK_CONTOUR, …)` *sebelum* mengambil data berwaktu.
- **Nilai tidak terduga?** Verifikasi bahwa tanggal mulai dan selesai tugas telah diatur dengan benar di MPP sumber.
- **Tip kinerja:** Gunakan kembali instance `Project` yang sama saat mengiterasi beberapa kontur untuk menghindari I/O file yang tidak perlu.

## FAQ
### Apakah saya dapat menggunakan Aspose.Tasks dengan pustaka Java lain?
Ya, Aspose.Tasks dapat diintegrasikan dengan pustaka Java lain untuk meningkatkan kemampuan manajemen proyek.

### Apakah Aspose.Tasks cocok untuk proyek perusahaan berskala besar?
Tentu saja, Aspose.Tasks dirancang untuk menangani proyek dari semua ukuran, termasuk inisiatif perusahaan berskala besar.

### Apakah Aspose.Tasks menyediakan dukungan untuk berbagai format file proyek?
Ya, Aspose.Tasks mendukung berbagai format, seperti MPP, XML, dan MPX.

### Bisakah saya menyesuaikan kontur kerja sesuai kebutuhan proyek saya?
Ya, Anda dapat mendefinisikan kontur kerja khusus untuk menyesuaikan kebutuhan penjadwalan tertentu.

### Apakah ada forum komunitas tempat saya dapat mendapatkan bantuan dengan Aspose.Tasks?
Ya, Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi.

---

**Terakhir Diperbarui:** 2026-01-10  
**Diuji Dengan:** Aspose.Tasks untuk Java (rilis terbaru)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}