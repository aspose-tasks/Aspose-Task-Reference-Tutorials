---
title: Ambil Pengecualian Kalender dengan Aspose.Tasks
linktitle: Ambil Pengecualian Kalender dengan Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengambil pengecualian kalender dari MS Project menggunakan Aspose.Tasks untuk Java. Tutorial langkah demi langkah untuk integrasi yang lancar.
weight: 13
url: /id/java/calendar-exceptions/retrieve/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ambil Pengecualian Kalender dengan Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengambil pengecualian kalender dari MS Project menggunakan perpustakaan Aspose.Tasks untuk Java. Aspose.Tasks adalah alat canggih yang memungkinkan pengembang memanipulasi file Microsoft Project secara terprogram. Kami akan memandu Anda melalui proses langkah demi langkah, membagi setiap contoh menjadi beberapa langkah agar mudah dipahami.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal JDK di sistem Anda.
2.  Aspose.Tasks for Java: Unduh dan instal Aspose.Tasks for Java dari[Di Sini](https://releases.aspose.com/tasks/java/).
3. Lingkungan Pengembangan Terpadu (IDE): Anda dapat menggunakan IDE apa pun pilihan Anda, seperti IntelliJ IDEA atau Eclipse.

## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan untuk bekerja dengan Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Langkah 1: Siapkan Direktori Data Anda
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Data Directory";
```
 Pastikan untuk mengganti`"Your Data Directory"` dengan path ke direktori Anda yang berisi file MS Project.
## Langkah 2: Muat File Proyek MS
```java
Project project = new Project(dataDir + "project.mpp");
```
 Baris ini menginisialisasi yang baru`Project` objek dengan memuat file MS Project yang ditentukan oleh jalur.
## Langkah 3: Ambil Pengecualian Kalender
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Di sini, kami mengulangi setiap kalender dalam proyek dan kemudian melalui setiap pengecualian kalender dalam kalender tersebut. Kami mencetak tanggal mulai dan berakhir setiap pengecualian.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara mengambil pengecualian kalender dari MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah sederhana ini, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi Java Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah Aspose.Tasks menangani versi file MS Project yang berbeda?
Ya, Aspose.Tasks mendukung berbagai versi file MS Project, termasuk format MPP, MPT, dan XML.
### Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 Ya, Anda dapat mengunduh uji coba gratis Aspose.Tasks dari[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dokumentasi untuk Aspose.Tasks untuk Java?
 Anda dapat merujuk ke dokumentasi[Di Sini](https://reference.aspose.com/tasks/java/).
### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
 Anda bisa mendapatkan dukungan dari forum komunitas[Di Sini](https://forum.aspose.com/c/tasks/15).
### Apakah ada opsi untuk lisensi sementara untuk Aspose.Tasks?
 Ya, Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
