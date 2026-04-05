---
date: 2026-02-26
description: Pelajari cara memecah tugas dengan Aspose.Tasks untuk Java – panduan
  definitif tentang cara memecah tugas, mengatur kalender proyek, dan membuat penugasan
  sumber daya.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Membagi Tugas di Aspose.Tasks
url: /id/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membagi Tugas di Aspose.Tasks

## Introduction
Jika Anda mencari **cara membagi tugas** dalam proyek berbasis Java, Anda berada di tempat yang tepat. Aspose.Tasks untuk Java memberikan cara yang bersih dan programatis untuk memecah tugas yang berlangsung lama menjadi bagian‑bagian yang lebih kecil dan dapat dikelola, yang membantu dalam penyeimbangan sumber daya, pelaporan yang akurat, dan jadwal proyek yang lebih ketat. Dalam tutorial ini kami akan membahas seluruh proses—dari menyiapkan kalender proyek hingga membuat penugasan sumber daya dan akhirnya membagi tugas menjadi beberapa segmen.

## Quick Answers
- **Apa itu pembagian tugas?** Membagi satu tugas menjadi beberapa interval yang lebih kecil sambil mempertahankan total durasinya.  
- **Mengapa membagi tugas di Java?** Hal ini memungkinkan alokasi sumber daya yang tepat dan pelacakan kemajuan yang lebih baik.  
- **Perpustakaan mana yang membantu?** Aspose.Tasks untuk Java menyediakan metode bawaan untuk membagi dan fase waktu.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi diperlukan untuk produksi.  
- **Versi Java apa yang didukung?** Perpustakaan ini bekerja dengan Java 8 dan yang lebih baru.

## Prerequisites
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Java Development Kit (JDK) terpasang di mesin Anda.  
- Perpustakaan Aspose.Tasks untuk Java diunduh dan ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari [dokumentasi Aspose.Tasks untuk Java](https://reference.aspose.com/tasks/java/).

## Import Packages
Mulailah dengan mengimpor paket yang diperlukan ke dalam proyek Java Anda:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Step 1: Create a New Project
Mulailah dengan membuat proyek baru menggunakan perpustakaan Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Step 2: Set Project Calendar
Menetapkan **kalender proyek** menentukan hari kerja, hari libur, dan keseluruhan timeline untuk jadwal Anda. Langkah ini penting untuk perhitungan fase waktu yang akurat.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Step 3: Add a Root Task
Setiap proyek memerlukan kontainer root. Menambahkan tugas root memberi Anda tempat untuk melampirkan semua tugas berikutnya.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Step 4: Add a New Task to Split
Buat tugas yang ingin Anda bagi. Di sini kami menetapkan durasi tiga hari sebagai contoh.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Step 5: Create a Resource Assignment
**Penugasan sumber daya** menghubungkan sumber daya (atau placeholder) ke tugas. Ini diperlukan sebelum menghasilkan data fase waktu.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Step 6: Generate Timephased Data
Data fase waktu menggambarkan bagaimana pekerjaan didistribusikan selama durasi tugas. Menghasilkannya mempersiapkan tugas untuk dibagi.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Step 7: Split the Task
Sekarang kami **membagi tugas menjadi bagian‑bagian**. Dalam contoh ini kami membagi tugas tiga hari menjadi tiga segmen satu hari.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Why Split Tasks?
Membagi tugas memberi Anda kontrol yang lebih terperinci atas:
- **Penyeimbangan sumber daya:** Menetapkan sumber daya yang berbeda untuk setiap segmen.
- **Pelacakan kemajuan:** Memperbarui status per segmen.
- **Pelaporan:** Menghasilkan diagram Gantt dan laporan yang lebih detail.

## Common Issues and Solutions
- **Data kalender hilang:** Pastikan Anda memanggil `timephasedDataFromTaskDuration` sebelum membagi.  
- **Segmen dengan durasi nol:** Verifikasi bahwa setiap interval yang dibagi memiliki durasi bukan nol; jika tidak, perpustakaan akan mengabaikannya.  
- **Pengecualian lisensi:** Menjalankan tanpa lisensi yang valid dapat menambahkan watermark pada file yang diekspor.

## Frequently Asked Questions
### Can I split tasks with different durations?
Ya, Anda dapat menyesuaikan durasi setiap bagian agar sesuai dengan kebutuhan proyek Anda.

### Is Aspose.Tasks for Java compatible with all Java versions?
Aspose.Tasks untuk Java dirancang untuk bekerja mulus dengan Java 8 dan yang lebih baru, memastikan kompatibilitas yang luas.

### Can I use Aspose.Tasks for Java for free?
Aspose.Tasks untuk Java menawarkan percobaan gratis, memungkinkan Anda menjelajahi fiturnya sebelum melakukan pembelian.

### How can I get support for Aspose.Tasks for Java?
Kunjungi [forum dukungan Aspose.Tasks untuk Java](https://forum.aspose.com/c/tasks/15) untuk mendapatkan bantuan dan terhubung dengan komunitas.

### Do I need a temporary license for Aspose.Tasks for Java?
Anda dapat memperoleh lisensi sementara dari [tautan ini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}