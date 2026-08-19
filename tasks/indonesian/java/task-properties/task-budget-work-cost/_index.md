---
date: 2026-02-28
description: Pelajari cara mengelola anggaran, pekerjaan, dan biaya untuk tugas dalam
  proyek Java menggunakan Aspose.Tasks. Panduan ini juga menunjukkan cara menghitung
  biaya tugas secara efisien.
linktitle: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengelola Anggaran, Pekerjaan, dan Biaya di Aspose.Tasks Java
url: /id/java/task-properties/task-budget-work-cost/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengelola Anggaran, Pekerjaan, dan Biaya dalam Aspose.Tasks Java

Mengelola keuangan proyek merupakan tanggung jawab utama bagi setiap manajer proyek. Dalam tutorial ini Anda akan menemukan **cara mengelola anggaran** untuk tugas, pekerjaan, dan sumber daya menggunakan Aspose.Tasks Java API, serta melihat cara **menghitung biaya tugas** ketika Anda memerlukan pelaporan keuangan yang tepat. Pada akhir panduan, Anda akan dapat membaca, menampilkan, dan memanipulasi bidang terkait anggaran langsung dari file Microsoft Project Anda.

## Jawaban Cepat
- **Apa yang dimaksud dengan “budget work”?** Jumlah pekerjaan (dalam jam) yang dialokasikan untuk sebuah tugas atau sumber daya.  
- **Bisakah saya mengambil biaya anggaran secara programatis?** Ya, dengan menggunakan bidang `BUDGET_COST` pada tugas, sumber daya, atau penugasan.  
- **Apakah saya memerlukan lisensi untuk Aspose.Tasks?** Lisensi diperlukan untuk produksi; versi percobaan gratis tersedia.  
- **Versi Java mana yang didukung?** Aspose.Tasks bekerja dengan Java 8 dan yang lebih baru.  
- **Apakah memungkinkan menghitung biaya tugas dari penugasan?** Tentu – jumlahkan nilai `BUDGET_COST` pada penugasan.

## Apa Itu Manajemen Anggaran di Aspose.Tasks?
Aspose.Tasks menyimpan informasi anggaran dalam bidang khusus (`BUDGET_WORK`, `BUDGET_COST`) untuk tugas, sumber daya, dan penugasan. Bidang-bidang ini memungkinkan Anda merencanakan upaya dan biaya moneter yang diharapkan sebelum pekerjaan apa pun dilakukan, sehingga memungkinkan peramalan yang akurat dan analisis varians.

## Mengapa Menghitung Biaya Tugas?
- Melacak kinerja keuangan terhadap perkiraan asli.
- Menghasilkan laporan berbasis biaya untuk pemangku kepentingan.
- Mengidentifikasi tugas yang melebihi anggaran mereka secara dini.

## Prasyarat
Sebelum kita masuk ke kode, pastikan Anda memiliki:

- Lingkungan pengembangan Java (JDK 8+).
- Perpustakaan Aspose.Tasks untuk Java – unduh **[di sini](https://releases.aspose.com/tasks/java/)**.
- File contoh Microsoft Project (misalnya `BudgetWorkAndCost.mpp`) yang ditempatkan di direktori yang diketahui.

## Impor Paket
Dalam proyek Java Anda, mulailah dengan mengimpor paket yang diperlukan. Ini memastikan Anda memiliki akses ke fungsionalitas Aspose.Tasks. Sertakan baris berikut di awal file Java Anda:
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

## Langkah 1: Atur Direktori Dokumen
Mulailah dengan mengatur jalur ke direktori dokumen Anda. Di sinilah file proyek Anda disimpan.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Langkah 2: Muat Proyek
Muat file proyek menggunakan perpustakaan Aspose.Tasks. Ganti `"BudgetWorkAndCost.mpp"` dengan nama file proyek Anda.
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```

## Langkah 3: Ambil Anggaran Proyek dan Sumber Daya
Ambil dan tampilkan anggaran tingkat proyek dan tingkat sumber daya. Langkah ini menunjukkan cara **menghitung biaya tugas** dengan membaca nilai yang disimpan.
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```

## Langkah 4: Tampilkan Anggaran Penugasan
Iterasi melalui penugasan pada tugas ringkasan (atau tugas apa pun) dan tampilkan informasi anggaran setiap penugasan. Ini memungkinkan Anda melihat biaya yang dialokasikan per sumber daya.
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```

## Masalah Umum & Tips Profesional
- **Nilai null:** Jika bidang anggaran mengembalikan `null`, file proyek mungkin tidak berisi data tersebut. Gunakan pemeriksaan `project.getRootTask().get(Tsk.BUDGET_WORK) != null` sebelum mencetak.
- **UID tidak tepat:** Pastikan UID sumber daya yang Anda query (`getByUid(2)`) ada; jika tidak, Anda akan mendapatkan `NullPointerException`.
- **Pemformatan mata uang:** `BUDGET_COST` mengembalikan nilai double mentah. Formatlah menggunakan `NumberFormat.getCurrencyInstance()` untuk output yang ramah pengguna.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dengan kerangka kerja Java lainnya?**  
A: Ya, Aspose.Tasks untuk Java kompatibel dengan berbagai kerangka kerja Java, memastikan fleksibilitas dalam integrasi.

**Q: Apakah tersedia versi percobaan untuk Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat mengakses percobaan gratis Aspose.Tasks untuk Java **[di sini](https://releases.aspose.com/)**.

**Q: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks untuk Java?**  
A: Jelajahi forum komunitas Aspose.Tasks **[di sini](https://forum.aspose.com/c/tasks/15)** untuk dukungan dan diskusi.

**Q: Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Tasks untuk Java?**  
A: Dapatkan lisensi sementara **[di sini](https://purchase.aspose.com/temporary-license/)** untuk tujuan pengujian dan evaluasi.

**Q: Apakah ada sumber daya tambahan untuk Aspose.Tasks untuk Java?**  
A: Lihat dokumentasi **[di sini](https://reference.aspose.com/tasks/java/)** untuk informasi mendalam dan contoh.

---

**Terakhir Diperbarui:** 2026-02-28  
**Diuji Dengan:** Aspose.Tasks for Java 24.10  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}