---
date: 2025-12-23
description: Узнайте, как создать сводку MPP и обновить автора проекта с помощью Aspose.Tasks
  для Java. Легко задавайте и получайте информацию о проекте.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как создать сводку MPP и обновить автора проекта с помощью Aspose.Tasks
url: /ru/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание сводки проекта MPP в Aspose.Tasks

## Введение
В этом руководстве вы **create MPP summary** информацию для файла Microsoft Project и узнаете, как **update project author** детали с помощью библиотеки Aspose.Tasks для Java. Независимо от того, создаёте ли вы инструмент управления проектами или автоматизируете отчётность, программное управление свойствами сводки экономит время и обеспечивает согласованность ваших проектов.

## Быстрые ответы
- **Что означает “create MPP summary”?** Это установка высокоуровневых свойств проекта (author, revision, keywords и т.д.), которые отображаются в диалоговом окне Project Summary Information Microsoft Project.  
- **Какая библиотека обрабатывает это?** Aspose.Tasks for Java предоставляет удобный API для чтения и записи этих свойств.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия, но для использования в продакшене требуется коммерческая лицензия.  
- **Можно ли также изменить автора после сохранения файла?** Да — вы можете **update project author**, вызвав `project.set(Prj.AUTHOR, "New Author")`, а затем повторно сохранить файл.  
- **Какие форматы файлов поддерживаются?** Полностью поддерживаются как MPP, так и XML (SaveFileFormat.Xml).

## Что такое create MPP summary?
Создание MPP summary подразумевает заполнение метаданных проекта — автора, номера ревизии, ключевых слов, комментариев, даты создания и даты печати. Эти метаданные хранятся в записи Project Summary Information и отображаются в разделе **File → Info** Microsoft Project.

## Почему обновлять project author?
Точная информация о **project author** важна для аудита, совместной работы и отчётности. Когда над проектом работают несколько участников, может потребоваться **update project author**, чтобы отразить последние изменения или правильно указать авторство.

## Предварительные требования
Перед началом убедитесь, что у вас есть следующее:
1. Java Development Kit (JDK), установленный на вашем компьютере.  
2. Aspose.Tasks for Java – скачайте его [здесь](https://releases.aspose.com/tasks/java/).  
3. IDE, например IntelliJ IDEA, Eclipse или NetBeans.

## Импорт пакетов
Сначала импортируйте необходимые пакеты в ваш Java‑класс:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Шаг 1: Настройка проекта и определение сведений о сводке
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
В приведённом коде мы **create MPP summary** поля, такие как author, revision и keywords. Позже вы также можете **update project author**, вызвав `project.set(Prj.AUTHOR, "New Name")`.

## Шаг 2: Сохранение сведений о сводке проекта
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Сохранение проекта сохраняет все данные сводки, которые вы только что определили.

## Шаг 3: Чтение сведений о сводке проекта
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Этот фрагмент демонстрирует, как **read back** сведения о сводке, подтверждая, что операция **create MPP summary** прошла успешно.

## Распространённые проблемы и решения
- **Null значения после чтения:** Убедитесь, что проект был успешно сохранён перед повторной загрузкой. Проверьте пути к файлам и права доступа.  
- **Различия в форматировании дат:** `project.get(Prj.CREATION_DATE)` возвращает `java.util.Date`. Используйте `SimpleDateFormat`, если нужен пользовательский формат отображения.  
- **Лицензия не установлена:** Без действующей лицензии Aspose.Tasks работает в режиме оценки и может добавлять водяной знак. Зарегистрируйте лицензию в начале кода.

## Часто задаваемые вопросы
**Q: Можно ли использовать Aspose.Tasks for Java вместе с другими Java‑библиотеками?**  
A: Да, Aspose.Tasks for Java легко интегрируется с другими Java‑библиотеками для расширения возможностей управления проектами.

**Q: Доступна ли пробная версия Aspose.Tasks for Java?**  
A: Да, бесплатную пробную версию можно скачать [здесь](https://releases.aspose.com/).

**Q: Как часто обновляется Aspose.Tasks for Java?**  
A: Aspose.Tasks for Java регулярно обновляется, чтобы обеспечить совместимость с последними версиями Java и файлов Microsoft Project.

**Q: Можно ли дальше настраивать сведения о сводке проекта?**  
A: Конечно, Aspose.Tasks for Java предоставляет широкие возможности для настройки сведений о сводке проекта в соответствии с вашими требованиями.

**Q: Где можно получить поддержку по Aspose.Tasks for Java?**  
A: Поддержку можно получить на форуме сообщества Aspose.Tasks [здесь](https://forum.aspose.com/c/tasks/15).

## Заключение
В этом руководстве мы показали, как **create MPP summary** данные, **update project author** и проверить эти изменения с помощью Aspose.Tasks for Java. Автоматизируя эти шаги, вы получаете полный контроль над метаданными проекта, делая свои приложения более надёжными, а отчёты — более точными.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}