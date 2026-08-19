---
date: 2026-02-28
description: Pelajari cara mendapatkan durasi dalam menit, hari, jam, minggu, dan
  bulan menggunakan Aspose.Tasks untuk Java. Panduan terperinci dengan contoh kode.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara Mendapatkan Durasi dalam Berbagai Satuan dengan Aspose.Tasks
url: /id/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Mendapatkan Durasi dalam Berbagai Satuan dengan Aspose.Tasks

## Pendahuluan
Memahami **cara mendapatkan durasi** untuk tugas merupakan bagian inti dari alur kerja manajemen proyek apa pun. Apakah Anda memerlukan menit untuk pelacakan detail atau bulan untuk perencanaan tingkat tinggi, Aspose.Tasks untuk Java membuat konversi menjadi sederhana. Pada tutorial ini kami akan memandu Anda mengambil durasi tugas dalam menit, hari, jam, minggu, dan bulan, sambil menjelaskan mengapa setiap satuan dapat berguna dalam proyek dunia nyata.

## Jawaban Cepat
- **Apa arti “cara mendapatkan durasi”?** Itu adalah proses mengekstrak rentang waktu tugas dan mengonversinya ke satuan yang Anda butuhkan.  
- **Metode API mana yang melakukan konversi?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Versi percobaan gratis cukup untuk pengujian; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengonversi ke satuan khusus?** Anda dapat menumpuk konversi atau menggunakan `TimeSpan` untuk perhitungan khusus.  
- **Apakah kode ini kompatibel dengan Java 17?** Ya, Aspose.Tasks mendukung Java 8 dan versi yang lebih baru.

## Apa itu “cara mendapatkan durasi” di Aspose.Tasks?
Aspose.Tasks menyimpan panjang tugas sebagai objek `Duration`. Dengan memanggil metode `convert` dan menentukan `TimeUnitType` (Minute, Hour, Day, Week, Month), Anda dapat mengambil nilai yang sama dalam satuan yang diinginkan. Fleksibilitas ini memungkinkan Anda membuat laporan, melakukan perhitungan, atau memberi data ke sistem lain tanpa harus menghitung secara manual.

## Mengapa menggunakan Aspose.Tasks untuk konversi durasi?
- **Akurasi:** Menangani pengecualian kalender, waktu kerja, dan kalender non‑standar secara otomatis.  
- **Kinerja:** Konversi satu baris menghindari loop atau parsing khusus.  
- **Portabilitas:** Berfungsi sama di lingkungan Windows, Linux, dan macOS.  
- **Integrasi:** Terpadu mulus ke dalam aplikasi Java yang sudah menggunakan Aspose.Tasks.

## Prasyarat
Sebelum kita masuk ke kode, pastikan Anda memiliki:

- Java Development Kit (JDK) terpasang
- Perpustakaan Aspose.Tasks untuk Java. Anda dapat mengunduhnya [di sini](https://releases.aspose.com/tasks/java/)
- Pemahaman dasar tentang pemrograman Java

## Impor Paket
Di proyek Java Anda, sertakan perpustakaan Aspose.Tasks. Tambahkan pernyataan impor berikut di awal kode Anda:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Langkah 1: Siapkan Proyek Anda
Buat proyek Java baru di IDE favorit Anda (IntelliJ, Eclipse, VS Code, dll.) dan tambahkan JAR Aspose.Tasks ke classpath proyek. Ini memastikan kelas‑kelas di atas tersedia saat kompilasi.

## Langkah 2: Baca Template Proyek
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

Ganti `"Your Document Directory"` dengan folder sebenarnya yang berisi file proyek `.xml` atau `.mpp` Anda.

## Langkah 3: Ambil Sebuah Tugas
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

Pemanggilan `getById(1)` mengambil tugas dengan ID 1. Sesuaikan ID untuk menargetkan tugas lain dalam file Anda.

## Langkah 4: Durasi dalam Menit – Cara mendapatkan durasi dalam menit?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

Variabel `mins` kini berisi panjang tugas yang diekspresikan dalam menit.

## Langkah 5: Durasi dalam Hari – Cara mendapatkan durasi dalam hari?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

Gunakan nilai ini ketika Anda memerlukan granularitas tingkat hari untuk pelaporan atau alokasi sumber daya.

## Langkah 6: Durasi dalam Jam – Cara mendapatkan durasi dalam jam?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

Jam berguna untuk lembar waktu atau ketika Anda ingin memecah hari menjadi shift kerja.

## Langkah 7: Durasi dalam Minggu – Cara mendapatkan durasi dalam minggu?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

Minggu sering dipakai dalam diagram Gantt tingkat tinggi atau perencanaan milestone.

## Langkah 8: Durasi dalam Bulan – Cara mendapatkan durasi dalam bulan?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

Durasi tingkat bulan membantu saat Anda menyelaraskan fase proyek dengan periode fiskal.

## Masalah Umum dan Solusinya
| Gejala | Penyebab Kemungkinan | Solusi |
|---------|----------------------|--------|
| `NullPointerException` pada `task` | ID tugas salah atau anak tidak ada | Verifikasi ID tugas ada dengan menggunakan `project.getRootTask().getChildren()` |
| Nilai tidak terduga (mis., 0) | Proyek menggunakan kalender khusus dengan hari non‑kerja | Pastikan kalender proyek didefinisikan dengan benar atau gunakan `project.getCalendar()` untuk memeriksanya |
| Konversi menghasilkan minggu pecahan | Minggu dihitung berdasarkan panjang minggu default proyek (biasanya 5 hari) | Kalikan dengan 5 jika Anda memerlukan minggu kalender, atau sesuaikan pengaturan kalender |

## Pertanyaan yang Sering Diajukan
### T: Apakah saya dapat menggunakan Aspose.Tasks untuk Java dengan IDE Java apa pun?
J: Ya, Aspose.Tasks untuk Java kompatibel dengan semua Integrated Development Environment (IDE) Java.

### T: Bagaimana cara memperoleh ID tugas dalam file Microsoft Project?
J: Anda dapat memeriksa file proyek secara manual atau memanggil `project.getRootTask().getChildren()` dan mengiterasi koleksi untuk membaca `ID` setiap tugas.

### T: Apakah Aspose.Tasks cocok untuk menangani proyek berskala besar?
J: Tentu. Aspose.Tasks dirancang untuk memproses proyek dengan ribuan tugas dan sumber daya secara efisien.

### T: Di mana saya dapat menemukan dokumentasi lebih lanjut?
J: Kunjungi [dokumentasi](https://reference.aspose.com/tasks/java/) untuk referensi API lengkap, contoh kode, dan panduan praktik terbaik.

### T: Bisakah saya mencoba Aspose.Tasks untuk Java sebelum membeli?
J: Ya, Anda dapat menjelajahi [percobaan gratis](https://releases.aspose.com/) untuk mengevaluasi kemampuannya.

---

**Terakhir Diperbarui:** 2026-02-28  
**Diuji Dengan:** Aspose.Tasks untuk Java 24.12  
**Penulis:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}