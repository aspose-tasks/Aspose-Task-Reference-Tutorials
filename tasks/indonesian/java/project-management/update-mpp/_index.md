---
date: 2026-06-25
description: Pelajari cara menambahkan tugas dan memperbarui file MPP menggunakan
  Aspose.Tasks untuk Java, sebuah perpustakaan manajemen proyek Java yang memungkinkan
  Anda membuat file Microsoft Project tugas dan menyimpan proyek sebagai MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Cara Menambahkan Tugas dan Memperbarui File MPP di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara Menambahkan Tugas dan Memperbarui File MPP di Aspose.Tasks
url: /id/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Menambahkan Tugas dan Memperbarui File MPP di Aspose.Tasks

## Pendahuluan
Dalam tutorial ini Anda akan belajar **cara menambahkan tugas** ke file Microsoft Project (MPP) yang ada dan kemudian menyimpan jadwal yang diperbarui menggunakan Aspose.Tasks untuk Java, sebuah **perpustakaan manajemen proyek java** terkemuka. Baik Anda membangun penjadwal khusus, mengotomatisasi pembaruan massal, atau mengintegrasikan data proyek ke dalam sistem yang lebih besar, panduan langkah demi langkah di bawah ini menunjukkan secara tepat cara memuat proyek, menyisipkan tugas baru, mengatur tanggalnya, dan menyimpan hasilnya sebagai dokumen MPP baru.

## Jawaban Cepat
- **Apa arti “cara menambahkan tugas” dalam konteks ini?** Artinya membuat item kerja baru secara programatis di dalam file MPP yang ada.  
- **Perpustakaan mana yang menangani operasi ini?** Aspose.Tasks untuk Java, sebuah perpustakaan manajemen proyek java yang kuat.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Apakah saya dapat menyimpan hasil sebagai MPP?** Ya—gunakan `project.save(..., SaveFileFormat.Mpp)` untuk **menyimpan proyek sebagai mpp**.  
- **Versi Java apa yang diperlukan?** Java 8 atau lebih baru.

## Apa itu “cara menambahkan tugas” dalam file MPP?
Menambahkan tugas berarti menyisipkan item kerja baru ke dalam hierarki proyek, menentukan tanggal mulai/selesai, dan menyimpan perubahan kembali ke file MPP. Aspose.Tasks menyederhanakan detail format file tingkat rendah, memungkinkan Anda fokus pada logika bisnis sambil secara otomatis menangani penugasan sumber daya, kalender, dan perhitungan ketergantungan. Ia juga memperbarui penugasan terkait dan menghitung ulang jadwal proyek untuk menjaga konsistensi antar tugas yang bergantung.

## Mengapa menggunakan Aspose.Tasks untuk Java?
- **Kompatibilitas penuh**: Mendukung 100% fitur di seluruh Microsoft Project 2007‑2021 (lebih dari 150 tipe tugas dan 200 bidang sumber daya).  
- **Tanpa ketergantungan**: Tidak memerlukan COM, Office, atau perpustakaan native—API Java murni dapat dijalankan di mana saja JRE berjalan.  
- **Set fitur lengkap**: Termasuk penautan tugas, alokasi sumber daya, bidang khusus, dan pelaporan bawaan.  
- **Kinerja tinggi**: Memproses proyek dengan hingga 10.000 tugas menggunakan kurang dari 200 MB RAM, menjadikannya ideal untuk otomasi sisi server.

## Prasyarat
1. **Lingkungan Pengembangan Java** – JDK 8+ terpasang dan terkonfigurasi.  
2. **Aspose.Tasks untuk Java** – Unduh dari [halaman unduhan](https://releases.aspose.com/tasks/java/).  
3. **Pengetahuan dasar Java** – Familiaritas dengan kelas, objek, dan penanganan tanggal.  

## Impor Paket
Pertama, impor kelas-kelas yang Anda perlukan. Ini memberi Anda akses ke manipulasi proyek, properti tugas, dan penanganan tanggal.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` mewakili file Microsoft Project yang dimuat di memori. `SaveFileFormat` mencantumkan format yang dapat Anda simpan, seperti MPP atau PDF. `Task` memodelkan item kerja individual dalam hierarki proyek. `Tsk` menyediakan konstanta untuk bidang tugas yang digunakan saat mengatur atau mengambil nilai. `Calendar` menawarkan utilitas tanggal‑waktu untuk mendefinisikan jadwal.

## Langkah 1: Tentukan Direktori Data
```java
String dataDir = "Your Data Directory";
```  
Ganti `"Your Data Directory"` dengan path absolut tempat file MPP sumber Anda berada.

## Langkah 2: Baca Proyek yang Ada
Kelas `Project` adalah objek inti Aspose.Tasks yang mewakili file Microsoft Project di memori.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Konstruktor memuat **SampleMSP2010.mpp**, memberi Anda model objek yang dapat dimanipulasi sepenuhnya.

## Langkah 3: Buat Tugas Baru (cara menambahkan tugas)
Kelas `Task` mewakili item kerja individual di dalam hierarki proyek.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Baris ini **membuat tugas dalam mpp** dengan menambahkan anak bernama *Task1* ke tugas root.

## Langkah 4: Atur Tanggal Mulai dan Selesai
Kelas `Calendar` menyediakan utilitas tanggal‑waktu; bulan dimulai dari nol (mis., `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Di sini kami mendefinisikan jadwal untuk tugas yang baru ditambahkan. Sesuaikan tanggal agar cocok dengan timeline proyek Anda.

## Langkah 5: Simpan Proyek (simpan proyek sebagai mpp)
`SaveFileFormat.Mpp` memberi tahu Aspose.Tasks untuk menulis file kembali dalam format Microsoft Project native.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Proyek yang diperbarui, kini berisi tugas baru, disimpan sebagai **AfterLinking.mpp**.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **File tidak ditemukan** | Verifikasi `dataDir` berakhir dengan pemisah path (`/` atau `\\`) dan nama file sudah benar. |
| **Tanggal tidak tepat** | Ingat bahwa bulan pada `Calendar` dimulai dari nol; `Calendar.JULY` adalah benar untuk Juli. |
| **Pengecualian lisensi** | Instal lisensi Aspose.Tasks yang valid sebelum memanggil API apa pun untuk menghindari watermark evaluasi. |

## Pertanyaan yang Sering Diajukan
**Q: Bagaimana cara menambahkan beberapa tugas sekaligus?**  
A: Lakukan iterasi pada koleksi nama tugas dan ulangi blok “buat tugas” di dalam loop.

**Q: Bisakah saya mengatur bidang khusus untuk tugas baru?**  
A: Ya—gunakan `task.set(Tsk.CUSTOM_FIELD_x, value)` dimana *x* adalah indeks bidang.

**Q: Apakah memungkinkan menyalin tugas yang ada sebagai templat?**  
A: Kloning tugas sumber (`Task cloned = sourceTask.clone();`) lalu tambahkan ke induk yang diinginkan.

**Q: Bagaimana jika saya perlu memperbarui tugas yang sudah ada alih-alih menambahkan yang baru?**  
A: Ambil tugas berdasarkan ID (`Task existing = project.getRootTask().getChildren().getById(id);`) dan ubah propertinya.

**Q: Apakah Aspose.Tasks mendukung penyimpanan ke format lain seperti PDF atau PNG?**  
A: Ya—gunakan `project.save("output.pdf", SaveFileFormat.Pdf);` atau `SaveFileFormat.Png` untuk representasi visual.

**Terakhir Diperbarui:** 2026-06-25  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat File MPP – Buat & Simpan Proyek Kosong dalam Format MPP dengan Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Cara Membuat Proyek – Atur Atribut Tugas Baru dengan Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Buat Daftar Tugas Java – Baseline MS Project menggunakan Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}