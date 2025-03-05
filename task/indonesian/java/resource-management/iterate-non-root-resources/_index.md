---
title: Ulangi Sumber Daya Non-Root di Aspose.Tasks
linktitle: Ulangi Sumber Daya Non-Root di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara melakukan iterasi secara efisien pada sumber daya non-root di file Microsoft Project menggunakan Aspose.Tasks untuk Java. Tingkatkan proses pengembangan Anda.
type: docs
weight: 12
url: /id/java/resource-management/iterate-non-root-resources/
---
## Perkenalan
Aspose.Tasks untuk Java adalah perpustakaan canggih yang menyediakan alat yang dibutuhkan pengembang untuk memanipulasi file Microsoft Project secara efisien. Dengan antarmuka intuitif dan fungsionalitas yang luas, Aspose.Tasks menyederhanakan proses bekerja dengan data proyek, memungkinkan pengembang untuk fokus dalam membangun aplikasi yang tangguh.
## Prasyarat
Sebelum mendalami penggunaan Aspose.Tasks untuk Java, pastikan Anda memiliki hal berikut:
1.  Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda. Anda dapat mengunduhnya dari[situs web Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks untuk Java Library: Unduh dan instal Aspose.Tasks untuk perpustakaan Java dari[Unduh Halaman](https://releases.aspose.com/tasks/java/).

## Paket Impor
Di proyek Java Anda, impor paket yang diperlukan untuk mulai bekerja dengan Aspose.Tasks:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Langkah 1: Siapkan Direktori Data
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur ke direktori tempat file proyek Anda disimpan.
## Langkah 2: Muat File Proyek
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
 Baris ini menginisialisasi yang baru`Project` objek dengan memuat file proyek bernama`"ResourceCosts.mpp"` dari direktori data yang ditentukan.
## Langkah 3: Ulangi Sumber Daya Non-Root
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
Perulangan ini mengulangi setiap sumber daya dalam proyek (`prj.getResources()`). Jika sumber daya adalah sumber daya root, maka sumber daya tersebut akan melompat ke iterasi berikutnya. Jika tidak, ia akan mencetak nama sumber daya non-root.

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara melakukan iterasi pada sumber daya non-root menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat memanipulasi data proyek secara efektif dan menyederhanakan proses pengembangan Anda.
## FAQ
### Bisakah saya menggunakan Aspose.Tasks untuk Java untuk membuat file proyek baru?
Ya, Aspose.Tasks menyediakan fungsionalitas untuk membuat, memodifikasi, dan menyimpan file proyek dalam berbagai format.
### Apakah Aspose.Tasks mendukung semua versi file Microsoft Project?
Aspose.Tasks mendukung format file Microsoft Project 2003-2019, termasuk MPP, MPT, dan XML.
### Apakah Aspose.Tasks kompatibel dengan kerangka Java seperti Spring?
Ya, Aspose.Tasks dapat diintegrasikan dengan mulus ke dalam kerangka Java seperti Spring untuk aplikasi tingkat perusahaan.
### Bisakah saya menyesuaikan bidang data proyek menggunakan Aspose.Tasks?
Tentu saja, Aspose.Tasks menawarkan API ekstensif untuk menyesuaikan bidang data proyek sesuai kebutuhan Anda.
### Apakah Aspose.Tasks menyediakan dukungan dan dokumentasi untuk pengembang?
Ya, Aspose.Tasks menawarkan dokumentasi komprehensif dan forum dukungan khusus untuk membantu pengembang dengan pertanyaan atau masalah apa pun yang mereka temui.