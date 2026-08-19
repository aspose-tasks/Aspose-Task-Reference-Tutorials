---
date: 2026-02-28
description: Aspose.Tasks kullanarak Java projelerindeki görevlerin bütçe, iş ve maliyetini
  nasıl yöneteceğinizi öğrenin. Bu rehber ayrıca görev maliyetini verimli bir şekilde
  nasıl hesaplayacağınızı gösterir.
linktitle: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Java'da Bütçe, İş ve Maliyeti Nasıl Yönetilir
url: /tr/java/task-properties/task-budget-work-cost/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Java'da Bütçe, İş ve Maliyet Yönetimi

Bir projenin finansmanını yönetmek, her proje yöneticisinin temel sorumluluğudur. Bu öğreticide **görevler, işler ve kaynaklar için bütçeyi nasıl yöneteceğinizi** Aspose.Tasks Java API'si ile keşfedecek ve aynı zamanda **görev maliyetini nasıl hesaplayacağınızı** göreceksiniz. Kılavuzun sonunda, Microsoft Project dosyalarınızdan bütçe ile ilgili alanları okuyabilecek, görüntüleyebilecek ve manipüle edebileceksiniz.

## Hızlı Yanıtlar
- **“budget work” neyi temsil eder?** Bir görev veya kaynak için ayrılan iş miktarı (saat olarak).  
- **Bütçe maliyetini programlı olarak alabilir miyim?** Evet, görevlerde, kaynaklarda veya atamalarda `BUDGET_COST` alanını kullanarak.  
- **Aspose.Tasks için lisansa ihtiyacım var mı?** Üretim için lisans gereklidir; ücretsiz deneme mevcuttur.  
- **Hangi Java sürümü destekleniyor?** Aspose.Tasks Java 8 ve üzeri sürümlerle çalışır.  
- **Atamalardan görev maliyetini hesaplamak mümkün mü?** Kesinlikle – atama `BUDGET_COST` değerlerini toplayın.

## Aspose.Tasks'te Bütçe Yönetimi Nedir?
Aspose.Tasks, görevler, kaynaklar ve atamalar için ayrılmış alanlarda (`BUDGET_WORK`, `BUDGET_COST`) bütçe bilgilerini saklar. Bu alanlar, herhangi bir iş yapılmadan önce beklenen çaba ve maliyeti planlamanızı sağlar ve doğru tahmin ile sapma analizine imkan tanır.

## Görev Maliyeti Neden Hesaplanmalı?
Görev maliyetini hesaplamak şunlara yardımcı olur:
- Orijinal tahminle karşılaştırmalı finansal performansı izlemek.
- Paydaşlar için maliyet bazlı raporlar oluşturmak.
- Bütçeyi aşan görevleri erken aşamada tespit etmek.

## Ön Koşullar
Kodlamaya başlamadan önce şunların kurulu olduğundan emin olun:

- Java geliştirme ortamı (JDK 8+).
- Aspose.Tasks for Java kütüphanesi – **[buradan](https://releases.aspose.com/tasks/java/)** indirin.
- Bilinen bir dizine yerleştirilmiş örnek bir Microsoft Project dosyası (ör. `BudgetWorkAndCost.mpp`).

## Import Packages
Java projenizde gerekli paketleri içe aktararak Aspose.Tasks işlevselliğine erişim sağlayın. Java dosyanızın başına aşağıdaki satırları ekleyin:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Set the Document Directory
Proje dosyalarınızın bulunduğu dizinin yolunu ayarlayın.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Step 2: Load the Project
Aspose.Tasks kütüphanesini kullanarak proje dosyasını yükleyin. `"BudgetWorkAndCost.mpp"` ifadesini kendi proje dosyanızın adıyla değiştirin.
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```

## Step 3: Retrieve Project and Resource Budgets
Proje‑seviyesi ve kaynak‑seviyesi bütçeleri alın ve görüntüleyin. Bu adım, **görev maliyetini** saklanan değerleri okuyarak nasıl hesaplayacağınızı gösterir.
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```

## Step 4: Display Assignment Budgets
Özet görevin (veya herhangi bir görevin) atamalarını döngüye alarak her atamanın bütçe bilgilerini gösterin. Bu sayede kaynak başına tahsis edilen maliyeti görebilirsiniz.
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```

## Common Issues & Pro Tips
- **Null değerler:** Bir bütçe alanı `null` döndürürse, proje dosyasında o veri bulunmayabilir. Yazdırmadan önce `project.getRootTask().get(Tsk.BUDGET_WORK) != null` kontrolleri yapın.  
- **Yanlış UID:** Sorguladığınız kaynak UID'sinin (`getByUid(2)`) mevcut olduğundan emin olun; aksi takdirde `NullPointerException` alırsınız.  
- **Para birimi biçimlendirme:** `BUDGET_COST` ham bir double değer döndürür. Kullanıcı dostu çıktı için `NumberFormat.getCurrencyInstance()` ile biçimlendirin.

## Frequently Asked Questions

**S: Aspose.Tasks for Java'yı diğer Java çerçeveleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks for Java çeşitli Java çerçeveleriyle uyumludur ve entegrasyonda esneklik sağlar.

**S: Aspose.Tasks for Java için deneme sürümü mevcut mu?**  
C: Evet, Aspose.Tasks for Java **[buradan](https://releases.aspose.com/)** ücretsiz deneme sürümüne erişebilirsiniz.

**S: Aspose.Tasks for Java için ek destek nereden bulabilirim?**  
C: Destek ve tartışmalar için Aspose.Tasks topluluk forumunu **[burada](https://forum.aspose.com/c/tasks/15)** inceleyin.

**S: Aspose.Tasks for Java için geçici bir lisans nasıl alabilirim?**  
C: Test ve değerlendirme amaçlı geçici lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** temin edebilirsiniz.

**S: Aspose.Tasks for Java için başka kaynaklar var mı?**  
C: Derinlemesine bilgi ve örnekler için dokümantasyonu **[burada](https://reference.aspose.com/tasks/java/)** inceleyin.

---

**Son Güncelleme:** 2026-02-28  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}