---
date: 2026-02-20
description: Pelajari cara mengatur tanggal mulai proyek dan mengelola variasi proyek
  menggunakan Aspose.Tasks untuk Java. Panduan ini juga menunjukkan cara mengatur
  durasi tugas secara efisien.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Atur tanggal mulai proyek & tangani variasi tugas Aspose.Tasks
url: /id/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atur tanggal mulai proyek & tangani variasi tugas Aspose.Tasks

## Pendahuluan
Dalam dunia manajemen proyek, **set project start date** adalah salah satu tindakan pertama yang Anda lakukan untuk memberikan fondasi yang kuat pada jadwal Anda. Aspose.Tasks untuk Java membuat langkah ini—dan penanganan variasi tugas selanjutnya—menjadi sederhana dan dapat diandalkan. Dalam tutorial ini Anda akan belajar cara mengatur tanggal mulai proyek, mengatur durasi tugas, dan mengelola variasi proyek secara efisien.

## Jawaban Cepat
- **Apa metode utama untuk mengatur tanggal mulai proyek?** Gunakan `project.set(Prj.START_DATE, …)` dengan instance `java.util.Calendar`.  
- **Kelas mana yang mewakili baseline untuk pelacakan variasi?** `BaselineType.Baseline`.  
- **Bisakah saya menyesuaikan tanggal mulai dan selesai tugas setelah baseline ditetapkan?** Ya, cukup perbarui `Tsk.START` dan `Tsk.STOP`.  
- **Apakah saya memerlukan lisensi untuk penggunaan pengembangan?** Lisensi sementara tersedia untuk evaluasi.  
- **Versi Aspose.Tasks mana yang bekerja dengan kode ini?** Rilis terbaru Aspose.Tasks untuk Java.

## Apa itu **set project start date**?
Menetapkan tanggal mulai proyek mendefinisikan hari kalender dari mana semua tanggal tugas dihitung. Ini memengaruhi perhitungan jadwal, analisis jalur kritis, dan pembuatan baseline, menjadikannya penting untuk manajemen variasi yang akurat.

## Mengapa mengatur tanggal mulai proyek dan mengelola variasi?
- **Prediktabilitas:** Menetapkan baseline yang diketahui untuk membandingkan kemajuan aktual.  
- **Fleksibilitas:** Memungkinkan Anda menyesuaikan tanggal tugas individu tanpa kehilangan rencana asli.  
- **Pelaporan:** Memungkinkan laporan variasi yang jelas yang menyoroti keterlambatan jadwal atau penyelesaian lebih awal.  

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Lingkungan Pengembangan Java – JDK terpasang dan IDE atau alat build siap.  
- Perpustakaan Aspose.Tasks – unduh perpustakaan **[di sini](https://releases.aspose.com/tasks/java/)**.  

## Impor Paket
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Langkah 1: Menyiapkan Proyek
Buat instance `Project` baru yang akan menyimpan semua tugas dan informasi jadwal.

```java
Project project = new Project();
```

## Langkah 2: Menambahkan Tugas
Tambahkan tugas di bawah tugas root. Ini akan menjadi item kerja yang nanti akan kami sesuaikan.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Langkah 3: Mengatur Tanggal Mulai dan Durasi
Tentukan tanggal mulai proyek dan berikan durasi pada tugas. Ini menunjukkan **set task duration** dalam praktik.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Langkah 4: Menetapkan Baseline
Buat baseline sehingga Anda dapat membandingkan tanggal yang direncanakan dengan tanggal aktual—penting untuk **manage project variances**.

```java
project.setBaseline(BaselineType.Baseline);
```

## Langkah 5: Menyesuaikan Tanggal Mulai dan Selesai Tugas
Ubah tanggal mulai dan selesai tugas untuk mensimulasikan skenario variasi.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*Silakan sesuaikan tanggal dan durasi agar sesuai dengan kebutuhan spesifik proyek Anda.*

## Masalah Umum & Tips
- **Baseline harus ditetapkan sebelum menyesuaikan tanggal.** Jika Anda mengubah tanggal terlebih dahulu, baseline akan menangkap jadwal yang diubah alih-alih rencana asli.  
- **Bulan kalender berbasis nol.** Ingat bahwa `Calendar.FEBRUARY` sama dengan bulan 1, bukan 2.  
- **Satuan durasi:** `project.getDuration(2)` membuat durasi dua hari secara default; sesuaikan satuannya jika Anda memerlukan jam atau minggu.

## Kesimpulan
Dengan menguasai cara **set project start date**, **set task duration**, dan **manage project variances**, Anda mendapatkan kontrol penuh atas jadwal proyek Anda menggunakan Aspose.Tasks untuk Java. Langkah-langkah di atas memberikan fondasi yang kuat yang dapat Anda kembangkan ke skenario yang lebih kompleks seperti proyek multi‑fase, alokasi sumber daya, dan pelaporan otomatis.

## Pertanyaan yang Sering Diajukan
### Apakah Aspose.Tasks cocok untuk semua kebutuhan manajemen proyek?
Aspose.Tasks adalah alat serbaguna yang cocok untuk berbagai kebutuhan manajemen proyek, menyediakan fleksibilitas dan fitur yang kuat.

### Bisakah saya mengintegrasikan Aspose.Tasks ke dalam proyek Java saya yang sudah ada?
Ya, Anda dapat dengan mudah mengintegrasikan Aspose.Tasks ke dalam proyek Java Anda dengan mengikuti dokumentasi yang disediakan **[di sini](https://reference.aspose.com/tasks/java/)**.

### Apakah lisensi sementara tersedia untuk Aspose.Tasks?
Ya, Anda dapat memperoleh lisensi sementara untuk Aspose.Tasks **[di sini](https://purchase.aspose.com/temporary-license/)**.

### Di mana saya dapat mendapatkan dukungan untuk Aspose.Tasks?
Untuk dukungan dan diskusi, kunjungi forum Aspose.Tasks **[di sini](https://forum.aspose.com/c/tasks/15)**.

### Bisakah saya mengunduh Aspose.Tasks untuk Java?
Ya, unduh versi terbaru Aspose.Tasks untuk Java **[di sini](https://releases.aspose.com/tasks/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks latest Java release  
**Author:** Aspose