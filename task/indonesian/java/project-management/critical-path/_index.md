---
title: Hitung Jalur Proyek MS Kritis di Aspose.Tasks
linktitle: Hitung Jalur Kritis di Proyek Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara menghitung jalur kritis di MS Project menggunakan Aspose.Tasks untuk Java. Ini memberikan panduan langkah demi langkah untuk manajemen proyek yang efisien.
type: docs
weight: 10
url: /id/java/project-management/critical-path/
---
## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses penghitungan jalur kritis di MS Project menggunakan Aspose.Tasks untuk Java. Jalur kritis sangat penting bagi manajemen proyek karena membantu mengidentifikasi urutan tugas yang harus diselesaikan tepat waktu untuk memastikan jadwal keseluruhan proyek tidak tertunda.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK) diinstal pada sistem Anda.
2.  Aspose.Tasks untuk perpustakaan Java diunduh dan ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).

## Paket Impor
Untuk memulai, impor paket yang diperlukan di kelas Java Anda:
```java
import com.aspose.tasks.*;
```
## Langkah 1: Siapkan Direktori Data
Tentukan jalur ke direktori data tempat file MS Project Anda berada.
```java
String dataDir = "Your Data Directory";
```
## Langkah 2: Muat File Proyek MS
Muat file MS Project menggunakan perpustakaan Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Langkah 3: Atur Mode Perhitungan
Atur mode penghitungan ke otomatis untuk mengaktifkan penghitungan jalur kritis.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## Langkah 4: Tambahkan Tugas
Tambahkan tugas ke proyek Anda. Dalam contoh ini, kami menambahkan tiga subtugas.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## Langkah 5: Buat Tautan Tugas
Buat tautan tugas untuk menentukan ketergantungan antar tugas.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## Langkah 6: Tampilkan Jalur Kritis
Ambil dan tampilkan jalur kritis proyek.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## Langkah 7: Tampilkan Hasil
Menampilkan pesan yang menunjukkan keberhasilan penyelesaian proses.
```java
System.out.println("Process completed Successfully");
```

## Kesimpulan
Menghitung jalur kritis di MS Project menggunakan Aspose.Tasks untuk Java sangat penting untuk manajemen proyek yang efektif. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat secara akurat mengidentifikasi urutan tugas penting untuk timeline proyek Anda.
## FAQ
### T: Dapatkah saya menggunakan Aspose.Tasks untuk Java dengan versi file MS Project apa pun?
J: Ya, Aspose.Tasks for Java mendukung berbagai versi file MS Project, termasuk file .mpp dari MS Project 2003 hingga MS Project 2019.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk Java?
 J: Anda dapat menemukan dukungan di[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
### T: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks untuk Java?
 J: Ya, Anda dapat membeli lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Bagaimana cara membeli Aspose.Tasks untuk Java?
 J: Anda dapat membeli Aspose.Tasks untuk Java dari situs web[Di Sini](https://purchase.aspose.com/buy).