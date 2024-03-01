---
title: Pantau Lembur, Sisa Biaya, dan Kerja Sesuai Aspose.Tugas
linktitle: Pantau Lembur, Sisa Biaya, dan Kerja Sesuai Aspose.Tugas
second_title: Aspose.Tugas Java API
description: Pelajari cara memantau lembur, sisa biaya, dan bekerja di proyek Java menggunakan Aspose.Tasks. Langkah mudah untuk manajemen proyek yang efektif.
type: docs
weight: 18
url: /id/java/resource-assignments/overtime-remaining-costs-work/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Tasks untuk Java untuk memantau lembur, sisa biaya, dan pekerjaan dalam sebuah proyek. Hal ini dapat sangat berharga bagi manajer proyek dan pimpinan tim untuk memastikan proyek tetap berjalan sesuai rencana dan sesuai anggaran.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Java Development Kit (JDK): Aspose.Tasks untuk Java memerlukan Java SE 6 atau lebih baru.
2.  Aspose.Tugas untuk Perpustakaan Java: Unduh dan instal perpustakaan dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Lingkungan Pengembangan Terintegrasi (IDE): Semua IDE Java seperti Eclipse, IntelliJ IDEA, atau NetBeans.

## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan dalam file Java Anda:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Langkah 1: Siapkan Direktori Data
Tentukan direktori tempat file proyek Anda berada:
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur ke file proyek Anda.
## Langkah 2: Muat Proyek
 Buat contoh a`Project` objek dan memuat file proyek:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Mengganti`"ResourceAssignmentOvertimes.mpp"` dengan nama file proyek Anda.
## Langkah 3: Ulangi Melalui Penugasan Sumber Daya
Ulangi setiap penetapan sumber daya dalam proyek:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Langkah 4: Cetak Biaya Lembur dan Pekerjaan
Ambil dan cetak biaya lembur dan pekerjaan untuk setiap penetapan sumber daya:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Langkah 5: Cetak Sisa Biaya dan Pekerjaan
Ambil dan cetak sisa biaya dan pekerjaan untuk setiap penetapan sumber daya:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Langkah 6: Cetak Sisa Biaya Lembur dan Pekerjaan
Ambil dan cetak sisa biaya lembur dan pekerjaan untuk setiap penetapan sumber daya:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Kesimpulan
Memantau waktu lembur, sisa biaya, dan pekerjaan dalam suatu proyek sangat penting untuk keberhasilan manajemen proyek. Dengan Aspose.Tasks untuk Java, Anda dapat dengan mudah mengakses dan melacak informasi ini, memastikan proyek Anda tetap sesuai jadwal dan sesuai anggaran.
## FAQ
### Bisakah saya menggunakan Aspose.Tasks untuk Java dengan perpustakaan Java lainnya?
Ya, Aspose.Tasks untuk Java kompatibel dengan pustaka dan kerangka kerja Java lainnya.
### Apakah Aspose.Tasks mendukung format file proyek yang berbeda?
Ya, Aspose.Tasks mendukung berbagai format file proyek termasuk MPP, XML, dan lainnya.
### Apakah ada versi uji coba yang tersedia?
 Ya, Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat memperoleh dukungan jika saya mengalami masalah?
 Anda dapat mengunjungi forum Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15) untuk dukungan.
### Bagaimana cara membeli lisensi untuk Aspose.Tasks?
 Anda dapat membeli lisensi dari[Di Sini](https://purchase.aspose.com/buy).