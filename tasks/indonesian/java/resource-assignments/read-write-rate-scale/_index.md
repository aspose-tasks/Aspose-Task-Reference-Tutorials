---
date: 2026-06-10
description: Pelajari cara membaca tarif dan cara menulis skala tarif untuk penugasan
  sumber daya menggunakan Aspose.Tasks untuk Java. Mendukung sumber daya material,
  berbagai format, dan proyek besar.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Membaca dan Menulis Skala Tarif untuk Penugasan Sumber Daya di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
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

Dalam tutorial ini Anda akan menemukan **cara membaca tarif** pengaturan skala dan menyesuaikannya untuk penugasan sumber daya menggunakan Aspose.Tasks untuk Java. Baik Anda sedang membangun penjadwal, alat pelaporan, atau sekadar perlu mengotomatisasi pembaruan proyek, menguasai manipulasi skala tarif memberi Anda kontrol terperinci atas sumber daya material dan kerja.

## Jawaban Cepat
`ResourceAssignment` menghubungkan tugas ke sumber daya dan menyimpan data khusus penugasan.  
`Asn` berisi konstanta untuk bidang penugasan, termasuk `RATE_SCALE`.  
`RateScaleType` enum mencantumkan unit waktu yang mungkin untuk skala tarif.  

- **Apa kelas utama untuk penanganan tarif?** `ResourceAssignment` dengan properti `Asn.RATE_SCALE`.  
- **Enum mana yang mendefinisikan opsi skala?** `RateScaleType` (Day, Week, Month, dll.).  
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Lisensi evaluasi gratis dapat digunakan untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah skala setelah menyimpan?** Ya – muat ulang proyek dan modifikasi `Asn.RATE_SCALE` seperti yang ditunjukkan.  
- **IDE yang didukung?** Semua IDE Java (IntelliJ IDEA, Eclipse, NetBeans) dapat mengompilasi kode.

## Cara membaca skala tarif untuk penugasan sumber daya?
Muat proyek, temukan `ResourceAssignment` yang diinginkan, dan panggil `getRateScale()` – ini mengembalikan nilai `RateScaleType` yang memberi tahu Anda apakah tarif diterapkan per hari, minggu, bulan, atau unit lainnya. Jawabannya langsung dan hanya memerlukan dua panggilan API, menjadikannya ideal untuk skrip audit atau tampilan UI.

## Cara menulis skala tarif untuk penugasan sumber daya?
Buat atau ambil objek `ResourceAssignment`, atur properti `Asn.RATE_SCALE`-nya ke `RateScaleType` yang diinginkan (mis., `RateScaleType.Week`), lalu simpan proyek. Perubahan properti tunggal ini secara otomatis memperbarui perhitungan biaya dan dipertahankan di semua format file yang didukung. Setelah mengatur skala, Anda mungkin juga perlu menyesuaikan tarif standar atau tarif lembur sumber daya untuk mencerminkan unit waktu baru, memastikan perhitungan biaya tetap akurat.

## Apa Itu Skala Tarif?
Skala tarif menentukan unit waktu (hari, minggu, bulan, dll.) yang diterapkan pada tarif biaya sumber daya. Menyesuaikan skala memungkinkan Anda memodelkan konsumsi material atau upaya tenaga kerja secara akurat. Misalnya, mengatur skala ke Week berarti tarif biaya diartikan sebagai biaya per minggu, dan total biaya untuk sebuah tugas dihitung berdasarkan jumlah minggu sumber daya tersebut ditugaskan.

## Mengapa membaca dan menulis skala tarif?
Membaca skala saat ini membantu Anda mengaudit jadwal yang ada, sementara menulis skala baru memungkinkan Anda menyelaraskan sumber daya dengan kebijakan penagihan atau konsumsi proyek. Ini sangat berguna ketika **menentukan biaya sumber daya material** atau ketika Anda perlu **mengatur skala** untuk kalender kerja non‑standar.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. **Lingkungan Pengembangan Java** – JDK 8 atau lebih tinggi terpasang.  
2. **Pustaka Aspose.Tasks untuk Java** – Unduh dan instal pustaka dari [di sini](https://releases.aspose.com/tasks/java/).

## Impor Paket
Kelas `ResourceAssignment` mewakili tautan antara tugas dan sumber daya, sementara `RateScaleType` mengenumerasikan unit waktu yang mungkin untuk tarif. Impor kelas Aspose.Tasks yang diperlukan sebelum Anda mulai menulis kode.  

`Project` adalah objek utama yang memuat dan menyimpan file Microsoft Project.  
`Resource` mendefinisikan sumber daya proyek seperti kerja atau material.  
`ResourceType` enum menentukan apakah sumber daya adalah kerja atau material.  
`Task` mewakili item kerja dalam jadwal proyek.  
`SaveFileFormat` enum mendefinisikan format output untuk menyimpan proyek.

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

## Langkah 1: Siapkan proyek Java Anda
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
- **UID Tidak Cocok** – Saat mengambil penugasan berdasarkan UID, pastikan nilai UID cocok dengan yang diberikan selama pembuatan.  
- **Tipe Sumber Daya Salah** – Menggunakan `ResourceType.Material` untuk sumber daya kerja akan menyebabkan perhitungan tarif berperilaku tidak terduga.  
- **Format Penyimpanan** – Selalu simpan menggunakan `SaveFileFormat.Mpp` (atau format lain yang didukung) untuk mempertahankan bidang khusus seperti skala tarif.  
- **Proyek Besar** – Aspose.Tasks dapat memproses file dengan **lebih dari 500 halaman** tanpa memuat seluruh dokumen ke memori, berkat arsitektur streamingnya.

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
A: Ya, Anda dapat menemukan dukungan dan berinteraksi dengan pengguna lain di forum Aspose.Tasks [di sini](https://forum.aspose.com/c/tasks/15).

---

**Terakhir Diperbarui:** 2026-06-10  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (terbaru pada saat penulisan)  
**Penulis:** Aspose

## Tutorial Terkait

- [Buat Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Cara Memodifikasi Penugasan – Baca Sumber Daya Bersama dengan Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Cara Menambahkan Catatan ke Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}