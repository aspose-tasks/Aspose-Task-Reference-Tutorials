---
title: Ambil Info Kalender Proyek MS di Aspose.Tasks
linktitle: Ambil Info Kalender di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Pelajari cara mengambil info kalender MS Project menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah untuk mengakses detail kalender secara terprogram.
weight: 14
url: /id/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ambil Info Kalender Proyek MS di Aspose.Tasks

## Perkenalan
Dalam tutorial ini, kita akan mempelajari cara mengambil informasi kalender dari file Microsoft Project menggunakan pustaka Aspose.Tasks untuk Java. Aspose.Tasks menyediakan fitur canggih untuk memanipulasi data proyek, termasuk mengakses detail kalender seperti hari dan jam kerja.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
- Pengetahuan dasar tentang pemrograman Java.
- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Tugas untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/tasks/java/).
## Paket Impor
Pertama, Anda perlu mengimpor paket yang diperlukan dalam kode Java Anda untuk menggunakan fungsionalitas Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Sekarang mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk pemahaman yang lebih baik.
## Langkah 1: Tetapkan Direktori Data
```java
String dataDir = "Your Data Directory";
```
 Mengganti`"Your Data Directory"` dengan jalur ke direktori file proyek Anda.
## Langkah 2: Tentukan Satuan Waktu
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Konstanta ini mewakili satuan waktu dalam mikrodetik.
## Langkah 3: Buat Instans Proyek
```java
Project project = new Project(dataDir + "project.mpp");
```
 Baris ini membuat sebuah instance dari`Project` kelas, menginisialisasinya dengan jalur ke file proyek (`project.mpp`).
## Langkah 4: Ambil Informasi Kalender
```java
CalendarCollection alCals = project.getCalendars();
```
Di sini, kami mengambil kumpulan kalender yang ada di file proyek.
## Langkah 5: Ulangi Kalender
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Informasi Kalender
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Ulangi Melalui Hari Kerja
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Waktu dalam milidetik
            double time = ts / (OneHour); // Konversikan ke jam
            if (wd.getDayWorking()) {
                // Menampilkan Hari dan Jam Kerja
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Perulangan ini mengulangi setiap kalender dan mencetak UID, nama, dan hari kerjanya dengan jam kerja masing-masing.
## Langkah 6: Tampilkan Pesan Penyelesaian
```java
System.out.println("Process completed Successfully");
```
Akhirnya, sebuah pesan ditampilkan yang menunjukkan selesainya proses.
## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengambil informasi kalender dari file MS Project menggunakan Aspose.Tasks untuk Java. Dengan mengikuti langkah-langkah ini, Anda dapat mengakses dan memanipulasi data proyek secara efisien di aplikasi Java Anda.

## FAQ
### T: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?
J: Ya, Aspose.Tasks mendukung berbagai platform dan bahasa pemrograman, termasuk .NET, C++, Python, dan Jawa.
### T: Apakah ada uji coba gratis yang tersedia untuk Aspose.Tasks?
 J: Ya, Anda dapat mengunduh versi uji coba gratis dari[Di Sini](https://releases.aspose.com/).
### T: Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Tasks?
J: Anda bisa mendapatkan dukungan dari forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15).
### T: Dapatkah saya membeli lisensi sementara untuk Aspose.Tasks?
 J: Ya, lisensi sementara tersedia untuk dibeli[Di Sini](https://purchase.aspose.com/temporary-license/).
### T: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks?
 A: Anda dapat merujuk ke dokumentasinya[Di Sini](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
