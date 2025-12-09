---
date: 2025-12-07
description: Pelajari cara **membuat proyek uji** dan **menambahkan bidang khusus**
  sambil memanipulasi file Microsoft Project menggunakan Aspose.Tasks untuk Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Buat Proyek Uji dan Gunakan Rumus dengan Aspose.Tasks untuk Java
url: /id/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Buat Proyek Uji dan Gunakan Rumus dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial ini Anda akan **membuat file proyek uji**, menambahkan bidang khusus, dan bekerja dengan rumus MS Project menggunakan pustaka Aspose.Tasks untuk Java. Aspose.Tasks memudahkan **manipulasi data Microsoft Project** secara programatis—baik Anda perlu menghasilkan jadwal, menghitung tanggal, atau mengotomatisasi pelaporan. Pada akhir panduan Anda akan memiliki contoh yang dapat dijalankan yang mendefinisikan atribut ekstensi, menetapkan batas waktu untuk sebuah tugas, dan menyimpan proyek sebagai file MPP.

## Jawaban Cepat
- **Apa yang dibahas dalam tutorial ini?** Membuat proyek uji, menambahkan bidang khusus, mendefinisikan atribut ekstensi, dan menetapkan batas waktu tugas dengan rumus.  
- **Pustaka apa yang diperlukan?** Aspose.Tasks untuk Java (versi terbaru).  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi diperlukan untuk produksi.  
- **IDE apa yang dapat saya gunakan?** Semua IDE Java (IntelliJ IDEA, Eclipse, VS Code) yang mendukung JDK 8+.  
- **Berapa lama implementasinya?** Sekitar 10‑15 menit untuk menyalin kode dan menjalankannya.

## Apa Itu “Proyek Uji” di Aspose.Tasks?
**Proyek uji** adalah file Microsoft Project ringan yang dibuat secara programatis untuk mendemonstrasikan atau memvalidasi fungsionalitas. Ia berisi sekumpulan tugas, sumber daya, dan bidang khusus minimal yang dapat Anda manipulasi tanpa memengaruhi data proyek yang sebenarnya.

## Mengapa Menggunakan Aspose.Tasks untuk Memanipulasi Microsoft Project?
- **Cakupan API penuh** – akses setiap properti Project, Task, dan Resource.  
- **Tidak memerlukan instalasi Office** – dapat dijalankan di server, pipeline CI, dan kontainer Docker.  
- **Lintas‑platform** – berjalan di Windows, Linux, dan macOS dengan kode Java yang sama.  
- **Mesin rumus yang kuat** – menghitung tanggal, durasi, dan bidang khusus langsung di dalam file proyek.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal‑hal berikut:

- **Java Development Kit (JDK) 8+** – unduh dari situs Oracle atau gunakan OpenJDK.  
- **Aspose.Tasks untuk Java** – dapatkan JAR terbaru dari [halaman unduhan Aspose.Tasks untuk Java](https://releases.aspose.com/tasks/java/) dan tambahkan ke classpath proyek Anda atau ke dependensi Maven/Gradle.

## Impor Paket
Pertama, impor kelas‑kelas yang diperlukan:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Panduan Langkah‑per‑Langkah

### Langkah 1: Buat Proyek Uji dengan Bidang Khusus
Kita mulai dengan **membuat proyek uji** dan menambahkan bidang khusus yang nantinya akan menampung hasil rumus kita.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Tip profesional:* `CreateTestProjectWithCustomField()` adalah metode pembantu yang membangun jadwal minimal dan mendaftarkan atribut ekstensi siap untuk penugasan rumus.

### Langkah 2: Definisikan Atribut Ekstensi (Tambahkan Bidang Khusus)
Selanjutnya, kita **mendefinisikan atribut ekstensi** – pada dasarnya bidang khusus – dan memberikan alias yang mudah dipahami. Di sinilah logika **menambahkan bidang khusus** diterapkan.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** membuat bidang dapat dibaca di Project.  
- **Formula** menghitung jumlah hari antara tanggal *Finish* tugas dan *Deadline*‑nya.

### Langkah 3: Tetapkan Batas Waktu untuk Tugas (Tambahkan Tugas Batas Waktu & Tetapkan Batas Waktu Tugas)
Sekarang kita **menambahkan data tugas batas waktu** dengan menetapkan properti *Deadline* pada tugas tertentu.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Instance `Calendar` menentukan momen batas waktu yang tepat.  
- `set(Tsk.DEADLINE, …)` **menetapkan batas waktu tugas** untuk tugas yang dipilih.

### Langkah 4: Simpan Proyek (Manipulasi File Microsoft Project)
Akhirnya, kita **memanipulasi Microsoft Project** dengan menyimpan perubahan ke file MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Anda dapat membuka `SaveFile.mpp` di Microsoft Project untuk melihat bidang khusus, hasil rumus, dan batas waktu yang tercermin dalam jadwal.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|-------|----------|
| **Rumus tidak dievaluasi** | Pastikan string `Formula` atribut menggunakan nama bidang yang benar (misalnya `[Deadline]`, `[Finish]`). |
| **Tugas tidak ditemukan** | Verifikasi bahwa ID tugas (`1` pada contoh) memang ada; gunakan `project.getRootTask().getChildren().size()` untuk debugging. |
| **Pengecualian lisensi** | Terapkan lisensi Aspose.Tasks yang valid sebelum memanggil metode API apa pun (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Pertanyaan yang Sering Diajukan

**T: Bisakah saya menggunakan Aspose.Tasks dengan bahasa pemrograman lain?**  
J: Ya, Aspose.Tasks menyediakan API untuk .NET, Java, dan platform lainnya, memungkinkan Anda **memanipulasi file Microsoft Project** dalam bahasa pilihan Anda.

**T: Apakah ada versi percobaan gratis untuk Aspose.Tasks?**  
J: Tentu saja. Unduh percobaan penuh fungsi dari [halaman unduhan Aspose.Tasks](https://releases.aspose.com/).

**T: Di mana saya dapat menemukan dokumentasi lengkap untuk Aspose.Tasks?**  
J: Dokumentasi resmi tersedia di [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**T: Bagaimana cara mendapatkan dukungan untuk Aspose.Tasks?**  
J: Kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) untuk mengajukan pertanyaan dan berbagi pengalaman dengan komunitas.

**T: Apakah saya memerlukan lisensi sementara untuk evaluasi?**  
J: Lisensi sementara tersedia untuk pengujian jangka pendek; Anda dapat memintanya [di sini](https://purchase.aspose.com/temporary-license/).

---

**Terakhir Diperbarui:** 2025-12-07  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12 (versi terbaru pada saat penulisan)  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}