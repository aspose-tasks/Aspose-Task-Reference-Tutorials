---
date: 2025-12-20
description: Pelajari cara menggunakan Aspose.Tasks untuk mengekstrak detail kalender
  proyek dari file Microsoft Project menggunakan Java. Panduan langkah demi langkah
  dengan contoh kode.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menggunakan Aspose.Tasks untuk Mengambil Info Kalender MS Project
url: /id/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menggunakan Aspose.Tasks untuk Mengambil Info Kalender MS Project

## Pendahuluan
Dalam tutorial ini, **Anda akan mempelajari cara menggunakan Aspose.Tasks** untuk secara programatik mengambil informasi kalender dari file Microsoft Project. Mengakses data kalender seperti hari kerja, jam kerja, dan pengecualian sangat penting ketika Anda perlu **mengekstrak kalender proyek** untuk pelaporan, integrasi, atau logika penjadwalan khusus. Mari kita jalani prosesnya langkah demi langkah.

## Jawaban Cepat
- **Perpustakaan apa yang digunakan dalam tutorial ini?** Aspose.Tasks untuk Java.  
- **Kata kunci utama apa yang dibahas?** *how to use aspose.tasks*.  
- **Apa yang dapat Anda ekstrak?** Kalender proyek, termasuk hari kerja dan jam kerja.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis tersedia; lisensi diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Java 8 atau lebih tinggi.

## Mengapa mengekstrak informasi kalender proyek?
Kalender proyek mengatur tanggal tugas, alokasi sumber daya, dan perhitungan garis waktu keseluruhan. Dengan mengekstrak data ini Anda dapat:
- Membuat laporan khusus yang mencerminkan jadwal kerja sebenarnya.  
- Menyinkronkan garis waktu Microsoft Project dengan sistem eksternal (ERP, BI, dll.).  
- Melakukan analisis “what‑if” dengan memodifikasi pengaturan kalender secara programatik.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

- Pengetahuan dasar pemrograman Java.  
- Java Development Kit (JDK) terpasang di sistem Anda.  
- Perpustakaan Aspose.Tasks untuk Java. Anda dapat mengunduhnya dari [sini](https://releases.aspose.com/tasks/java/).

## Impor Paket
Pertama, impor kelas Aspose.Tasks yang diperlukan ke dalam proyek Java Anda.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Langkah 1: Atur Direktori Data
Tentukan folder yang berisi file *.mpp* Anda.

```java
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan jalur absolut ke folder tempat **project.mpp** berada.

## Langkah 2: Definisikan Unit Waktu
Buat konstanta yang membantu mengonversi representasi waktu internal menjadi jam yang dapat dibaca manusia.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Nilai‑nilai ini dinyatakan dalam mikrodetik, yang merupakan cara Aspose.Tasks menyimpan waktu secara internal.

## Langkah 3: Buat Instance Project
Muat file Microsoft Project ke dalam objek `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Konstruktor `Project` mem-parsing file *.mpp* dan membuat semua data proyek, termasuk kalender, dapat diakses melalui API.

## Langkah 4: Ambil Informasi Kalender
Dapatkan koleksi kalender yang didefinisikan dalam proyek.

```java
CalendarCollection alCals = project.getCalendars();
```

Sebuah proyek dapat berisi beberapa kalender (standar, sumber daya, dan kalender khusus). Koleksi ini memberi Anda akses ke masing‑masing kalender.

## Langkah 5: Iterasi Melalui Kalender
Loop melalui setiap kalender, tampilkan UID, nama, dan hari kerja beserta jam kerja yang bersangkutan.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Loop dalam memeriksa setiap objek `WeekDay`. Jika hari tersebut ditandai sebagai hari kerja, ia mencetak tipe hari (Senin, Selasa, …) bersama dengan jam kerja yang dihitung.

## Langkah 6: Tampilkan Pesan Penyelesaian
Berikan sinyal bahwa proses ekstraksi telah selesai.

```java
System.out.println("Process completed Successfully");
```

## Kesimpulan
Dengan mengikuti langkah‑langkah ini, **Anda kini tahu cara menggunakan Aspose.Tasks untuk mengekstrak informasi kalender proyek** dari file MS Project menggunakan Java. Anda dapat mengintegrasikan logika ini ke dalam aplikasi yang lebih besar, mengotomatisasi pelaporan, atau menyinkronkan jadwal dengan sistem perusahaan lainnya.

## Pertanyaan yang Sering Diajukan

**T: Apakah saya dapat menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
J: Ya, Aspose.Tasks mendukung banyak platform dan bahasa pemrograman, termasuk .NET, C++, Python, dan Java.

**T: Apakah ada versi percobaan gratis untuk Aspose.Tasks?**  
J: Ya, Anda dapat mengunduh versi percobaan gratis dari [sini](https://releases.aspose.com/).

**T: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks?**  
J: Anda dapat memperoleh dukungan melalui forum komunitas Aspose.Tasks [sini](https://forum.aspose.com/c/tasks/15).

**T: Apakah saya dapat membeli lisensi sementara untuk Aspose.Tasks?**  
J: Ya, lisensi sementara tersedia untuk dibeli [sini](https://purchase.aspose.com/temporary-license/).

**T: Di mana saya dapat menemukan dokumentasi detail untuk Aspose.Tasks?**  
J: Anda dapat merujuk ke dokumentasi [sini](https://reference.aspose.com/tasks/java/).

---

**Terakhir Diperbarui:** 2025-12-20  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}