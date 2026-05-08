---
date: 2026-01-07
description: Pelajari cara menambahkan sumber daya ke proyek dan menangani properti
  penundaan leveling untuk penugasan sumber daya menggunakan Aspose.Tasks untuk Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Menambahkan Sumber Daya ke Proyek dan Menangani Properti Penundaan Penyeimbangan
  di Aspose.Tasks
url: /id/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Sumber Daya ke Proyek dan Menangani Properti Penundaan Leveling di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini, Anda akan belajar **cara menambahkan sumber daya ke proyek** sekaligus mengelola properti penundaan leveling untuk penugasan sumber daya dengan Aspose.Tasks untuk Java. Baik Anda membangun mesin penjadwalan atau mengotomatisasi pembaruan proyek, menguasai langkah‑langkah ini memungkinkan Anda menjaga data proyek tetap akurat tanpa perlu menginstal Microsoft Project.

## Jawaban Cepat
- **Apa arti “add resource to project”?** Itu membuat entri sumber daya baru yang dapat ditugaskan ke tugas.  
- **Bisakah saya mengatur penundaan leveling setelah penugasan?** Ya, dengan menggunakan bidang `Asn.DELAY` atau `Asn.LEVELING_DELAY`.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode ini?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi berbayar diperlukan untuk produksi.  
- **Versi Java mana yang didukung?** Java 8 atau yang lebih baru.  
- **Apakah ini kompatibel dengan semua format file MS Project?** Aspose.Tasks mendukung .MPP, .XML, .XER, dan lainnya.

## Apa itu “add resource to project” di Aspose.Tasks?
Menambahkan sumber daya ke proyek berarti membuat objek `Resource` di dalam model `Project`. Objek ini kemudian dapat dihubungkan ke tugas melalui `ResourceAssignment`, memungkinkan Anda melacak pekerjaan, biaya, dan pengaturan leveling.

## Mengapa menangani properti penundaan leveling?
Penundaan leveling membantu penjadwal menyebarkan pekerjaan ketika sumber daya terlalu dialokasikan. Dengan mengatur penundaan, Anda memberi tahu mesin untuk menunda mulai penugasan, menghindari konflik dan menjaga proyek tetap realistis.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda telah menginstal Java JDK di sistem Anda. Anda dapat mengunduh dan menginstalnya dari [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Perpustakaan Aspose.Tasks untuk Java: Unduh perpustakaan Aspose.Tasks untuk Java dari [halaman unduhan](https://releases.aspose.com/tasks/java/).

## Impor Paket
Pertama, impor paket yang diperlukan ke dalam proyek Java Anda untuk menggunakan fungsionalitas Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Langkah 1: Buat Objek Project
Instansiasi objek `Project`, yang akan berfungsi sebagai wadah untuk semua tugas, sumber daya, dan penugasan:
```java
Project prj = new Project();
```

## Langkah 2: Buat Tugas
Tambahkan tugas ke proyek. Ini menunjukkan **cara menambahkan tugas** secara programatis:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Langkah 3: Atur Tanggal Mulai Tugas dan Durasi
Tentukan kapan tugas dimulai dan berapa lama akan berjalan:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Langkah 4: Tambahkan Sumber Daya
Sekarang kita **add resource to project** dengan membuat entri `Resource` baru:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Langkah 5: Buat Penugasan Sumber Daya
Hubungkan tugas dan sumber daya yang baru ditambahkan bersama-sama:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Langkah 6: Atur Penundaan Leveling
Konfigurasikan penundaan leveling untuk penugasan. Mengaturnya ke nol berarti tidak ada penundaan tambahan, tetapi Anda dapat menyesuaikan nilai sesuai kebutuhan:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Langkah 7: Tampilkan Hasil
Cetak properti penting untuk memverifikasi bahwa semuanya telah diatur dengan benar:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Kesalahan Umum & Tips
- **Kesalahan:** Lupa mengatur tanggal mulai tugas dapat menyebabkan penugasan default ke awal proyek.  
- **Tip:** Gunakan `prj.getDuration(value, TimeUnitType.Day)` untuk mengontrol granularitas penundaan.  
- **Tip:** Setelah menambahkan beberapa sumber daya, panggil `prj.updateResourceAssignments()` agar penjadwal menghitung ulang leveling.

## Kesimpulan
Dengan mengikuti langkah‑langkah ini, Anda kini mengetahui **cara menambahkan sumber daya ke proyek**, menugaskannya ke tugas, dan mengelola properti penundaan leveling menggunakan Aspose.Tasks untuk Java. Pengetahuan ini memungkinkan Anda membangun solusi otomatisasi proyek yang kuat dan tetap selaras dengan kendala sumber daya dunia nyata.

## FAQ
### Q: Bisakah saya menggunakan Aspose.Tasks dengan perpustakaan Java lain?

A: Ya, Aspose.Tasks dapat diintegrasikan dengan perpustakaan Java lain untuk meningkatkan kemampuan manajemen proyek.

### Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?

A: Ya, Aspose.Tasks mendukung berbagai versi file Microsoft Project, memastikan kompatibilitas di berbagai lingkungan.

### Q: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks?

A: Anda dapat menemukan dukungan dan sumber daya di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q: Bisakah saya mencoba Aspose.Tasks sebelum membeli?

A: Ya, Anda dapat memperoleh percobaan gratis Aspose.Tasks dari [halaman rilis](https://releases.aspose.com/).

### Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks?

A: Anda dapat meminta lisensi sementara dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk keperluan evaluasi.

## Pertanyaan Umum Tambahan

**Q: Apa yang terjadi jika saya mengatur penundaan leveling tidak nol?**  
A: Penjadwal akan menunda mulai penugasan selama durasi yang ditentukan, membantu menyelesaikan alokasi berlebih.

**Q: Bisakah saya mengambil penundaan leveling setelah menyimpan proyek?**  
A: Ya, Anda dapat membuka kembali file proyek dan membaca properti `Asn.DELAY` dari penugasan.

**Q: Apakah ada cara untuk menerapkan penundaan leveling ke semua penugasan sekaligus?**  
A: Anda dapat mengiterasi `prj.getResourceAssignments()` dan mengatur penundaan untuk setiap penugasan dalam sebuah loop.

---

**Terakhir Diperbarui:** 2026-01-07  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}