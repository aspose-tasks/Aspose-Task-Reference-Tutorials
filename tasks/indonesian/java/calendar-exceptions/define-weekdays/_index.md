---
date: 2026-01-28
description: Pelajari cara membuat kalender proyek Aspose, menentukan hari kerja untuk
  pengecualian kalender, dan mengelola jadwal hari non‑kerja menggunakan Aspose.Tasks
  untuk Java.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Buat Kalender Proyek Aspose – Tentukan Hari Kerja untuk Pengecualian Kalender
url: /id/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Kalender Proyek Aspose – Tentukan Hari Kerja untuk Pengecualian Kalender

### Perkenalan
Ketika Anda perlu **membuat kalender proyek aspose**, Anda harus dapat memodelkan hari kerja non‑standar seperti hari libur, shift khusus, atau penutupan sementara. Aspose.Tasks untuk Java memberi Anda kontrol penuh atas definisi kalender, memungkinkan Anda menambahkan mengirimkan yang mencerminkan jadwal dunia nyata. Dalam tutorial ini kami akan memandu Anda langkah demi langkah untuk mendefinisikan hari kerja untuk mengirimkan kalender, sehingga timeline proyek Anda tetap akurat dan dapat diandalkan. Pada akhir tutorial Anda juga akan melihat bagaimana hal ini masuk ke dalam strategi **jadwal non-hari kerja** yang lebih luas untuk proyek perusahaan mana pun.

## Jawaban Cepat
- **Apa arti “buat kalender proyek seolah-olah”?** 
Ini Merujuk pada penggunaan Aspose.Tugas untuk membuat objek kalender khusus yang mengatur penjadwalan tugas.
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** 
Versi trial gratis cukup untuk pengembangan; lisensi komersial diperlukan untuk produksi.
- **IDE mana yang didukung?** 
IntelliJ IDEA, Eclipse, NetBeans, atau IDE apa pun yang mendukung Java8+.
- ** meminta saya menambahkan beberapa mengirimkan ke kalender yang sama?** 
Ya – Anda dapat menambahkan sebanyak yang diperlukan objek `CalendarException`.
- **Format file apa yang dapat saya simpan proyek?** 
XML, MPP, dan beberapa format lain yang didukung oleh Aspose.Tasks.

## Apa itu Kalender Proyek di Aspose.Tasks?
**Kalender proyek** mendefinisikan hari kerja dan jam kerja untuk sebuah proyek. Kalender ini mempengaruhi tanggal mulai/selesai tugas, alokasi sumber daya, dan perhitungan jadwal secara keseluruhan. Dengan menyesuaikan kalender, Anda memastikan jadwal menghormati batasan dunia nyata seperti libur perusahaan atau kebijakan kerja akhir pekan.

## Mengapa menentukan hari kerja untuk pengecualian kalender?
- **Jalur waktu yang akurat:** Tugas tidak akan dijadwalkan pada hari yang ditandai tidak berfungsi.
- **Perencanaan sumber daya:** Sumber daya hanya dialokasikan pada hari kerja yang sah.
- **Kepatuhan:** Menyelaraskan jadwal proyek dengan kebijakan organisasi atau hari libur resmi.

## Jadwal Hari Tidak Bekerja dengan Pengecualian Kalender
Saat Anda memelihara **jadwal non‑hari kerja**, biasanya Anda memiliki daftar utama libur, jendela pemeliharaan, atau periode pemadaman lainnya. Menambahkan tanggal‑tanggal tersebut sebagai objek `CalendarException` menjamin setiap perhitungan—baik analisis jalur kritis maupun leveling sumber daya—secara otomatis mematuhi batasan tersebut. Pendekatan ini menghilangkan tanggal penyesuaian manual dan mengurangi risiko penyimpangan jadwal.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru.
2. **Aspose.Tasks for Java** – unduh dari halaman resmi [halaman unduh Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans, atau editor lainnya yang kompatibel dengan Java.

## Cara membuat kalender proyek di Aspose – Menentukan hari kerja untuk pengecualian kalender

### Panduan Langkah demi Langkah

### Langkah 1: Impor Paket yang Diperlukan
Kita membutuhkan kelas inti Aspose.Tasks dan `GregorianCalendar` Java untuk penanganan tanggal.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Langkah 2: Tentukan Direktori Data
Tentukan di mana file proyek yang dihasilkan akan disimpan.

```java
String dataDir = "Your Data Directory";
```

### Langkah 3: Buat Instans Proyek
Buat objek `Project` baru – ini adalah wadah untuk semua data proyek, termasuk kalender.

```java
Project project = new Project();
```

### Langkah 4: Tentukan Kalender
Tambahkan kalender khusus ke proyek. Kalender ini akan menyimpan pengecualian kita.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Langkah 5: Tentukan Pengecualian Hari Kerja
Buat `CalendarException` yang menandai rentang hari (misalnya, minggu terakhir Desember) sebagai hari libur.
Contoh ini menetapkan pengecualian dari **24Des2009** hingga **31Des2009**, menonaktifkan pekerjaan untuk hari-hari tersebut, dan memperlakukan pengecualian sebagai tipe harian.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Langkah 6: Simpan Proyek
Simpan proyek, termasuk kalender khusus dan pengecualiannya, ke dalam file XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Masalah Umum dan Solusinya
| Edisi | Solusi |
|-------|----------|
| **Tanggal pengecualian tidak diterapkan** | Pastikan `setEnteredByOccurrences(false)` dan nilai `FromDate/ToDate` sudah benar. |
| **File yang disimpan kosong** | Verifikasi bahwa `dataDir` mengarahkan ke folder yang dapat ditulisi dan nama file berakhiran `.xml`. |
| **Kalender tidak tercermin dalam penjadwalan tugas** | Tetapkan kalender ke tugas atau sumber daya menggunakan `task.setCalendar(cal)` atau `resource.setCalendar(cal)`. |

## Pertanyaan yang Sering Diajukan

**T: Dapatkah saya menentukan beberapa pengecualian untuk hari kerja berbeda dalam kalender yang sama?**
J: Ya. Tambahkan objek `CalendarException` tambahan ke `cal.getExceptions()` untuk setiap periode atau aturan yang berbeda.

**T: Apakah Aspose.Tasks untuk Java kompatibel dengan IDE Java yang berbeda?**
J: Tentu saja. Library ini bekerja dengan IntelliJ IDEA, Eclipse, NetBeans, dan IDE apa pun yang mendukung proyek Java standar.

**T: Dapatkah saya menyesuaikan jenis pengecualian selain pengecualian harian?**
J: Ya. Gunakan `CalendarExceptionType.Weekly`, `Monthly`, atau `Yearly` sesuai kebutuhan penjadwalan Anda.

**T: Bagaimana cara menangani pengecualian secara dinamis berdasarkan persyaratan proyek?**
A: Bangun objek secara programatis—misalnya, baca tanggal libur dari basis data atau file konfigurasi dan buat instance `CalendarException` dalam loop.

**T: Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?**
A: Ya, Anda dapat mengunduh uji coba gratis dari [halaman unduh Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).

## Kesimpulan
Dengan mengikuti langkah‑langkah ini Anda kini tahu cara **create project kalender aspose** dan mendefinisikan mengirimkan hari kerja yang secara akurat mencerminkan hari libur atau periode tidak bekerja khusus. Konfigurasi kalender yang tepat sangat penting untuk jadwal yang realistis, alokasi sumber daya, dan keberhasilan proyek secara keseluruhan. Penjelajahan lebih lanjut dengan kalender khusus ke tugas atau sumber daya serta eksperimen dengan tipe perekrutan lain untuk membangun **jadwal non-hari kerja** yang komprehensif bagi proyek apa pun.

---

**Terakhir Diperbarui:** 28-01-2026
**Diuji Dengan:** Aspose.Tasks untuk Java 24.11
**Penulis:** Beranggapan  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}