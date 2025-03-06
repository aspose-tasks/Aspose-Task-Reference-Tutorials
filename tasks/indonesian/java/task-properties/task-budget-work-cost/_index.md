---
title: Manajemen Anggaran, Pekerjaan, dan Biaya untuk Tugas di Aspose.Tasks
linktitle: Manajemen Anggaran, Pekerjaan, dan Biaya untuk Tugas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Buka manajemen anggaran dan biaya yang efisien dalam proyek Java dengan Aspose.Tasks. Jelajahi panduan langkah demi langkah untuk integrasi yang lancar.
weight: 31
url: /id/java/task-properties/task-budget-work-cost/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manajemen Anggaran, Pekerjaan, dan Biaya untuk Tugas di Aspose.Tasks

## Perkenalan
Mengelola anggaran, pekerjaan, dan biaya secara efisien sangat penting untuk keberhasilan pelaksanaan proyek. Aspose.Tasks untuk Java memberikan solusi tangguh untuk menangani tugas terkait proyek, termasuk penganggaran dan manajemen biaya. Dalam tutorial ini, kita akan mempelajari cara memanfaatkan Aspose.Tasks untuk Java untuk mencapai manajemen anggaran, pekerjaan, dan biaya yang efektif dalam proyek Anda.
## Prasyarat
Sebelum kita mempelajari tutorialnya, pastikan Anda memiliki prasyarat berikut:
- Lingkungan Pengembangan Java: Pastikan Anda telah menyiapkan lingkungan pengembangan Java di sistem Anda.
-  Aspose.Tasks untuk Perpustakaan Java: Unduh dan instal perpustakaan Aspose.Tasks untuk Java. Anda dapat menemukan perpustakaan[Di Sini](https://releases.aspose.com/tasks/java/).
## Paket Impor
Di proyek Java Anda, mulailah dengan mengimpor paket yang diperlukan. Ini memastikan bahwa Anda memiliki akses ke fungsionalitas Aspose.Tasks. Sertakan baris berikut di awal file Java Anda:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```
## 1. Atur Direktori Dokumen
Mulailah dengan mengatur jalur ke direktori dokumen Anda. Di sinilah file proyek Anda disimpan. Gunakan cuplikan kode berikut:
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
```
## 2. Muat Proyek
Muat file proyek menggunakan perpustakaan Aspose.Tasks. Ganti "BudgetWorkAndCost.mpp" dengan nama file proyek Anda.
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```
## 3. Ambil Anggaran Proyek dan Sumber Daya
Ambil dan tampilkan anggaran proyek dan sumber daya menggunakan kode berikut:
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```
## 4. Menampilkan Anggaran Penugasan
Ulangi penugasan proyek dan tampilkan informasi anggaran:
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```
Ulangi langkah-langkah ini sesuai kebutuhan untuk menggabungkan fungsi anggaran, pekerjaan, dan manajemen biaya dalam proyek Aspose.Tasks untuk Java Anda.
## Kesimpulan
Mengelola anggaran, pekerjaan, dan biaya secara efektif sangat penting untuk keberhasilan proyek. Aspose.Tasks untuk Java menyederhanakan proses ini, memberikan solusi komprehensif untuk kebutuhan manajemen proyek Anda. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah mengintegrasikan manajemen anggaran dan biaya ke dalam proyek Java Anda.
## FAQ
### Bisakah saya menggunakan Aspose.Tasks untuk Java dengan kerangka Java lainnya?
Ya, Aspose.Tasks untuk Java kompatibel dengan berbagai kerangka kerja Java, memastikan fleksibilitas dalam integrasi.
### Apakah ada versi uji coba yang tersedia untuk Aspose.Tasks untuk Java?
 Ya, Anda dapat mengakses uji coba gratis Aspose.Tasks untuk Java[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks untuk Java?
 Jelajahi forum komunitas Aspose.Tasks[Di Sini](https://forum.aspose.com/c/tasks/15) untuk dukungan dan diskusi.
### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?
 Dapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/) untuk tujuan pengujian dan evaluasi.
### Apakah ada sumber daya tambahan untuk Aspose.Tasks untuk Java?
 Lihat dokumentasi[Di Sini](https://reference.aspose.com/tasks/java/) untuk informasi mendalam dan contoh.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
