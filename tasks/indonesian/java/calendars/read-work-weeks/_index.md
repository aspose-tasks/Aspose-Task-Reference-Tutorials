---
date: 2025-12-03
description: Pelajari cara membaca minggu kerja Java dari kalender Microsoft Project
  menggunakan Aspose.Tasks. Ikuti panduan langkah demi langkah dengan contoh kode
  lengkap.
language: id
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Baca Work Weeks Java dari Kalender MS Project Aspose.Tasks
url: /java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membaca Work Weeks Java dari Kalender MS Project dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan **membaca work weeks Java** dari kalender Microsoft Project menggunakan pustaka Aspose.Tasks. Baik Anda sedang membangun alat pelaporan, menyinkronkan jadwal, atau mengotomatisasi ekstraksi data proyek, kemampuan mengakses definisi work‑week secara programatik menghemat banyak jam kerja manual. Kami akan memandu Anda melalui penyiapan yang diperlukan, menunjukkan kode tepat untuk mengambil detail work‑week, dan menjelaskan setiap langkah sehingga Anda dapat menyesuaikan solusi ini untuk proyek Anda sendiri.

## Jawaban Cepat
- **Apa arti “read work weeks java”?** Itu merujuk pada mengekstrak definisi work‑week dari file Project menggunakan kode Java.  
- **Pustaka apa yang dibutuhkan?** Aspose.Tasks untuk Java (tersedia trial gratis).  
- **Apakah saya memerlukan lisensi untuk pengembangan?** Trial dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Format file apa yang didukung?** Baik *.mpp* maupun file Project XML didukung.  
- **Berapa lama implementasinya?** Biasanya kurang dari 10 menit setelah pustaka terpasang.

## Apa itu “read work weeks java”?
Membaca work weeks dalam Java berarti menggunakan API Aspose.Tasks untuk mengakses `WorkWeekCollection` dari objek kalender di dalam file Microsoft Project. Setiap `WorkWeek` berisi tanggal mulai/berakhir serta definisi waktu kerja harian yang menentukan bagaimana sumber daya dijadwalkan.

## Mengapa membaca work weeks java dari kalender Microsoft Project?
- **Otomatisasi:** Menghilangkan penyalinan‑tempel data jadwal secara manual.  
- **Integrasi:** Menyalurkan informasi work‑week ke sistem ERP, HR, atau pelaporan khusus.  
- **Konsistensi:** Memastikan semua alat hilir menghormati aturan kalender yang sama yang didefinisikan dalam file Project.

## Prasyarat
Sebelum masuk ke kode, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru terpasang.  
2. **Aspose.Tasks untuk Java** – unduh JAR terbaru dari situs resmi: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Sebuah **file Project contoh** (`ReadWorkWeeksInformation.mpp`) yang ditempatkan di folder yang diketahui.

## Impor Paket
Pertama, impor kelas‑kelas yang diperlukan untuk berinteraksi dengan kalender dan work weeks:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Langkah 1: Menyiapkan Direktori Data Anda
Tentukan folder yang berisi file `.mpp`. Ganti placeholder dengan jalur sebenarnya di mesin Anda:

```java
String dataDir = "Your Data Directory";
```

## Langkah 2: Membuat Instance Project dan Mengakses Kalender
Instansiasi objek `Project`, pilih kalender yang diinginkan (berdasarkan UID), dan peroleh `WorkWeekCollection`‑nya:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Tip pro:** Jika Anda tidak yakin tentang UID kalender, Anda dapat melakukan iterasi melalui `project.getCalendars()` dan mencetak nama serta UID setiap kalender.

## Langkah 3: Mengiterasi Work Weeks
Lakukan loop pada setiap `WorkWeek` untuk menampilkan nama, tanggal mulai/berakhir, dan waktu kerja harian:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Apa yang akan Anda lihat:** Konsol mencetak label setiap work‑week (misalnya “Standard”), rentang tanggal efektifnya, dan Anda dapat menelusuri jam kerja tepat untuk setiap hari.

## Masalah Umum dan Solusinya
| Masalah | Alasan | Solusi |
|-------|--------|-----|
| `NullPointerException` saat mengakses `calendar` | UID salah atau kalender tidak ada | Verifikasi UID dengan `project.getCalendars().size()` dan daftar kalender yang tersedia terlebih dahulu. |
| Tidak ada output untuk work weeks | Kalender yang dipilih tidak memiliki work weeks khusus (menggunakan default) | Gunakan kalender default (`project.getDefaultCalendar()`) atau buat work week secara programatik. |
| Format tanggal terlihat aneh | `System.out.println` menggunakan format default `java.util.Date` | Terapkan `SimpleDateFormat` untuk memformat tanggal sesuai kebutuhan. |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya memodifikasi informasi work weeks menggunakan Aspose.Tasks untuk Java?**  
J: Ya. API menyediakan metode seperti `addWorkWeek()`, `removeWorkWeek()`, dan setter properti untuk mengubah nama, tanggal, serta waktu kerja.

**T: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?**  
J: Tentu. Ia mendukung file MPP dari Project 98 hingga versi terbaru, serta file Project XML.

**T: Bisakah saya mengintegrasikan Aspose.Tasks dengan kerangka kerja Java lainnya?**  
J: Ya. Pustaka ini murni Java, sehingga dapat digunakan bersama Spring, Jakarta EE, atau kerangka kerja lainnya.

**T: Apakah ada versi trial yang tersedia untuk Aspose.Tasks?**  
J: Ya, Anda dapat mengunduh trial gratis selama 30 hari dari situs resmi: [Aspose.Tasks trial](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?**  
J: Forum komunitas Aspose adalah tempat terbaik: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Kesimpulan
Anda kini telah menguasai **read work weeks java** menggunakan Aspose.Tasks. Dengan mengikuti langkah‑langkah di atas, Anda dapat secara programatik menarik definisi work‑week dari kalender MS Project mana pun, mengintegrasikan data tersebut ke dalam aplikasi Anda, dan mengotomatisasi alur kerja terkait jadwal. Jangan ragu untuk bereksperimen dengan membuat atau memperbarui work weeks—Aspose.Tasks membuatnya menjadi mudah.

---

**Terakhir Diperbarui:** 2025-12-03  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}