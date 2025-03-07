---
title: Propiedades de días laborables en Aspose.Tasks
linktitle: Propiedades de días laborables en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a administrar las propiedades de los días laborables de manera eficiente en Aspose.Tasks para Java. Personalice las fechas de inicio de la semana, los días del mes y más con facilidad.
weight: 25
url: /es/java/project-file-operations/weekday-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Propiedades de días laborables en Aspose.Tasks

## Introducción
Aspose.Tasks para Java es una potente API que permite a los desarrolladores de Java trabajar con archivos de Microsoft Project sin que Microsoft Project esté instalado en la máquina. Una de sus funcionalidades clave es administrar las propiedades de los días laborables, lo que permite a los usuarios personalizar las fechas de inicio de la semana, los días por mes, los minutos por día y los minutos por semana. Este tutorial proporcionará una guía detallada sobre cómo utilizar estas funciones de forma eficaz.
## Requisitos previos
Antes de sumergirse en Aspose.Tasks para Java, asegúrese de tener los siguientes requisitos previos:
### Kit de desarrollo de Java (JDK)
Asegúrese de tener JDK instalado en su sistema. Puede descargar e instalar el JDK más reciente desde el sitio web de Oracle.
### Aspose.Tasks para la biblioteca Java
 Descargue e instale la biblioteca Aspose.Tasks para Java desde el sitio web. Puedes acceder al enlace de descarga[aquí](https://releases.aspose.com/tasks/java/).
### Entorno de desarrollo integrado (IDE)
Elija un IDE de su preferencia para el desarrollo de Java. Las opciones populares incluyen IntelliJ IDEA, Eclipse o NetBeans.
## Importar paquetes
Para comenzar, importe los paquetes Aspose.Tasks necesarios a su proyecto Java. Así es cómo:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Ahora, dividamos el ejemplo proporcionado en varios pasos para una mejor comprensión.
## Paso 1: cargar el archivo del proyecto
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Este paso implica cargar un archivo de proyecto llamado "project.mpp" desde el directorio de datos especificado.
## Paso 2: mostrar las propiedades de los días laborables
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Aquí, recuperamos e imprimimos las propiedades de fecha de inicio de la semana, días por mes, minutos por día y minutos por semana del proyecto cargado.
## Paso 3: configurar las propiedades de los días laborables
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Este paso implica crear una nueva instancia de proyecto y configurar propiedades personalizadas de los días de la semana, como el día de inicio de la semana, los días del mes, los minutos por día y los minutos por semana.
## Paso 4: guardar proyecto
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Finalmente, guardamos el proyecto modificado con las propiedades actualizadas del día de la semana como un archivo XML.
## Paso 5: Mostrar resultado
```java
System.out.println("Process completed Successfully");
```
Este paso confirma la finalización exitosa del proceso.
## Conclusión
Dominar las propiedades de los días laborables en Aspose.Tasks para Java es crucial para una gestión eficaz de proyectos. Siguiendo este tutorial, habrá aprendido cómo manipular y personalizar las propiedades de los días laborables sin esfuerzo. Explore más documentación y ejemplos para mejorar sus capacidades de gestión de proyectos.
## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks para Java manejar estructuras de proyectos complejas?
R: Sí, Aspose.Tasks para Java proporciona soporte integral para manejar estructuras de proyectos complejas con facilidad.
### P: ¿Aspose.Tasks para Java es compatible con diferentes versiones de archivos de Microsoft Project?
R: Por supuesto, Aspose.Tasks para Java admite varias versiones de archivos de Microsoft Project, lo que garantiza la compatibilidad entre plataformas.
### P: ¿Puedo integrar Aspose.Tasks para Java en mis aplicaciones Java existentes?
R: Sí, Aspose.Tasks para Java ofrece capacidades de integración perfecta, lo que le permite mejorar sus aplicaciones Java con potentes funciones de gestión de proyectos.
### P: ¿Aspose.Tasks para Java proporciona documentación y soporte?
 R: Sí, puede acceder a documentación extensa y soporte comunitario para Aspose.Tasks para Java en su[sitio web](https://releases.aspose.com/).
### P: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?
R: Sí, puede descargar una versión de prueba gratuita de Aspose.Tasks para Java desde su[sitio web](https://reference.aspose.com/tasks/java/) para explorar sus características antes de realizar una compra.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
