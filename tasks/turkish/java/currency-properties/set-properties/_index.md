---
date: 2025-12-04
description: Aspose.Tasks Java projelerinde para birimini nasıl ayarlayacağınızı,
  para birimini ve para birimi simgesini Java’da nasıl değiştireceğinizi öğrenin.
  Microsoft Project dosyalarını zahmetsizce yönetin.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Projelerinde Para Birimini Nasıl Ayarlarsınız – Java Rehberi
url: /tr/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Projelerinde Para Birimini Ayarlama – Java Rehberi

## Introduction
Bu öğreticide Microsoft Project dosyası için Aspose.Tasks Java API'sini kullanarak **para birimini nasıl ayarlayacağınızı** öğreneceksiniz. Uluslararası ekipler için *para birimini değiştirmek* ya da Java'da *para birimi simgesini* ayarlamak ister misiniz, aşağıdaki adımlar net açıklamalar ve çalıştırmaya hazır kodlarla süreci size gösterecek.

## Quick Answers
- **Hangi kütüphane gereklidir?** Aspose.Tasks for Java.  
- **Para birimi simgesini değiştirebilir miyim?** Evet – `CurrencySymbolPositionType` ve `Prj.CURRENCY_SYMBOL` kullanın.  
- **Hangi dosya formatları destekleniyor?** XML, MPP ve `SaveFileFormat` aracılığıyla birçok diğer format.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme sürümü çalışır; üretim için lisans gereklidir.  
- **Uygulama ne kadar sürer?** Temel bir kurulum için yaklaşık 5‑10 dakika.

## What is “currency” in a Project file?
Bir Projenin para birimi, maliyet değerlerinin nasıl gösterileceğini tanımlar—kod (ör. `AUD`), ondalık basamak sayısı, simge (`$`) ve simgenin konumu. Bu özellikleri ayarlamak, her maliyet‑ile ilgili alanın (kaynak oranları, görev bütçeleri vb.) izleyiciniz için doğru para formatını yansıtmasını sağlar.

## Why use Aspose.Tasks to change currency?
- **Microsoft Project kurulumuna gerek yok** – dosyaları herhangi bir sunucuda işleyin.  
- **Tam API kapsamı** – tüm para birimiyle ilgili alanlar `Prj` sabitleri aracılığıyla erişilebilir.  
- **Çapraz platform** – Windows, Linux ve macOS'ta herhangi bir Java uyumlu IDE ile çalışır.  
- **Yüksek performans** – büyük proje dosyalarını hızlı ve güvenilir bir şekilde işleyin.

## Prerequisites
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri.  
2. **Aspose.Tasks for Java** – en son JAR'ı [Aspose.Tasks indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
3. **Bir IDE** – Eclipse, IntelliJ IDEA veya tercih ettiğiniz herhangi bir editör.  
4. **Yazılabilir bir klasör** – oluşturulan proje dosyasının kaydedileceği yer.

## Import Packages
First, import the classes that provide access to project properties and file handling.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
Specify the contains your source files and where the output will be written.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
Instantiate a fresh `Project` object. This object represents an in‑memory Microsoft Project file.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
Here’s where we **how to set currency** details such as code, digits, symbol, and symbol position.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tip:** If you need to **change currency** for an existing project, simply load the file with `new Project("file.mpp")` before applying the above settings.

### Step 4: Save the Updated Project
Write the project back to disk in the desired format. In this example we use the XML format, but you can also choose `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
Print a friendly message so you know the operation completed without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`project.save` üzerinde `NullPointerException`** | `dataDir` geçerli bir yol değil veya yazma izni yok. | Dizinin mevcut olduğundan ve Java sürecinizin yazma erişimine sahip olduğundan emin olun. |
| **Para birimi simgesi görünmüyor** | Simge konumu bölgeniz için yanlış ayarlanmış. | Miktardan önce gelmesi gerekiyorsa `CurrencySymbolPositionType.Before` kullanın. |
| **Proje dosyası MS Project'te açılamıyor** | Eski bir formatta kaydedildi ve uyumsuz ayarlar var. | En son MS Project sürümleriyle tam uyumluluk için `SaveFileFormat.MPP` ile kaydedin. |

## Frequently Asked Questions

**S: Aspose.Tasks kullanarak tek bir projede birden fazla para birimi ayarlayabilir miyim?**  
**C:** Evet, Aspose.Tasks bir proje dosyasında kaynak veya görev bazında para birimi özelliklerini ayarlayarak birden fazla para birimini yönetmenize olanak tanır.

**S: Aspose.Tasks farklı Microsoft Project dosya sürümleriyle uyumlu mu?**  
**C:** Kesinlikle. Kütüphane Project 2000'den en yeni sürümlere kadar MPP dosyalarını, ayrıca XML ve diğer formatları destekler.

**S: Aspose.Tasks özel para birimi formatlarını destekliyor mu?**  
**C:** Evet, herhangi bir bölgesel gereksinimi karşılamak için özel simgeler, ondalık basamaklar ve konumlandırma tanımlayabilirsiniz.

**S: Aspose.Tasks'i diğer Java kütüphaneleri veya çerçeveleriyle entegre edebilir miyim?**  
**C:** Elbette. API saf Java olduğundan Spring, Hibernate, Maven, Gradle ve diğer ekosistemlerle sorunsuz çalışır.

**S: Aspose.Tasks için ek destek veya yardım nereden bulabilirim?**  
**C:** Topluluk yardımı için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin veya ayrıntılı API referansları için resmi dokümantasyona bakın.

## Conclusion
Artık **para birimini nasıl ayarlayacağınızı**, **para birimi** değerlerini nasıl **değiştireceğinizi** ve Aspose.Tasks for Java kullanarak **Java tarzında para birimi simgesini nasıl değiştireceğinizi** biliyorsunuz. Bu yetenekler, maliyet verilerini küresel ekipler için özelleştirmenizi, bölge‑spesifik raporlar oluşturmanızı ve proje dosyalarınızı sınırlar arasında tutarlı tutmanızı sağlar.

---

**Son Güncelleme:** 2025-12-04  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}