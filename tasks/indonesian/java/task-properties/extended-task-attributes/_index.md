---
title: Atribut Tugas yang Diperluas di Aspose.Tasks
linktitle: Atribut Tugas yang Diperluas di Aspose.Tasks
second_title: Aspose.Tugas Java API
description: Jelajahi atribut tugas yang diperluas di Aspose.Tasks untuk Java. Panduan langkah demi langkah, FAQ, dan dukungan. Optimalkan manajemen proyek Anda hari ini!
weight: 16
url: /id/java/task-properties/extended-task-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atribut Tugas yang Diperluas di Aspose.Tasks

## Perkenalan
Selamat datang di panduan komprehensif kami tentang memanfaatkan atribut tugas yang diperluas di Aspose.Tasks untuk Java. Aspose.Tasks adalah perpustakaan Java yang kuat yang memungkinkan Anda bekerja dengan dokumen Microsoft Project dengan lancar. Dalam tutorial ini, kami akan mempelajari atribut tugas yang diperluas dan menunjukkan bagaimana Anda dapat memanfaatkannya untuk meningkatkan kemampuan manajemen proyek Anda.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang pemrograman Java.
- Menginstal Java Development Kit (JDK) di mesin Anda.
- Lingkungan pengembangan terintegrasi (IDE) seperti IntelliJ atau Eclipse.
## Paket Impor
Mulailah dengan mengimpor paket yang diperlukan untuk memulai proyek Aspose.Tasks Anda:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
Sekarang, mari kita bagi contoh ini menjadi beberapa langkah untuk memandu Anda melalui prosesnya:
## Langkah 1: Mengakses Tugas dan Atribut yang Diperluas
```java
// Jalur ke direktori dokumen.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## Langkah 2: Mengambil ID Bidang dan GUID Nilai
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## Langkah 3: Menangani Berbagai Jenis Atribut
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
Ulangi langkah-langkah ini untuk setiap tugas dalam proyek Anda untuk menjelajahi dan memanipulasi atribut tugas yang diperluas.
## Kesimpulan
Kesimpulannya, memahami dan memanfaatkan atribut tugas yang diperluas di Aspose.Tasks untuk Java dapat meningkatkan kemampuan manajemen proyek Anda secara signifikan. Panduan ini memberikan dasar yang kuat untuk membantu Anda memulai perjalanan ini.
## Pertanyaan yang Sering Diajukan
### Bisakah saya mengubah atribut tugas yang diperluas secara terprogram?
Ya, Anda dapat mengubah atribut tugas yang diperluas menggunakan Aspose.Tasks untuk Java. Lihat dokumentasi untuk petunjuk rinci.
### Apakah ada versi uji coba yang tersedia?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.aspose.com/).
### Di mana saya dapat menemukan dukungan untuk Aspose.Tasks untuk Java?
 Untuk dukungan, kunjungi[Forum Aspose.Tugas](https://forum.aspose.com/c/tasks/15).
### Bagaimana saya bisa mendapatkan lisensi sementara?
 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
### Di mana saya dapat membeli Aspose.Tasks versi lengkap untuk Java?
 Anda dapat membeli versi lengkap[Di Sini](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
