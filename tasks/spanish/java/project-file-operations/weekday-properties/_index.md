---
date: 2025-12-23
description: Aprende a usar Aspose.Tasks para Java para actualizar el cronograma del
  proyecto, establecer el día de inicio de la semana, cambiar los días por mes y personalizar
  el calendario del proyecto de manera eficiente.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Gestión de propiedades de los días laborables
url: /es/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Gestión de Propiedades de Días Laborables

## Introducción
Aspose.Tasks for Java (aspose tasks java) es una API robusta que permite a los desarrolladores Java trabajar con archivos Microsoft Project sin necesidad de tener Microsoft Project instalado. En este tutorial aprenderá a **cargar un archivo MPP**, **establecer el día de inicio de la semana**, **cambiar los días por mes**, y, en general, **personalizar el calendario del proyecto** — todos pasos esenciales para actualizar el cronograma de un proyecto. Al final, podrá ajustar programáticamente las propiedades de los días laborables y guardar los cambios en el formato que necesite.

## Respuestas Rápidas
- **¿Cuál es la clase principal para manejar proyectos?** `Project` de la biblioteca Aspose.Tasks.  
- **¿Cómo cambio el día de inicio de la semana?** Use `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **¿Puedo cargar un archivo .mpp existente?** Yes—instantiate `Project` with the file path.  
- **¿Qué método guarda el proyecto como XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **¿Necesito una licencia para desarrollo?** A free trial works for evaluation; a license is required for production.

## Requisitos Previos
Antes de comenzar, asegúrese de tener lo siguiente:

- **Java Development Kit (JDK)** – última versión instalada.  
- **Aspose.Tasks for Java library** – descárguela [aquí](https://releases.aspose.com/tasks/java/).  
- **Un IDE** como IntelliJ IDEA, Eclipse o NetBeans.  

## Importar Paquetes
Para comenzar, importe las clases esenciales de Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Ahora repasemos cada paso para gestionar las propiedades de los días laborables.

## Paso 1: Cargar un Archivo MPP
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Aquí **cargamos un archivo .mpp existente** (`load mpp file`) para poder inspeccionar y modificar sus configuraciones de calendario.*

## Paso 2: Mostrar Propiedades Actuales de los Días Laborables
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Este código imprime el **día de inicio de la semana** actual, los **días por mes**, los **minutos por día** y los **minutos por semana** — los elementos clave que a menudo necesitará para **personalizar el calendario del proyecto**.

## Paso 3: Establecer Nuevas Propiedades de los Días Laborables
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
En este paso **establecemos el día de inicio de la semana** a Monday, **cambiamos los días por mes** a 24 y ajustamos los recuentos de minutos diarios y semanales. Estas configuraciones son típicas cuando necesita **actualizar el cronograma del proyecto** para que coincida con un calendario laboral no estándar.

## Paso 4: Guardar el Proyecto Actualizado
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
El proyecto modificado se guarda como un archivo XML, lo que facilita compartirlo o importarlo a otras herramientas.

## Paso 5: Confirmar la Operación
```java
System.out.println("Process completed Successfully");
```
Un mensaje simple en la consola le indica que el flujo de trabajo finalizó sin errores.

## Problemas Comunes y Consejos
- **Ruta de archivo incorrecta** – Verifique que `dataDir` termine con una barra diagonal o use `Paths.get(...)` para rutas independientes de la plataforma.  
- **Licencia no establecida** – En un entorno de producción, llame a `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` antes de crear `Project`.  
- **Día de inicio de semana inesperado** – Asegúrese de usar el valor correcto del enum `DayType` (p.ej., `DayType.Sunday`).  

## Preguntas Frecuentes

**Q: ¿Puede Aspose.Tasks for Java manejar estructuras de proyecto complejas?**  
A: Sí, Aspose.Tasks for Java ofrece soporte integral para manejar estructuras de proyecto complejas con facilidad.

**Q: ¿Es Aspose.Tasks for Java compatible con diferentes versiones de archivos Microsoft Project?**  
A: Absolutamente, Aspose.Tasks for Java soporta varias versiones de archivos Microsoft Project, garantizando compatibilidad en distintas plataformas.

**Q: ¿Puedo integrar Aspose.Tasks for Java en mis aplicaciones Java existentes?**  
A: Sí, Aspose.Tasks for Java ofrece capacidades de integración sin problemas, permitiéndole mejorar sus aplicaciones Java con potentes funciones de gestión de proyectos.

**Q: ¿Aspose.Tasks for Java proporciona documentación y soporte?**  
A: Sí, puede acceder a una documentación extensa y al soporte de la comunidad para Aspose.Tasks for Java en su [sitio web](https://releases.aspose.com/).

**Q: ¿Hay una prueba gratuita disponible para Aspose.Tasks for Java?**  
A: Sí, puede descargar una versión de prueba gratuita de Aspose.Tasks for Java desde su [sitio web](https://reference.aspose.com/tasks/java/) para explorar sus funcionalidades antes de realizar una compra.

---

**Última actualización:** 2025-12-23  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}