---
date: 2026-06-05
description: Pelajari cara membuat resource assignment dengan Aspose.Tasks untuk Java,
  menambahkan sumber daya ke proyek, dan mengelola leveling delay properties.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Kelola Leveling Delay Properties untuk Resource Assignments di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Buat Resource Assignment dengan Aspose.Tasks untuk Java
url: /id/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Penugasan Sumber Daya dengan Aspose.Tasks untuk Java

Dalam panduan komprehensif ini Anda akan belajar **cara membuat penugasan sumber daya aspotasks** menggunakan pustaka Aspose.Tasks untuk Java. Baik Anda membangun mesin penjadwalan khusus, mengotomatisasi pembaruan proyek massal, atau sekadar perlu memanipulasi file Microsoft Project tanpa aplikasi desktop, menguasai langkah‑langkah ini memungkinkan Anda menjaga data proyek tetap akurat dan sepenuhnya dapat dikontrol.

## Jawaban Cepat
- **Apa arti “add resource to project”?** Itu membuat entri sumber daya baru yang kemudian dapat ditetapkan ke tugas.  
- **Bisakah saya mengatur penundaan leveling setelah penugasan?** Ya, dengan menggunakan bidang `Asn.DELAY` atau `Asn.LEVELING_DELAY`.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode ini?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi berbayar diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Java 8 atau lebih baru.  
- **Apakah ini kompatibel dengan semua format file MS Project?** Aspose.Tasks mendukung lebih dari 12 format—termasuk .MPP, .XML, .XER, .CSV, .PDF, dan lainnya.

## Apa itu “add resource to project” dalam Aspose.Tasks?
Menambahkan sumber daya ke proyek berarti membuat objek `Resource` di dalam model `Project`. Objek ini kemudian dapat dihubungkan ke tugas melalui `ResourceAssignment`, memungkinkan Anda melacak pekerjaan, biaya, dan pengaturan leveling. Dengan memasukkan sumber daya, Anda memberi penjadwal sesuatu untuk dialokasikan, dan Anda dapat kemudian menanyakan atau mengubah propertinya seperti ketersediaan, tarif, dan penugasan kalender.

## Mengapa menangani properti penundaan leveling?
Penundaan leveling memberi tahu penjadwal untuk menunda mulai penugasan yang terlalu dialokasikan, menyebarkan pekerjaan lebih merata sepanjang garis waktu. Dengan mengonfigurasi penundaan ini, Anda menghindari tanggal mulai yang tidak realistis, mengurangi peringatan alokasi berlebih, dan menghasilkan jadwal yang mencerminkan batasan sumber daya dunia nyata. Menyesuaikan penundaan juga memberi Anda kontrol detail tentang berapa banyak kelonggaran yang dapat dimasukkan mesin, membantu Anda memenuhi tenggat proyek sambil menghormati batas sumber daya.

## Cara membuat penugasan sumber daya aspotasks?
Muat objek `Project` Anda, tambahkan sebuah tugas, buat sebuah sumber daya, dan kemudian hubungkan mereka dengan `ResourceAssignment`. Alur end‑to‑end ini memungkinkan Anda secara programatis membangun struktur proyek lengkap dan langsung mengontrol penundaan leveling pada penugasan. Proses ini menunjukkan alur kerja inti: inisialisasi proyek, definisi tugas, pembuatan sumber daya, pengaitan penugasan, dan akhirnya menerapkan parameter penjadwalan seperti penundaan leveling.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan Anda memiliki Java JDK terpasang di sistem Anda. Anda dapat mengunduh dan menginstalnya dari [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Perpustakaan Aspose.Tasks untuk Java: Unduh perpustakaan Aspose.Tasks untuk Java dari [halaman unduhan](https://releases.aspose.com/tasks/java/).

## Impor Paket
Impor berikut membawa kelas inti Aspose.Tasks yang diperlukan untuk manipulasi proyek.  
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

## Cara membuat penugasan sumber daya aspotasks?
Muat objek `Project` Anda, tambahkan sebuah tugas, buat sebuah sumber daya, dan kemudian hubungkan mereka dengan `ResourceAssignment`. Alur end‑to‑end ini memungkinkan Anda secara programatis membangun struktur proyek lengkap dan langsung mengontrol penundaan leveling pada penugasan. Proses ini menunjukkan alur kerja inti: inisialisasi proyek, definisi tugas, pembuatan sumber daya, pengaitan penugasan, dan akhirnya menerapkan parameter penjadwalan seperti penundaan leveling.

## Langkah 1: Buat Objek Project
Kelas `Project` adalah kontainer tingkat‑atas Aspose.Tasks yang mewakili seluruh file proyek dalam memori. Menginstansiasinya memberi Anda kanvas bersih untuk menambahkan tugas, sumber daya, dan penugasan.
```java
Project prj = new Project();
```

## Langkah 2: Buat Tugas
Kelas `Task` mewakili satu item kerja dalam jadwal. Menambahkan tugas menunjukkan **cara menambahkan tugas** secara programatis dan menyediakan target untuk penugasan sumber daya yang akan datang.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Langkah 3: Atur Tanggal Mulai Tugas dan Durasi
Tentukan kapan tugas dimulai dan berapa lama akan berjalan. Tanggal mulai yang tepat sangat penting karena perhitungan leveling menggunakannya sebagai dasar untuk penundaan apa pun yang Anda tentukan kemudian.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Langkah 4: Tambahkan Sumber Daya
Sekarang kita **menambahkan sumber daya ke proyek** dengan membuat entri `Resource` baru. Kelas `Resource` merupakan representasi dari orang, peralatan, atau material yang dapat ditetapkan ke tugas.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Langkah 5: Buat Penugasan Sumber Daya
`ResourceAssignment` menghubungkan `Task` dan `Resource`. Asosiasi ini memungkinkan Anda mencatat pekerjaan, biaya, dan detail leveling untuk sumber daya tertentu pada tugas tertentu.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Langkah 6: Atur Penundaan Leveling
Konfigurasikan penundaan leveling untuk penugasan. Mengaturnya ke nol berarti tidak ada penundaan tambahan, tetapi Anda dapat menyesuaikan nilai sesuai kebutuhan. Field `Asn.DELAY` menyimpan penundaan dalam menit; `Asn.LEVELING_DELAY` adalah alias yang berfungsi sama.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Langkah 7: Tampilkan Hasil
Cetak properti penting untuk memverifikasi bahwa semuanya telah diatur dengan benar. Langkah ini membantu Anda memastikan bahwa nilai sumber daya, tugas, dan penundaan tepat seperti yang Anda harapkan sebelum menyimpan file.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Kesalahan Umum & Tips
- **Kesalahan:** Lupa mengatur tanggal mulai tugas dapat menyebabkan penugasan default ke mulai proyek.  
- **Tip:** Gunakan `prj.getDuration(value, TimeUnitType.Day)` untuk mengontrol granularitas penundaan.  
- **Tip:** Setelah menambahkan beberapa sumber daya, panggil `prj.updateResourceAssignments()` agar penjadwal menghitung ulang leveling.  
- **Pro tip:** Untuk proyek besar (10.000+ tugas) aktifkan `prj.setAutoCalculate(false)` sebelum pembaruan massal, kemudian panggil `prj.calculate()` sekali di akhir untuk meningkatkan kinerja.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks dengan perpustakaan Java lain?**  
A: Ya, Aspose.Tasks terintegrasi dengan mulus dengan perpustakaan seperti Jackson untuk penanganan JSON atau Apache POI untuk operasi spreadsheet tambahan, memungkinkan Anda membangun solusi manajemen proyek yang lebih kaya.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi file Microsoft Project?**  
A: Aspose.Tasks mendukung lebih dari 12 format file—termasuk .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML, dan .MPP12—memastikan penyuntingan bolak‑balik yang mulus di semua versi utama Project.

**Q: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks?**  
A: Anda dapat menemukan dukungan dan diskusi komunitas di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Bisakah saya mencoba Aspose.Tasks sebelum membeli?**  
A: Ya, percobaan gratis yang berfungsi penuh tersedia di [halaman rilis](https://releases.aspose.com/).

**Q: Bagaimana saya dapat memperoleh lisensi sementara untuk evaluasi?**  
A: Minta lisensi sementara dari [halaman lisensi sementara](https://purchase.aspose.com/temporary-license/) untuk menjalankan perpustakaan tanpa batasan evaluasi.

---

**Terakhir Diperbarui:** 2026-06-05  
**Diuji Dengan:** Aspose.Tasks for Java 24.11  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Kelola Anggaran Penugasan Java menggunakan Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [Cara Menghentikan Penugasan dan Melanjutkan Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}