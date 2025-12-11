---
date: 2025-12-09
description: Pelajari cara mengatur direktori data dan mengonfigurasi tampilan diagram
  Gantt di Aspose.Tasks menggunakan Java. Panduan ini juga menunjukkan cara menyesuaikan
  bidang tabel dan mengonfigurasi proyek Java diagram Gantt langkah demi langkah.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Atur Direktori Data untuk Tampilan Diagram Gantt di Aspose.Tasks
url: /id/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Direktori Data untuk Tampilan Gantt Chart di Aspose.Tasks

## Introduction
Dalam tutorial ini, Anda akan mempelajari **cara mengatur direktori data** dan mengonfigurasi Tampilan Gantt MS Project Chart di proyek Aspose.Tasks menggunakan Java. Aspose.Tasks adalah API Java yang kuat yang memungkinkan Anda memanipulasi file Microsoft Project secara programatis. Pada akhir panduan ini Anda akan dapat **menyesuaikan bidang tabel**, mengatur direktori data, dan memvisualisasikan proyek Anda persis seperti yang Anda inginkan.

## Quick Answers
- **Apa langkah pertama?** Atur jalur direktori data tempat file proyek Anda berada.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk Java (dapat diunduh dari situs resmi).  
- **Apakah saya dapat menambahkan atribut khusus?** Ya – Anda dapat mendefinisikan atribut ekstended dan menampilkannya di diagram Gantt.  
- **Apakah saya memerlukan lisensi untuk pengujian?** Lisensi sementara tersedia untuk tujuan evaluasi.  
- **IDE mana yang paling cocok?** Semua IDE Java (IntelliJ IDEA, Eclipse, NetBeans) dapat digunakan.

## Apa itu “set data directory” dan mengapa penting?
Mengatur direktori data memberi tahu Aspose.Tasks di mana harus membaca dan menulis file proyek. Tanpa jalur yang benar API tidak dapat menemukan file `.mpp` Anda, yang mengakibatkan error FileNotFound. Menetapkan direktori ini di awal kode membuat alur kerja selanjutnya menjadi bersih dan dapat diulang.

## Mengapa menyesuaikan bidang tabel di diagram Gantt?
Bidang tabel khusus memungkinkan Anda menampilkan informasi tambahan—seperti atribut khusus, data sumber daya, atau catatan proyek—langsung di tampilan Gantt. Hal ini membuat diagram lebih informatif bagi pemangku kepentingan dan mengurangi kebutuhan beralih antara beberapa laporan.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. **Java Development Kit (JDK)** – versi terbaru (8+).  
2. **Aspose.Tasks Library** – unduh dari [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, atau editor Java lain yang Anda sukai.

## Import Packages
Pertama, impor namespace Aspose.Tasks agar Anda dapat bekerja dengan kelas‑klsnya:

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
Sisipkan tugas baru (aktivitas) ke dalam root proyek.

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
Tetapkan atribut yang baru didefinisikan ke tugas yang telah Anda buat.

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
Simpan perubahan ke file baru yang dapat dibuka di Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** saat memuat proyek | Jalur **set data directory** tidak tepat atau kehilangan slash di akhir. | Pastikan `dataDir` mengarah ke folder yang tepat dan sertakan pemisah file yang sesuai (`/` atau `\\`). |
| Atribut khusus tidak terlihat di tampilan Gantt | Bidang tabel ditambahkan pada indeks yang salah atau lebar kolom terlalu kecil. | Pastikan `table.getTableFields().add(3, attrField);` menggunakan indeks yang valid dan sesuaikan `setWidth` bila diperlukan. |
| LicenseException saat menyimpan | Tidak ada lisensi yang valid diterapkan untuk penggunaan produksi. | Terapkan lisensi sementara atau permanen sebelum memanggil `project.save()`. |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks is available for multiple programming languages including .NET, Java, and C++.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Yes, you can download a free trial from [here](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: How can I purchase a license for Aspose.Tasks?**  
A: You can purchase a license from [here](https://purchase.aspose.com/buy).

**Q: Do I need a temporary license for testing purposes?**  
A: Yes, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
Anda kini telah mempelajari cara **mengatur direktori data**, menambahkan aktivitas baru, mendefinisikan dan melampirkan atribut khusus, serta **menyesuaikan bidang tabel** dalam tampilan diagram Gantt menggunakan Aspose.Tasks untuk Java. Langkah‑langkah ini memberi Anda kontrol penuh atas cara data proyek ditampilkan, menjadikan diagram Gantt lebih informatif dan disesuaikan dengan kebutuhan pemangku kepentingan Anda.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}