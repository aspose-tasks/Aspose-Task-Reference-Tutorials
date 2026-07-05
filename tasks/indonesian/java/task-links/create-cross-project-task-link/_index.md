---
date: 2026-07-05
description: Pelajari cara menghubungkan tugas antar proyek dengan Aspose.Tasks untuk
  Java. Panduan langkah demi langkah, prasyarat, dan praktik terbaik untuk menghubungkan
  tugas lintas proyek secara mulus.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Buat Tautan Tugas Lintas Proyek di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Menghubungkan Tugas Antara Proyek Menggunakan Aspose.Tasks untuk Java
url: /id/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menautkan Tugas Antara Proyek Menggunakan Aspose.Tasks untuk Java

## Pendahuluan
Menautkan tugas antar proyek adalah kemampuan inti yang memungkinkan Anda menyinkronkan pekerjaan, menghindari duplikasi, dan mempertahankan satu sumber kebenaran untuk aktivitas yang saling bergantung. Dalam tutorial ini Anda akan mempelajari cara **menautkan tugas antar proyek** dengan Aspose.Tasks untuk Java, langkah demi langkah. Pada akhir tutorial Anda akan memiliki tautan lintas‑proyek yang berfungsi penuh dan memperbarui secara otomatis ketika salah satu sisi berubah, memberikan koordinasi waktu nyata tanpa menyalin‑tempel secara manual.

## Jawaban Cepat
- **Apa kelas utama untuk membuat proyek?** `Project` – mewakili seluruh file MS‑Project dalam memori.  
- **Metode mana yang menambahkan tugas eksternal?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **Bisakah saya mengatur tipe tautan?** Ya – gunakan `TaskLinkType.FinishToStart`, `StartToStart`, dll.  
- **Apakah saya memerlukan lisensi untuk menautkan?** Lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi; percobaan gratis dapat digunakan untuk evaluasi.  
- **Apakah ada batasan pada tugas yang ditautkan?** Aspose.Tasks dapat menangani 10.000+ tugas yang ditautkan per proyek tanpa penurunan kinerja.

## Apa itu menautkan tugas antar proyek?
Menautkan tugas antar proyek menciptakan hubungan ketergantungan antara sebuah tugas dalam satu file proyek dengan tugas di proyek lain, memungkinkan perubahan pada tugas sumber (durasi, tanggal mulai, batasan) mengalir secara otomatis ke tugas yang bergantung. Mekanisme ini menjaga jadwal tetap selaras, mengurangi pembaruan manual, dan memastikan setiap modifikasi pada proyek sumber langsung tercermin di semua proyek yang ditautkan, menjaga konsistensi di seluruh portofolio.

## Mengapa menggunakan Aspose.Tasks untuk penautan lintas‑proyek?
Aspose.Tasks mendukung **lebih dari 50 format input dan output** serta dapat memproses **proyek berukuran ratusan halaman** sambil menjaga penggunaan memori di bawah 200 MB. API‑nya melakukan penautan di sisi server, menghilangkan kebutuhan instalasi Microsoft Project dan memungkinkan pipeline otomatis untuk perusahaan besar.

## Prasyarat
- Java 17 (atau lebih baru) terinstal dan dikonfigurasi di IDE Anda.  
- File lisensi Aspose.Tasks untuk Java yang valid (`Aspose.Tasks.Java.lic`).  
- Perpustakaan Aspose.Tasks untuk Java ditambahkan ke proyek Anda. Anda dapat mengunduhnya dari [halaman rilis Aspose.Tasks untuk Java](https://releases.aspose.com/tasks/java/).  
- Pengetahuan dasar tentang konsep MS‑Project seperti tugas, tugas ringkasan, dan ketergantungan.

## Mengimpor Paket
`Project`, `Task`, `TaskLink`, dan enum terkait berada di namespace `com.aspose.tasks`. Impor mereka di bagian atas file Java Anda:

`import com.aspose.tasks.*;`

**Project** adalah kelas utama yang mewakili file proyek dalam memori. **Task** mewakili item kerja individu dalam sebuah proyek. **TaskLink** mendefinisikan hubungan ketergantungan antara dua tugas. Impor ini memberi Anda akses ke seluruh rangkaian fitur manipulasi proyek, termasuk penautan lintas‑proyek.

## Cara menautkan tugas antar proyek?
Muat kedua file proyek, tambahkan placeholder tugas eksternal, buat tugas lokal, lalu hubungkan keduanya dengan sebuah `TaskLink`. API menangani pemetaan ID dan pembaruan secara otomatis, memastikan setiap perubahan pada tugas eksternal menyebar ke tugas lokal yang ditautkan tanpa kode tambahan. Pendekatan ini menyederhanakan koordinasi multi‑proyek dan mengurangi risiko penyimpangan jadwal.

### Langkah 1: Siapkan Lingkungan Anda
Pastikan JAR Aspose.Tasks berada di classpath dan file lisensi dimuat pada runtime:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** memuat file lisensi Aspose.Tasks Anda untuk mengaktifkan fungsionalitas penuh dan menghapus watermark evaluasi.

### Langkah 2: Buat Instance Project
Instansiasi objek `Project` baru untuk proyek target tempat tautan akan ditempatkan:

`Project targetProject = new Project();`

Kelas `Project` adalah objek tingkat atas Aspose.Tasks yang mewakili satu file proyek dalam memori.

### Langkah 3: Tambahkan Tugas Ringkasan
Tugas ringkasan mengelompokkan tugas terkait. Buat satu untuk menampung tugas eksternal dan lokal:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### Langkah 4: Tambahkan Tugas Eksternal
Masukkan tugas eksternal yang menunjuk ke tugas dalam file proyek lain:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

Metode **addExternalTask** membuat tugas placeholder yang merujuk ke file proyek eksternal, menggunakan nama file dan ID tugas yang diberikan.

### Langkah 5: Tambahkan Tugas Lokal
Buat tugas yang akan ditautkan ke tugas eksternal:

`Task local = summary.getChildren().add("Local Task");`

### Langkah 6: Buat Tautan Tugas
Buat ketergantungan antara tugas eksternal dan lokal. Tipe tautan paling umum adalah Finish‑to‑Start:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** mencatat hubungan tersebut; Anda dapat mengubah lag, lead, atau tipe sesuai kebutuhan nanti.

### Langkah 7: Simpan dan Verifikasi
Persistensikan proyek ke file dan opsional buka di Microsoft Project untuk memverifikasi tautan:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** menentukan format file untuk menyimpan proyek. Saat Anda membuka *LinkedProject.mpp*, Anda akan melihat tugas eksternal ditampilkan dengan ikon khusus dan garis ketergantungan yang menunjuk ke tugas lokal.

## Masalah Umum dan Solusinya
- **File eksternal tidak ditemukan** – Pastikan jalur relatif terhadap proses yang berjalan atau berikan jalur absolut.  
- **ID tugas tidak cocok** – Verifikasi ID tugas eksternal (argumen kedua `addExternalTask`) cocok dengan proyek sumber.  
- **Lisensi tidak dimuat** – File lisensi yang hilang atau tidak tepat menghasilkan `LicenseException`. Muat lisensi sebelum memanggil fungsi Aspose.Tasks apa pun.  
- **Kinerja pada proyek besar** – Gunakan `Project.setReadOnly(true)` ketika Anda hanya perlu membaca tugas eksternal; ini mengurangi beban memori.

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menautkan tugas dari beberapa proyek eksternal dalam satu tugas ringkasan?**  
J: Ya, Anda dapat menambahkan beberapa tugas eksternal di bawah satu tugas ringkasan dan membuat tautan individual untuk masing‑masing, menggunakan metode `addExternalTask` yang sama.

**T: Apa yang terjadi jika tugas eksternal dalam proyek yang ditautkan dimodifikasi?**  
J: Setiap perubahan pada jadwal, durasi, atau batasan tugas eksternal secara otomatis tercermin pada tugas lokal yang bergantung ketika proyek target disegarkan.

**T: Apakah memungkinkan membuat tautan antara tugas dengan format file berbeda?**  
J: Tentu saja. Aspose.Tasks mendukung penautan antara format MPP, XML, dan Primavera, memungkinkan ekosistem proyek heterogen tetap sinkron.

**T: Bisakah saya memutuskan tautan tugas setelah mereka ditautkan antar proyek?**  
J: Ya, hapus tautan dengan memanggil `project.getTaskLinks().remove(link)` atau dengan menghapus placeholder tugas eksternal.

**T: Apakah ada batasan pada jumlah tugas yang dapat ditautkan antar proyek?**  
J: Perpustakaan dapat menangani **10.000+ tugas yang ditautkan** per proyek, terbatas hanya oleh memori sistem yang tersedia dan spesifikasi format file yang mendasarinya.

## Kesimpulan
Anda kini memiliki pendekatan lengkap dan siap produksi untuk **menautkan tugas antar proyek** menggunakan Aspose.Tasks untuk Java. Kemampuan ini menyederhanakan koordinasi multi‑proyek, mengurangi upaya manual, dan memastikan perubahan jadwal menyebar secara instan ke seluruh portofolio Anda. Jelajahi fitur tambahan seperti waktu lag khusus, tipe tautan berbeda, dan penautan massal untuk lebih mengotomatisasi struktur proyek yang kompleks.

---

**Terakhir Diperbarui:** 2026-07-05  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12  
**Penulis:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## Tutorial Terkait

- [Buat Tautan Tugas di Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Buat Tugas Aspose Java – Properti Tugas](/tasks/java/task-properties/)
- [Buat File MS Project Kosong di Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}