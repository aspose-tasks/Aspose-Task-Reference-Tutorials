---
date: 2025-12-18
description: Pelajari cara membuat tampilan di Aspose.Tasks untuk Java, termasuk cara
  menyimpan tampilan proyek dan mengatur properti tampilan. Tingkatkan efisiensi manajemen
  proyek dengan tampilan MS Project khusus yang disesuaikan.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Cara Membuat Tampilan - Tampilan Kustom MS Project di Aspose.Tasks'
url: /id/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Tampilan: Tampilan Kustom MS Project di Aspose.Tasks

## Perkenalan
Jika Anda mencari **cara membuat tampilan** yang sesuai dengan kebutuhan pelaporan unik proyek Anda, Anda berada di tempat yang tepat. Dalam proyek manajemen, penyesuaian tampilan dapat secara dramatis meningkatkan kecerahan dan efisiensi saat menangani tugas dan sumber daya. **Aspose.Tasks for Java** menyediakan API yang kaya untuk **menambahkan tampilan kustom java**‑style, memungkinkan Anda menyesuaikan tampilan MS Project persist seperti yang Anda butuhkan. Pada tutorial ini kami akan memandu proses langkah demi langkah, mulai dari menyiapkan proyek hingga menyimpan tampilan proyek.

## Jawaban Cepat
- **Apa tujuan utamanya?** Untuk membuat dan menyimpan tampilan kustom MS Project menggunakan Aspose.Tasks for Java.
- **Kelas mana yang membuat tampilan?** `GanttChartView` (atau tipe tampilan lainnya).
- **Bagaimana cara menampilkan tampilan di menu?** Atur `view.setShowInMenu(true)`.
- **Bagaimana cara menyimpan tampilan dengan proyek?** Gunakan `MPPSaveOptions` dengan `setWriteViewData(true)`.
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tugas yang valid diperlukan untuk penggunaan produksi.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

### Lingkungan Pengembangan Java
Pastikan Java telah terinstal di sistem Anda.

### Aspose.Tugas untuk Java
Unduh dan instal Aspose.Tasks for Java dari [di sini](https://releases.aspose.com/tasks/java/).

## Impor Paket
Pertama, impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## Langkah 1: Siapkan Proyek
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Langkah 2: Buat Tampilan
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Langkah 3: Sesuaikan Properti Tampilan *(atur properti tampilan)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### Cara Menampilkan Menu Tampilan
Pemanggilan `view.setShowInMenu(true)` memastikan tampilan yang baru dibuat muncul di **view menu** MS Project, memberikan akses cepat bagi pengguna akhir.

## Langkah 4: Sesuaikan Pengaturan Tampilan
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Langkah 5: Tambahkan Tampilan ke Proyek *(tambahkan tampilan kustom Java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Langkah 6: Simpan Proyek *(simpan tampilan proyek)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Mengapa Menyimpan Tampilan Proyek Itu Penting
Menetapkan `options.setWriteViewData(true)` memberi tahu Aspose.Tasks untuk **save project view** informasi di dalam file MPP, sehingga tampilan kustom tetap ada di antara sesi.

## Langkah 7: Periksa Lihat Properti
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Kasus Penggunaan Umum
- **Pelaporan Pemangku Kepentingan:** Buat tampilan yang hanya menampilkan pencapaian tingkat tinggi dan tugas kritis.
- **Alokasi Sumber Daya:** Bangun tampilan yang menampilkan sumber daya beserta tugas yang mereka kerjakan untuk pemeriksaan kapasitas cepat.
- **Dokumen Siap Cetak:** Sesuaikan pengaturan halaman (seperti pada Langkah4) untuk menghasilkan snapshot proyek yang siap dicetak.

## Tip Mengatasi Masalah
- **Tampilan Tidak Muncul di Menu:** Pastikan `view.setShowInMenu(true)` dipanggil sebelum menyimpan.
- **Kolom Hilang di Cetakan:** Pastikan `setFirstColumnsCount` sesuai dengan kolom yang Anda perlukan dan `setPrintFirstColumnsCountOnAllPages(true)` diaktifkan.
- **Pengecualian Lisensi:** Jika Anda menemukan kesalahan lisensi, pastikan file lisensi Aspose.Tasks yang valid dimuat sebelum membuat objek `Project`.

## Pertanyaan yang Sering Diajukan
### Q1: Dapatkah saya menyesuaikan tampilan di luar diagram Gantt?
A: Ya, Aspose.Tasks for Java menyediakan pengaturan untuk menyesuaikan berbagai jenis tampilan selain Gantt chart, termasuk tabel dan grafik.

### Q2: Apakah Aspose.Tasks untuk Java cocok untuk proyek berskala besar?
J: Tentu saja. Perpustakaan ini dirancang untuk menangani proyek berukuran apa pun, menawarkan kinerja yang kuat dan manajemen memori yang efisien.

### Q3: Apakah Aspose.Tasks untuk Java mendukung ekspor tampilan ke format berbeda?
A: Ya, Anda dapat mengekspor tampilan ke PDF, XLSX, HTML, dan format lainnya, memastikan berbagi dengan lancar di berbagai platform.

### Q4: Bisakah saya mengotomatiskan pembuatan tampilan kustom menggunakan Aspose.Tasks untuk Java?
J: Tentu. API memungkinkan otomatisasi penuh, memungkinkan Anda menghasilkan dan mengelola tampilan kustom secara terprogram.

### Q5: Apakah ada forum komunitas untuk dukungan Aspose.Tasks untuk Java?
A: Ya, Anda dapat menemukan bantuan dan berinteraksi dengan pengguna lain di [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) untuk pertanyaan dan diskusi terkait Java.

---

**Terakhir Diperbarui:** 18-12-2025
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12
**Penulis:** Beranggapan 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}