---
title: Lembur dalam Tugas dengan Aspose.Tasks
linktitle: Lembur dalam Tugas dengan Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi manajemen lembur yang efisien dalam tugas proyek dengan Aspose.Tasks untuk Java. Sederhanakan pelacakan dan alokasi sumber daya dengan mudah.
weight: 23
url: /id/java/task-properties/overtimes-in-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lembur dalam Tugas dengan Aspose.Tasks

## Perkenalan
Mengelola lembur dalam tugas-tugas proyek sangat penting bagi manajer proyek dan pemimpin tim untuk memastikan pelacakan dan alokasi sumber daya yang akurat. Aspose.Tasks untuk Java memberikan solusi ampuh untuk menangani aspek terkait lembur dalam manajemen proyek. Dalam tutorial ini, kita akan mempelajari cara memanfaatkan Aspose.Tasks untuk mengelola dan menganalisis lembur secara efektif dalam tugas proyek.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di mesin Anda.
-  Aspose.Tasks untuk Java: Unduh dan instal perpustakaan Aspose.Tasks. Anda dapat menemukan perpustakaan dan dokumentasinya[Di Sini](https://reference.aspose.com/tasks/java/).
- File Proyek: Siapkan file proyek (misalnya, TaskOvertimes.mpp) untuk digunakan selama tutorial.
## Paket Impor
Di proyek Java Anda, impor paket Aspose.Tasks yang diperlukan untuk memanfaatkan fungsinya. Tambahkan pernyataan import berikut:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```
## Langkah 1: Buat Proyek Baru
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
// Buat proyek baru
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```
## Langkah 2: Ulangi Tugas dan Cetak Detail Lembur
```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Tetapkan persen selesai
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```
Ikuti langkah-langkah berikut untuk memanfaatkan Aspose.Tasks untuk Java secara efektif dalam mengelola dan menganalisis lembur dalam tugas proyek Anda. Jangan ragu untuk menyesuaikan kode sesuai dengan kebutuhan spesifik proyek Anda.
## Kesimpulan
Aspose.Tasks untuk Java menyederhanakan manajemen lembur dalam tugas proyek, menyediakan seperangkat alat yang tangguh bagi pengembang. Dengan mengikuti panduan ini, Anda dapat mengintegrasikan Aspose.Tasks dengan lancar ke dalam proyek Java Anda, memastikan manajemen proyek yang efisien.
## FAQ
### Apakah Aspose.Tasks cocok untuk manajemen proyek skala besar?
Ya, Aspose.Tasks dirancang untuk menangani proyek dengan berbagai ukuran, mulai dari inisiatif skala kecil hingga proyek besar dan kompleks.
### Bisakah saya mengintegrasikan Aspose.Tasks dengan kerangka Java lainnya?
Sangat! Aspose.Tasks terintegrasi secara mulus dengan kerangka kerja Java lainnya, meningkatkan keserbagunaannya dalam pengembangan proyek.
### Apakah ada pertimbangan lisensi untuk menggunakan Aspose.Tasks?
 Ya, Anda dapat menemukan rincian perizinan dan mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat mencari bantuan atau mendiskusikan pertanyaan terkait Aspose.Tasks?
 Mengunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15) untuk terlibat dengan komunitas dan mencari dukungan.
### Apakah ada versi uji coba gratis yang tersedia untuk Aspose.Tasks?
 Ya, Anda dapat mengakses versi uji coba gratis[Di Sini](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
