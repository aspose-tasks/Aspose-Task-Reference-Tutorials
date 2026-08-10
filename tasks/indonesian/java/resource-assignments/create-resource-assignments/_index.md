---
date: 2026-05-20
description: Pelajari cara menambahkan resource ke project dan membuat resource assignments
  menggunakan Aspose.Tasks for Java, sebuah perpustakaan manajemen proyek Java yang
  kuat.
keywords:
- add resource to project
- how to add task
- assign resource to task
- java project management library
linktitle: Buat Resource Assignments di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  headline: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource to project and create resource assignments
    using Aspose.Tasks for Java, a robust Java project management library.
  name: How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks
  steps:
  - name: Create a Project Object
    text: 'The `Project` class is the top‑level container that represents a single
      project file in memory. Instantiate a `Project` object, which represents the
      project file you''re working with:'
  - name: Add a Task to the Project
    text: 'The `Task` class models an individual work item within the schedule. Add
      a task to the project using the `addChild` method of the root task:'
  - name: Add a Resource to the Project
    text: 'The `Resource` class defines a person, equipment, or material that can
      be assigned to tasks. Add a resource to the project using the `add` method of
      the `Resources` collection:'
  - name: Create a Resource Assignment
    text: 'The `ResourceAssignment` class links a `Task` and a `Resource` and stores
      allocation details such as work hours and cost. Create a resource assignment
      for the task and resource using the `add` method of the `ResourceAssignments`
      collection:'
  type: HowTo
- questions:
  - answer: Yes, you can update assignment properties such as `Work`, `Cost`, and
      `Start` using the setters provided by the `ResourceAssignment` class.
    question: Can I modify resource assignments after creation?
  - answer: Absolutely, Aspose.Tasks for Java supports MPP, XML, CSV, and many other
      formats, allowing seamless import and export.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Yes, a valid commercial license is required. A free evaluation license
      is available for testing purposes.
    question: Does Aspose.Tasks for Java require a license for commercial use?
  - answer: Yes, the library is fully thread‑safe and can be integrated into servlet‑based
      or Spring‑Boot web services.
    question: Can I use Aspose.Tasks for Java in my web applications?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for technical assistance and community discussions.
    question: Where can I find additional support for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara Menambahkan Resource ke Project dan Membuat Resource Assignments di Aspose.Tasks
url: /id/java/resource-assignments/create-resource-assignments/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tambahkan Sumber Daya ke Proyek – Buat Penugasan Sumber Daya di Aspose.Tasks

## Pendahuluan
Pada manajemen proyek modern, **add resource to project** adalah landasan utama penjadwalan yang efektif dan kontrol biaya. Aspose.Tasks untuk Java memberikan cara programatik yang berperforma tinggi untuk mengelola sumber daya, tugas, dan penugasan tanpa meninggalkan IDE Anda. Dalam tutorial ini Anda akan melihat secara tepat cara menambahkan sumber daya ke proyek, melampirkannya ke tugas, dan menyempurnakan detail penugasan—semua dengan kode Java yang bersih dan siap produksi.

## Jawaban Cepat
- **Apa langkah pertama?** Buat instance `Project` yang mewakili file .mpp atau .xml Anda.  
- **Bagaimana cara menambahkan tugas?** Gunakan metode `addChild` pada tugas root dan beri nama tugas tersebut.  
- **Bagaimana cara menambahkan sumber daya?** Panggil `project.getResources().add` dengan objek `Resource`.  
- **Bagaimana cara menghubungkan sumber daya ke tugas?** Gunakan `project.getResourceAssignments().add(task, resource)`.  
- **Apakah saya memerlukan lisensi?** Ya – lisensi Aspose.Tasks untuk Java yang valid diperlukan untuk penggunaan produksi.

## Apa itu “add resource to project”?
**Add resource to project** berarti membuat objek `Resource` dalam file proyek dan menghubungkannya ke satu atau lebih tugas sehingga data pekerjaan, biaya, dan kalender dihitung secara otomatis. Operasi ini adalah tulang punggung dari setiap aplikasi berbasis jadwal.

## Mengapa memilih Aspose.Tasks untuk Java?
Aspose.Tasks untuk Java mendukung **lebih dari 30 format input dan output** (termasuk MPP, XML, dan CSV) dan dapat memproses proyek dengan **lebih dari 10.000 tugas** sambil menjaga penggunaan memori di bawah 200 MB. Perpustakaan ini berjalan pada Java 8‑17, tidak memerlukan instalasi Microsoft Project, dan menyediakan API yang thread‑safe untuk otomatisasi sisi server.

## Prasyarat
Sebelum kita menyelami pembuatan penugasan sumber daya, pastikan Anda memiliki hal berikut:

### Lingkungan Pengembangan Java
Pastikan Anda memiliki Java Development Kit (JDK) terpasang di sistem Anda. Anda dapat mengunduh dan menginstal JDK dari [di sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Perpustakaan Aspose.Tasks untuk Java
Unduh perpustakaan Aspose.Tasks untuk Java dari [halaman unduhan](https://releases.aspose.com/tasks/java/). Ikuti petunjuk instalasi untuk menyiapkan perpustakaan dalam proyek Java Anda.

## Cara menambahkan sumber daya ke proyek?
Muat proyek Anda, buat sebuah tugas, tambahkan sumber daya, dan akhirnya hubungkan semuanya – semua dalam empat langkah singkat. Potongan kode di bawah (placeholder) menunjukkan pemanggilan API yang tepat; Anda hanya perlu mengganti teks placeholder dengan jalur file dan nama Anda sendiri.

### Langkah 1: Buat Objek Project
Kelas `Project` adalah kontainer tingkat atas yang mewakili satu file proyek dalam memori.  
Instansiasi objek `Project`, yang mewakili file proyek yang sedang Anda kerjakan:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
```

### Langkah 2: Tambahkan Tugas ke Proyek
Kelas `Task` memodelkan item kerja individu dalam jadwal.  
Tambahkan tugas ke proyek menggunakan metode `addChild` dari tugas root:
```java
Project project = new Project();
```

### Langkah 3: Tambahkan Sumber Daya ke Proyek
Kelas `Resource` mendefinisikan orang, peralatan, atau material yang dapat ditugaskan ke tugas.  
Tambahkan sumber daya ke proyek menggunakan metode `add` dari koleksi `Resources`:
```java
Task task = project.getRootTask().getChildren().add("Task");
```

### Langkah 4: Buat Penugasan Sumber Daya
Kelas `ResourceAssignment` menghubungkan `Task` dan `Resource` serta menyimpan detail alokasi seperti jam kerja dan biaya.  
Buat penugasan sumber daya untuk tugas dan sumber daya menggunakan metode `add` dari koleksi `ResourceAssignments`:
```java
Resource rsc = project.getResources().add("Rsc");
```

## Masalah Umum dan Solusinya
- **NullPointerException pada `addChild`** – Pastikan Anda memanggil `project.getRootTask()` sebelum menambahkan anak.  
- **Lisensi tidak ditemukan** – Tempatkan file `Aspose.Tasks.lic` Anda di classpath atau atur lisensi secara programatik dengan `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Penurunan kinerja pada proyek besar** – Gunakan `project.setReadOnly(true)` ketika Anda hanya perlu membaca data; ini mengurangi beban memori.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya memodifikasi penugasan sumber daya setelah dibuat?**  
A: Ya, Anda dapat memperbarui properti penugasan seperti `Work`, `Cost`, dan `Start` menggunakan setter yang disediakan oleh kelas `ResourceAssignment`.

**Q: Apakah Aspose.Tasks untuk Java kompatibel dengan berbagai format file proyek?**  
A: Tentu saja, Aspose.Tasks untuk Java mendukung MPP, XML, CSV, dan banyak format lainnya, memungkinkan impor dan ekspor yang mulus.

**Q: Apakah Aspose.Tasks untuk Java memerlukan lisensi untuk penggunaan komersial?**  
A: Ya, lisensi komersial yang valid diperlukan. Lisensi evaluasi gratis tersedia untuk tujuan pengujian.

**Q: Bisakah saya menggunakan Aspose.Tasks untuk Java dalam aplikasi web saya?**  
A: Ya, perpustakaan ini sepenuhnya thread‑safe dan dapat diintegrasikan ke dalam layanan web berbasis servlet atau Spring‑Boot.

**Q: Di mana saya dapat menemukan dukungan tambahan untuk Aspose.Tasks untuk Java?**  
A: Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk bantuan teknis dan diskusi komunitas.

---

**Terakhir Diperbarui:** 2026-05-20  
**Diuji Dengan:** Aspose.Tasks for Java 24.12  
**Penulis:** Aspose  

```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Cara Membuat Sumber Daya – Manajemen Sumber Daya dengan Aspose.Tasks untuk Java](/tasks/java/resource-management/)
- [Cara Menambahkan Catatan ke Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Cara Menambahkan Sumber Daya ke Proyek dan Menangani Properti Penundaan Leveling di Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}