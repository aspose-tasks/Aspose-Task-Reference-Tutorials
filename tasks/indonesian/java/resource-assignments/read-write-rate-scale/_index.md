---
date: 2026-01-10
description: Pelajari cara membaca skala tarif dan mengelola penugasan sumber daya
  di Aspose.Tasks untuk Java. Definisikan sumber daya material, cara mengatur skala,
  dan menugaskan sumber daya ke tugas.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Membaca Skala Tarif dan Menulis Skala Tarif untuk Penugasan Sumber Daya
  di Aspose.Tasks
url: /id/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca Skala Tarif dan Menulis Skala Tarif untuk Penugasan Sumber Daya di Aspose.Tasks

Dalam tutorial ini Anda akan menemukan **cara membaca tarif** pengaturan skala dan menyesuaikannya untuk penugasan sumber daya menggunakan Aspose.Tasks untuk Java. Baik Anda membangun penjadwal, alat pelaporan, atau hanya perlu mengotomatisasi pembaruan proyek, menguasai manipulasi skala tarif memberi Anda kontrol terperinci atas sumber daya material dan kerja.

## Jawaban Cepat
- **Apa kelas utama untuk penanganan tarif?** `ResourceAssignment` dengan properti `Asn.RATE_SCALE`.  
- **Enum mana yang mendefinisikan opsi skala?** `RateScaleType` (Day, Week, Month, dll.).  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Lisensi evaluasi gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah skala setelah menyimpan?** Ya – muat ulang proyek dan modifikasi `Asn.RATE_SCALE` seperti yang ditunjukkan.  
- **IDE yang didukung?** Semua IDE Java (IntelliJ IDEA, Eclipse, NetBeans) dapat mengompilasi kode.

## Apa Itu Skala Tarif?
Skala tarif menentukan satuan waktu (hari, minggu, bulan, dll.) yang diterapkan pada tarif biaya sumber daya. Menyesuaikan skala memungkinkan Anda memodelkan konsumsi material atau upaya tenaga kerja secara akurat.

## Mengapa Membaca dan Menulis Skala Tarif?
Membaca skala saat ini membantu Anda mengaudit jadwal yang ada, sementara menulis skala baru memungkinkan Anda menyelaraskan sumber daya dengan kebijakan penagihan atau konsumsi proyek. Ini sangat berguna saat **mendefinisikan sumber daya material** biaya atau ketika Anda perlu **mengatur skala** untuk kalender kerja non‑standar.

## Prasyarat
1. **Lingkungan Pengembangan Java** – JDK 8 atau lebih tinggi terpasang.  
2. **Pustaka Aspose.Tasks untuk Java** – Unduh dan instal pustaka dari [here](https://releases.aspose.com/tasks/java/).

## Impor Paket
Pertama, impor kelas Aspose.Tasks yang diperlukan.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Langkah 1: Siapkan Proyek Java Anda
Buat proyek Maven atau Gradle dan tambahkan JAR Aspose.Tasks ke classpath Anda. Langkah ini memastikan kompiler dapat menemukan kelas yang diimpor.

## Langkah 2: Muat File Proyek
Muat file Microsoft Project yang ada yang ingin Anda kerjakan.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Langkah 3: Tambahkan Tugas
Buat tugas baru yang nantinya akan menerima penugasan sumber daya.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Langkah 4: Definisikan Sumber Daya
Di sini kami **mendefinisikan sumber daya material** dan sumber daya kerja reguler. Perhatikan penggunaan `ResourceType.Material` untuk sumber daya tipe material.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Langkah 5: Tugaskan Sumber Daya ke Tugas
Sekarang kami **menugaskan sumber daya ke tugas** dan menentukan **cara mengatur skala** dengan menggunakan `RateScaleType.Week`. Ini menggambarkan baik membaca maupun menulis skala tarif.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Langkah 6: Simpan Proyek
Simpan perubahan ke file baru sehingga kami dapat memverifikasi skala tarif yang disimpan nanti.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Langkah 7: Ambil Penugasan Sumber Daya
Muat ulang proyek yang disimpan dan **baca skala tarif** untuk memastikan bahwa itu telah ditulis dengan benar.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Kesalahan Umum & Tips
- **UID Tidak Cocok** – Saat mengambil penugasan berdasarkan UID, pastikan nilai UID cocok dengan yang ditetapkan selama pembuatan.  
- **Tipe Sumber Daya Salah** – Menggunakan `ResourceType.Material` untuk sumber daya kerja akan menyebabkan perhitungan tarif berperilaku tidak terduga.  
- **Format Penyimpanan** – Selalu simpan menggunakan `SaveFileFormat.Mpp` (atau format lain yang didukung) untuk mempertahankan bidang khusus seperti skala tarif.

## Kesimpulan
Mengelola dan memeriksa skala tarif untuk penugasan sumber daya di Aspose.Tasks untuk Java menjadi mudah setelah Anda mengetahui kelas dan properti yang relevan. Dengan mengikuti panduan ini Anda dapat **membaca informasi tarif**, **mendefinisikan objek sumber daya material**, **mengatur skala**, dan **menugaskan sumber daya ke tugas** dengan percaya diri.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dengan IDE Java apa pun?**  
A: Ya, Aspose.Tasks untuk Java kompatibel dengan semua IDE Java utama, termasuk IntelliJ IDEA, Eclipse, dan NetBeans.

**Q: Apakah Aspose.Tasks mendukung format file lain selain MPP?**  
A: Ya, Aspose.Tasks mendukung berbagai format file, termasuk MPP, XML, dan HTML.

**Q: Apakah Aspose.Tasks cocok untuk manajemen proyek tingkat perusahaan?**  
A: Tentu saja, Aspose.Tasks menawarkan fitur lengkap untuk mengelola proyek dalam skala apa pun, menjadikannya cocok untuk manajemen proyek tingkat perusahaan.

**Q: Bisakah saya menyesuaikan penugasan sumber daya lebih lanjut selain skala tarif?**  
A: Ya, Aspose.Tasks menyediakan kemampuan luas untuk menyesuaikan penugasan sumber daya, termasuk penyesuaian biaya, kerja, dan durasi.

**Q: Apakah ada forum komunitas untuk dukungan Aspose.Tasks?**  
A: Ya, Anda dapat menemukan dukungan dan berinteraksi dengan pengguna lain di forum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Terakhir Diperbarui:** 2026-01-10  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}