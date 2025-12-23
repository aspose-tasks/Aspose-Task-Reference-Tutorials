---
date: 2025-12-23
description: Pelajari cara membuat ketergantungan tugas dan menghitung jalur kritis
  di MS Project menggunakan Aspose.Tasks untuk Java. Panduan langkah demi langkah
  untuk manajemen proyek.
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Buat Ketergantungan Tugas dan Hitung Jalur Kritis di Aspose.Tasks
url: /id/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Ketergantungan Tugas dan Hitung Jalur Kritis di Aspose.Tasks

## Introduction
Dalam tutorial ini, **Anda akan belajar cara membuat ketergantungan tugas** dan menghitung jalur kritis dalam file MS Project menggunakan Aspose.Tasks untuk Java. Memahami dan memvisualisasikan jalur kritis membantu Anda menjaga proyek tetap sesuai jadwal, sementara menghubungkan tugas dengan benar memastikan setiap penundaan langsung terlihat. Mari kita jalani seluruh proses, mulai dari menyiapkan lingkungan hingga menampilkan jalur kritis akhir.

## Quick Answers
- **Apa langkah pertama?** Siapkan proyek Java Anda dan tambahkan pustaka Aspose.Tasks.  
- **Mode mana yang harus diaktifkan?** `CalculationMode.Automatic` (atur perhitungan otomatis).  
- **Bagaimana cara menghubungkan tugas?** Gunakan `project.getTaskLinks().add(...)` untuk membuat ketergantungan tugas.  
- **Bagaimana cara melihat jalur kritis?** Iterasi melalui `project.getCriticalPath()` dan cetak nama setiap tugas.  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.

## What is “create task dependencies”?
Membuat ketergantungan tugas berarti mendefinisikan hubungan (misalnya Finish‑to‑Start) antara tugas sehingga jadwal mencerminkan kendala dunia nyata. Di Aspose.Tasks, hal ini dilakukan melalui objek `TaskLink`.

## Why calculate the critical path in MS Project?
**Jalur kritis MS Project** menunjukkan urutan terpanjang dari tugas‑tugas yang saling bergantung yang menentukan durasi minimum proyek. Dengan menghitungnya, Anda dapat dengan cepat mengidentifikasi tugas‑tugas yang tidak boleh terlambat tanpa memengaruhi keseluruhan timeline—penting untuk aplikasi **manajemen proyek Java** yang efektif.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

1. Java Development Kit (JDK) terpasang di sistem Anda.  
2. Pustaka Aspose.Tasks untuk Java yang sudah diunduh dan ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari [here](https://releases.aspose.com/tasks/java/).  

## Import Packages
Untuk memulai, impor paket yang diperlukan dalam kelas Java Anda:
```java
import com.aspose.tasks.*;
```

## How to set automatic calculation?
Mengatur mode perhitungan ke otomatis memastikan setiap perubahan pada tugas atau tautan langsung memperbarui jadwal, termasuk jalur kritis.
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
Tentukan jalur ke folder yang berisi file MS Project Anda.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load MS Project File
Muat file proyek yang sudah ada (misalnya *New project 2013.mpp*) menggunakan Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### Step 3: Add Tasks
Buat tiga subtugas sederhana yang nanti akan kita hubungkan.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### Step 4: Create Task Links (create task dependencies)
Definisikan ketergantungan antara tugas‑tugas. Di sini kami menggunakan tautan Finish‑to‑Start, yang merupakan tipe paling umum.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### Step 5: Display Critical Path (display critical path)
Ambil dan cetak jalur kritis. Metode `getCriticalPath()` mengembalikan daftar tugas yang membentuk rantai kritis.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### Step 6: Confirm Completion
Tampilkan pesan ramah setelah proses selesai.
```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Critical path is empty** | Pastikan `CalculationMode.Automatic` diatur sebelum menambahkan tautan. |
| **Tasks not linked** | Verifikasi bahwa Anda telah menambahkan objek `TaskLink` untuk setiap ketergantungan. |
| **License exception** | Muat lisensi Aspose.Tasks yang valid sebelum membuat instance `Project`. |

## FAQ's
### Q: Can I use Aspose.Tasks for Java with any version of MS Project files?
A: Yes, Aspose.Tasks for Java supports various versions of MS Project files, including .mpp files from MS Project 2003 to MS Project 2019.  

### Q: Is there a free trial available for Aspose.Tasks for Java?
A: Yes, you can download a free trial from [here](https://releases.aspose.com/).  

### Q: Where can I find support for Aspose.Tasks for Java?
A: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).  

### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
A: Yes, you can purchase a temporary license from [here](https://purchase.aspose.com/temporary-license/).  

### Q: How can I buy Aspose.Tasks for Java?
A: You can purchase Aspose.Tasks for Java from the website [here](https://purchase.aspose.com/buy).

## Conclusion
Dengan mengikuti langkah‑langkah ini Anda telah **membuat ketergantungan tugas**, mengatur **perhitungan otomatis**, dan berhasil **menampilkan jalur kritis** untuk file MS Project Anda. Alur kerja ini memberi Anda kontrol penuh atas logika jadwal dan membantu menjaga proyek tetap pada jalurnya menggunakan kode **manajemen proyek** berbasis Java.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}