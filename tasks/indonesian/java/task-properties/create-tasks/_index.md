---
date: 2026-01-25
description: Pelajari cara membuat tugas di Aspose.Tasks untuk Java. Kelola proyek,
  buat tugas ringkasan, atur direktori dokumen, dan lain‑lain dengan panduan langkah
  demi langkah ini.
linktitle: Create Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Membuat Tugas di Aspose.Tasks
url: /id/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Tugas di Aspose.Tasks

## Introduction
Selamat datang! Pada tutorial ini Anda akan menemukan **cara membuat tugas** di Aspose.Tasks untuk Java, mulai dari mengatur direktori dokumen hingga menambahkan tugas ringkasan dan subtugas. Baik Anda membangun daftar tugas sederhana maupun jadwal proyek lengkap, langkah‑langkah di bawah ini memberikan panduan praktis untuk menyiapkan hierarki proyek Anda dengan cepat.

## Quick Answers
- **Apa tujuan utama?** Untuk secara programatis membuat dan mengatur tugas dalam file Microsoft Project menggunakan Aspose.Tasks untuk Java.  
- **Versi perpustakaan apa yang dibutuhkan?** Versi terbaru Aspose.Tasks untuk Java (API tetap stabil di semua versi).  
- **Apakah saya memerlukan lisensi?** Lisensi sementara cukup untuk evaluasi; lisensi penuh diperlukan untuk produksi.  
- **Bisakah saya membuat tugas ringkasan?** Ya – gunakan metode `add` pada koleksi anak tugas root.  
- **Di mana file disimpan?** Di direktori yang Anda tetapkan dengan langkah *set document directory*.

## What is “how to create tasks” in Aspose.Tasks?
Membuat tugas berarti menambahkan objek `Task` secara programatis ke instance `Project`, menentukan hierarki mereka (tugas ringkasan, subtugas) dan menyimpan struktur tersebut ke file MPP. Ini memungkinkan pembuatan proyek otomatis, pembaruan massal, dan integrasi dengan sistem lain.

## Why use Aspose.Tasks for Java?
- **Full control** atas data proyek tanpa perlu menginstal Microsoft Project.  
- **Cross‑platform** kompatibilitas – berfungsi di Windows, Linux, dan macOS.  
- **Rich API** untuk atribut tugas, sumber daya, kalender, dan lainnya.  
- **Scalable** – cocok untuk utilitas kecil maupun mesin penjadwalan tingkat perusahaan.

## Prerequisites
Sebelum memulai, pastikan Anda memiliki:

- **Java Development Kit (JDK)** terpasang di mesin Anda.  
- **Aspose.Tasks for Java** library yang diunduh dari [here](https://releases.aspose.com/tasks/java/).  
- Sebuah IDE seperti **Eclipse** atau **IntelliJ IDEA** untuk menulis dan menjalankan kode Java.

## Import Packages
Tambahkan kelas Aspose.Tasks yang diperlukan di bagian atas file sumber Java Anda:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Step 1: Set the Document Directory
Tentukan folder tempat file proyek Anda akan dibaca atau ditulis.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

*Langkah ini memenuhi persyaratan **set document directory**, memberikan API lokasi yang jelas untuk file MPP.*

## Step 2: Create a New Project
Instansiasi objek `Project`, secara opsional memuat file MPP yang sudah ada atau memulai dari templat kosong.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

## Step 3: Add a Summary Task
Tugas ringkasan mengelompokkan subtugas terkait. Di sini kita **create summary task** “Summary1”.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

## Step 4: Add a Subtask
Sekarang tambahkan tugas anak di bawah tugas ringkasan untuk membangun hierarki.

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

Lanjutkan menambahkan tugas dan subtugas tambahan sesuai kebutuhan untuk mencerminkan struktur proyek Anda. Setiap pemanggilan `add` memperluas hierarki, memungkinkan Anda memodelkan jadwal kompleks secara programatis.

## Common Issues & Tips
- **Path errors:** Pastikan `dataDir` diakhiri dengan pemisah file yang tepat (`/` atau `\\`).  
- **License exceptions:** Jika muncul kesalahan lisensi, pastikan file lisensi yang valid dimuat sebelum membuat `Project`.  
- **Saving changes:** Setelah memodifikasi proyek, panggil `project.save(dataDir + "updated_project.mpp");` untuk menyimpan perubahan Anda.

## Frequently Asked Questions

### Is Aspose.Tasks suitable for small‑scale projects?
Absolutely! The API scales from simple task lists to massive enterprise schedules.

### Where can I find detailed documentation for Aspose.Tasks for Java?
Refer to the documentation [here](https://reference.aspose.com/tasks/java/).

### How do I obtain a temporary license for Aspose.Tasks?
Visit [this link](https://purchase.aspose.com/temporary-license/) for a trial license that works for evaluation.

### Can I customize task attributes using Aspose.Tasks?
Yes, you can set start dates, durations, resources, custom fields, and many other properties on each `Task` object.

### Is there a support community for Aspose.Tasks users?
Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

**Last Updated:**ed With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

---