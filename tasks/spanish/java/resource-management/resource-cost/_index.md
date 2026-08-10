---
date: 2026-06-15
description: Aprenda cómo gestionar los costos en archivos de MS Project usando Aspose.Tasks
  para Java, incluyendo cómo cargar un archivo MPP y leer actual cost work y budgeted
  cost schedule.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Manejar el costo de recursos en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cómo gestionar los costos en MS Project con Aspose.Tasks para Java
url: /es/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo gestionar los costos en MS Project con Aspose.Tasks para Java

## Introducción

Gestionar los presupuestos de los proyectos es una responsabilidad central para cualquier director de proyecto, y **cómo gestionar los costos** de manera eficaz puede determinar el éxito o el fracaso de un proyecto. Aspose.Tasks para Java le brinda control programático sobre los archivos de Microsoft Project, permitiéndole leer y actualizar los datos de costos de recursos sin abrir manualmente el archivo .mpp. En este tutorial verá paso a paso cómo cargar un archivo MPP, inspeccionar el trabajo de costo real y extraer el cronograma de costo presupuestado para cada recurso.

## Respuestas rápidas
- **¿Qué hace Aspose.Tasks para Java?** Lee y escribe archivos de Microsoft Project (.mpp) sin requerir que Microsoft Project esté instalado.  
- **¿Cómo puedo cargar un archivo MPP?** Use `new Project("path/to/file.mpp")` – la API analiza el archivo en memoria.  
- **¿Qué campos de costo están disponibles?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS) y Budgeted Cost of Work Performed (BCWP).  
- **¿Necesito una licencia para desarrollo?** Una licencia temporal gratuita funciona para pruebas; se requiere una licencia completa para producción.  
- **¿Qué versiones de Java son compatibles?** Java 8 y posteriores, incluido Java 17 LTS.

## Cómo gestionar los costos en MS Project?

Cargue su proyecto con `new Project("yourFile.mpp")`, luego itere a través de cada objeto `Resource` para leer las propiedades relacionadas con el costo, como ACWP, BCWS y BCWP. Aspose.Tasks convierte automáticamente los valores internos de costo a la moneda del proyecto, por lo que puede mostrarlos o almacenarlos directamente. Este enfoque elimina los cálculos manuales en hojas de cálculo y garantiza la consistencia de los datos en todos los informes del proyecto.

## Requisitos previos

1. Comprensión básica de la programación en Java.  
2. Biblioteca Aspose.Tasks para Java añadida a su proyecto (Maven/Gradle o JAR manual).  
3. Acceso a un archivo Microsoft Project (`.mpp`) que desea analizar.  

## Importar paquetes

Las clases `Project` y `Resource` son los puntos de entrada para trabajar con los datos del proyecto.

La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un único archivo Microsoft Project en memoria.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Paso 1: Definir el directorio de datos

Primero, especifique la carpeta que contiene su archivo `.mpp`. Esta ruta puede ser absoluta o relativa al directorio de trabajo de su aplicación.

```text
```java
String dataDir = "Your Data Directory";
```
```

## Paso 2: Cargar el archivo MS Project

`Project` carga el archivo y construye un modelo de objetos que puede consultar. La API analiza el archivo sin necesidad de que Microsoft Project esté instalado, y admite más de 30 formatos de entrada.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Paso 3: Recorrer los recursos

Los objetos `Resource` representan personas, equipos o materiales que consumen el presupuesto. Puede iterar la colección `project.getResources()` para acceder a cada uno.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## Paso 4: Verificar el nombre y los costos del recurso

Para cada recurso, verifique que el nombre esté definido y luego lea los campos de costo. El método `getActualCost()` devuelve el **actual cost work** (ACWP), mientras que `getBudgetedCost()` le brinda el **budgeted cost schedule** (BCWS/BCWP).

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## ¿Por qué usar Aspose.Tasks para Java para cargar un archivo MPP?

Aspose.Tasks soporta **más de 30 formatos de archivo** (incluidos `.mpp`, `.xml` y `.xlsx`) y puede procesar proyectos con **hasta 10 000 tareas** mientras utiliza menos de 200 MB de RAM. La biblioteca realiza todos los cálculos del lado del servidor, eliminando la necesidad de una copia con licencia de Microsoft Project.

## Problemas comunes y soluciones

- **Nombres de recurso nulos:** Algunos archivos heredados contienen recursos de marcador de posición. Siempre verifique `resource.getName() != null` antes de acceder a las propiedades de costo.  
- **Archivos grandes que generan presión de memoria:** `LoadOptions` es una clase de configuración que le permite especificar qué datos del proyecto cargar. Use `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` para cargar solo los datos que necesita y habilítelos más tarde si es necesario.  
- **Desajustes de moneda:** La API respeta la configuración de moneda del proyecto; puede sobrescribirla con `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` si es necesario. `CostRateTableType` enumera las diferentes tablas de tarifas de costo que pueden aplicarse a una tarea.

## Preguntas frecuentes

**Q: ¿Puede Aspose.Tasks para Java manejar estructuras de proyecto complejas?**  
A: Sí, soporta completamente tareas de resumen anidadas, múltiples calendarios de recursos y campos personalizados en todas las versiones de Project compatibles.

**Q: ¿Es la biblioteca compatible con diferentes versiones de archivos de Microsoft Project?**  
A: Absolutamente. Aspose.Tasks lee y escribe archivos desde Microsoft Project 2000 hasta el formato más reciente de 2023.

**Q: ¿Puedo integrar Aspose.Tasks para Java con otras bibliotecas Java?**  
A: Sí, la API devuelve objetos Java estándar, lo que permite una integración fluida con marcos de registro, herramientas ORM o bibliotecas de generación de informes.

**Q: ¿Aspose.Tasks para Java ofrece soporte al cliente?**  
A: Aspose proporciona soporte dedicado en foros, documentación detallada y asistencia por correo electrónico para usuarios con licencia.

**Q: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?**  
A: Puede descargar una licencia de evaluación de 30 días desde el sitio web de Aspose para explorar todas las funciones sin costo.

---

**Última actualización:** 2026-06-15  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo calcular la variación de costos y gestionar los costos de asignación con Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Gestión de presupuesto, trabajo y costos para tareas en Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Agregar recurso al proyecto con Aspose.Tasks para Java](/tasks/java/resource-management/create-resources/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}