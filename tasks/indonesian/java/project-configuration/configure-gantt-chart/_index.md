---
date: 2026-02-13
description: Pelajari cara membuat aktivitas baru, mengatur direktori data, dan menyimpan
  proyek sebagai MPP di Aspose.Tasks Java. Panduan langkah demi langkah ini juga mencakup
  penyesuaian bidang tabel.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Membuat Aktivitas Baru & Menetapkan Direktori Data Aspose.Tasks
url: /id/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Aktivitas Baru & Menetapkan Direktori Data Aspose.Tasks

## Introduction
Dalam tutorial ini, Anda akan mempelajari **cara menetapkan direktori data**, cara **membuat aktivitas baru**, dan cara **menyimpan proyek sebagai MPP** sambil mengonfigurasi Tampilan Diagram Gantt MS Project di proyek Aspose.Tasks menggunakan Java. Aspose.Tasks adalah API Java yang kuat yang memungkinkan Anda memanipulasi file Microsoft Project secara programatis. Pada akhir panduan ini Anda akan dapat **menyesuaikan bidang tabel**, mengatur direktori data, dan memvisualisasikan proyek Anda persis seperti yang Anda butuhkan.

## Quick Answers
- **Apa langkah pertama?** Tetapkan jalur direktori data tempat file proyek Anda berada.  
- **Perpustakaan mana yang diperlukan?** Aspose.Tasks untuk Java (dapat diunduh dari situs resmi).  
- **Bisakah saya menambahkan atribut khusus?** Ya – Anda dapat mendefinisikan atribut tambahan dan menampilkannya di diagram Gantt.  
- **Apakah saya memerlukan lisensi untuk pengujian?** Lisensi sementara tersedia untuk tujuan evaluasi.  
- **IDE mana yang paling cocok?** Semua IDE Java (IntelliJ IDEA, Eclipse, NetBeans) dapat digunakan.

## What is “set data directory” and why does it matter?
Menetapkan direktori data memberi tahu Aspose.Tasks di mana harus membaca dan menulis file proyek. Tanpa jalur yang benar API tidak dapat menemukan file `.mpp` Anda, yang mengakibatkan kesalahan FileNotFound. Menentukan direktori ini di awal kode membuat alur kerja selanjutnya bersih dan dapat diulang.

## Why customize table fields in a Gantt chart?
Bidang tabel khusus memungkinkan Anda menampilkan informasi tambahan—seperti atribut khusus, data sumber daya, atau catatan proyek—langsung di tampilan Gantt. Hal ini membuat diagram lebih informatif bagi pemangku kepentingan dan mengurangi kebutuhan beralih antara banyak laporan.

## How to create new activity?
Membuat aktivitas baru (tugas) adalah salah satu operasi inti saat membangun atau memperbarui jadwal proyek. Dengan menambahkan tugas secara programatis Anda dapat mengotomatisasi pembuatan rencana proyek yang kompleks, mengintegrasikan data dari sistem lain, atau menerapkan perubahan massal tanpa penyuntingan manual.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi terbaru apa pun (8+).  
2. **Aspose.Tasks Library** – unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, atau editor kompatibel Java apa pun yang Anda sukai.

## Import Packages
Pertama, impor namespace Aspose.Tasks sehingga Anda dapat bekerja dengan kelas‑kelnya:

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
Tentukan folder yang berisi file proyek Anda. Ini adalah langkah **set data directory** yang menjadi fokus tutorial.

```java
String dataDir = "Your Data Directory";
```

Ganti `"Your Data Directory"` dengan jalur absolut ke folder tempat `project.mpp` disimpan.

### Step 2: Load Project File
Buat instance `Project` dengan memuat file Microsoft Project yang sudah ada.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: Add New Activity
Sisipkan tugas (aktivitas) baru ke dalam akar proyek. Ini mendemonstrasikan **cara membuat aktivitas baru** secara programatis.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Step 4: Define Custom Attribute
Buat definisi atribut khusus yang nantinya dapat Anda lampirkan ke tugas.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Step 5: Add Custom Attribute to Task
Tetapkan atribut yang baru didefinisikan ke tugas yang Anda buat.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Step 6: Customize Table – **customize table fields**
Tambahkan atribut khusus sebagai kolom dalam tabel diagram Gantt, dengan menentukan lebar, judul, dan perataan.

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

### Step 7: Save Project
Simpan perubahan ke file baru yang dapat dibuka di Microsoft Project. Langkah ini **menyimpan proyek sebagai MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** when loading the project | Jalur **set data directory** tidak benar atau kehilangan slash di akhir. | Verifikasi `dataDir` mengarah ke folder yang tepat dan sertakan pemisah file yang sesuai (`/` atau `\\`). |
| Custom attribute not visible in Gantt view | Bidang tabel ditambahkan pada indeks yang salah atau lebar kolom terlalu kecil. | Pastikan `table.getTableFields().add(3, attrField);` menggunakan indeks yang valid dan sesuaikan `setWidth` bila diperlukan. |
| LicenseException on save | Tidak ada lisensi yang valid diterapkan untuk penggunaan produksi. | Terapkan lisensi sementara atau permanen sebelum memanggil `project.save()`. |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Ya, Aspose.Tasks tersedia untuk beberapa bahasa pemrograman termasuk .NET, Java, dan C++.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Ya, Anda dapat mengunduh trial gratis dari [here](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: Anda dapat menemukan dukungan dan mengajukan pertanyaan di [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: How can I purchase a license for Aspose.Tasks?**  
A: Anda dapat membeli lisensi dari [here](https://purchase.aspose.com/buy).

**Q: Do I need a temporary license for testing purposes?**  
A: Ya, Anda dapat memperoleh lisensi sementara dari [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
Anda kini telah mempelajari cara **menetapkan direktori data**, **membuat aktivitas baru**, mendefinisikan dan melampirkan atribut khusus, serta **menyimpan proyek sebagai MPP** sambil **menyesuaikan bidang tabel** dalam tampilan diagram Gantt menggunakan Aspose.Tasks untuk Java. Langkah‑langkah ini memberi Anda kontrol penuh atas cara data proyek ditampilkan, menjadikan diagram Gantt Anda lebih informatif dan disesuaikan dengan kebutuhan pemangku kepentingan.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}