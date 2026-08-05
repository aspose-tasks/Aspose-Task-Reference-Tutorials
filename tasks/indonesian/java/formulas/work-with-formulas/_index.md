---
date: 2026-02-13
description: Pelajari cara menghitung hari antara tanggal, membuat proyek percobaan,
  dan menambahkan bidang khusus saat memanipulasi file Microsoft Project menggunakan
  Aspose.Tasks untuk Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Hitung hari antara tanggal dengan Aspose.Tasks untuk Java
url: /id/java/formulas/work-with-formulas/
weight: 11
---

 translations.

Let's assemble.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Menghitung hari antara tanggal dengan Aspose.Tasks untuk Java

## Pendahuluan
In this tutorial you’ll **calculate days between dates** by creating a test project, adding a custom field, and using Microsoft Project formulas through the Aspose.Tasks library for Java. Whether you need to generate schedules, compute deadlines, or automate reporting, Aspose.Tasks lets you manipulate Project data programmatically without a desktop installation. By the end of the guide you’ll have a runnable example that defines an extended attribute, sets a deadline for a task, and saves the project as an MPP file.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Creating a test project, adding a custom field, defining an extended attribute, and setting a task deadline with a formula to calculate days between dates.  
- **Perpustakaan apa yang diperlukan?** Aspose.Tasks for Java (latest version).  
- **Apakah saya memerlukan lisensi?** A free trial works for development; a license is required for production.  
- **IDE apa yang dapat saya gunakan?** Any Java IDE (IntelliJ IDEA, Eclipse, VS Code) that supports JDK 8+.  
- **Berapa lama implementasinya?** About 10‑15 minutes to copy the code and run it.

## Apa itu “calculate days between dates” dalam Aspose.Tasks?
Calculating days between dates means using a Project formula that subtracts one date field (e.g., **Finish**) from another (e.g., **Deadline**) and returns the numeric difference in days. This is useful for tracking schedule slippage, measuring buffer time, or generating custom reports.

## Mengapa Menggunakan Aspose.Tasks untuk Menghitung Hari Antara Tanggal?
- **Cakupan API penuh** – access every Project, Task, and Resource property.  
- **Tidak memerlukan instalasi Office** – works on servers, CI pipelines, and Docker containers.  
- **Lintas‑platform** – runs on Windows, Linux, and macOS with the same Java code.  
- **Mesin formula yang kuat** – lets you define calculations such as `[Deadline] - [Finish]` directly inside the project file.

## Cara menetapkan tenggat waktu untuk sebuah tugas
Setting a deadline is the first step before you can calculate the interval. The deadline is stored in the `Tsk.DEADLINE` field of a task and can be assigned using a `java.util.Calendar` instance.

## Cara mendefinisikan atribut ekstensi
An extended attribute is the custom field that will hold the result of your formula. You define it once, give it an alias for readability, and then attach a formula that performs the date subtraction.

## Prasyarat
Before you start, make sure you have the following:

- **Java Development Kit (JDK) 8+** – download from the Oracle website or adopt OpenJDK.  
- **Aspose.Tasks for Java** – obtain the latest JAR from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) and add it to your project’s classpath or Maven/Gradle dependencies.

## Impor Paket
First, import the classes we’ll need:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Buat Proyek Percobaan dengan Bidang Khusus
We begin by **creating a test project** and adding a custom field that will later hold our formula result.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Tip profesional:* `CreateTestProjectWithCustomField()` is a helper method that builds a minimal schedule and registers an extended attribute ready for formula assignment.

### Langkah 2: Definisikan Atribut Ekstensi (Tambahkan Bidang Khusus)
Next, we **define an extended attribute** – essentially the custom field – and give it a friendly alias. This is where we **add custom field** logic.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** makes the field readable in Project.  
- **Formula** calculates the number of days between a task’s *Finish* date and its *Deadline* – the core of *calculate days between dates*.

### Langkah 3: Tetapkan Tenggat Waktu untuk Tugas (Tambahkan Tugas Deadline & Tetapkan Tenggat Waktu Tugas)
Now we **add deadline task** data by setting the *Deadline* property on a specific task.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- The `Calendar` instance defines the exact deadline moment.  
- `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.

### Langkah 4: Simpan Proyek (Manipulasi File Microsoft Project)
Finally, we **manipulate Microsoft Project** by persisting the changes to an MPP file.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

You can open `SaveFile.mpp` in Microsoft Project to see the custom field, formula result, and deadline reflected in the schedule.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Formula tidak dievaluasi** | Ensure the attribute’s `Formula` string uses correct field names (e.g., `[Deadline]`, `[Finish]`). |
| **Tugas tidak ditemukan** | Verify the task ID (`1` in the example) exists; use `project.getRootTask().getChildren().size()` to debug. |
| **Pengecualian lisensi** | Apply a valid Aspose.Tasks license before calling any API methods (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
A: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing you to **manipulate Microsoft Project** files in the language of your choice.

**Q: Apakah ada percobaan gratis untuk Aspose.Tasks?**  
A: Absolutely. Download a fully functional trial from the [Aspose.Tasks download page](https://releases.aspose.com/).

**Q: Di mana saya dapat menemukan dokumentasi terperinci untuk Aspose.Tasks?**  
A: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Bagaimana saya dapat mendapatkan dukungan untuk Aspose.Tasks?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to ask questions and share experiences with the community.

**Q: Apakah saya memerlukan lisensi sementara untuk evaluasi?**  
A: A temporary license is available for short‑term testing; you can request one [here](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2026-02-13  
**Diuji Dengan:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}