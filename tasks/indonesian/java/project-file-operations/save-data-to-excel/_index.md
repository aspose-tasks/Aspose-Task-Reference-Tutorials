---
date: 2025-12-21
description: Pelajari cara mengekspor MPP ke Excel dan mengonversi file proyek ke
  Excel menggunakan Aspose.Tasks untuk Java. Langkah sederhana untuk pengembang Java.
linktitle: Save Data to Excel in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mengekspor MPP ke Excel dengan Aspose.Tasks untuk Java
url: /id/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengekspor MPP ke Excel dengan Aspose.Tasks untuk Java

## Introduction
Aspose.Tasks untuk Java adalah perpustakaan kuat yang memungkinkan Anda **mengekspor MPP ke Excel** dengan cepat dan andal. Dalam tutorial ini kami akan memandu Anda melalui langkah‑langkah tepat yang diperlukan untuk mengonversi file Microsoft Project (.mpp) menjadi buku kerja Excel (.xlsx). Pada akhir tutorial Anda akan memahami cara **mengonversi file proyek ke Excel**, mengapa konversi ini berguna, dan bagaimana mengintegrasikan proses ini ke dalam aplikasi Java apa pun.

## Quick Answers
- **What does the API do?** It reads Project files and saves them directly as XLSX workbooks.  
- **Which format is produced?** An Excel file using the `SaveFileFormat.Xlsx` option.  
- **Do I need a license?** A trial works for testing; a commercial license is required for production.  
- **What are the prerequisites?** JDK installed and Aspose.Tasks for Java library added to your project.  
- **How long does implementation take?** Typically under 10 minutes for a basic export.

## What is “how to export MPP to Excel”?
Mengekspor MPP ke Excel berarti mengambil jadwal, sumber daya, dan data tugas yang disimpan dalam file Microsoft Project dan menuliskannya ke dalam spreadsheet Excel yang terstruktur. Hal ini memudahkan berbagi data proyek dengan pemangku kepentingan yang mungkin tidak memiliki Project terpasang.

## Why convert MPP file to XLSX?
- **Broader accessibility:** Excel is ubiquitous in business environments.  
- **Simplified reporting:** Use Excel’s pivot tables, charts, and formulas to analyze project metrics.  
- **Automation friendly:** Excel files can be processed by other systems or scripts without needing Project.  

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki hal‑hal berikut:

1. **Java Development Kit (JDK)** – terpasang dan ditambahkan ke PATH sistem Anda.  
2. **Aspose.Tasks for Java library** – unduh dari [download link](https://releases.aspose.com/tasks/java/) dan tambahkan JAR ke classpath proyek Anda.

## Import Packages
Pertama, impor kelas‑kelas yang Anda perlukan. Pertahankan blok ini persis seperti yang ditampilkan – diperlukan agar API berfungsi.

```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory Path
Tetapkan folder tempat file `.mpp` Anda berada. Ganti placeholder dengan jalur aktual Anda.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
Buat instance `Project` dengan memuat file `.mpp` yang ingin Anda konversi. Ini akan membaca semua tugas, sumber daya, dan informasi penjadwalan.

```java
Project project = new Project(dataDir + "project5.mpp");
```

### Step 3: Save the Project as XLSX
Akhirnya, ekspor proyek yang sudah dimuat ke buku kerja Excel. Flag `SaveFileFormat.Xlsx` memberi tahu Aspose.Tasks untuk menghasilkan file `.xlsx` modern, secara efektif **mengonversi file MPP ke XLSX**.

```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```

## Common Use Cases
- **Executive reporting:** Provide high‑level project snapshots in Excel for senior management.  
- **Data analysis:** Feed task and resource data into Excel’s Power Query for deeper insights.  
- **Integration:** Pass the exported Excel file to downstream systems that only accept CSV/Excel inputs.

## Conclusion
Dalam panduan ini kami menunjukkan **cara mengekspor MPP ke Excel** menggunakan Aspose.Tasks untuk Java. Dengan mengikuti tiga langkah sederhana—menentukan direktori data, memuat file Project, dan menyimpannya sebagai XLSX—Anda dapat dengan mudah **mengekspor data proyek ke Excel** dan memberi tim Anda laporan yang fleksibel serta dapat dibagikan.

## FAQ's
### Can I use Aspose.Tasks for Java to manipulate project data programmatically?
Yes, Aspose.Tasks for Java provides extensive features to manipulate project data, including reading, writing, and modifying project files.

### Is there a free trial available for Aspose.Tasks for Java?
Yes, you can download a free trial version of Aspose.Tasks for Java from [here](https://releases.aspose.com/).

### Where can I find documentation for Aspose.Tasks for Java?
You can find the documentation for Aspose.Tasks for Java [here](https://reference.aspose.com/tasks/java/).

### How can I get support for any issues or queries related to Aspose.Tasks for Java?
You can get support by visiting the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).

### Can I purchase a temporary license for Aspose.Tasks for Java?
Yes, you can purchase a temporary license from [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

---