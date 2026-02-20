---
date: 2026-02-20
description: Jelajahi cara menambahkan tugas ke proyek dan mengelola durasi dengan
  Aspose.Tasks untuk Java. Pelajari cara mengatur durasi dan cara mengonversi durasi
  dengan mudah.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Tambahkan Tugas ke Proyek dan Kelola Durasi dengan Aspose.Tasks
url: /id/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Tugas ke Proyek dan Kelola Durasi dengan Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara menambahkan tugas ke proyek** dan mengontrol durasinya menggunakan Aspose.Tasks untuk Java. Baik Anda sedang membangun alat perencanaan proyek baru atau memperluas solusi yang sudah ada, menguasai penanganan durasi tugas sangat penting untuk penjadwalan dan pelaporan yang akurat.

## Jawaban Cepat
- **Apa arti “add task to project”?** Itu membuat objek tugas baru di bawah root proyek atau tugas ringkasan tertentu.  
- **Kelas mana yang mewakili durasi?** `com.aspose.tasks.Duration`.  
- **Bagaimana cara mengatur durasi?** Gunakan `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Bisakah saya mengonversi durasi ke satuan lain?** Ya, panggil `duration.convert(TimeUnitType.Hour)` atau `TimeUnitType` lainnya.  
- **Apakah saya memerlukan lisensi untuk produksi?** Lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan komersial.

## Apa itu “add task to project”?
Menambahkan tugas ke proyek berarti membuat objek `Task` dan melampirkannya ke hierarki tugas proyek. Operasi ini adalah langkah pertama sebelum Anda dapat mendefinisikan pekerjaan, sumber daya, atau durasi untuk tugas tersebut.

## Mengapa mengelola durasi tugas?
Durasi yang akurat menghasilkan timeline yang realistis, alokasi sumber daya, dan analisis jalur kritis. Dengan Aspose.Tasks Anda dapat mengatur, membaca, mengonversi, dan menyesuaikan durasi secara programatis, memberi Anda kontrol penuh atas jadwal proyek.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki hal‑hal berikut:

- Java Development Kit (JDK): Pastikan Anda telah menginstal Java di mesin Anda. Anda dapat mengunduhnya [di sini](https://www.oracle.com/java/technologies/javase-downloads.html).
- Perpustakaan Aspose.Tasks: Unduh dan sertakan perpustakaan Aspose.Tasks dalam proyek Anda. Anda dapat menemukan perpustakaan tersebut [di sini](https://releases.aspose.com/tasks/java/).

## Impor Paket
Dalam proyek Java Anda, impor paket yang diperlukan untuk bekerja dengan Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Langkah 1: Siapkan Proyek Anda
```java
// Create a new project
Project project = new Project();
```

## Langkah 2: Tambahkan Tugas Baru (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Cara Mengatur Durasi
Sekarang tugas sudah ada, Anda dapat menentukan panjangnya. Secara default, durasi dinyatakan dalam hari.

## Langkah 3: Dapatkan dan Konversi Durasi Tugas
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Cara Mengonversi Durasi
Metode `convert` memungkinkan Anda menerjemahkan sebuah `Duration` dari satu `TimeUnitType` ke yang lain (mis., hari → jam, minggu → hari).

## Langkah 4: Perbarui Durasi Tugas menjadi 1 Minggu
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Langkah 5: Kurangi Durasi Tugas
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Dengan mengikuti langkah-langkah ini, Anda telah berhasil **menambahkan tugas ke proyek** dan mengelola durasinya menggunakan Aspose.Tasks untuk Java.

## Kesalahan Umum & Tips
- **Kesalahan:** Lupa mengonversi durasi sebelum melakukan operasi aritmatika dapat menghasilkan hasil yang salah. Selalu periksa satuannya dengan `duration.getTimeUnit()`.
- **Tips:** Gunakan `project.getDuration(value, TimeUnitType)` untuk membuat durasi dalam satuan yang diinginkan daripada mengonversinya nanti.
- **Kesalahan:** Menetapkan durasi negatif akan memunculkan pengecualian. Pastikan Anda memvalidasi nilai input.

## Kesimpulan
Dalam panduan ini kami membahas cara **menambahkan tugas ke proyek**, membaca durasi defaultnya, **mengatur durasi**, dan **mengonversi durasi** ke satuan waktu yang berbeda. Anda kini dapat mengintegrasikan teknik ini ke dalam aplikasi penjadwalan yang lebih besar untuk perencanaan proyek yang tepat.

## FAQ

### Apakah Aspose.Tasks kompatibel dengan semua versi Java?
Aspose.Tasks kompatibel dengan Java 6 dan versi yang lebih baru.

### Bisakah saya menggunakan Aspose.Tasks untuk proyek komersial?
Ya, Anda dapat menggunakan Aspose.Tasks untuk proyek pribadi maupun komersial. Kunjungi [di sini](https://purchase.aspose.com/buy) untuk detail lisensi.

### Di mana saya dapat menemukan dukungan dan sumber daya tambahan?
Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk dukungan komunitas dan diskusi.

### Bagaimana saya dapat memperoleh lisensi sementara untuk tujuan pengujian?
Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/) untuk pengujian dan evaluasi.

### Apakah ada percobaan gratis untuk Aspose.Tasks?
Ya, Anda dapat mengakses percobaan gratis [di sini](https://releases.aspose.com/) untuk menjelajahi Aspose.Tasks sebelum melakukan pembelian.

## Pertanyaan yang Sering Diajukan

**Q: Bagaimana cara mengubah durasi tugas setelah ditetapkan?**  
A: Dapatkan durasi saat ini dengan `task.get(Tsk.DURATION)`, ubah (mis., `add`, `subtract`, atau `convert`), dan kemudian set kembali menggunakan `task.set(Tsk.DURATION, newDuration)`.

**Q: Bisakah saya mengatur durasi dalam menit?**  
A: Ya, gunakan `TimeUnitType.Minute` saat memanggil `project.getDuration(value, TimeUnitType.Minute)`.

**Q: Apakah mengubah durasi secara otomatis memperbarui tanggal mulai dan selesai tugas?**  
A: Hanya jika mode penjadwalan proyek diatur ke otomatis. Jika tidak, Anda mungkin perlu menghitung ulang jadwal dengan `project.calculateCriticalPath()`.

**Q: Apakah memungkinkan untuk mengambil durasi sebagai angka mentah?**  
A: Panggil `duration.getTimeSpan()` untuk mendapatkan nilai numerik dalam satuan waktu saat ini.

**Q: Apa yang terjadi jika saya mengurangi lebih dari durasi saat ini?**  
A: API akan memunculkan `ArgumentOutOfRangeException`. Selalu validasi bahwa durasi yang dihasilkan tetap positif.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}