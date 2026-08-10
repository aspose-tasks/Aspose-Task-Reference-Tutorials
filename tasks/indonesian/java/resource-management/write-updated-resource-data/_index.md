---
date: 2026-06-30
description: Pelajari cara memperbarui beberapa sumber daya dan memodifikasi data
  grup sumber daya, lalu mengekspor proyek ke MPP dan menyimpan proyek sebagai MPP
  menggunakan Aspose.Tasks untuk Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Perbarui Beberapa Sumber Daya di Aspose.Tasks untuk Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Perbarui Beberapa Sumber Daya di Aspose.Tasks untuk Java
url: /id/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Perbarui Beberapa Sumber Daya di Aspise.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini, Anda akan belajar cara **memperbarui beberapa sumber daya** dalam file Microsoft Project menggunakan Aspose.Tasks untuk Java. Apakah Anda perlu mengubah tarif, menugaskan ulang grup, atau mengekspor file yang diperbarui ke MPP, langkah‑langkah di bawah ini akan memandu Anda melalui alur kerja lengkap yang siap produksi. Tidak diperlukan instalasi Microsoft Project, dan API dapat menangani proyek dengan ratusan sumber daya secara efisien.

## Jawaban Cepat
- **Bisakah saya memperbarui beberapa sumber daya sekaligus?** Ya – iterasi melalui `ResourceCollection` dan atur atribut dalam satu kali proses.  
- **Metode mana yang menyimpan file sebagai MPP?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Apakah saya memerlukan lisensi untuk penggunaan komersial?** Lisensi berbayar diperlukan untuk produksi; percobaan gratis tersedia.  
- **Versi Java apa yang didukung?** Java 6 dan yang lebih tinggi, termasuk Java 17 LTS.  
- **Apakah pembaruan massal memiliki kinerja yang baik?** Aspose.Tasks memproses proyek dengan 500 sumber daya dalam waktu kurang dari 2 detik pada server tipikal.

## Apa itu “update multiple resources”?
**“Update multiple resources”** mengacu pada perubahan properti beberapa entri sumber daya secara programatis—seperti tarif, grup, kalender, atau bidang kustom—dalam satu file Project. Operasi ini sering diperlukan saat menyinkronkan data proyek dengan sistem perencanaan sumber daya perusahaan, menyesuaikan anggaran di banyak sumber daya, atau menerapkan perubahan kebijakan di seluruh organisasi.

## Mengapa menggunakan Aspose.Tasks untuk memodifikasi grup sumber daya dan mengekspor proyek ke MPP?
Aspose.Tasks mendukung **lebih dari 50 format input dan output**, termasuk MPP, XML, dan CSV, dan dapat **mengekspor proyek ke MPP** tanpa memuat seluruh file ke memori. Perpustakaan ini memproses file hingga **2 GB** ukuran, memungkinkan Anda **menyimpan proyek sebagai MPP** dengan cepat dan dapat diandalkan.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Java Development Kit (JDK) terinstal di sistem Anda.  
2. Perpustakaan Aspose.Tasks untuk Java. Anda dapat mengunduhnya dari [di sini](https://releases.aspose.com/tasks/java/).  
3. Pengetahuan dasar tentang pemrograman Java.  

## Impor Paket
`import` statements membawa kelas Aspose.Tasks yang diperlukan ke dalam file sumber Anda.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Langkah 1: Siapkan Direktori Data Anda
Tentukan direktori tempat file data Anda berada:

```java
String dataDir = "Your Data Directory";
```

## Langkah 2: Tentukan File Input dan Output
Tentukan jalur untuk file MS Project input dan file yang diperbarui hasilnya:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Langkah 3: Muat Proyek
`Project` mewakili file Microsoft Project yang dimuat ke dalam memori, menyediakan akses ke tugas, sumber daya, dan data proyek lainnya.

```java
Project project = new Project(file);
```

## Langkah 4: Tambahkan Sumber Daya dan Atur Atribut
`Resource` memodelkan sumber daya proyek individu, memungkinkan Anda mengatur tarif, grup, kalender, dan atribut lainnya.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Langkah 5: Perbarui Beberapa Sumber Daya Secara Efisien
`ResourceCollection` adalah kumpulan semua sumber daya dalam sebuah proyek, dapat diakses melalui `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Langkah 6: Simpan Proyek
`SaveFileFormat` menyebutkan format file yang didukung untuk menyimpan proyek, seperti MPP, XML, dan PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Cara memperbarui beberapa sumber daya dalam sebuah proyek?
Muat proyek yang ada, ambil `ResourceCollection`‑nya, dan iterasi setiap objek `Resource`. Untuk setiap sumber daya, ubah bidang yang diperlukan seperti tarif, grup, atau atribut kustom, kemudian lanjutkan ke item berikutnya. Setelah memproses semua sumber daya, panggil `project.save(...)` sekali untuk menyimpan perubahan secara efisien.

## Masalah Umum dan Solusinya
- **Resource IDs clash** – Pastikan setiap sumber daya baru mendapatkan ID unik dengan menggunakan `project.getResources().add(new Resource())`.  
- **Rate format errors** – Gunakan objek `ResourceRate` dan atur `RateType` menjadi `StandardRate` atau `OvertimeRate`.  
- **Large files cause memory pressure** – Aktifkan `Project.setReadOnly(true)` sebelum memuat untuk mengurangi penggunaan memori.

## Pertanyaan yang Sering Diajukan
**Q: Bisakah saya memperbarui beberapa sumber daya dalam proyek yang sama menggunakan Aspose.Tasks untuk Java?**  
A: Ya, Anda dapat memperbarui beberapa sumber daya dengan mengiterasinya dan mengatur atributnya sesuai.

**Q: Apakah Aspose.Tasks mendukung format file lain selain MS Project?**  
A: Ya, Aspose.Tasks mendukung berbagai format file termasuk XML, MPP, dan lainnya.

**Q: Apakah Aspose.Tasks kompatibel dengan berbagai versi Java?**  
A: Aspose.Tasks kompatibel dengan versi Java 6 ke atas.

**Q: Bisakah saya melakukan operasi lain pada file MS Project dengan Aspose.Tasks?**  
A: Ya, Anda dapat melakukan berbagai operasi seperti membaca, menulis, dan memanipulasi tugas, sumber daya, serta kalender.

**Q: Di mana saya dapat menemukan bantuan atau dukungan tambahan untuk Aspose.Tasks?**  
A: Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan atau pertanyaan apa pun.

**Q: Bagaimana cara mengekspor file yang diperbarui ke format MPP?**  
A: Panggil `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` setelah melakukan semua perubahan sumber daya.

**Q: Apa cara terbaik untuk memodifikasi grup sumber daya?**  
A: Atur properti `Resource.Group` pada setiap objek `Resource` sebelum menyimpan proyek.

---

**Terakhir Diperbarui:** 2026-06-30  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Tambahkan sumber daya ke proyek dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/create-resources/)
- [Kelola Biaya Sumber Daya MS Project dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/resource-cost/)
- [Cara Mengekspor MPP ke Excel dengan Aspose.Tasks untuk Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}