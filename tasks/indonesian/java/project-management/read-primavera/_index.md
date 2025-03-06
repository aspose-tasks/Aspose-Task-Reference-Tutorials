---
title: Baca Proyek MS dari Primavera dengan Aspose.Tasks untuk Java
linktitle: Baca Proyek dari Primavera di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara membaca file MS Project dari Primavera XML dengan lancar menggunakan Aspose.Tasks untuk Java. Tingkatkan efisiensi manajemen proyek Anda.
weight: 20
url: /id/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Baca Proyek MS dari Primavera dengan Aspose.Tasks untuk Java

## Perkenalan
Dalam manajemen proyek, interoperabilitas antara platform perangkat lunak yang berbeda sangat penting untuk kelancaran alur kerja. Aspose.Tasks untuk Java menyediakan fungsionalitas yang kuat untuk membaca file Microsoft Project dari Primavera XML. Tutorial ini akan memandu Anda melalui proses membaca file MS Project dari Primavera menggunakan Aspose.Tasks untuk Java, memungkinkan Anda memeriksa properti khusus Primavera tugas secara efisien.
## Prasyarat
Sebelum melanjutkan, pastikan Anda telah menginstal dan menyiapkan prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Tasks for Java: Unduh dan instal Aspose.Tasks for Java dari[Di Sini](https://releases.aspose.com/tasks/java/).

## Paket Impor
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Langkah 1: Siapkan Direktori Data
```java
String dataDir = "Your Data Directory";
```
 Pastikan untuk mengganti`"Your Data Directory"` dengan jalur sebenarnya ke direktori data Anda.
## Langkah 2: Baca Proyek dari Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Pastikan untuk mengganti`"PrimaveraProject.xml"` dengan nama sebenarnya dari file XML Primavera Anda.
## Langkah 3: Ulangi Tugas dan Ambil Properti Spesifik Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Kode ini mengulangi setiap tugas dalam proyek, mencetak properti khusus Primavera yang relevan.

## Kesimpulan
Dalam tutorial ini, Anda mempelajari cara membaca file MS Project dari Primavera XML menggunakan Aspose.Tasks untuk Java. Fungsionalitas ini memungkinkan integrasi dan analisis data proyek yang lancar di berbagai platform, sehingga meningkatkan efisiensi manajemen proyek secara keseluruhan.
## FAQ
### T: Bisakah saya mengubah properti tugas khusus Primavera menggunakan Aspose.Tasks untuk Java?
J: Ya, Aspose.Tasks untuk Java menyediakan API untuk mengubah properti tugas khusus Primavera sesuai kebutuhan.
### T: Apakah Aspose.Tasks untuk Java mendukung pembacaan format file proyek lainnya?
J: Ya, Aspose.Tasks untuk Java mendukung pembacaan berbagai format file proyek termasuk MPP, XML, dan Primavera XML.
### T: Apakah Aspose.Tasks untuk Java cocok untuk aplikasi manajemen proyek tingkat perusahaan?
J: Tentu saja, Aspose.Tasks untuk Java menawarkan fitur dan skalabilitas yang tangguh, sehingga cocok untuk aplikasi manajemen proyek tingkat perusahaan.
### T: Dapatkah saya mengekstrak informasi sumber daya dari proyek Primavera menggunakan Aspose.Tasks untuk Java?
J: Ya, Aspose.Tasks untuk Java memungkinkan Anda mengekstrak informasi sumber daya beserta detail tugas dari proyek Primavera.
### T: Di mana saya dapat menemukan dukungan atau dokumentasi tambahan untuk Aspose.Tasks untuk Java?
 J: Anda dapat menemukan dokumentasi komprehensif dan akses ke forum dukungan di[Aspose.Tasks untuk dokumentasi Java](https://reference.aspose.com/tasks/java/) halaman.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
