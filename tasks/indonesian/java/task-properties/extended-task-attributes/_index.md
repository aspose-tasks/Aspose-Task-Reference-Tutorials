---
date: 2026-01-28
description: Pelajari cara membaca atribut tugas yang diperluas menggunakan Aspose.Tasks
  untuk Java dan mengubah tipe bidang khusus secara efisien.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Baca Atribut Tugas yang Diperluas dengan Aspose.Tasks untuk Java
url: /id/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Membaca Atribut Tugas yang Diperluas dengan Aspose.Tasks untuk Java

## Pendahuluan
Dalam tutorial komprehensif ini Anda akan menemukan cara **membaca atribut tugas yang diperluas** dari file Microsoft Project menggunakan pustaka Aspose.Tasks untuk Java. Baik Anda sedang membangun alat pelaporan, menyinkronkan data, atau hanya membutuhkan wawasan lebih dalam tentang bidang khusus, menguasai fitur ini akan memungkinkan Anda mengekstrak setiap informasi yang disimpan dalam sebuah proyek. Kami akan membimbing Anda melalui penyiapan yang diperlukan, menunjukkan cara mengubah tipe bidang khusus saat memproses atribut, dan memberikan tip praktis untuk menghindari jebakan umum.

## Jawaban Cepat
- **Apa arti “membaca atribut tugas yang diperluas”?** Ini merujuk pada mengekstrak nilai bidang khusus yang melampaui properti tugas default dalam file Project.  
- **Kelas mana yang menyediakan akses ke atribut ini?** Kelas `ExtendedAttribute` di Aspose.Tasks.  
- **Apakah saya memerlukan lisensi untuk menjalankan kode?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi komersial diperlukan untuk produksi.  
- **Bisakah saya mengubah tipe atribut saat runtime?** Ya – gunakan pernyataan `switch` untuk **mengubah tipe bidang khusus** berdasarkan `CustomFieldType`.  
- **Apakah ini kompatibel dengan Java 8 dan versi selanjutnya?** Tentu saja, API mendukung JDK 8+.

## Apa itu membaca atribut tugas yang diperluas?
Atribut tugas yang diperluas adalah bidang yang didefinisikan pengguna (teks, tanggal, angka, bendera, dll.) yang melengkapi properti tugas standar di Microsoft Project. Aspose.Tasks menampilkannya melalui koleksi `ExtendedAttribute` yang terlampir pada setiap objek `Task`, memungkinkan Anda membaca atau memodifikasi nilainya secara programatik.

## Mengapa membaca atribut tugas yang diperluas?
- **Visibilitas penuh:** Dapatkan wawasan tentang data khusus yang ditambahkan pemangku kepentingan ke jadwal.  
- **Otomasi:** Isi dasbor, hasilkan laporan khusus, atau migrasikan data ke sistem lain tanpa ekspor manual.  
- **Fleksibilitas:** Bekerja dengan tipe bidang khusus apa pun—teks, tanggal, durasi, biaya, bendera—dengan menangani setiap kasus secara tepat.

## Prasyarat
- Pengetahuan dasar pemrograman Java.  
- Java Development Kit (JDK) terinstal di mesin Anda.  
- IDE seperti IntelliJ IDEA atau Eclipse.  

## Impor Paket
Start by importing the necessary classes for the Aspose.Tasks project:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Langkah 1: Mengakses Tugas dan Atribut yang Diperluas
Load a Project file and iterate through each task to reach its extended attributes:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Langkah 2: Mengambil ID Bidang dan GUID Nilai
Print the internal identifiers that help you understand which custom field you are dealing with:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Langkah 3: Cara mengubah tipe bidang khusus saat membaca atribut tugas yang diperluas
Use a `switch` statement on `CustomFieldType` to handle each possible data type correctly:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Ulangi langkah-langkah ini untuk setiap tugas dalam proyek Anda guna menjelajahi dan memanipulasi setiap atribut tugas yang diperluas.

## Masalah Umum dan Solusinya
| Masalah | Solusi |
|---------|--------|
| **Nilai null dikembalikan** | Verifikasi bahwa bidang khusus memang terisi dalam file .mpp sumber. |
| **Tipe yang ditampilkan tidak tepat** | Pastikan Anda menggunakan `CustomFieldType` yang benar dalam pernyataan `switch`; tipe yang tidak cocok akan menghasilkan nilai default. |
| **Penurunan kinerja pada proyek besar** | Proses tugas dalam batch atau filter hanya tugas yang diperlukan dengan menggunakan `project.getRootTask().getChildren().stream()` dengan predikat yang sesuai. |

## Pertanyaan yang Sering Diajukan
### Bisakah saya memodifikasi atribut tugas yang diperluas secara programatik?
Ya, Anda dapat memodifikasi atribut tugas yang diperluas menggunakan Aspose.Tasks untuk Java. Lihat dokumentasi untuk petunjuk detail.

### Apakah ada versi percobaan yang tersedia?
Ya, Anda dapat mengakses versi percobaan gratis [di sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk Java?
Untuk dukungan, kunjungi [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Bagaimana cara mendapatkan lisensi sementara?
Anda dapat memperoleh lisensi sementara [di sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat membeli versi lengkap Aspose.Tasks untuk Java?
Anda dapat membeli versi lengkap [di sini](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks Java API (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}