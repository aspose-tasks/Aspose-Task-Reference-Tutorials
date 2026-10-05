---
date: 2026-10-05
description: Pelajari cara membuat proyek uji dan menghitung hari antara tanggal menggunakan
  Aspose.Tasks for Java, menambahkan bidang khusus, dan memanipulasi file MPP secara
  efisien.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Bekerja dengan rumus di Aspose.Tasks
og_description: Buat proyek uji dan hitung hari antara tanggal menggunakan Aspose.Tasks
  for Java. Panduan ini menunjukkan cara menambahkan bidang khusus, menetapkan tenggat
  waktu tugas, dan menyimpan proyek sebagai file MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Buat proyek uji dan hitung hari antara tanggal
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Buat proyek uji dan hitung hari antara tanggal
url: /id/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat proyek uji dan hitung hari antara tanggal

Dalam tutorial ini Anda akan **membuat proyek uji** dan **menghitung hari antara tanggal** dengan menambahkan bidang khusus, mendefinisikan atribut ekstensi, dan menerapkan formula Microsoft Project melalui pustaka Aspose.Tasks untuk Java. Baik Anda perlu menghasilkan jadwal, menghitung tenggat waktu, atau mengotomatisasi pelaporan, Aspose.Tasks memungkinkan Anda memanipulasi data Project secara programatis tanpa instalasi desktop, mendukung lebih dari 50 format input dan output serta menangani file ratusan halaman dalam mode efisien memori.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Menunjukkan cara membuat proyek uji, mendefinisikan atribut ekstensi, menetapkan tenggat waktu tugas, dan menggunakan formula untuk menghitung hari antara tanggal.  
- **Pustaka mana yang diperlukan?** Aspose.Tasks for Java (latest version).  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk penggunaan produksi.  
- **IDE apa yang dapat saya gunakan?** IDE Java apa pun (IntelliJ IDEA, Eclipse, VS Code) yang mendukung JDK 8+.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk menyalin kode dan menjalankannya.

## Apa itu “calculate days between dates” dalam Aspose.Tasks?
Dalam Aspose.Tasks, formula adalah string yang dapat merujuk ke bidang tugas dan melakukan perhitungan. `[Deadline] - [Finish]` adalah sintaks formula yang digunakan Aspose.Tasks untuk mengembalikan selisih numerik dalam hari antara dua bidang tanggal. Hasilnya disimpan sebagai nilai numerik yang mewakili hari penuh, yang dapat Anda tampilkan dalam bidang khusus atau gunakan dalam perhitungan lebih lanjut.

## Mengapa menggunakan Aspose.Tasks untuk menghitung hari antara tanggal?
Aspose.Tasks menyediakan **cakupan API lengkap** untuk setiap properti Project, Task, dan Resource, berjalan di Windows, Linux, dan macOS, serta **tidak memerlukan Microsoft Project atau Office** terinstal. Mesin ini dapat memproses proyek dengan **lebih dari 500 tugas** dalam waktu kurang dari satu detik pada perangkat keras server tipikal, menjadikannya ideal untuk pipeline CI, kontainer Docker, dan pemrosesan batch volume tinggi.

## Cara menetapkan tenggat waktu untuk tugas
java.util.Calendar adalah kelas Java yang mewakili momen tertentu dalam waktu. Anda menetapkan tenggat waktu dengan memberikan nilai `java.util.Calendar` ke bidang `Tsk.DEADLINE` pada sebuah tugas. Setelah membuat instance Calendar, atur tahun, bulan, dan hari ke tenggat waktu yang diinginkan, lalu panggil `task.set(Tsk.DEADLINE, calendar);`. Tenggat waktu disimpan dalam file proyek dan dapat digunakan dalam formula seperti `[Deadline] - [Finish]`.

## Cara mendefinisikan atribut ekstensi
Atribut ekstensi adalah bidang khusus yang menyimpan hasil formula Anda. Anda membuatnya sekali, memberi alias yang mudah dipahami, dan melampirkan ekspresi `[Deadline] - [Finish]` sehingga setiap tugas dapat secara otomatis menghitung interval. Buatlah dengan menginstansiasi `ExtendedAttribute`, mengatur Alias-nya, menetapkan formula, dan menambahkannya ke koleksi proyek.

## Prasyarat
Sebelum Anda memulai, pastikan Anda memiliki hal berikut:

- **Java Development Kit (JDK) 8+** – unduh dari situs web Oracle atau gunakan OpenJDK.  
- **Aspose.Tasks for Java** – dapatkan JAR terbaru dari [halaman unduhan Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) dan tambahkan ke classpath proyek Anda atau dependensi Maven/Gradle.

## Impor paket
Pertama, impor kelas yang akan kami butuhkan:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Panduan langkah‑demi‑langkah

### Langkah 1: Buat proyek uji dengan bidang khusus
Kami memulai dengan **membuat proyek uji** dan menambahkan bidang khusus yang nantinya akan menyimpan hasil formula kami.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Tip pro:* `CreateTestProjectWithCustomField()` adalah metode pembantu yang membuat jadwal minimal dan mendaftarkan atribut ekstensi siap untuk penetapan formula.

### Langkah 2: Definisikan atribut ekstensi (tambahkan bidang khusus)
Selanjutnya, kami **mendefinisikan atribut ekstensi** – pada dasarnya bidang khusus – dan memberi alias yang mudah dipahami. Di sinilah kami menambahkan logika **bidang khusus**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** membuat bidang dapat dibaca di Project.  
- **Formula** menghitung jumlah hari antara tanggal *Finish* tugas dan *Deadline*‑nya – inti dari *calculate days between dates*.

### Langkah 3: Tetapkan tenggat waktu untuk tugas (tambahkan tugas tenggat waktu & setel tenggat waktu tugas)
Sekarang kami **menambahkan data tugas tenggat waktu** dengan mengatur properti *Deadline* pada tugas tertentu.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Instansi `Calendar` menentukan momen tenggat waktu yang tepat.  
- `set(Tsk.DEADLINE, …)` **menetapkan tenggat waktu tugas** untuk tugas yang dipilih.

### Langkah 4: Simpan proyek (manipulasi file Microsoft Project)
Akhirnya, kami **memanipulasi Microsoft Project** dengan menyimpan perubahan ke file MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Anda dapat membuka `SaveFile.mpp` di Microsoft Project untuk melihat bidang khusus, hasil formula, dan tenggat waktu yang tercermin dalam jadwal.

## Masalah umum dan solusi

| Masalah | Solusi |
|---------|--------|
| **Formula tidak dievaluasi** | Pastikan string `Formula` atribut menggunakan nama bidang yang benar (mis., `[Deadline]`, `[Finish]`). |
| **Tugas tidak ditemukan** | Verifikasi bahwa ID tugas (`1` dalam contoh) ada; gunakan `project.getRootTask().getChildren().size()` untuk debug. |
| **Pengecualian lisensi** | Terapkan lisensi Aspose.Tasks yang valid sebelum memanggil metode API apa pun (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Pertanyaan yang sering diajukan

**Q: Dapatkah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
A: Ya, Aspose.Tasks menyediakan API untuk .NET, Java, dan platform lainnya, memungkinkan Anda memanipulasi file Microsoft Project dalam bahasa pilihan Anda.

**Q: Apakah ada percobaan gratis untuk Aspose.Tasks?**  
A: Tentu saja. Unduh percobaan penuh fungsi dari [halaman unduhan Aspose.Tasks](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks?**  
A: Dokumentasi resmi tersedia di [Referensi API Java Aspose.Tasks](https://reference.aspose.com/tasks/java/).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks?**  
A: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk mengajukan pertanyaan dan berbagi pengalaman dengan komunitas.

**Q: Apakah saya memerlukan lisensi sementara untuk evaluasi?**  
A: Lisensi sementara tersedia untuk pengujian jangka pendek; Anda dapat memintanya dari [halaman permintaan lisensi sementara](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-10-05  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose

## Tutorial Terkait

- [Cara Membuat File MPP – Buat & Simpan Proyek Kosong dalam Format MPP dengan Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Atur Tanggal Mulai Proyek di MS Project menggunakan Aspose.Tasks untuk Java](/tasks/java/project-properties/write-project-info/)
- [Cara membuat atribut ekstensi di Java dengan Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}