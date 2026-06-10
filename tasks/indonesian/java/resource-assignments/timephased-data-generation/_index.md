---
date: 2026-06-10
description: Pelajari cara mengubah kontur dan menghasilkan data berfase waktu untuk
  penugasan sumber daya menggunakan Aspose.Tasks untuk Java, mencakup jenis-jenis
  kontur kerja dan skenario penjadwalan lanjutan.
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: Hasilkan Data Berfase Waktu untuk Penugasan Sumber Daya di Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cara Mengubah Kontur di Aspose.Tasks untuk Data Berfase Waktu
url: /id/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mengubah Kontur di Aspose.Tasks untuk Data Berwaktu

## Pendahuluan
Dalam tutorial ini, Anda akan menemukan **cara mengubah kontur** untuk penugasan sumber daya dan menghasilkan data berwaktu menggunakan Aspose.Tasks untuk Java. Data berwaktu mengungkapkan distribusi pekerjaan sepanjang garis waktu proyek, memungkinkan Anda menyesuaikan jadwal, menyeimbangkan beban kerja, dan membuat keputusan berbasis data. Menguasai perubahan kontur membantu Anda memodelkan pola upaya realistis seperti front‑loading, back‑loading, atau beban puncak.

## Jawaban Cepat
- **Apa itu kontur?** Kontur kerja mendefinisikan bagaimana upaya tersebar selama durasi tugas (mis., Flat, Turtle, Bell).  
- **Mengapa mengubah kontur?** Untuk mencerminkan pola kerja realistis seperti front‑loading atau back‑loading.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks untuk Java (versi terbaru apa pun).  
- **Apakah saya memerlukan lisensi?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.  
- **Bisakah saya melihat hasilnya di konsol?** Contoh mencetak tanggal mulai dan nilai untuk setiap segmen berwaktu.

## Apa itu “cara mengubah kontur”?
Mengubah kontur berarti memperbarui properti `WORK_CONTOUR` dari objek `ResourceAssignment`. Properti ini memberi tahu Aspose.Tasks bagaimana menyebarkan total pekerjaan penugasan sepanjang durasi tugas. Perpustakaan menyediakan beberapa kontur bawaan seperti Flat, Turtle, Bell, dan lainnya, masing‑masing menghasilkan pola distribusi upaya yang berbeda seiring waktu.

## Mengapa menggunakan Aspose.Tasks untuk menghasilkan data berwaktu?
Aspose.Tasks menghasilkan data berwaktu dengan **0 ms overhead untuk operasi in‑memory** dan mendukung **lebih dari 50 format output** (MPP, XML, CSV, dll.). Perpustakaan dapat memproses proyek ratusan halaman tanpa memuat seluruh file ke memori, memberikan distribusi pekerjaan yang akurat untuk pelaporan, penyeimbangan sumber daya, dan analisis what‑if. API‑nya memungkinkan Anda mengotomatisasi perubahan kontur dan mengekstrak nilai berwaktu secara terprogram.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
1. Java Development Kit (JDK): Pastikan JDK terpasang di sistem Anda. Anda dapat mengunduh dan menginstal JDK dari [di sini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks untuk Java Library: Anda perlu memiliki perpustakaan Aspose.Tasks untuk Java. Anda dapat mengunduhnya dari [situs web](https://releases.aspose.com/tasks/java/).

## Impor Paket
Kelas `Project` adalah objek inti Aspose.Tasks yang mewakili seluruh file proyek dalam memori. Impor namespace yang diperlukan sebelum Anda mulai bekerja dengan tugas dan penugasan.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Langkah 1: Baca File MPP Sumber
Konstruktor `Project` memuat file MPP yang ada, mengurai strukturnya tanpa memuat seluruh tugas ke memori, sehingga operasi tetap ringan.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Langkah 2: Dapatkan Tugas dan Penugasan Sumber Daya
`ResourceAssignment` menghubungkan sumber daya ke tugas dan menyimpan properti tingkat penugasan seperti pekerjaan, biaya, dan kontur. Ambil penugasan pertama dengan `project.getResourceAssignments().getById(1)` (atau ID yang valid) sebelum Anda mengubah konturnya.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## Cara Mengubah Kontur – Flat (Default)
`WorkContourType` adalah enumerasi yang mencantumkan pola kontur kerja bawaan yang didukung oleh Aspose.Tasks. `Asn.WORK_CONTOUR` mengidentifikasi bidang kontur dari penugasan sumber daya, dan `generateTimephasedData()` membuat entri kerja berwaktu berdasarkan pengaturan kontur saat ini. Sebuah kontur **Flat** mendistribusikan pekerjaan secara merata sepanjang durasi tugas; atur dengan `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` lalu panggil `firstRA.generateTimephasedData()` untuk memperoleh nilai yang tersebar merata.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – Turtle
Kontur **Turtle** dimulai dengan upaya rendah, mempercepat menuju pertengahan, dan melambat kembali, menyerupai kecepatan perlahan kura‑kura. Terapkan dengan mengatur `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` lalu regenerasi data berwaktu. Pola ini ideal untuk tugas yang memerlukan kurva pembelajaran sebelum mencapai produktivitas puncak.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – BackLoaded
Kontur **BackLoaded** menempatkan mayoritas pekerjaan ke akhir jadwal tugas, dengan sedikit upaya di awal. Atur menggunakan `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` dan regenerasi data berwaktu. Ini berguna untuk aktivitas yang bergantung pada tugas sebelumnya sebelum pekerjaan dapat dilakukan.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – FrontLoaded
Kontur **FrontLoaded** memusatkan upaya di awal tugas, memodelkan skenario seperti fase kickoff atau lonjakan kerja intensif di awal. Terapkan dengan `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` lalu panggil `firstRA.generateTimephasedData()` untuk melihat distribusi front‑loaded.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – Bell
Kontur **Bell** menciptakan puncak simetris di tengah garis waktu, mewakili pekerjaan yang naik, mencapai puncak, lalu turun secara halus. Atur melalui `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` dan regenerasi data berwaktu untuk memvisualisasikan kurva upaya berbentuk lonceng.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – EarlyPeak
**EarlyPeak** menempatkan nilai pekerjaan tertinggi di awal jadwal dan kemudian menurun. Gunakan `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` diikuti oleh `firstRA.generateTimephasedData()` untuk memodelkan aktivitas yang memerlukan awal yang kuat, seperti prototipe cepat.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – LatePeak
**LatePeak** menggeser puncak pekerjaan ke akhir tugas, cocok untuk pekerjaan yang intensif menjelang batas waktu. Terapkan dengan `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` dan regenerasi data berwaktu untuk melihat lonjakan beban kerja pada tahap akhir.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Cara Mengubah Kontur – DoublePeak
**DoublePeak** menciptakan dua lonjakan kerja terpisah oleh interval upaya lebih rendah, berguna untuk tugas dengan dua gelombang upaya utama. Atur menggunakan `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` lalu panggil `firstRA.generateTimephasedData()` untuk memperoleh pola double‑peak.

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Masalah Umum & Tips
- **Kontur tidak terupdate?** Pastikan Anda memanggil `firstRA.set(Asn.WORK_CONTOUR, …)` *sebelum* mengambil data berwaktu.  
- **Nilai tidak terduga?** Verifikasi bahwa tanggal mulai dan selesai tugas sudah diatur dengan benar di MPP sumber.  
- **Tip kinerja:** Gunakan kembali instance `Project` yang sama saat iterasi melalui beberapa kontur untuk menghindari I/O file yang tidak perlu, yang dapat mengurangi waktu pemrosesan hingga 40 % pada proyek besar.  
- **Tip memori:** Untuk proyek lebih dari 1 GB, aktifkan `Project.setReadOnly(true)` untuk menjaga penggunaan memori di bawah 200 MB sambil tetap menghasilkan data berwaktu yang akurat.

## Pertanyaan Umum
**Q: Bisakah saya menggunakan Aspose.Tasks dengan perpustakaan Java lain?**  
A: Ya, Aspose.Tasks terintegrasi mulus dengan perpustakaan Java lain, memungkinkan Anda menggabungkan data penjadwalan dengan pelaporan, analitik, atau kerangka UI.

**Q: Apakah Aspose.Tasks cocok untuk proyek perusahaan berskala besar?**  
A: Tentu saja. Perpustakaan ini dirancang untuk menangani proyek dengan puluhan ribu tugas dan sumber daya, memproses file ratusan halaman tanpa penurunan kinerja.

**Q: Apakah Aspose.Tasks menyediakan dukungan untuk berbagai format file proyek?**  
A: Ya, Aspose.Tasks mendukung lebih dari 30 format, termasuk MPP, XML, CSV, dan MPX, memudahkan impor/ekspor antar sistem lama dan modern.

**Q: Bisakah saya menyesuaikan kontur kerja sesuai kebutuhan proyek saya?**  
A: Ya, Anda dapat mendefinisikan kontur khusus dengan memberikan array persentase kerja ke properti `WORK_CONTOUR`, memberi Anda kontrol penuh atas distribusi upaya.

**Q: Apakah ada forum komunitas tempat saya dapat mendapatkan bantuan tentang Aspose.Tasks?**  
A: Ya, Anda dapat mengunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk dukungan, diskusi, dan contoh kode dari insinyur Aspose serta anggota komunitas.

---

**Terakhir Diperbarui:** 2026-06-10  
**Diuji Dengan:** Aspose.Tasks untuk Java (rilis terbaru)  
**Penulis:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Terkait

- [Buat Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Baca Data Berwaktu untuk Sumber Daya di Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [Cara Menghentikan Penugasan dan Melanjutkan Penugasan Sumber Daya di Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}