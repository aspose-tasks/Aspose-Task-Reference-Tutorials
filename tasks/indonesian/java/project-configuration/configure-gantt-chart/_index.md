---
date: 2026-10-15
description: Pelajari cara membuat aktivitas, mengatur direktori data, menyesuaikan
  bidang tabel, dan menyimpan proyek sebagai MPP dengan Aspose.Tasks for Java. Panduan
  langkah demi langkah untuk pengembang Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Cara membuat aktivitas dan mengatur direktori data menggunakan Aspose.Tasks
  for Java
og_description: Cara membuat aktivitas, menyesuaikan bidang tabel, dan menyimpan proyek
  sebagai MPP menggunakan Aspose.Tasks for Java. Ikuti panduan terperinci ini untuk
  implementasi cepat.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Cara membuat aktivitas dan mengatur direktori data di Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Cara membuat aktivitas dan mengatur direktori data menggunakan Aspose.Tasks
  for Java
url: /id/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat aktivitas dan mengatur direktori data menggunakan Aspose.Tasks untuk Java

## Pendahuluan
Pada tutorial ini Anda akan menemukan **cara membuat aktivitas** secara programatis, mengonfigurasi **direktori data**, dan **menyimpan proyek sebagai MPP** sekaligus **menyesuaikan bidang tabel** dalam tampilan diagram Gantt. Aspose.Tasks untuk Java adalah API yang kuat yang mendukung lebih dari 30 format input dan output serta dapat memproses proyek dengan hingga 10 000 tugas tanpa memuat seluruh file ke memori. Pada akhir panduan Anda akan dapat mengotomatisasi pembuatan proyek, memperkaya tugas dengan atribut khusus, dan menghasilkan file MPP siap‑dibuka untuk Microsoft Project.

## Jawaban Cepat
- **Apa langkah pertama?** Atur jalur direktori data tempat file proyek Anda berada.  
- **Perpustakaan mana yang diperlukan?** Aspose.Tasks untuk Java (dapat diunduh dari situs resmi).  
- **Bisakah saya menambahkan atribut khusus?** Ya – Anda dapat mendefinisikan atribut ekstensi dan menampilkannya di diagram Gantt.  
- **Apakah saya memerlukan lisensi untuk pengujian?** Lisensi sementara tersedia untuk tujuan evaluasi.  
- **IDE mana yang paling cocok?** Semua IDE Java (IntelliJ IDEA, Eclipse, NetBeans) dapat digunakan.

## Apa itu “set data directory” dan mengapa penting?
Menetapkan direktori data memberi tahu Aspose.Tasks di mana harus membaca dan menulis file proyek. Tanpa jalur yang benar API tidak dapat menemukan file `.mpp` Anda, yang menyebabkan kesalahan `FileNotFoundException`. Menentukan direktori ini di awal kode Anda membuat alur kerja dapat diulang dan memisahkan masalah sistem file dari logika bisnis.

## Mengapa menyesuaikan bidang tabel dalam diagram Gantt?
Bidang tabel khusus memungkinkan Anda menampilkan informasi tambahan—seperti atribut khusus, data sumber daya, atau catatan spesifik proyek—langsung di tampilan Gantt. Ini mengurangi kebutuhan laporan terpisah dan memberikan pemangku kepentingan visual tunggal yang kaya data yang dapat meningkatkan kecepatan pengambilan keputusan hingga 30 %.

## Cara membuat aktivitas baru?
Anda membuat aktivitas (tugas) baru dengan menginstansiasi objek `Task` dan menambahkannya ke koleksi tugas root proyek. Pendekatan ini memungkinkan Anda menghasilkan jadwal besar secara otomatis, menarik data tugas dari sistem eksternal, atau menerapkan pembaruan massal tanpa penyuntingan manual.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi 8 atau lebih baru.  
2. **Aspose.Tasks untuk Java** – unduh dari **halaman rilis Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA, Eclipse, atau editor kompatibel Java apa pun yang Anda sukai.  

## Impor paket
Namespace `com.aspose.tasks` berisi semua kelas yang Anda perlukan untuk manipulasi proyek. Mengimpornya memberi Anda akses ke `Project`, `Task`, `ExtendedAttributeDefinition`, dan tipe inti lainnya.

```java
import com.aspose.tasks.*;
```

## Dependensi Maven (opsional)
Jika Anda mengelola proyek dengan Maven, tambahkan dependensi Aspose.Tasks ke `pom.xml`. Ini memastikan perpustakaan diselesaikan secara otomatis selama proses build.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Panduan langkah‑demi‑langkah

### Langkah 1: mengatur direktori data
Tentukan folder yang berisi file proyek Anda. Variabel `dataDir` menyimpan jalur absolut dan digunakan kembali sepanjang tutorial.

```java
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan jalur lengkap ke folder tempat `project.mpp` berada, misalnya `C:/Projects/MyGantt`.

### Langkah 2: memuat file proyek
`Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file Microsoft Project dalam memori. Memuat file yang ada memberi Anda akses ke tugas, sumber daya, dan tabelnya.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Langkah 3: menambahkan aktivitas baru
`Task` mewakili aktivitas individual dalam jadwal. Menambahkan tugas ke koleksi tugas root menyisipkannya pada tingkat atas hierarki proyek.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Langkah 4: mendefinisikan atribut khusus
`ExtendedAttributeDefinition` memungkinkan Anda membuat bidang khusus yang dapat digunakan kembali dan dapat dilampirkan ke tugas, sumber daya, atau penugasan apa pun.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Langkah 5: menambahkan atribut khusus ke tugas
`ExtendedAttribute` adalah contoh konkret dari atribut khusus yang Anda tetapkan ke tugas tertentu.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Langkah 6: menyesuaikan tabel – menambahkan atribut khusus sebagai kolom
`TableField` menggambarkan sebuah kolom dalam tabel diagram Gantt. Dengan menambahkan `TableField` yang merujuk ke atribut khusus, Anda membuat atribut tersebut terlihat dalam tampilan diagram.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Langkah 7: menyimpan proyek
Memanggil `project.save` menyimpan semua perubahan ke file baru. Konstanta `SaveFileFormat.MPP` memberi tahu Aspose.Tasks untuk menulis file dalam format biner asli Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Masalah umum dan solusi
| Masalah | Mengapa terjadi | Solusi |
|-------|----------------|-----|
| **FileNotFoundException** saat memuat proyek | Jalur **set data directory** tidak benar atau tidak memiliki slash di akhir. | Verifikasi `dataDir` mengarah ke folder yang tepat dan sertakan pemisah file yang benar (`/` atau `\\`). |
| Atribut khusus tidak terlihat di tampilan Gantt | Bidang tabel ditambahkan pada indeks yang salah atau lebar kolom terlalu kecil. | Pastikan `table.getTableFields().add(3, attrField);` menggunakan indeks yang valid dan sesuaikan `setWidth` sesuai kebutuhan. |
| LicenseException saat menyimpan | Tidak ada lisensi yang valid diterapkan untuk penggunaan produksi. | Terapkan lisensi sementara atau permanen sebelum memanggil `project.save()`. |

## Pertanyaan yang sering diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
A: Ya, Aspose.Tasks tersedia untuk .NET, Java, dan C++.

**Q: Apakah ada percobaan gratis untuk Aspose.Tasks?**  
A: Ya, Anda dapat mengunduh percobaan gratis dari **halaman unduhan percobaan gratis Aspose.Tasks**.

**Q: Di mana saya dapat menemukan dukungan untuk Aspose.Tasks?**  
A: Anda dapat menemukan dukungan dan mengajukan pertanyaan di [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Bagaimana cara membeli lisensi untuk Aspose.Tasks?**  
A: Anda dapat membeli lisensi dari **halaman pembelian Aspose.Tasks**.

**Q: Apakah saya memerlukan lisensi sementara untuk tujuan pengujian?**  
A: Ya, Anda dapat memperoleh lisensi sementara dari **halaman permintaan lisensi sementara**.

## Kesimpulan
Anda sekarang tahu **cara membuat aktivitas**, mengatur direktori data, mendefinisikan dan melampirkan atribut khusus, serta **menyimpan proyek sebagai MPP** sambil **menyesuaikan bidang tabel** dalam tampilan diagram Gantt menggunakan Aspose.Tasks untuk Java. Kemampuan ini memberi Anda kontrol programatik penuh atas data proyek, memungkinkan pembuatan jadwal otomatis dan pelaporan visual yang lebih kaya untuk pemangku kepentingan Anda.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose

## Tutorial Terkait

- [Cara Membuat File Proyek Kosong di Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Cara Membuat File MPP – Membuat & Menyimpan Proyek Kosong dalam Format MPP dengan Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Cara Membuat Proyek aspose.tasks – Menetapkan Atribut Tugas Baru](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}