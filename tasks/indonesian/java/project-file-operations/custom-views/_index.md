---
date: 2025-12-18
description: Pelajari cara membuat tampilan di Aspose.Tasks untuk Java, termasuk cara
  menyimpan tampilan proyek dan mengatur properti tampilan. Tingkatkan efisiensi manajemen
  proyek dengan tampilan MS Project khusus yang disesuaikan.
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Cara Membuat Tampilan: Tampilan Kustom MS Project di Aspose.Tasks'
url: /id/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membuat Tampilan: Tampilan Kustom MS Project di Aspose.Tasks

## Introduction
Jika Anda mencari **how to create view** yang sesuai dengan kebutuhan pelaporan unik proyek Anda, Anda berada di tempat yang tepat. Dalam manajemen proyek, menyesuaikan tampilan dapat secara dramatis meningkatkan kejelasan dan efisiensi saat menangani tugas dan sumber daya. **Aspose.Tasks for Java** menyediakan API yang kaya untuk **add custom view java**‑style, memungkinkan Anda menyesuaikan tampilan MS Project persis seperti yang Anda butuhkan. Pada tutorial ini kami akan memandu proses langkah demi langkah, mulai dari menyiapkan proyek hingga menyimpan tampilan proyek.

## Quick Answers
- **What is the primary purpose?** Untuk membuat dan menyimpan tampilan kustom MS Project menggunakan Aspose.Tasks for Java.  
- **Which class creates a view?** `GanttChartView` (atau tipe tampilan lainnya).  
- **How do I make the view appear in the menu?** Atur `view.setShowInMenu(true)`.  
- **How can I save the view with the project?** Gunakan `MPPSaveOptions` dengan `setWriteViewData(true)`.  
- **Do I need a license?** Ya, lisensi Aspose.Tasks yang valid diperlukan untuk penggunaan produksi.

## Prerequisites
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

### Java Development Environment
Pastikan Java telah terinstal di sistem Anda.

### Aspose.Tasks for Java
Unduh dan instal Aspose.Tasks for Java dari [here](https://releases.aspose.com/tasks/java/).

## Import Packages
Pertama, impor paket yang diperlukan ke proyek Java Anda:
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```

## Step 1: Set Up Project
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## Step 2: Create View
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## Step 3: Customize View Properties *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### How to Show View Menu
Pemanggilan `view.setShowInMenu(true)` memastikan tampilan yang baru dibuat muncul di **view menu** MS Project, memberikan akses cepat bagi pengguna akhir.

## Step 4: Tune View Settings
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## Step 5: Add View to Project *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## Step 6: Save Project *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### Why Saving the Project View Matters
Menetapkan `options.setWriteViewData(true)` memberi tahu Aspose.Tasks untuk **save project view** informasi di dalam file MPP, sehingga tampilan kustom tetap ada di antara sesi.

## Step 7: Check View Properties
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## Common Use Cases
- **Stakeholder Reporting:** Buat tampilan yang hanya menampilkan milestone tingkat tinggi dan tugas kritis.  
- **Resource Allocation:** Bangun tampilan yang menampilkan sumber daya beserta tugas yang mereka kerjakan untuk pemeriksaan kapasitas cepat.  
- **Print‑Ready Documents:** Sesuaikan pengaturan halaman (seperti pada Step 4) untuk menghasilkan snapshot proyek yang siap dicetak.

## Troubleshooting Tips
- **View Not Appearing in Menu:** Pastikan `view.setShowInMenu(true)` dipanggil sebelum menyimpan.  
- **Missing Columns in Printout:** Pastikan `setFirstColumnsCount` sesuai dengan kolom yang Anda butuhkan dan `setPrintFirstColumnsCountOnAllPages(true)` diaktifkan.  
- **License Exceptions:** Jika Anda menemui kesalahan lisensi, pastikan file lisensi Aspose.Tasks yang valid dimuat sebelum membuat objek `Project`.

## Frequently Asked Questions
### Q1: Can I customize views beyond Gantt charts?
A: Ya, Aspose.Tasks for Java menyediakan fleksibilitas untuk menyesuaikan berbagai jenis tampilan selain Gantt chart, termasuk tabel dan grafik.

### Q2: Is Aspose.Tasks for Java suitable for large‑scale projects?
A: Tentu saja. Perpustakaan ini dirancang untuk menangani proyek berukuran apa pun, menawarkan kinerja yang kuat dan manajemen memori yang efisien.

### Q3: Does Aspose.Tasks for Java support exporting views to different formats?
A: Ya, Anda dapat mengekspor tampilan ke PDF, XLSX, HTML, dan format lainnya, memastikan berbagi yang mulus di berbagai platform.

### Q4: Can I automate the creation of custom views using Aspose.Tasks for Java?
A: Tentu. API memungkinkan otomatisasi penuh, memungkinkan Anda menghasilkan dan mengelola tampilan kustom secara programatis.

### Q5: Is there a community forum for Aspose.Tasks for Java support?
A: Ya, Anda dapat menemukan bantuan dan berinteraksi dengan pengguna lain di [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) untuk pertanyaan dan diskusi terkait Java.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}