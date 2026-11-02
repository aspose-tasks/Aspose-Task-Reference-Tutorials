---
date: 2026-10-31
description: Projeyi PDF olarak kaydetmeyi ve Microsoft Project veritabanını Aspose.Tasks
  for Java ile okumayı öğrenin; ayrıca Project Server'a bağlanmayı, projeyi HTML'e
  dönüştürmeyi ve projeyi XML'e dışa aktarmayı keşfedin.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Aspose.Tasks içinde Microsoft Project Veritabanından Proje Verilerini Okuma
og_description: Projeyi PDF olarak kaydedin ve Microsoft Project veritabanını Aspose.Tasks
  for Java kullanarak okuyun. Project Server'a bağlanmayı, HTML, XML ve CSV olarak
  dışa aktarmayı öğrenin.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Projeyi PDF olarak kaydedin ve Microsoft Project veritabanını Aspose.Tasks
  for Java ile okuyun
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Projeyi PDF olarak kaydedin ve Microsoft Project veritabanını Aspose.Tasks
  for Java ile okuyun
url: /tr/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeyi PDF olarak kaydedin ve Microsoft Project veritabanını Aspose.Tasks for Java ile okuyun

## Giriş
Bu öğreticide, **read Microsoft Project database**'i doğrudan bir Microsoft Project Server'dan nasıl okuyacağınızı ve ardından Aspose.Tasks Java API'sını kullanarak **save the project as PDF**'yi nasıl yapacağınızı keşfedeceksiniz. Yazdırılabilir raporlar oluşturmanız, eski verileri taşımanız veya proje bilgilerini özel bir portalda gömmeniz gerekse, bu kılavuz JDBC bağlantısını yapılandırmadan projeyi PDF, XML veya HTML olarak dışa aktarmaya kadar her adımı size gösterir. Sonuna geldiğinizde, Microsoft Project kurulumuna ihtiyaç duymadan herhangi bir Java sunucusunda çalışabilen üretim‑hazır bir çözümünüz olacak.

## Hızlı cevaplar
- **What does Aspose.Tasks do?** Microsoft Project dosyalarını ve veritabanlarını okuma, yazma ve manipüle etme için saf‑Java bir API sağlar.  
- **Do I need Microsoft Project installed?** Hayır, Aspose.Tasks Microsoft Project'ten bağımsız çalışır.  
- **Which database type is supported?** Microsoft SQL Server, Project Server'ın arka ucudur.  
- **Can I export to other formats?** Evet—PDF, XML, HTML, CSV, PNG, JPEG ve daha fazlası.  
- **What are the main prerequisites?** JDK 8 veya daha yeni, Aspose.Tasks for Java kütüphanesi, SQL Server JDBC sürücüsü ve geçerli Project Server kimlik bilgileri.

## “read Microsoft Project database” nedir?
Microsoft Project veritabanını okumak, Project Server'ın SQL Server deposuna bağlanmak, depolanmış proje verilerini çıkarmak ve bunları Aspose.Tasks'in manipüle edebileceği bir `Project` nesnesine yüklemek anlamına gelir. Bu yaklaşım otomatik raporlama, veri taşıma veya özel analizler için idealdir.

## Neden Aspose.Tasks for Java kullanmalı?
Aspose.Tasks for Java, masaüstü uygulamasına ihtiyaç duymadan Microsoft Project verileriyle çalışmanıza olanak tanır ve herhangi bir platformda çalışan saf‑Java bir çözüm sunar. Görevler, kaynaklar, takvimler ve özel alanlar için kapsamlı bir nesne modeli sağlar ve büyük kurumsal projeleri verimli bir şekilde işleyebilir, bu da otomatik raporlama, taşıma ve entegrasyon senaryoları için idealdir.

- **No Microsoft Project dependency** – Microsoft Project bağımlılığı yok – herhangi bir sunucu veya CI ortamında çalışır.  
- **Rich object model** – Zengin nesne modeli – görevleri, kaynakları, atamaları, takvimleri ve özel alanları programlı olarak erişin.  
- **Multiple export options** – Birden fazla dışa aktarma seçeneği – Aspose.Tasks, **20'den fazla dosya formatına** dışa aktarmayı destekler, PDF, XML, HTML, CSV, PNG ve JPEG dahil, tek bir API çağrısıyla.  
- **High performance** – Yüksek performans – kütüphane, **10.000'e kadar görev** içeren projeleri bir dakikadan kısa sürede işleyebilir ve tüm dosyayı belleğe yüklemeyi önlemek için verileri akış olarak gönderir.

## Önkoşullar
1. Çalışan bir Java geliştirme ortamı (JDK 8 veya daha yeni).  
2. Aspose.Tasks for Java kütüphanesinin projenizin sınıf yoluna eklenmesi.  
3. Project Server SQL veritabanına erişim kimlik bilgileri (sunucu adı, port, veritabanı adı, kullanıcı adı, şifre) Project Server'a bağlanmak için.  
4. Microsoft JDBC Sürücüsü for SQL Server (ör. `sqljdbc4.jar`).  

## Paketleri içe aktar
İlk olarak, ihtiyacınız olan sınıfları içe aktarın. Liste Aspose.Tasks çekirdek sınıfları ve standart Java yardımcılarını içerir.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Project Server'a nasıl bağlanılır
Güvenilir bir bağlantı kurmak, proje verilerini okumak için temeldir. SQL Server örneğinin Java ana bilgisayarınızdan erişilebilir olduğundan ve kullandığınız oturum açma bilgilerinin Project Server şemasında **SELECT** izinlerine sahip olduğundan emin olun. Ayrıca ağ gecikmesini doğrulamalı ve güvenli iletişim için gerekli SSL ayarlarını yapılandırmalısınız.

## Adım 1: veritabanı bağlantısını kurun
`MspDbSettings` sınıfı, bir Microsoft Project Server veritabanına erişmek için gereken JDBC bağlantı ayrıntılarını kapsüller. JDBC bağlantı dizesini tutan bir `MspDbSettings` örneği oluşturun. Yer tutucu değerleri gerçek sunucu ayrıntılarınızla değiştirin.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Bağlantı dizesini kimlik bilgilerini doğrudan kodlamaktan kaçınarak güvenli bir yapılandırma dosyasında veya ortam değişkeninde saklayın.

## Adım 2: JDBC sürücüsünü ekleyin
Microsoft SQL Server JDBC sürücüsünü çalışma zamanında yükleyin, böylece JVM veritabanı ile iletişim kurabilir.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Uyarı:** Sürücü sürümünün SQL Server sürümünüzle eşleştiğinden emin olun. Uyumsuz bir sürücü kullanmak bağlantı hatalarına neden olabilir.

## Adım 3: proje verilerini okuyun
`Project` sınıfı, belleğe yüklenmiş bir Microsoft Project dosyasını temsil eder ve görevleri, kaynakları ve atamaları ortaya çıkarır. `MspDbSettings` nesnesini geçirerek bir `Project` nesnesi oluşturun. Aspose.Tasks, proje verilerini otomatik olarak veritabanından alacaktır.

```java
Project project = new Project(settings);
```

Bu noktada `project` nesnesini keşfedebilirsiniz—görevleri, kaynakları listeleyebilir veya gerektiği gibi alanları değiştirebilirsiniz.

## Adım 4: projeyi PDF olarak kaydedin
`SaveFileFormat` enumu, `Project.save` metodunun çıktı formatını (PDF, XML veya HTML gibi) tanımlar. Yüklenmiş projeyi istediğiniz dosya formatına dışa aktarın. Aşağıdaki örnek projeyi **PDF** olarak kaydeder; bu, yazdırılabilir raporlar için mükemmeldir. `SaveFileFormat` enumunu değiştirerek **projeyi XML olarak dışa aktarabilir** veya **projeyi HTML'e dönüştürebilirsiniz**.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

XML tercih ederseniz, `SaveFileFormat.Pdf` yerine `SaveFileFormat.Xml` koymanız yeterlidir. HTML çıktısı için `SaveFileFormat.Html` kullanın.

## Yaygın sorunlar ve çözümler
| Issue | Typical cause | Fix |
|-------|---------------|-----|
| **Connection timeout** | Yanlış sunucu/port veya güvenlik duvarı engellemesi | Sunucu adresini doğrulayın, 1433 portunu açın ve basit bir JDBC test programı ile bağlantıyı test edin. |
| **Authentication error** | Geçersiz kullanıcı adı/şifre veya SQL Server SQL kimlik doğrulaması için yapılandırılmamış | Geçerli bir SQL oturumu kullanın veya sunucuda karma‑mod (mixed‑mode) kimlik doğrulamayı etkinleştirin. |
| **Driver not found** | JDBC jar sınıf yolunda değil | `addJDBCDriver`'ın doğru `.jar` dosyasına işaret ettiğinden ve yolun çift ters eğik çizgi (`\\`) kullandığından emin olun. |
| **Empty project after load** | Project Server tablolarını okuma izni yetersiz | Oturuma Project Server veritabanı şemasında SELECT hakları verin. |

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks Microsoft Project dışındaki diğer veritabanlarından proje verilerini okuyabilir mi?**  
A: Evet, Aspose.Tasks XML dosyalarından, Primavera veritabanlarından ve diğer standart proje formatlarından proje verisi okumayı destekler.

**Q: Aspose.Tasks farklı Microsoft Project sürümleriyle uyumlu mu?**  
A: Evet, kütüphane Microsoft Project 2007'den en yeni 2024 sürümlerine kadar çalışır ve sürümler arasında sorunsuz entegrasyon sağlar.

**Q: Projeyi kaydetmeden önce proje verilerini manipüle edebilir miyim?**  
A: Kesinlikle, dışa aktarmadan önce zengin API'yi kullanarak görevleri, kaynakları ve özel alanları ekleyebilir, güncelleyebilir veya silebilirsiniz.

**Q: Aspose.Tasks birden fazla çıktı formatını destekliyor mu?**  
A: Evet, projeleri PDF, XML, HTML, CSV, PNG, JPEG ve daha fazlası olarak kaydedebilirsiniz—toplamda 20'den fazla format.

**Q: Aspose.Tasks ile ilgili daha fazla destek veya yardım nereden bulabilirim?**  
A: Ek yardım için Aspose.Tasks forumunu ziyaret edebilir veya web sitesinde bulunan belgeleri inceleyebilirsiniz [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Sonuç
Bu adım‑adım kılavuzu izleyerek artık **read Microsoft Project database**, **projeyi PDF olarak kaydet** ve Aspose.Tasks for Java kullanarak diğer formatlara dışa aktarabilirsiniz. Bu yaklaşım Microsoft Project bağımlılığını ortadan kaldırır, otomatik raporlamayı kolaylaştırır ve güçlü özel entegrasyonların kapısını açar.

---

**Son Güncelleme:** 2026-10-31  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.5 (yazım zamanındaki en son)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks ile Projeyi PDF Olarak Kaydetme – Dışa Aktarma Kılavuzu](/tasks/java/project-file-operations/save-as-pdf/)
- [Projeyi PDF Olarak Kaydet – Aspose.Tasks for Java ile Görev Sayfasını Oluşturma](/tasks/java/task-properties/render-task-sheet/)
- [Projeyi PDF Olarak Dışa Aktar ve Aspose.Tasks'te Görev Listesi ile Altbilgi Arasındaki Boşluğu Azalt](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}